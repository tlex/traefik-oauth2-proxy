# Use docker-compose to deploy Prometheus, Grafana, Portainer behind Traefik cloud native edge router, all protected by oauth2_proxy

## Usage

```sh
git clone https://github.com/tlex/traefik-oauth2-proxy.git demo
cd demo
bash ./create-folders.sh
cp .env.example .env
```

Now you need to edit `.env` and set the correct values for all the variables there. Once this is done, you can proceed:

```sh
for i in grafana-db portainer-db prometheus traefik; do mkdir -p "./folders/${i}"; done
sudo chown 99:99 ./folders/prometheus
sudo docker-compose up --remove-orphans
```

## Details

For deatils, see the blog entry: [alex.thom.ae/2020/01/12/configure-traefik-oauth2_proxy-docker-compose-prometheus-grafana/](https://alex.thom.ae/2020/01/12/configure-traefik-oauth2_proxy-docker-compose-prometheus-grafana/)
