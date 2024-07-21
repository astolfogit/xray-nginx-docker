# xray-nginx-docker
Xray + Vaultwarden + AdguardHome w/ nginx reverse proxy and acme.sh via Docker compose

First read the comments i left, edit each config file to your liking (don't forget to replace my.domain with your domain). Use `sudo docker exec acme.sh --command` to set up certificate issue and renewal. Recommended way - https://github.com/acmesh-official/acme.sh/wiki/dnsapi#dns_cf

Sources:
- Xray examples - https://github.com/XTLS/Xray-examples/tree/main/VLESS-TCP-XTLS-Vision
- Vaultwarden - https://github.com/dani-garcia/vaultwarden/wiki/Using-Docker-Compose
- Adguard Home - [dbeley/docker-compose](https://github.com/dbeley/docker-compose/blob/master/adguard-home/docker-compose.yml)
- acme.sh - [setup](https://github.com/acmesh-official/acme.sh/wiki/Run-acme.sh-in-docker#3-run-acmesh-as-a-docker-daemon), [dnsapi](https://github.com/acmesh-official/acme.sh/wiki/dnsapi)
