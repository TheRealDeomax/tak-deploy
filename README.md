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
- Optionally deploys CloudTAK (when DEPLOY_CLOUDTAK=true)

## Prerequisites

- AWS CLI configured
- Docker installed and running
- Node.js and npm
- [Route53 hosted zone](https://github.com/TAK-NZ/base-infra/blob/main/docs/AWS_GITHUB_SETUP.md#1-route-53-dns-setup)
- TAK server zip file (takserver-docker-\<version\>.zip) from [tak.gov](https://tak.gov/products/tak-server) in current directory

## Usage

```bash
./deployAllLayers --r53ZoneName tak.your-domain.com
./deployAllLayers --destroy  # Remove all infrastructure
```

To enable CloudTAK deployment, edit the script and set `DEPLOY_CLOUDTAK=true` at the top of the file.

See `./deployAllLayers --help` for full options.
