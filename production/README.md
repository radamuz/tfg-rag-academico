## Arrancar servicio

* Copia etc/systemd/system/streamlit.service en la ruta del servidor /etc/systemd/system/streamlit.service

* Recarga el demonio de systemctl, habilitalo para que inicie cuando arranque la máquina y arranca ahora streamlit:
```bash
sudo systemctl daemon-reload
sudo systemctl enable streamlit
sudo systemctl start streamlit
```

* Comprueba el estado
```bash
sudo systemctl status streamlit
```

## Arrancar proxy con caddy y su certificado automático SSL para conseguir HTTPS
* Instala caddy:
```bash
sudo apt update
sudo apt install -y debian-keyring debian-archive-keyring apt-transport-https
curl -1sLf 'https://dl.cloudsmith.io/public/caddy/stable/gpg.key' | sudo tee /etc/apt/trusted.gpg.d/caddy-stable.asc
curl -1sLf 'https://dl.cloudsmith.io/public/caddy/stable/debian.deb.txt' | sudo tee /etc/apt/sources.list.d/caddy-stable.list
sudo apt update
sudo apt install caddy
```

* Copia etc/caddy/Caddyfile en la ruta del servidor /etc/caddy/Caddyfile

* Reinicia Caddy para aplicar los cambios:
```bash
sudo systemctl restart caddy
```

## Arrancar servicio GitHub Runner

* Copia etc/systemd/system/github-runner.service en la ruta del servidor /etc/systemd/system/github-runner.service

* Recarga el demonio de systemctl, habilitalo para que inicie cuando arranque la máquina y arranca ahora github-runner:
```bash
sudo systemctl daemon-reload
sudo systemctl enable github-runner
sudo systemctl start github-runner
```

* Comprueba el estado
```bash
sudo systemctl status github-runner
```