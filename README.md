# Awesome-Status-Page-Incident-Communication

# Top Status Page & Incident Communication Ecosystem

**Curated List of SaaS Products & Open-Source GitHub Projects**  
*Focused on Public Status Communication, Subscriber Notifications & Self-Hosted Incident Pages*  
**Last updated: October 2026**

This repository tracks notable **SaaS platforms** and **open-source projects** for **Status Page & Incident Communication**. These tools enable organizations to publish real-time service health, announce incidents and maintenance windows, and keep customers informed during outages—turning downtime into a trust-building moment rather than a support ticket flood.

**Examples** include Statuspage (Atlassian), Better Stack, Incident.io, Instatus, Status.io, Hund, StatusCast, Cachet, StatusTicker, and FireHydrant (the category leaders).

**Open-source emphasis**: Status Page & Incident Communication is a domain where open-source tooling is **genuinely viable but requires careful selection based on whether you need monitoring, communication, or both**. **Cachet** is the classic status-page-first tool—components, incidents, maintenance, metrics, and email/webhook subscribers—but its v3 rewrite has been in progress for years and the newest stable release is v2.4.1 from November 2023 . **Kener** offers a modern Node.js alternative with full incident lifecycle, 11 monitoring types, email/RSS subscribers, and an MIT license . **Uptime Kuma** is the default monitoring-first option with 31 check types and a built-in status page, but it lacks subscriber notifications beyond RSS . **OpenStatus** (AGPL-3.0) combines uptime checks and status pages with email, webhook, Slack, and RSS subscribers, plus a REST API and Terraform provider—but self-hosting requires operating several services . The critical caveat: **no single open-source project perfectly balances monitoring, communication, and operational simplicity**—Uptime Kuma is easy but lacks subscribers, Cachet has subscribers but is stagnant, and OpenStatus has both but requires more infrastructure .

Contributions welcome! Open a PR to add/update entries. Keep descriptions factual and link to official sites.

