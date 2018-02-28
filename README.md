Ansible role: nerdfonts
=========

[![MIT licensed][mit-badge]][mit-link]
[![Galaxy Role][role-badge]][galaxy-link]

Cross-platform ansible role for [NerdFonts][nerdfonts] ([on GitHub][nf-git]) installation.

Requirements
------------

One of the following OS (or deriviatives):
 - Debian | Ubuntu
 - MacOS (with [Homebrew][homebrew])

For MacOS:
if Homebrew is not installed on the managed host, install the following role via galaxy:

    ansible-galaxy install drew-kun.homebrew

 And include it in the playbook:

    roles:
        - drew-kun.homebrew

Role Variables
--------------

OS-Agnostic:

| Variable | Description | Default |
|----------|-------------|---------|
| **nerdfonts_fonts** | list of nerdfonts to be installed | see *defaults/main.yml* |

Debian-Specific:

| Variable | Description | Default |
|----------|-------------|---------|
| **nerdfonts_env** | install fonts system- or user-wide | `system` |
| **nerdfonts_deb_fonts_sys_dir** | system-wide fonts directory | `/usr/local/share/fonts` |
| **nerdfonts_deb_fonts_user_dir** | user-specific fonts directory | `~/.local/share/fonts` |
| **nerdfonts_users** | list of users nerdfonts to be installed | see *vars/Debian.yml* |

MacOS-Specific:

| Variable | Description | Default |
|----------|-------------|---------|
| **nerdfonts_mono** | install mono font from homebrew cask | `no` |

Dependencies
------------

None

Example Playbook
----------------

    - hosts: dev_clients_macos
      roles:
        - drew-kun.homebrew
        - drew-kun.nerdfonts

License
-------

[MIT][mit-link]

Author Information
------------------

Andrew Shagayev | [e-mail](mailto:drewshg@gmail.com)

[role-badge]: https://img.shields.io/badge/role-drew--kun.nerdfonts-green.svg
[galaxy-link]: https://galaxy.ansible.com/drew-kun/nerdfonts/
[mit-badge]: https://img.shields.io/badge/license-MIT-blue.svg
[mit-link]: https://raw.githubusercontent.com/drew-kun/ansible-nerdfonts/master/LICENSE
[homebrew]: http://brew.sh/
[nerdfonts]: https://nerdfonts.com/
[nf-git]: https://github.com/ryanoasis/nerd-fonts
