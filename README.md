# adam-lander

Personal site for **Adam Lewkovitz** at https://adam.makeacompany.ai — Senior AI Product Leader at Google, DJ Bigfoot, Black Rock City regular.

## Stack

- `index.html` — vanilla HTML/CSS/JS, Google Fonts (Fraunces + Inter + JetBrains Mono), inline SVG data viz, no build step.
- `Dockerfile` — `nginx:1.27-alpine` serving the file.
- `.github/workflows/build.yml` — builds + pushes `geeemoney/adam-lander:<version>` to Docker Hub on tag.
- Cluster manifests live in [`BimRoss/rancher-admin`](https://github.com/BimRoss/rancher-admin) under `admin/apps/adam/`.

## Releasing

```sh
git tag -a v0.1.0 -m "v0.1.0"
git push origin v0.1.0
# bump the image tag in rancher-admin/admin/apps/adam/deployment.yaml via PR
```

## Local preview

```sh
docker build -t adam-lander . && docker run --rm -p 8080:80 adam-lander
# open http://localhost:8080
```
