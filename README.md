# Awesome-Container-Security-Software

# Awesome-Container-Security-Software

**Top Container Security Software (Opensource) 🌟 Star if you like it! 🌟**



**Curated List of SaaS Products & Open-Source GitHub Projects**

*Focused on Image Scanning, Runtime Protection, Kubernetes Security & Supply Chain Defense*

**Last updated: November 2026**



This repository tracks notable **SaaS platforms** and **open-source projects** for **Container Security Software**. These tools enable organizations to scan container images for vulnerabilities, detect runtime threats in Kubernetes and container environments, enforce admission policies, and secure the software supply chain—from fully managed CNAPP platforms with agentless scanning and runtime protection to open-source scanners and runtime engines that give security teams complete control over their container security posture.



**Examples** include CrowdStrike Falcon Container Security, Aqua Security, Sysdig Secure, Prisma Cloud, Snyk Container, Wiz, Docker Scout, JFrog Xray, GitHub Advanced Security, and Anchore Enterprise (the category leaders in commercial space).



**Open-source emphasis**: This section is expanded with every relevant project for self-hosted container scanning, runtime detection, and open supply chain security. **Critical note**: The open-source container security landscape is anchored by **Trivy**—the most widely adopted image scanner, which Aqua acquired and maintains as open source . **Falco** is the de facto runtime detection standard, **Kyverno** handles admission control, and **dsecrat** offers a comprehensive single-binary alternative. No single open-source project matches Aqua's vShield micro-patching or Prisma Cloud's full-lifecycle Defenders, but for image scanning and runtime detection, the open-source options are production-proven.



Contributions welcome! Open a PR to add/update entries. Keep descriptions factual and link to official sites.



## Table of Contents

