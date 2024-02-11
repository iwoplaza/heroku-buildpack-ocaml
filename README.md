# Heroku Buildpack for Ocaml

> **In Development** 🛠️

> Based on the official Node.js buildpack

## Pipeline

- Running `esy` to install dependencies
- Running `bash ./heroml-build.sh`
  - needs to be defined by the user, example of such file [here](./heroml-build.example.sh)
- ...
- Running `bash ./heroml-cleanup.sh` (if it exists)

```mermaid
flowchart TB
  install-dependencies["<big><b>Install dependencies</b></big>
  Running `esy` to install dependencies.
  "]

  build-script["<big><b>Build script</b></big>
  Running `./heroml-build.sh`
  "]

  cleanup-script["<big><b>Cleanup script (if exists)</b></big>
  Running `./heroml-cleanup.sh`
  "]

  install-dependencies --> build-script
  build-script --> cleanup-script
```
