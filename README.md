# M A P D R (Hyper4Saken)

![MAPDR](https://github.com/hyper4saken/ohif-orthanc-pacs/blob/main/ohif/config/logo.png)

# OHIF v3 with Orthanc(PostgresDB) with Authentik for Auth and Nginx Proxy Manager for Proxy

_Ohif v3_: (OHIF) Viewer is an open source, web-based, medical imaging platform.

_Orthanc_: Its free and open-source, lightweight DICOM server for medical imaging.

### File Structure

```bash
├── authentik
│   ├── certs
│   ├── custom-templates
│   ├── database
│   ├── media
│   │   └── public
│   │       ├── favicon.svg
│   │       ├── flow-backgrounds
│   │       │   └── star-wars-poster-4k-af-1920x1080.jpg
│   │       └── logo.png
│   └── redis
├── docker-compose.yml
├── ohif
│   ├── config
│   │   ├── logo.png
│   │   └── ohif.js
│   └── nginx
│       ├── default-ohif-nginx.conf
│       └── ohif-nginx.conf
├── orthanc
│   ├── config
│   │   ├── orthanc.json
│   │   └── postgresql.json
│   ├── database
│   └── dicomImages
├── proxy
└── README.md
```

### Create new docker network _pacs_

```bash
docker network create pacs
```

### Clone This Repo

```bash
git clone https://github.com/hyper4saken/ohif-orthanc.git
cd ohif-orthanc-pacs
```

### Set `.env` variable for Authentik

```bash
echo "PG_PASS=$(openssl rand 36 | base64)" >> .env
echo "AUTHENTIK_SECRET_KEY=$(openssl rand 60 | base64)" >> .env
```

### Spin up containers

```bash
docker-compose up -d
```
