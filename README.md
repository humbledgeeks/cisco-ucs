# cisco-ucs

Reusable automation for **Cisco UCS Manager** (UCSM) domains. Read-only inventory only; nothing
here changes UCS configuration.

## Contents

| Path | Language | What it does | Effect |
|---|---|---|---|
| `ansible/ucs-gather-inventory.yml` | Ansible (`cisco.ucs` collection) | Gathers UCS inventory from a UCS Manager | read-only |
| `powershell/get-ucs-inventory.ps1` | PowerShell (Cisco PowerTool, `Cisco.UCSManager`) | Lists blades and their service-profile associations | read-only |
| `docs/legacy-README-*.md` | — | Original per-repository READMEs (prerequisites, usage examples) | — |

## Prerequisites

- Ansible: `ansible-galaxy collection install cisco.ucs`; run with `--ask-vault-pass` and a vault providing the UCS credentials.
- PowerShell 5.1/7 with `Install-Module Cisco.UCSManager`.
- Network reachability to the UCS Manager VIP over HTTPS.

## Environment-specific configuration

Target hostnames and credentials are supplied at run time (inventory/vault or prompts). No lab or
customer environment data is kept in this repository. Site-specific UCS build automation (pools,
VLAN/VSAN, policies, service profiles) is intentionally **not** part of this repository.

## Credentials and safety

No credentials are stored in this repository. PowerShell scripts prompt (`Get-Credential`) or read
environment variables; Ansible playbooks expect an Ansible Vault (`--ask-vault-pass`) providing the
`vault_*` variables named in `group_vars`. Never commit vault files, Clixml exports or `.env` files
(see `.gitignore`). Run output (reports, CSV, logs) is generated content and is git-ignored; keep it
outside the repository.

## Provenance

Consolidated from previous local automation repositories during the 2026 LabOps repository
cleanup. This repository starts with a fresh history; earlier history is retained locally only.
