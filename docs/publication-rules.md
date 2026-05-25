# Publication rules

Security and content guidelines for all content published on
witzops.dev.

## Why this exists

This repository is public. It is built and deployed as a static site
to Cloudflare Pages. Every commit to `main` is live within minutes.

Private infrastructure runbooks, internal hostnames, and operational
procedures must **never** appear in this repository. Those belong in a
separate, private repository.

## What can be published

- Architecture decision records that describe patterns and trade-offs.
- Tool evaluations and comparison notes.
- Implementation guides for self-hosted services — written generically
  so others can follow along.
- Configuration patterns (e.g., Ansible roles, Terraform modules) with
  specific values replaced by placeholders.
- Diagrams that use generic labels (`lab-proxmox-01` instead of the
  real FQDN).
- Lessons learned and post-mortem notes (sanitized).

## What must not be published

- IP addresses (public or private).
- Internal hostnames, FQDNs, or DNS records pointing to real
  infrastructure.
- API keys, tokens, passwords, certificates, or any credential.
- SSH keys or authorized_keys content.
- Runbook procedures that describe step-by-step operational actions
  against live systems.
- Network topology diagrams with real labels.
- Vendor account IDs, resource IDs, or subscription identifiers.
- Any personally identifiable information (PII) beyond what is
  intentionally public (e.g., the author's name in the LICENSE file).

## How to sanitize content

When writing content that references real infrastructure:

1. Replace real hostnames with descriptive placeholders:
   - `proxmox.lab.example.com` → `lab-hypervisor`
   - `192.168.10.5` → `10.x.x.x` or `lab-ip`

2. Replace real API endpoints with generic paths:
   - `https://api.provider.com/v2/...` → `PROVIDER_API`

3. Strip shell prompts that show real hostnames:
   - `root@prod-db-01:~#` → `$` or change the hostname.

4. Replace real domain names in examples with `example.com` or
   `domain.tld`.

5. Obfuscate or remove any values that could be used to fingerprint
   real systems (MAC addresses, serial numbers, cloud instance IDs).

## Review checklist

Before publishing any article or page:

- [ ] No IP addresses.
- [ ] No real hostnames or FQDNs.
- [ ] No credentials, tokens, or keys.
- [ ] No operational runbook procedures against live systems.
- [ ] Placeholder values are clearly distinguishable from real data.
- [ ] Content teaches a reusable pattern, not a specific internal
  procedure.

## Relationship to private documentation

| Aspect              | Public (this repo)              | Private (separate repo)        |
|---------------------|---------------------------------|--------------------------------|
| Audience            | Anyone on the internet          | Authorized operators only      |
| Content             | Patterns, lessons, architecture | Runbooks, configs, credentials |
| Detail level        | Generic, reusable               | Specific, operational          |
| Hostnames           | Placeholders only               | Real hostnames                 |
| Credentials         | Never                           | Encrypted at rest              |
