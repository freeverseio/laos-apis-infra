# HOW TO DEPLOY

```bash
export IMAGE_TAG=2613b0bc504c7e4cca203447bb9e70e2c94e6120
helmfile -f deployment/indexer/helmfile.yaml.gotmpl -e production sync
```

Helmfile has several issues with the diff plugin, you can skip it by using `sync` instead of `apply`