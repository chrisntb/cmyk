# CMYK

> Felix Felicis - VS Code workspace [cmyk.code-workspace](cmyk.code-workspace)

> ⚠️ This workspace is for `cmyk`, work with a submodule using its own workspace ⚠️

`CMYK` is a thing for understanding how to build a multi-tenant HPC cluster where CPU and GPU work can be submitted by users, run fairly and the results distributed conveniently.

`CMYK` is composed of three repositories configured as `git submodules`:

- Infrastructure configuration management
  - `components/cmyk-system` AKA [cmyk-system](https://github.com/chrisntb/cmyk-system)
    - Includes tutorials explaining how to manually create Kubernetes and Slurm clusters which support queues and scheduling work on compute and GPU nodes
- Services
  - `components/cmyk-svc` AKA [cmyk-svc](https://github.com/chrisntb/cmyk-svc)
- Web application
  - `components/cmyk-app` AKA [cmyk-app](https://github.com/chrisntb/cmyk-app)

To clone this repository and its submodules:

```shell
git clone --recursive git@github.com:chrisntb/cmyk.git
```

To get the latest changes, or to grab the submodules if you forgot when you cloned:

```shell
git pull origin main

# This next statement is required to retrieve the content for a newly added submodule and so normally not needed
git submodule update --init --recursive

git submodule sync --recursive
git submodule foreach --recursive "(git checkout main; git pull origin main)"
```

## Documentation

See [docs/README.md](docs/README.md).

## Initial Repository Setup

```shell
git clone git@github.com:chrisntb/cmyk.git

cd cmyk

git submodule add -b main \
  git@github.com:chrisntb/cmyk-system.git components/cmyk-system
git commit -m 'Add cmyk-system submodule'
git push origin main

git submodule add -b main \
  git@github.com:chrisntb/cmyk-svc.git components/cmyk-svc
git commit -m 'Add cmyk-svc submodule'
git push origin main

git submodule add -b main \
  git@github.com:chrisntb/cmyk-app.git components/cmyk-app
git commit -m 'Add cmyk-app submodule'
git push origin main
```
