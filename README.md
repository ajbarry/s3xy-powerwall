# s3xy-solar-wallboard

Tesla Vehicle and Solar Information Wallboards

Brought to you by these awesome projects:

- [teslamate](https://github.com/adriankumpf/teslamate) - Vehicle information provided by TeslaMate
- [teslaPowerDash](https://github.com/rhodesman/teslaPowerDash) - PowerWall information provided by Tesla Powerwall Dashboard

and consolidated into sexy Grafana playlists by s3xy-solar-wallboard.

## Getting Started

This project is currenly an early work in progess. Star this repo to keep up with the progress.

### Requirements

- Tesla Vehicle
- Tesla Energy Gateway
- Local always-on home server or Raspberry Pi running Docker Compose

### Installation

More instruction comming soon but for now the basic steps are:

1. Clone this repo or download a zip archive
1. Copy `.env.example` to `.env` and fill in the blanks
1. Run:
   ```console
   docker-compose -f docker-compose.yaml \
     -f docker-compose.teslamate.yaml \
     -f docker-compose.powerwall.yaml \
     up -d
   ```
1. Set TeslaMate Preferences at: [http://server-ip:4000](http://localhost:4000)
1. View Grafana Dashboards at: [http://server-ip:3000](http://localhost:3000)

### Configuration

Comming Soon...

#### Obtaining a POWERWALL_TOKEN

Use the following commands to request an authentication token that can be used
in place of the `POWERWALL_TOKEN` environment variable:

```console
curl --location --request POST 'https://192.168.144.5/api/login/Basic' \
  --insecure --silent --header 'Content-Type: application/json' \
  --data-raw '{
    "username": "customer",
    "password": "your gateway password",
    "email": "you@someplace.com"
  }' \
  | jq -r .token
```

Copy the token output from the console and use this as the value for `POWERWALL_TOKEN`

## Troubleshooting

### Starting Over From Scratch

Sometimes you just need to start over:

```console
docker-compose -f docker-compose.yaml \
  -f docker-compose.teslamate.yaml \
  -f docker-compose.powerwall.yaml \
  down --rmi all -v --remove-orphans
```
