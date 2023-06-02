# ansible-roles
 Collection of roles for our configurations

### Testing

Test Ansible role and keep the instance running:
```bash
molecule converge -s <role-name>
```

Destroy the instance:
```bash
molecule destroy [--all|-s <role-name>]
```

Run full suite of tests:
```bash
molecule test -s <role-name>
```
