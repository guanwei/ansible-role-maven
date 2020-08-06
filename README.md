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

# Filename of Maven redistributable package
maven_redis_filename: "apache-maven-{{ maven_version }}-bin.zip"

# If this is the default installation, /etc/profile.d/maven.sh will be set.
maven_is_default_installation: false
```

`maven_download_dir` default is "%TEMP%/ansible/downloads" on Windows, "$HOME/.ansible/tmp/downloads" on Linux.

`maven_install_dir` default is "C:/Maven" on Windows, "/opt/maven" on Linux.

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
