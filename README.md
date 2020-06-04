# My First Website
![](https://github.com/atiehamidi/myFirstProject/workflows/.github/workflows/releases.yml/badge.svg)

## github actions
On new releases (tags) github automatically pushes new image to [pyguy/first-website](https://hub.docker.com/repository/docker/pyguy/first-website) docker repository.

Create a new release like the following:
```bash
git fetch
git tag v0.0.2 # new tag
git push origin v0.0.2
```

## deploy on k3s
After the github actions is sucessful, run the following to deploy the app:
```bash
kubectl --record -n atieh set image deploy/first-website first-website=pyguy/first-website:v0.0.2 # new tag
```
Replace v0.0.2 above with the new tag created.