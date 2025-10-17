# Multi-cluster Service Extension Chart

This Helm Chart provides installation configuration for multi-cluster service extension, supporting three different installation types.

## Installation Types

### 1. Global Installation (`installationType: global`)
Installs `mcs-addon-crd` and `mcs-addon` components:
- Installs CRDs required for DataPlane
- Installs mcs-addon-global controller

```bash
helm install mcs-ext ./mcs-ext-chart --set global.installationType=global
```

### 2. Submariner Installation (`installationType: submariner`)
Installs `mcs-addon` and `submariner-operator` components:
- Suitable for cross-cluster network connectivity and service discovery
- Includes mcs-addon controller and Submariner networking components

```bash
helm install mcs-ext ./mcs-ext-chart --set global.installationType=submariner
```

### 3. Cluster Installation (`installationType: cluster`)
Installs only `mcs-addon` component:
- Includes mcs-addon controller and lighthouse components

```bash
helm install mcs-ext ./mcs-ext-chart --set global.installationType=cluster
```

## Prerequisites

- Kubernetes cluster (1.23.0+)
- Rancher 2.10.0+

## Components

### mcs-addon-crd
- Custom Resource Definitions for multi-cluster services
- Only installed in global mode

### mcs-addon
- Multi-cluster service controller
- Installed in all modes

### submariner-operator
- Submariner networking operator
- Cross-cluster network connectivity
- Only installed in submariner mode

## Troubleshooting

For troubleshooting and support, please refer to the project documentation or create an issue in the project repository.