- [Sector Overview & Market Dynamics](#sector-overview--market-dynamics)
- [SaaS/Hosted Platforms](#saas-hosted-platforms)
- [Open-Source GitHub Projects](#open-source-github-projects)
- [How to Contribute](#how-to-contribute)
- [Disclaimer](#disclaimer)

## Sector Overview & Market Dynamics

The global container security and cloud workload protection market is estimated at **.6B–.9B in 2026** (scaling within the broader **.7B–.2B** CWPP sector at a ~20–25% CAGR), driven by enterprise Kubernetes adoption, microservices expansion, and compliance mandates (e.g., NIS2, PCI-DSS 4.0 SBOM requirements).
The sector exhibits a **moderately concentrated yet bifurcated market structure**: core enterprise mindshare is dominated by mega-cap cybersecurity consolidators and CNAPP platforms (e.g., Palo Alto Networks, CrowdStrike, Wiz/Alphabet), while remaining fragmented across specialized niche domains such as eBPF-based runtime observability, software supply chain defense, and developer-centric vulnerability remediation.

## SaaS/Hosted Platforms

| Product | Company Valuation / Revenue | Pricing (Starting Tier) | Free Tier / Trial Limits | Key Capabilities & Trade-offs |
| :--- | :--- | :--- | :--- | :--- |
| **[GitHub Advanced Security](https://github.com/features/security)** | Parent (Microsoft): **~.8T–.0T Market Cap** / GitHub: **~.0B ARR** | **/active committer/month** (/mo Secret Protection + /mo Code Security add-ons; requires GitHub Enterprise) | **Free for public repos** (CodeQL, secret scanning & Dependabot free indefinitely); **30-day free trial** for GitHub Enterprise private evaluation | Native security integration with GitHub CI/CD, CodeQL, and secret scanning. **Trade-off**: No native deep container/IaC runtime scanner; limited to Dependabot Dockerfile FROM scanning. |
| **[Prisma Cloud Compute](https://www.paloaltonetworks.com/prisma/cloud)** | **~– Market Cap** / **.48B FY2026 Rev** (Palo Alto Networks) | **/credit/year** (~,000/yr for 100-credit base pack on AWS Marketplace; container hosts require 5 credits/host) | **No free tier**; **15-to-30 day guided Proof-of-Concept (PoC)** / Private Offer evaluation via sales | Comprehensive full-stack CWPP and CSPM across multi-cloud and bare-metal container hosts. **Trade-off**: Complex credit-based licensing model; enterprise-heavy deployment. |
| **[CrowdStrike Falcon Container Security](https://www.crowdstrike.com/)** | **~– Market Cap** / **.81B FY2026 Rev** (CrowdStrike Holdings) | **,392.99/license** (Falcon Flex list starting point on CDW; enterprise bundles custom quoted) | **No free tier**; **15-day free trial** of Falcon Cloud Security (agentless posture scanning and workload visibility without credit card upfront) | Unified agentless and agent-based kernel/runtime security integrated into the Falcon EDR ecosystem. **Trade-off**: Requires Falcon tier investment; steep learning curve for non-Falcon shops. |
| **[Wiz](https://www.wiz.io/)** | ** Valuation** (Acquired by Alphabet/Google) / **> ARR** | **,000/year** (Wiz Essential starting tier for up to 100 workloads; ~/workload/year) | **No free tier**; **14-day free trial** with full platform access for connected cloud environments | Fast agentless discovery, multi-cloud risk graph, and rapid posture management across Kubernetes. **Trade-off**: High annual enterprise spend floors; runtime defense less deep than eBPF agent-based tooling. |
| **[JFrog Xray](https://jfrog.com/xray/)** | **~.2B Market Cap** / **~ FY2025 Rev** (JFrog Ltd.) | **/month** (Cloud Pro tier, 25 GB transfer/storage) or **,000/year** (Pro X self-hosted with Xray included) | **Free-forever community tier**: JFrog Container Registry (storage only, no Xray); **14-day full free trial** with Xray enabled (no credit card required) | Deep artifact registry integration, dependency security, and recursive SBOM analysis within Artifactory pipelines. **Trade-off**: Full Xray scanning unavailable on free/OSS tiers; advanced security requires Enterprise tiers. |
| **[Snyk Container](https://snyk.io/product/container-vulnerability-management/)** | **~.7B Valuation** (Private secondary) / ** Rev** (Snyk Ltd.) | **/contributing developer/month** (Team plan, 5-developer minimum = /month) | **Free-forever plan**: **100 container tests/month** across up to 5 active projects (unlimited users) | Actionable automated remediation with base image recommendations to bulk-eliminate CVEs. **Trade-off**: Free tier caps out rapidly in active CI/CD pipelines; credit consumption on Enterprise tier. |
| **[Sysdig Secure](https://sysdig.com/)** | **.5B Valuation** (Permira Series G) / **~ ARR** (Sysdig Inc.) | **/host/month** (Enterprise CNAPP starting rate on AWS Marketplace; 20-host minimum commit) | **Free OSS tier**: Falco OSS runtime engine is completely free; **30-day free trial** of Sysdig Secure platform (cloud & Kubernetes evaluation) | Built on open-source Falco with unmatched eBPF system-call observability and 100+ MITRE ATT&CK runtime policies. **Trade-off**: Requires kernel agent deployment for runtime capabilities; node-based cost scales with cluster density. |
| **[Docker Scout](https://www.docker.com/)** | **.1B Valuation** (Private) / **~ ARR** (Docker Inc.) | **/user/month** (Docker Team tier billed annually, or /mo monthly; includes unlimited Scout remote repos) | **Free-forever tier (Personal)**: **Unlimited local scans**, but strictly capped at **1–3 remote repositories** and **3 GB max image size** | Zero-friction developer ergonomics directly integrated into Docker Desktop and Docker Hub. **Trade-off**: Lightweight vulnerability scanning lacking deep runtime or admission control enforcement. |
| **[Aqua Security](https://www.aquasec.com/)** | **.0B Valuation** (Evolution Equity Series E) / **~ ARR** (Aqua Security Software) | **/workload/month** (Workload-based list pricing; AWS Marketplace contracts from ,000/year) | **Free OSS tier**: Trivy CLI/scanner is free forever; **14-to-30 day free trial** of Aqua CNAPP platform on AWS Marketplace | Full-lifecycle CNAPP, Trivy-backed vulnerability intelligence, behavioral profiling, and unique vShield micro-patching in running pods. **Trade-off**: Heavy overhead and administrative overhead for smaller cluster footprints (<10 nodes). |
| **[Anchore Enterprise](https://anchore.com/)** | **~– Est. Revenue** / Series A funded (Anchore Inc.) | **,500/year** (Anchore Enterprise Cloud Image AMI on AWS Marketplace; up to 500 SBOMs/month) | **Free OSS tier**: Syft (SBOM) and Grype (scanner) are completely free; **15-day free trial** of Anchore Enterprise AMI | Industry-standard SBOM management with FedRAMP, DoD, and strict government compliance policy enforcement. **Trade-off**: Annual contract pricing tied to monthly SBOM generation volume. |

## Open-Source GitHub Projects



- **[Trivy](https://github.com/aquasecurity/trivy)**

  **Comprehensive open-source scanner** (Apache 2.0) — **the most widely used multi-purpose scanner** for containers, IaC, and SBOMs, maintained by Aqua Security and serving as the foundation for Aqua's commercial image scanning . **Features**: Vulnerability scanning (OS packages, language dependencies), **IaC misconfiguration detection** (Terraform, CloudFormation, Kubernetes, Dockerfile), **secrets scanning**, **SBOM generation** (CycloneDX, SPDX); CI/CD native; single binary. **Tech stack**: Go. **Deploy**: CLI, CI/CD, Docker. **Trade-off**: **Scanner only**—no runtime detection or admission control. Open-source Trivy may miss some Red Hat/SUSE base image coverage that Aqua's proprietary feed adds . **Best for**: teams wanting the most practical entry point for container and IaC scanning—shift-left security in CI/CD pipelines.



- **[Falco](https://github.com/falcosecurity/falco)**

  **Cloud-native runtime security** (Apache 2.0, CNCF Graduated) — **the de facto standard for container and Kubernetes runtime threat detection**, and the open-source engine powering Sysdig Secure's behavioral detections . **Features**: **eBPF-based** monitoring of system calls across hosts, containers, Kubernetes, and cloud services (via plugins for AWS CloudTrail, GitHub, Okta); **YAML rule engine** with out-of-the-box rules for container escapes, cryptojacking, reverse shells, privilege escalation, and fileless attacks; **50+ integrations** for forwarding alerts to SIEM, Slack, and data lakes. **Tech stack**: C++, Go. **Deploy**: Self-hosted (DaemonSet on Kubernetes, Helm chart). **Trade-off**: **Runtime detection only**—no posture management, vulnerability scanning, or admission control. Requires rule tuning to avoid alert fatigue. **Best for**: teams needing runtime threat detection for Kubernetes and containers—the foundation of the runtime layer in any open-source container security stack.



- **[dsecrat (docker-security)](https://pkg.go.dev/github.com/Ratnadeepdeyroy/docker-security)**

  **Unified container-security tool in Go** (license per package) — **the most comprehensive single-binary open-source container security tool** found in this research, covering the full lifecycle. **Features**: **18 capability modules** in one engine—SBOM, vulnerability scanning, secret detection, static image and Dockerfile analysis, license and malware gates, signing/attestation verification (Cosign), registry posture, **CIS/NIST/PCI compliance**, RBAC and cloud-IAM risk, network-egress policy, container hardening, **admission control** (Kubernetes webhook), **Docker daemon authorization plugin**, continuous monitoring, and **eBPF-backed runtime detection**. **Offline & deterministic**—no network required; vulnerability DB and malware/compliance packs ship embedded and refreshable. **CI-ready**: `--fail-on`, SARIF/JSON/OSCAL output, policy-as-code gate, connectors (webhook, Slack, SIEM, MCP). **Tech stack**: Go (standard library only for scanner; eBPF runtime uses one dependency). **Deploy**: `go install dsecrat@latest`; optional runtime sensor `dsecrat-runtime`. **Trade-off**: **Newer project (v0.1.0)** with limited community validation. Runtime sensor is Linux-only. **Best for**: teams wanting a single static binary covering scanning, compliance, admission control, and runtime detection—especially air-gapped or offline environments where no network access is available for scanning.



- **[Kyverno](https://github.com/kyverno/kyverno)**

  **Kubernetes-native policy engine** (Apache 2.0, CNCF incubating) — **the admission control layer for container security**, enforcing policies at the Kubernetes admission gate. **Features**: **Policy enforcement via CRDs**—validate, mutate, and generate resources; **signed-image verification via Sigstore**; **image registry allowlists**; **resource quotas and limits**; **policy exceptions and reports**. **Tech stack**: Go. **Deploy**: Self-hosted (Helm, operator). **Trade-off**: **Admission control only**—not runtime detection or vulnerability scanning. **Best for**: teams wanting to block non-compliant workloads before they run—the gatekeeper in a container security stack.



### Additional Strong Open-Source Options



- **Grype** — Vulnerability scanner for container images and filesystems (Apache 2.0). From Anchore; pairs with Syft for SBOM generation . **Note**: Scanner only—no runtime or admission control. **Best for**: teams wanting Anchore's scanning engine without the commercial platform.

- **Syft** — SBOM generation tool (Apache 2.0). From Anchore; generates SBOMs from container images and filesystems in CycloneDX and SPDX formats . **Note**: SBOM generation only—no scanning or policy. **Best for**: supply chain transparency and compliance requirements.

- **KubeArmor** — LSM-based runtime policy enforcement (Apache 2.0). Blocks file, process, and network operations at kernel level using AppArmor/SELinux/BPF-LSM. **Note**: Enforcement only—no detection library or scanning. **Best for**: teams needing least-privilege enforcement on container workloads.



**Frameworks for building custom systems**: Combine **Trivy** for image and IaC scanning with **Falco** for runtime detection, **Kyverno** for admission control, and **dsecrat** for a single-binary comprehensive alternative—creating a composable open-source container security stack. **None of these match Aqua's vShield micro-patching or Prisma Cloud's full-lifecycle Defenders**, but for image scanning, runtime detection, and policy enforcement, the open-source options are production-proven.



## How to Contribute



1. Fork the repo.

2. Add/edit entries in `README.md` (follow existing format).

3. Include: name, link, 1–2 sentence description, license (for open-source), and whether it's SaaS or open-source.

4. Submit PR with a short explanation.



Star the repo if you find it useful!



## Disclaimer



- This is a **community-curated** list — not exhaustive and not an endorsement.

- Container security platforms handling image data and runtime telemetry must comply with data protection regulations (GDPR, CCPA, etc.) and implement appropriate access controls.

- **The "image scanning" vs. "runtime detection" vs. "admission control" vs. "full platform" distinction is critical.** **Trivy, Grype, and Syft** are **image/SBOM scanners**—they find vulnerabilities before deployment . **Falco and dsecrat-runtime** are **runtime detection**—they alert on threats during execution . **Kyverno and dsecrat admission** are **admission control**—they block non-compliant workloads before they run. **dsecrat** is a **comprehensive single-binary tool** covering scanning, compliance, admission, and runtime . **Commercial platforms (CrowdStrike, Aqua, Sysdig, Prisma Cloud, Snyk, Wiz, JFrog, Anchore)** bundle these capabilities into unified products. **No single open-source project replaces a commercial platform.** Compose the stack based on your gaps.

- **Aqua Security's vShield is a genuine differentiator**—it applies binary patches to vulnerable libraries inside running containers without rebuilding images, addressing C library vulnerabilities that would otherwise require a full image rebuild . **The trade-off**: it works less well on logic-layer issues in interpreted languages . **No open-source tool replicates this capability.**

- **Trivy is the safest starting point for container scanning.** It is the most widely adopted open-source image scanner, and Aqua continues to maintain it as open source even while adding proprietary data to the commercial product . **The trade-off**: open-source Trivy may miss some Red Hat/SUSE base image coverage.

- **Prisma Cloud's credit model rewards container density**—a container host consumes 5 credits whether it runs 1 container or 100 . **This is unusual**—many competitors price per container, which penalizes high-density environments. **Model your workload density carefully before comparing pricing.**

- **Snyk Container's base image recommendation is the most actionable remediation workflow** in open-source-adjacent tools—it tells you which base image swap eliminates the most CVEs, rather than listing every vulnerability individually . **The trade-off**: credit-based pricing from 2026 requires careful volume modeling.

- **JFrog Xray is not available in free tiers.** If you are on JFrog Community or OSS edition, you do not have Xray—it requires Pro X or higher . **Do not assume Xray is included** in your JFrog subscription.

- **GitHub Advanced Security has no native container scanning.** As of 2026, GHAS covers code scanning, secret scanning, and dependency review—but **not container images or IaC** . Teams must pair GHAS with a separate container security tool .

- **Pricing opacity varies.** CrowdStrike publishes Flex pricing (~$1,392.99/license) . Aqua publishes AWS Marketplace tiers ($50K–$150K/year) and reviewer-observed per-workload pricing ($35–$55/month list) . Prisma Cloud uses credit metering . Snyk uses credit consumption . JFrog bundles with platform tiers . Anchore scales by SBOM volume . **Validate with direct vendor conversations against your container count and runtime requirements.**

- Self-hosted open-source solutions require proper infrastructure (Kubernetes for Falco/Kyverno, Go runtime for dsecrat), security hardening for scanner credentials, and ongoing maintenance. **Container security tools have deep visibility into workloads and registries**—ensure your deployment meets your organization's security standards before connecting production environments.



---



**Made for container security engineers, platform teams, and organizations building transparent container security solutions.**

Let's make Container Security more open, data-driven, and supply-chain-aware.
