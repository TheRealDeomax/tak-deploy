# TAK Deploy

One-line installer for TAK (Team Awareness Kit) infrastructure on AWS.

## Quick Install

```bash
curl -fsSL https://tak-nz.github.io/tak-deploy/install | bash
```

## Manual Download

```bash
curl -O https://raw.githubusercontent.com/TAK-NZ/tak-deploy/main/deployAllLayers
chmod +x deployAllLayers
./deployAllLayers --help
```

## What This Does

Downloads and runs the TAK infrastructure deployment script that:
- Deploys BaseInfra (VPC, ECS, S3, certificates)
- Deploys AuthInfra (Authentik SSO, LDAP)
- Deploys TakInfra (TAK Server)

## Prerequisites

- AWS CLI configured
- Docker installed and running
- Node.js and npm
- Route53 hosted zone
- TAK server zip file (takserver-docker-<version>.zip) from [tak.gov](https://tak.gov/products/tak-server) in current directory

## Usage

```bash
./deployAllLayers --r53ZoneName tak.your-domain.com
./deployAllLayers --destroy  # Remove all infrastructure
```

See `./deployAllLayers --help` for full options.