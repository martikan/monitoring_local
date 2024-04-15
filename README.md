# monitoring_local

This is a project for local testing & dashboard creation

### About this project

This is a project for local testing & dashboard creation. </br>
For the simplicity and easier startup, it uses prometheus without persistence.
So the collected metrics will be erased after the container recreation.

### First steps

Required pieces of software and tools:
- Docker
- Kubernetes (Kind or Docker-desktop)
- Flux (version v0.28.4)

When your local Kubernetes is up & ready, you can bootstrap this project:
```shell
    # Check you have everything needed to run flux
    flux check --pre
```

Export required credentials:
```shell
    # export gitlab user
    export GITHUB_USER=martikan
    
    # export gitlab token
    # it can be found on avinty.bitwarder -> monitoring_local
    export GITHUB_TOKEN=<flux-local-token>
```

Bootstrap the project:
```shell
# Using SSH authentication
flux bootstrap github \
  --owner=$GITHUB_USER \
  --repository=monitoring_local \
  --branch=main \
  --personal
```

### Check Grafana
