# HOW TO DEPLOY

From the `laos-apis-v2` repository, build the Docker and upload to Dockerhub. Freeverse's dockerhub is [here](https://hub.docker.com/u/freeverseio) and [this is one example](https://hub.docker.com/layers/freeverseio/laos-indexer/mainnet-2613b0bc504c7e4cca203447bb9e70e2c94e6120/images/sha256-5a3cf08ceb291c12635182827b919727aa711f03f25a1305d9db481076ef5f1e) deployed in K8s at the time of writing.

Select the commit after `mainnet-`. For example:

To deploy the laos indexer, etc.:
```bash
export IMAGE_TAG=2613b0bc504c7e4cca203447bb9e70e2c94e6120
helmfile -f deployment/indexer/helmfile.yaml.gotmpl -e production sync
```

To deploy the laos-btc indexer (note the different path):
```bash
IMAGE_TAG=110ced05d76a0b05bcabd687f038a40a7ff71551 helmfile -f deployment/helmfile.yaml.gotmpl -e production sync
```


Helmfile has several issues with the diff plugin, you can skip it by using `sync` instead of `apply`