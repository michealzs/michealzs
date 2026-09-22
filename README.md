<h1 align="center">Micheal</h1>

<p align="center">
  DevOps engineer. I build and run the platform underneath the product: cloud infrastructure, Kubernetes, delivery pipelines, and the monitoring that catches problems before users do.
</p>

<p align="center">
  <a href="https://github.com/michealzs?tab=repositories">Repositories</a> ·
  <a href="https://gist.github.com/michealzs">Gists</a> ·
  <a href="https://github.com/michealzs/terraform-aws-platform">Terraform</a> ·
  <a href="https://github.com/michealzs/k8s-gitops-platform">Kubernetes</a> ·
  <a href="https://github.com/michealzs/github-actions-workflows">CI/CD</a> ·
  <a href="https://github.com/michealzs/observability-stack">Observability</a>
</p>

## Recent work

Platform engineering for a payments product on AWS: 22 microservices on EKS, RDS Postgres, ElastiCache Redis, Kafka, and SQS, deployed through Jenkins and Helm.

- Ran the clusters day to day: pending pods, crash loops, failed rollouts, node group sizing, Kubernetes version upgrades, namespace and RBAC manifests.
- Worked a live payment-processing incident through an RDS failover, then traced the outage to a Cluster Autoscaler capped at 8 nodes. Raised the limit, redeployed, and wrote the autoscaling section of the incident review.
- Brought hand-built infrastructure under code. About 40 percent of the estate had been built in the console. I walked it resource by resource, logged the drift, and pulled it into Terraform state with terraform import.
- Audited secrets for a SOC 2 review: base64 Kubernetes Secrets committed to private repos, a shared 1Password vault, and a partial Secrets Manager inventory, then mapped every credential to a single store with rotation.
- Designed the target platform: shared GitHub Actions workflows in place of 22 hand-rolled Jenkins jobs, Argo CD with health-gated syncs and automated rollback, Argo Rollouts for canary releases on the payment path, Kyverno and Conftest policy checks in CI, Atlantis for Terraform from pull requests, Karpenter in place of Cluster Autoscaler, External Secrets Operator, a structured logging standard, and CloudTrail plus EKS audit logs for the auditors.

## What I work with

| Area | Tools |
| --- | --- |
| Cloud | AWS (EKS, RDS, ElastiCache, S3, SQS, IAM, Secrets Manager, CloudWatch, CloudTrail), Cloudflare, Wasabi |
| Infrastructure as code | Terraform, OpenTofu, Ansible, Helm, Kustomize, Docker Compose |
| Kubernetes | EKS, Argo CD, Argo Rollouts, HPA, Cluster Autoscaler, Karpenter, External Secrets Operator, Kyverno, OPA Gatekeeper, Conftest |
| CI/CD | GitHub Actions, Jenkins, Atlantis, pre-commit, release automation |
| Data and messaging | PostgreSQL, Redis, Kafka, SQS |
| Observability | Prometheus, Alertmanager, Grafana, Loki, Datadog APM, CloudWatch Logs Insights, blackbox probes |
| Linux and networking | Ubuntu, Debian, RHEL, systemd, nginx, WireGuard, iptables/ufw, DNS/DHCP/NTP, Proxmox |
| Security | SSH hardening, fail2ban, auditd, Keycloak, certbot, least-privilege IAM, OIDC for CI, secrets rotation |
| Languages | Python, Bash, TypeScript, SQL, PromQL |

## Featured repositories

| Repository | What it is |
| --- | --- |
| [terraform-aws-platform](https://github.com/michealzs/terraform-aws-platform) | Terraform modules and environments for a small production AWS platform: VPC, EKS with IRSA, RDS Postgres, ElastiCache, CloudTrail, remote state. Checked by fmt, tflint, and Trivy in CI. |
| [k8s-gitops-platform](https://github.com/michealzs/k8s-gitops-platform) | Argo CD app-of-apps layout with Kustomize workloads, Argo Rollouts canaries, Helm platform components, Kyverno policies, and kubeconform checks on every PR. |
| [github-actions-workflows](https://github.com/michealzs/github-actions-workflows) | Reusable workflows and composite actions: container build, scan and attest, Terraform plan and apply over OIDC, Python CI, Helm and manifest checks, policy checks, releases. |
| [ansible-linux-baseline](https://github.com/michealzs/ansible-linux-baseline) | Ansible roles that take a fresh Ubuntu or Debian host to a hardened baseline: SSH, ufw, fail2ban, auditd, unattended upgrades, Docker, node_exporter. Tested with Molecule. |
| [observability-stack](https://github.com/michealzs/observability-stack) | Prometheus, Alertmanager, Grafana, Loki and exporters as one Compose stack, with alert rules and dashboards provisioned as code. |
| [ssh-cli](https://github.com/michealzs/ssh-cli) | SSH access provisioning: a Django REST API plus an idempotent CLI that writes ssh config, known_hosts and authorized_keys with an audit trail. |
| [contextual-feedback-api](https://github.com/michealzs/contextual-feedback-api) | Async document-analysis API with API-key auth, webhooks, Prometheus metrics, structured logging, Docker, and CI/CD. |

## How I work

Everything that touches production goes through a pull request, including infrastructure. Pipelines authenticate with short-lived OIDC tokens instead of stored keys. Every service ships with health checks, metrics, and an alert a human has agreed is worth waking up for. When something breaks twice, it gets a runbook or a fix, and usually both.

## Elsewhere

My [public gists](https://gist.github.com/michealzs) hold the setup notes I keep coming back to: Docker on a fresh host, DNS/DHCP/NTP for a small network, chrony, and object storage on AWS and Wasabi.

Open to DevOps, SRE, and platform engineering roles.
