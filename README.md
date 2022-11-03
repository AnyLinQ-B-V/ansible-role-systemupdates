# Ansible Role: System Updates

[![CI](https://github.com/AnyLinQ-B-V/ansible-role-systemupdates/actions/workflows/ci.yml/badge.svg?branch=main)](https://github.com/AnyLinQ-B-V/ansible-role-systemupdates/actions/workflows/ci.yml)
[![MIT License](http://img.shields.io/badge/license-MIT-blue.svg?style=flat)](LICENSE)

An Ansible role to manage system updates for Debian and RedHat-based systems.

## Requirements

- Ansible >= 2.10
- Debian or RedHat-based system

## Role Variables

No variables are required for this role.

## Dependencies

None.

## Example Playbook

```yaml
- hosts: servers
  roles:
    - anylinq.systemupdates
```

## Actions Performed

This role will:

- Update package cache for apt/dnf systems
- Perform system updates using appropriate package manager
- Run autoremove to clean up unused packages
- Handle both Debian and RedHat-based systems

### Debian-based Systems
- Updates package cache (apt update)
- Performs distribution upgrade (apt upgrade)
- Runs autoremove if updates were applied

### RedHat-based Systems
- Updates package cache (dnf update)
- Upgrades all packages to latest version
- Runs autoremove if updates were applied

## Testing

This role is tested using Molecule with the following test matrix:

- Debian 12 (Bookworm)
- AlmaLinux 9
- Ubuntu 22.04

## Setup for development

```python -m pip install --upgrade -r requirements.txt```

or

```pip install -r requirements.txt```

## License

MIT

## Author Information

This role was created by Ronny Roethof for AnyLinQ B.V.

## Contributing

Please read our [Contributing Guide](CONTRIBUTING.md) and our [Code of Conduct](CODE_OF_CONDUCT.md) before submitting a Pull Request.

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

For more detailed information about contributing to this project, please read:
- [Code of Conduct](CODE_OF_CONDUCT.md)
- [Contributing Guidelines](CONTRIBUTING.md)

## Security

For security-related issues, please see our [Security Policy](SECURITY.md). We take security seriously and encourage responsible disclosure.

Please do not report security vulnerabilities through public GitHub issues. Instead, please report them via:
- Email: security@anylinq.com
- [Security Advisory](https://github.com/AnyLinQ-B-V/ansible-role-systemupdates/security/advisories/new)

## CI/CD

The role uses GitHub Actions for:
- YAML Linting
- Ansible Linting
- Molecule Testing
- Automatic Galaxy Import

---

<div align="center">
Created and maintained by <a href="https://www.anylinq.com">AnyLinQ B.V.</a><br/><br/>
<a href="https://www.anylinq.com"><img src="https://anylinq.com/hs-fs/hubfs/logo-(1).png?width=164&height=69&name=logo-(1).png" alt="AnyLinQ Logo"/></a>
</div>

---

<sub>Author: Ronny Roethof (<a href="mailto:ronny@roethof.net">ronny@roethof.net</a>)</sub>
