# Ansible Role: Maven

Installs Maven on Debian/Ubuntu or Windows/Windows Core.

## Requirements

None.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

```
# Maven version number
maven_version: 3.6.3

# Mirror to download the Maven redistributable package from
maven_mirror: "http://archive.apache.org/dist/maven/maven-{{ maven_version.split('.')[0] }}/{{ maven_version }}/binaries"

# Directory to store files downloaded for Maven installation
maven_download_dir: "{{ x_ansible_download_dir | default(ansible_env.HOME + '/.ansible/tmp/downloads') }}"

# Base Maven installation directory
maven_install_dir: "/opt/maven"

# If this is the default installation, /etc/profile.d/maven.sh will be set.
maven_is_default_installation: false
```

## Dependencies

None.

## Example Playbook

requirements.yml
```
- name: maven
  src: <repo_url>
  version: <branch_name>
  scm: git
```

playbook.yml
```
- hosts: servers
  roles:
    - maven
```
