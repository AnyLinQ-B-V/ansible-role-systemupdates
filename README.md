# Ansible Role: System Updates

[![CI](https://github.com/AnyLinQ-B-V/ansible-role-systemupdates/actions/workflows/ci.yml/badge.svg?branch=main)](https://github.com/AnyLinQ-B-V/ansible-role-systemupdates/actions/workflows/ci.yml)
[![MIT License](http://img.shields.io/badge/license-MIT-blue.svg?style=flat)](https://github.com/AnyLinQ-B-V/ansible-role-systemupdates/blob/main/LICENSE)

An Ansible role to manage system updates across multiple Linux distributions.

## Supported Platforms

  - Debian
    - Debian 12 (Bookworm)
    - Debian 13 (Trixie)
  - Ubuntu
    - Ubuntu 22.04 LTS (Jammy)
    - Ubuntu 24.04 LTS (Noble)
  - Enterprise Linux
    - EL 9
  
## Requirements

  - Ansible >= 2.10
  - Python 3.x

## Role Variables

```yaml
# General settings
systemupdates_autoremove: true        # Run autoremove after updates
systemupdates_only_upgrade: false     # Only upgrade existing packages

# Apt specific settings (Debian/Ubuntu)
systemupdates_upgrade_type: "dist"    # Type of upgrade (safe|full|dist)
systemupdates_cache_valid_time: 3600  # Cache validity in seconds
systemupdates_autoclean: true         # Run apt autoclean

# DNF specific settings (RHEL/Rocky/Alma)
systemupdates_security_only: false    # Only install security updates
systemupdates_bugfix: true            # Include bugfix updates
```

## Dependencies

None.

## Example Playbook

```yaml
- hosts: servers
  roles:
    - anylinq.systemupdates
```

## Testing

This role is tested using Molecule with the following test matrix:
  - Debian 12
  - Ubuntu 22.04

### Running Tests Locally

First, install the Python dependencies:
```bash
python -m pip install --upgrade -r requirements.txt
```

Then run the tests for specific distributions:

```bash
# For Debian 12
MOLECULE_DISTRO=debian12 molecule test

# For Ubuntu 22.04
MOLECULE_DISTRO=ubuntu2404 molecule test
```

The CI pipeline automatically tests all supported distributions.

## License

MIT

## Changelog

See [CHANGELOG.md](https://github.com/AnyLinQ-B-V/ansible-role-systemupdates/blob/main/CHANGELOG.md) for a list of all notable changes to this project.

## Security

Please see our [Security Policy](https://github.com/AnyLinQ-B-V/ansible-role-systemupdates/blob/main/SECURITY.md) for reporting vulnerabilities.

## Contributing

Please read our [Contributing Guide](https://github.com/AnyLinQ-B-V/ansible-role-systemupdates/blob/main/CONTRIBUTING.md) and our [Code of Conduct](https://github.com/AnyLinQ-B-V/ansible-role-systemupdates/blob/main/CODE_OF_CONDUCT.md) before submitting a Pull Request.

---

<div align="center">
Created and maintained by <a href="https://www.anylinq.com">AnyLinQ B.V.</a><br/><br/>
<a href="https://www.anylinq.com"><img src="https://anylinq.com/hubfs/AnyLinQ%20transparant.png" width="120" alt="AnyLinQ Logo"/></a>
</div>

---

<sub>Author: Ronny Roethof (<a href="mailto:ronny@roethof.net">ronny@roethof.net</a>)</sub>
