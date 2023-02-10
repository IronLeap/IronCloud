<p align="center">
  <h1 align="center">IronCloud: Cloud Security</h1>
  <p align="center">
    <em>Secure your cloud.</em>
  </p>
</p>

<div align="center">

---

[![Prs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=shields)](http://makeapullrequest.com)
[![Join Slack](https://img.shields.io/badge/slack%20community-join-blue)](https://join.slack.com/t/ironleapcommunity/shared_invite/zt-1oxm8asmq-4oyM4fdqarSHMoMstGH6Lw)
[![License](https://img.shields.io/badge/license-Apache2.0-brightgreen)](/LICENSE)

---

</div>

<!-- omit in toc -->
## IronCloud is an open-source cloud security platform. 

Discover, prioritize, and remediate your risks in the cloud. 

- Build an asset inventory of your AWS accounts.
- Continuously monitor your environments for misconfigurations and attack paths.
- Customize security and compliance controls to fit your needs. 
- Contextually prioritize and remediate security findings
- Meet compliance standards PCI DSS, CIS, and more!

<!-- omit in toc -->
## Table of Contents

- [Quick start](#quick-start)
- [Features](#features)
- [Why IronCloud?](#why-ironcloud)
- [Future Roadmap](#future-roadmap)
- [Contributing](#contributing)
- [Development](#development)
- [Security](#security)
- [Open-source vs. paid](#open-source-vs-paid)

## Quick start

1. Clone repo: `git clone --recurse-submodules git@github.com:IronLeap/IronCloud.git`
2. Generate an encryption key: `openssl rand -base64 32`.
3. Run: `ENCRYPTION_KEY=[from previous step] docker-compose up`.
4. Visit http://localhost:3000

A cloud-hosted version is available on special request - email founders@ironleap.io to get access!

## Features

PLACE DEMO HERE

* **Identify Misconfigurations** - Discover the highest risk-of-exploit misconfigurations in your environments.
* **Fast Prioritization** - Filter, sort, and fast search to zoom in on your important risks.
* **Helpful Context** - Understand the surrounding context behind why security rules have passed or failed.
* **Configurability** - Configure which security rules are active, which alerts should be muted, and more.
* **Security as Code** - Modify rules or write your own with our extensible security as code approach.
* **Remediation** - Follow step by step guides to remediate security findings.
* **Compliance** - Ensure your cloud posture is compliant with PCI DSS, CIS benchmarks and more!


## Why IronCloud?
Cloud usage continues to grow. Companies are shifting more of their workloads from on-prem to the cloud and both adding and expanding new and existing workloads in the cloud. Cloud providers keep increasing their offerings and their complexity. Companies are having trouble keeping track of their security risks as their cloud environment scales and grows more complex. Several high profile attacks have occurred in recent times. Capital One had an S3 bucket breached, Amazon had an unprotected Prime Video server breached, Microsoft had an Azure DevOps server breached, Puma was the victim of ransomware, etc.

We had to take action.

- We noticed traditional cloud security tools are opaque, confusing, time consuming to set up, and expensive as you scale your cloud environment
- Cybersecurity vendors don't provide much actionable information to security, engineering, and devops teams by inundating them with non-contextual alerts
- IronCloud is easy to set up, transparent, and configurable, so you can prioritize the most important risks 
- Best of all, you can use **IronCloud for free**!

## Future Roadmap
- Multi-step attack paths based on IAM lateral movements
- Integrations with vulnerability and secret scanners
- Shift-left: Remediate risks earlier in the SDLC with context from your deployments
- Support for Azure and GCP environments

## Contributing
We love contributions of all sizes. What would be most helpful first: 

- Please give us feedback in our [Slack](https://join.slack.com/t/ironleapcommunity/shared_invite/zt-1oxm8asmq-4oyM4fdqarSHMoMstGH6Lw).
- Open a PR (see our instructions below on developing IronCloud locally)
- Submit a feature request or bug report through Github Issues.


## Development

Run containers in development mode:
```
cd frontend && yarn && cd -
docker-compose down && docker-compose -f docker-compose.dev.yaml --env-file .env.dev up --build
```

Reset neo4j and/or postgres data with the following:
```
rm -rf .compose/neo4j
rm -rf .compose/postgres
```

To develop on frontend, make the the code changes and save.

To develop on backend, run
```
docker-compose -f docker-compose.dev.yaml --env-file .env.dev up --no-deps --build backend
```

## Security

Please do not run IronCloud exposed to the public internet. Use the latest versions of IronCloud to get all security related patches. Report any security vulnerabilities to founders@ironleap.io. 

## Open-source vs. paid

This repo is freely available under the [Apache 2.0 license](https://github.com/IronLeap/IronCloud/blob/main/LICENSE).

A cloud-hosted solution with features like user management and advanced attack path analysis is available with an enterprise license. Contact us at founders@ironleap.io for more information.

Special thanks to the amazing [Cartography](https://github.com/lyft/cartography) project, which IronCloud uses for its asset inventory. Credit to PostHog and Airbyte for inspiration around public-facing materials - like this README!
