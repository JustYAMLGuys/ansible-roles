# Tailscale Client

Install and configure [tailscale](https://galaxy.ansible.com/artis3n/tailscale) using [artis3n](https://galaxy.ansible.com/artis3n) ansible role.

## Role variables

* `tailscale_args` - Default `--login-server='http://headscale.justyamlguys.com:8080/' --accept-routes`.
* `tailscale_up_skip` - Default: `true`
* `release_stability` - Default: `stable`.
* `state` - Default: `latest`.

`Note` - for var `tailscale_up_skip`:
```If set to true, tailscale_authkey is not required.

Default: false

Whether to install and configure Tailscale as a service but skip running tailscale up.
Helpful when packaging up a Tailscale installation into a build process such as AMI creation when the server should not yet authenticate to your Tailscale network.
```

## Example Playbook

```yaml
- name: Setup tailscale client
  hosts: node1
  become: true

  tasks:
    ansible.builtin.include_role:
      name: artis3n.tailscale
    vars:
      tailscale_args: "--login-server='http://headscale.justyamlguys.com:8080/' --accept-routes"
      tailscale_up_skip: true
      release_stability: stable
      state: latest
```

## Usage
``make tailscale``
