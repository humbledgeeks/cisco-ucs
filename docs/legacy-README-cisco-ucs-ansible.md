# cisco-ucs-ansible

Ansible automation for Cisco UCS infrastructure using the `cisco.ucs` collection.

## Contents

| File | Purpose |
|------|---------|
| `ucs-gather-inventory.yml` | Gather full UCS inventory |

## Prerequisites

- Ansible 2.12+
- `ansible-galaxy collection install cisco.ucs`

## Quick Start

```bash
ansible-playbook ucs-gather-inventory.yml -i inventory.yml --ask-vault-pass
```

## CI/CD

All PRs validated by ansible-lint, secret scan, and header compliance.

## Owner

humbledgeeks-allen | [HumbledGeeks.com](https://humbledgeeks.com)
