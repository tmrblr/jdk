
JDK
=========

 - [x] Installs archived JDK
 - [x] Configures environment variables in a file in /etc/profile.d.

Requirements
------------
The role has been tested with **Docker.** Check *.j2 files in *molecule/default* for required packages for each distro.

Role Variables
--------------
Check *defaults/main.yml* for examples. 

**jdk_url**

[URL of archive with JDK](https://www.oracle.com/java/technologies/downloads/)

**jdk_install_path**

Where to unarchive JDK archive

**jdk_env_vars_path**

Full path for a file with environment variables

**jdk_env_vars**

List of environment variables (JAVA_HOME, PATH, etc)

Dependencies
------------

Example Playbook
----------------
Install JDK 18:

    - hosts: all
      roles:
        - role: tmrblr.jdk
          vars:
            jdk_url: https://download.oracle.com/java/18/latest/jdk-18_linux-x64_bin.tar.gz
            jdk_install_path: /opt/java
            jdk_env_vars_path: /etc/profile.d/jdk.sh
            jdk_env_vars: |
              export JAVA_HOME={{ java_home }}
              export PATH=$PATH:{{ java_home }}/bin

License
-------
MIT
