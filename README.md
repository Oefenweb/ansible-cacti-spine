## cacti-spine

[![CI](https://github.com/Oefenweb/ansible-cacti-spine/workflows/CI/badge.svg)](https://github.com/Oefenweb/ansible-cacti-spine/actions?query=workflow%3ACI)
[![Ansible Galaxy](http://img.shields.io/badge/ansible--galaxy-cacti--spine-blue.svg)](https://galaxy.ansible.com/Oefenweb/cacti_spine)

Set up [Spine](https://github.com/Cacti/spine) (a poller for Cacti) in Debian-like systems.

#### Requirements

See `vars/main.yml`

#### Variables

* `cacti_spine_git_repo`: [default: `https://github.com/Cacti/spine.git`]: Spine git repo
* `cacti_spine_version`: [default: `1.2.17`]: Only used in `{{ cacti_spine_git_version }}`
* `cacti_spine_git_version`: [default: `"release/{{ cacti_spine_version }}"`]: What version of cacti-spine to check out (set up). This can be the full 40-character SHA-1 hash, the literal string HEAD, a branch name, or a tag name
* `cacti_spine_libmysqlclient_dev`: [default: `libmysqlclient-dev`]: `libmysqlclient-dev` version to install. Percona Server users might want to change this to `libperconaserverclient16-dev` (5.1), `libperconaserverclient18-dev` (5.5), `libperconaserverclient18.1-dev` (5.6) or `libperconaserverclient20-dev` (5.7).
* `cacti_spine_install_prefix`: [default: `/usr/local/spine`]: Install prefix
* `cacti_spine_configure_options`: [default: `["--prefix={{ cacti_spine_install_prefix }}"]`]: Options to pass to `./configure`
* `cacti_spine_etc_spine_conf`: [default: see `defaults/main.yml`]: List of lines to be added to `"{{ cacti_spine_etc_spine_conf_file }}"`
* `cacti_spine_etc_spine_conf_user`: [default: `root`]: Owner of `"{{ cacti_spine_etc_spine_conf_file }}"`
* `cacti_spine_etc_spine_conf_group`: [default: `www-data`]: Group of `"{{ cacti_spine_etc_spine_conf_file }}"`
* `cacti_spine_etc_spine_conf_mode`: [default: `0640`]: Mode of `"{{ cacti_spine_etc_spine_conf_file }}"`

## Dependencies

None

## Recommended

* `cacti-spine` ([see](https://github.com/Oefenweb/ansible-cacti-spine))
* `cacti-server` ([see](https://github.com/Oefenweb/ansible-cacti-server))
* `cacti-plugin-percona` ([see](https://github.com/Oefenweb/ansible-cacti-plugin-percona))

#### Example

##### Simple

```yaml
---
- hosts: all
  roles:
    - cacti-spine
```

##### Advanced

```yaml
---
- hosts: all
  roles:
    - cacti-spine
  vars:
    cacti_spine_git_repo: https://github.com/tersmitten/spine.git
    cacti_spine_git_version: fix-build-for-percona
    cacti_spine_etc_spine_conf:
      - |
        DB_Host       localhost
        DB_Database   cacti
        DB_User       cacti
        DB_Pass       secret
        DB_Port       3306
```

#### License

MIT

#### Author Information

Mischa ter Smitten

#### Feedback, bug-reports, requests, ...

Are [welcome](https://github.com/Oefenweb/ansible-cacti-spine/issues)!
