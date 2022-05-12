# Helm Chart Library

Krateo PlatformOps Helm chart library 

## Including the library chart

In your  Helm chart:

- add the library chart under `dependencies` and choose the version you want (example below) 
  - version number can include `~` or `^` to pick up latest PATCH and MINOR versions respectively.

- use the following commands to add the repo that contains the library chart, update the repo, then update dependencies in your Helm chart:

    ```
    $ helm repo add https://helm-chart-library.krateo.io
    $ helm repo update
    $ helm dependency update <helm_chart_location>
    ```

An example `Chart.yaml`:

```
apiVersion: v2
description: A Helm chart
name: my-cool-service
version: 1.0.0
dependencies:
- name: helm-chart-library
  version: ^0.1.0
  repository: https://helm-chart-library.krateo.io
```