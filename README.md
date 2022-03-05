# s3xy-solar-wallboard

Tesla Vehicle and Solar Information Wallboards

Inspired and cribbed from these awesome projects:

- [teslamate](https://github.com/adriankumpf/teslamate)
- [teslaPowerDash](https://github.com/rhodesman/teslaPowerDash)
- [Powerwall-Dashboard](https://github.com/jasonacox/Powerwall-Dashboard)
- [powerwall_monitor](https://github.com/mihailescu2m/powerwall_monitor)
- [dc-powerwall-dashboard](https://github.com/liveaverage/dc-powerwall-dashboard)

... and consolidated into a S3XY Energy Grafana playlist by s3xy-solar-wallboard.

## Getting Started

This project is currenly an early work in progess. Star this repo to keep up with the progress.

### Requirements

- Tesla Vehicle
- Tesla Energy Gateway
- Local always-on home server or Raspberry Pi with Docker Compose

### Installation and Configuration

More instruction comming soon but for now the basic steps are:

1. Clone this repo or download a zip archive
1. Copy `.env.example` to `.env` and fill in the blanks
1. Run:
   ```console
   docker-compose up -d
   ```
1. Set TeslaMate Preferences at: [http://server-ip:4000](http://localhost:4000)
1. View Grafana Dashboards at: [http://server-ip:3000](http://localhost:3000)

## Troubleshooting

- [Docker Compose](https://docs.docker.com/compose/)
- [How To Install Docker and Docker-Compose On Raspberry Pi](https://dev.to/elalemanyo/how-to-install-docker-and-docker-compose-on-raspberry-pi-1mo)
- [Connecting to Tesla Gateway](https://www.tesla.com/support/energy/powerwall/own/monitoring-from-home-network)

### Starting Over From Scratch

Sometimes you just need to start over:

```console
docker-compose down --rmi all -v --remove-orphans
```
