## cacti-spine

[![Build Status](https://travis-ci.org/Oefenweb/ansible-cacti-spine.svg?branch=master)](https://travis-ci.org/Oefenweb/ansible-cacti-spine)
[![Ansible Galaxy](http://img.shields.io/badge/ansible--galaxy-cacti--spine-blue.svg)](https://galaxy.ansible.com/Oefenweb/cacti-spine)

Set up [Spine](https://github.com/Cacti/spine) (a poller for Cacti) in Debian-like systems.

#### Requirements

* `git` (will be installed)
* `build-essential` (will be installed)
* `autoconf` (will be installed)
* `automake` (will be installed)
* `libpcre3-dev` (will be installed)
* `libevent-dev` (will be installed)
* `pkg-config` (will be installed)
* `zlib1g-dev` (will be installed)

#### Variables

* `cacti_spine_version` [default: `release/1.2.15`]: What version of cacti-spine to check out (set up). This can be the full 40-character SHA-1 hash, the literal string HEAD, a branch name, or a tag name

## Dependencies

None

## Recommended

* `cacti-client` ([see](https://github.com/Oefenweb/ansible-cacti-client))
* `cacti-server` ([see](https://github.com/Oefenweb/ansible-cacti-server))
* `cacti-plugin-percona` ([see](https://github.com/Oefenweb/ansible-cacti-plugin-percona))

#### Example

```yaml
---
- hosts: all
  roles:
    - cacti-spine
```

#### License

MIT

#### Author Information

Mischa ter Smitten

#### Feedback, bug-reports, requests, ...

Are [welcome](https://github.com/Oefenweb/ansible-cacti-spine/issues)!
