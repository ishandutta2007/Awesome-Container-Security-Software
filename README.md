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

- [SaaS/Hosted Platforms](#saas-hosted-platforms)

- [Open-Source GitHub Projects](#open-source-github-projects)

- [How to Contribute](#how-to-contribute)

- [Disclaimer](#disclaimer)



## SaaS/Hosted Platforms



- **[CrowdStrike Falcon Container Security](https://www.crowdstrike.com/)**

  **Container and Kubernetes protection** within Falcon Cloud Security. Integrates agent-based and agentless protection to stop adversaries across major clouds, workloads, and operating systems. Includes vulnerability management, continuous threat detection and response, runtime protection, compliance enforcement, and automated CI/CD pipeline security . **Pricing**: CDW lists Flex subscription at **$1,392.99** for a single license ; enterprise bundles quote-based. **Free tier**: None. **Best for**: CrowdStrike customers wanting container protection integrated with endpoint and cloud security—**trade-off**: container module requires appropriate Falcon tier.



- **[Aqua Security](https://www.aquasec.com/)**

  **Full-lifecycle CNAPP** securing containers, serverless, Kubernetes, and AI workloads. Image scanning built on **Trivy** (which Aqua maintains as open source) with proprietary vulnerability data, signed advisories, malware detection, and secret scanning; detection rates competitive with Wiz and Prisma Cloud at **~95–97%** with **4–6% false positives** . Differentiator: **vShield**—automated micro-patching that applies binary patches to vulnerable libraries inside running containers without rebuilding the image . Runtime protection remains deepest in market: behavioral profiling with low false positive rates after 2–3 week learning, eBPF-based detection, and mature response actions (container quarantine, network isolation, forensic snapshot) . **Pricing**: Per-protected-workload; full platform **~$35–$55/workload/month** list, **$20–$30** in enterprise deals; AWS Marketplace tiers from **$50K–$150K/year** . **Free tier**: None. **Best for**: teams that take runtime detection seriously and have staffed investigation functions—**trade-off**: platform overhead not justified for <10 clusters where Kyverno + Falco + Trivy deliver 80% of value at a fraction of cost .



- **[Sysdig Secure](https://sysdig.com/)**

  **CNAPP built on open-source Falco** with deep system call visibility for runtime threat detection. Core built on Falco, sysdig OSS, and Cloud Custodian; unified security and monitoring; **100+ out-of-the-box runtime policies** with MITRE ATT&CK mapping; serverless container support including inline Fargate scanning . **Simple node-based pricing** (per protected node) —contrast with complex pricing of many competitors . **Pricing**: Per-node; quote-based. **Free tier**: Falco OSS is free. **Best for**: Kubernetes-heavy environments wanting Falco-native runtime security with commercial support—**trade-off**: agent deployment required for runtime; node-based pricing scales with cluster size.



- **[Prisma Cloud Compute](https://www.paloaltonetworks.com/prisma/cloud)** (Palo Alto Networks)

  **CWPP delivered as part of Prisma Cloud** (formerly Twistlock). Protects hosts, containers, and serverless across any cloud or datacenter. **Credit-based licensing**: Hosts without containers **0.5 credit**; **container hosts 5 credits** (whether running 1 container or 100); app-embedded containers **1 credit**; serverless functions **1 credit per 6 defended functions** . **Two editions**: Enterprise Edition (SaaS, Palo Alto manages Console) and Compute Edition (self-hosted, air-gapped support) . **Pricing**: Credit-based; per-resource metering. **Free tier**: None. **Best for**: enterprises wanting a single platform for CSPM and CWPP—**note**: credit model rewards container density (1 host = 5 credits regardless of container count) .



- **[Snyk Container](https://snyk.io/product/container-vulnerability-management/)**

  **Container image scanning** with a distinctive remediation model: **base image recommendations** that suggest alternative base images to eliminate large batches of CVEs at once—turning "140 vulnerabilities" into "upgrade this base image and 90 go away" . Scans Docker and OCI images for OS and application dependency vulnerabilities; layer attribution identifies whether findings came from base image or added packages; connects to Docker Hub, ECR, GAR, ACR, and Harbor; CI pipeline integration; enterprise tier adds Kubernetes monitoring and runtime insights . **Pricing**: **Credit-based from January 1, 2026**—unified Platform Credit Consumption model; container scans, IaC scans, and cloud assessments each consume credits at their own rates; free tier with monthly limits . **Free tier**: Yes, basic image scanning with limits. **Best for**: teams wanting actionable base-image remediation guidance alongside CVE detection—**trade-off**: no native IaC or source code scanning in Container; credit model requires careful volume modeling .



- **[Wiz](https://www.wiz.io/)**

  **Agentless CNAPP** with container and Kubernetes visibility. Gartner reviewers highlight clear risk visualization, contextual prioritization, and quick onboarding across AWS, Azure, GCP, OCI, Alibaba Cloud, and Kubernetes . **Pricing**: Quote-only; enterprise contracts. **Free tier**: None. **Best for**: enterprises wanting agentless discovery with cross-cloud risk correlation—**trade-off**: higher cost as environments scale; less runtime depth than Aqua or Sysdig .



- **[Docker Scout](https://www.docker.com/)**

  **Container image analysis** integrated into Docker ecosystem. **Pricing**: Included with Docker subscriptions; free tier available. **Free tier**: Yes, limited. **Best for**: Docker Desktop users wanting basic image scanning without a separate tool—**trade-off**: less depth than dedicated security platforms.



- **[JFrog Xray](https://jfrog.com/xray/)**

  **Universal software composition analysis** within JFrog Artifactory ecosystem. **Important**: **Xray is not included in non-commercial licenses** (JCR or OSS)—available starting from **Pro X** commercial edition; **Xray HA requires Enterprise X or Enterprise+**; **JFrog Advanced Security (JAS) requires Enterprise X or Enterprise+**—Pro X includes only Xray's base vulnerability and license-compliance scanning . **Pricing**: Bundled with JFrog platform tiers. **Free tier**: No Xray in free tier. **Best for**: Artifactory users wanting container and dependency scanning within their artifact registry—**trade-off**: requires commercial JFrog license for Xray.



- **[GitHub Advanced Security](https://github.com/features/security)**

  **Native security for GitHub** with CodeQL, secret scanning, and Dependabot. **Critical limitation**: **GHAS has no native container or IaC scanning product as of 2026**—teams typically pair it with a separate tool. GitHub's coverage is limited to Dependabot picking up vulnerable base images in Dockerfile `FROM` lines . **Pricing**: Per unique committer per month on top of GitHub Enterprise; GHAS Code Security and GHAS Secret Protection are separate add-ons . **Free tier**: CodeQL free for public repos. **Best for**: GitHub-centric teams wanting code and secret scanning—**not** a container security solution without additional tools .



- **[Anchore Enterprise](https://anchore.com/)**

  **Container security and SBOM platform** with FedRAMP and DoD policy packs. **Pricing**: Container Image set via Helm; SBOM volume tiers (500–4,000 SBOMs/month); support tiers from Basic 9×5 SLA to 24×7 Priority . **Free tier**: Anchore Open Source (Syft, Grype) available separately. **Best for**: public sector and regulated enterprises needing FedRAMP/DoD compliance for container images—**trade-off**: pricing scaled by SBOM volume.



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
