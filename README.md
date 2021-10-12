# Desktop gnupg role

[![Generate tag](https://github.com/agoloncser/ansible-role-gnupg/actions/workflows/bump.yml/badge.svg)](https://github.com/agoloncser/ansible-role-gnupg/actions/workflows/bump.yml)
[![Generate tag](https://github.com/agoloncser/ansible-role-gnupg/actions/workflows/bump.yml/badge.svg)](https://github.com/agoloncser/ansible-role-gnupg/actions/workflows/bump.yml)
[![Molecule testing](https://github.com/agoloncser/ansible-role-gnupg/actions/workflows/ci.yml/badge.svg)](https://github.com/agoloncser/ansible-role-gnupg/actions/workflows/ci.yml)

Ansible role to install and configure GnuPG. Intended to use on `localhost` for the current user.

## Requirements

None.

## Role Variables

The following variables can be used to configure GnuPG. They are coming with a sane and fairly secure defaults. See defaults/main.yml for default values.

### `gnupg_gpg_conf`

Configures `~/.gnupg/gpg.conf`. All configuration option goes line-by-line into the config file.

``` yaml
gnupg_gpg_conf: |
  cert-digest-algo SHA512
  charset utf-8
  default-preference-list SHA512 SHA384 SHA256 AES256 AES192 AES ZLIB BZIP2 ZIP Uncompressed
  fixed-list-mode
```

### `gnupg_gpg_agent_conf`

Configures `~/.gnupg/gpg-agent.conf`.

``` yaml
gnupg_gpg_agent_conf: |
  default-cache-ttl 10
  max-cache-ttl 10
```

### `gnupg_scdaemon_conf`

Configures `~/.gnupg/scdaemon.conf`.

``` yaml
gnupg_scdaemon_conf: |
  card-timeout 30
```

## Dependencies

None.

## Example Playbook

    - hosts: localhost
      vars:
      roles:
         - agoloncser.gnupg

## License

BSD

## Author Information

https://github.com/agoloncser