## Table of Contents
- [SaaS/Hosted Platforms](#saas-products)
- [Open-Source GitHub Projects](#open-source-github-projects)
- [How to Contribute](#how-to-contribute)
- [Disclaimer](#disclaimer)

## SaaS/Hosted Platforms

- **[Statuspage (Atlassian)](https://www.statuspage.io/)**  
  The market-leading hosted status page platform; components, incidents, scheduled maintenance, subscriber notifications via email/SMS/Slack/webhooks, and a vast integration ecosystem. The benchmark against which all alternatives are measured.

- **[Better Stack](https://betterstack.com/)**  
  Observability and incident management platform with integrated uptime monitoring, on-call scheduling, and status pages; recent additions include AI post-mortems and SOC 2 Type 2 / ISO 27001 compliance.

- **[Incident.io](https://incident.io/)**  
  Incident management platform with automated Slack-based workflows, status page generation, and post-incident retrospectives; focused on engineering-led incident response.

- **[Instatus](https://instatus.com/)**  
  Lightweight, fast status page service with a clean interface and affordable pricing; popular with indie developers and small teams.

- **[Status.io](https://status.io/)**  
  Status page and incident communication platform with component management, subscriber notifications, and metrics integration.

- **[Hund](https://hund.io/)**  
  Status page platform focused on simplicity and speed; includes incident management, maintenance scheduling, and subscriber notifications.

- **[StatusCast](https://www.statuscast.com/)**  
  Incident communication platform with status pages, mass notifications, and integration with monitoring tools.

- **[Cachet (Cloud)](https://cachethq.io/)**  
  The hosted version of the open-source Cachet; provides the same component/incident/subscriber model without infrastructure management.

- **[StatusTicker](https://statusticker.com/)**  
  Simple status page service with component monitoring and incident updates; positioned for teams wanting minimal setup.

- **[FireHydrant](https://firehydrant.com/)**  
  Incident management platform with status page integration, runbooks, and retrospective workflows; focused on the full incident lifecycle beyond just the public page.

## Open-Source GitHub Projects

### Status-Page-First (Communication Focus)

- **[Cachet](https://github.com/cachethq/cachet)**  
  The classic open-source **self-hosted status page** (BSD-3-Clause for v2, source-available for v3) with ~15,200 GitHub stars . Features: **components** with status levels (Operational, Performance Issues, Partial Outage, Major Outage), **incident management** with timestamped updates, **scheduled maintenance**, custom **metrics** (response time, uptime), **subscriber notifications** via email and webhook, JSON API, and 30+ language translations . **Critical caveat**: the newest stable release is v2.4.1 from November 2023; **v3 ships from an untagged development branch and is not yet completely ready for production use**—it also moves from BSD to a source-available license . **Best for teams wanting a traditional, dashboard-driven status page** who can accept the maintenance risk of a project in transition—but verify which version you are deploying.

- **[cState](https://github.com/cstate/cstate)**  
  Ultra-lightweight **static status page** built with Hugo (MIT) . Generates a fast, serverless site hosted anywhere; incidents are created via Markdown files; **no active monitoring, no alerting, no subscriber notifications beyond RSS** . **Best for open-source projects or documentation sites** wanting a simple incident communication page with zero infrastructure—not for customer-facing SaaS status pages requiring subscribers.

### Monitoring-First (With Built-In Status Pages)

- **[Uptime Kuma](https://github.com/louislam/uptime-kuma)**  
  The default open-source **monitoring tool** with ~91,800 GitHub stars and a built-in status page (MIT) . Features: **31 check types** in one container, configurable status page on your own domain, and maintenance announcements. **Critical limitation**: **incidents are posted manually** even when Kuma detects a failure, and **visitors can only follow via RSS**—there is no email subscriber list . **Best for homelabs and internal pages** where RSS is sufficient; **not for customer-facing status pages** where subscribers expect email notifications.

- **[Gatus](https://github.com/TwiN/gatus)**  
  Developer-oriented **declarative monitoring** tool (Apache-2.0) with a lightweight status page UI . Features: **YAML-based configuration** (no database for config), 8+ check types, low resource usage (~10–30MB RAM), and a built-in status page . **Limitations**: **no incident management, no maintenance scheduling, no subscriber notifications, no REST API**—it is a health dashboard, not an incident communication platform . **Best for DevOps teams wanting monitoring-as-code** with a simple public health view.

### Modern All-in-One (Monitoring + Communication)

- **[OpenStatus](https://github.com/openstatusHQ/openstatus)**  
  The strongest open-source **combined monitoring and status page** platform (AGPL-3.0, ~9,100 GitHub stars) . Features: **uptime checks** (HTTP, TCP, DNS) in the open-source checker, **status page** with custom domains, **incidents opened automatically from failing checks**, **subscriber notifications** via email, webhook, Slack, and RSS, **REST API** and **Terraform provider** . **Caveats**: self-hosting requires operating **several separate services**, it ships continuously **without tagged releases**, and the open-source checker supports only HTTP/TCP/DNS (other types exist in the API schema but not the checker) . **Best for teams wanting an integrated open-source alternative to Statuspage + monitoring** who can handle the operational complexity of multiple services.

- **[Kener](https://github.com/rajnandan1/kener)**  
  Modern open-source **status page with incident management** (MIT, Node.js/SvelteKit) . Features: **11 monitoring types**, full incident lifecycle, maintenance windows with RRULE, **email subscriber notifications**, 4 alerting channels, REST API (17+ endpoints), RBAC (3 roles), multi-database support (SQLite/PostgreSQL/MySQL), custom theming, and embeddable widgets . **Best for teams wanting a modern, feature-complete status page with built-in monitoring**—MIT licensed and actively developed. **Caveat**: requires Node.js + Redis infrastructure, and smaller community than Uptime Kuma or Cachet .

### Additional Strong Open-Source Options

- **OneUptime** — Full observability platform with public/private status pages, monitoring, incident management, and subscriber notifications (Apache-2.0 + enterprise) . **Heavier stack**—for teams wanting an all-in-one observability suite with status pages, not just a status page.
- **Upptime** — GitHub Actions-powered monitoring and static status page (MIT); **zero server setup**, but **5-minute minimum check interval** (GitHub Actions constraint), **no subscriber notifications**, and GitHub-only . **Best for open-source projects** already on GitHub wanting free, zero-maintenance uptime pages.
- **Suchaka** — Self-hosted status page with Go agent for HTTP monitoring, React/Node.js dashboard, PostgreSQL time-series storage, and multi-region support (Docker) . **Newer project**—verify production maturity, but offers a modern stack and explicit comparison against Cachet .
- **Fyren** — Self-hosted status page and incident management (Elastic License 2.0) with HTTP/TCP/SSL monitoring, incident lifecycle, maintenance windows, email/Slack/Discord/webhook notifications, and embeddable widgets . **License caveat**: ELv2 restricts offering as a managed service—verify terms if embedding in a commercial product .

**Frameworks for building custom systems**: The choice hinges on whether you need **communication-first** or **monitoring-first**. For **status-page-first with subscribers** (Statuspage alternative), Cachet (accepting v3 transition risk) or Kener . For **monitoring-first with a status view** (Uptime Kuma alternative), Gatus for declarative config or Uptime Kuma for ease . For **combined monitoring + communication with subscribers**, OpenStatus (accepting multi-service complexity) or Kener (simpler, MIT) . For **zero-infrastructure static pages**, cState or Upptime . No open-source project perfectly matches Statuspage's **managed reliability and integration ecosystem**—self-hosting means owning uptime, email deliverability, and upgrades.

## How to Contribute

1. Fork the repo.
2. Add/edit entries in `README.md` (follow existing format).
3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.
4. Submit PR with a short explanation.

Star the repo if you find it useful!

## Disclaimer

- This is a **community-curated** list — not exhaustive and not an endorsement.
- Status page platforms handling incident data and subscriber lists must comply with applicable privacy regulations (GDPR, CCPA) and data retention policies; **self-hosted status pages are especially vulnerable during the exact outages they are meant to communicate**—ensure the status page infrastructure is independent of the services it monitors .
- **Open-source status pages are mature but fragmented**—Cachet is the classic but **v3 is not production-ready** ; Uptime Kuma is popular but **lacks email subscribers** ; OpenStatus and Kener provide combined monitoring and communication but require more infrastructure. **No open-source project matches Statuspage's managed reliability and subscriber ecosystem**—choose based on whether your priority is communication (Cachet/Kener), monitoring (Uptime Kuma/Gatus), or both (OpenStatus/Kener).
- Verify license terms for commercial use; Cachet v2 uses BSD-3-Clause but **v3 moves to source-available** , Kener uses MIT , Uptime Kuma uses MIT, Gatus uses Apache-2.0, and OpenStatus uses AGPL-3.0 .

---

**Made for SREs, support managers, and teams choosing their incident communication platform.**  
Let's make status pages more open, but with clear eyes about the v3 transition risks and subscriber notification gaps that define each tool.
