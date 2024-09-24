# Xray + Vaultwarden + AdguardHome w/ nginx reverse proxy and acme.sh via Docker compose.

Additionally, uncommenting a few lines enables you to host AFFiNE on the same domain.

- Skim through the config files first and edit all the necessary variables
- Adguard Home requires 3000:3000/tcp to be allowed for the initial setup (add it next to 853:853, remove after you're done)
- Run with `sudo docker compose up -d`. Use `sudo docker exec acme.sh --command` to set up certificate issue and renewal. Recommended way - https://github.com/acmesh-official/acme.sh/wiki/dnsapi#dns_cf
- Restart and set everything else up

If you opt into hosting AFFiNE, don't forget to connect 'proxy' as an external docker network in compose.yaml

`update-containers.sh` does exactly what it says (pulls the latest tag, rebuilds containers if needed and removes redundant images).

In order to use DoH, fill in the "HTTPS port" field in the Encryption settings panel with any port you want (it won't be used), then set `allow_unencrypted_doh: true` in AdGuardHome.yaml to allow AdGuard Home to respond to DoH requests without TLS encryption.

Sources:
- Xray examples - https://github.com/XTLS/Xray-examples/tree/main/VLESS-TCP-XTLS-Vision
- Vaultwarden - https://github.com/dani-garcia/vaultwarden/wiki/Using-Docker-Compose
- Adguard Home - [dbeley/docker-compose](https://github.com/dbeley/docker-compose/blob/master/adguard-home/docker-compose.yml), [official documentation](https://adguard-dns.io/kb/adguard-home/faq/#reverseproxy)
- acme.sh - [setup](https://github.com/acmesh-official/acme.sh/wiki/Run-acme.sh-in-docker#3-run-acmesh-as-a-docker-daemon), [dnsapi](https://github.com/acmesh-official/acme.sh/wiki/dnsapi)
- Self-host AFFiNE - https://docs.affine.pro/docs/self-host-affine
