
playbook
```
  - name: "Git installation"
    hosts: localhost
    connection: local
    tasks:
    - name: download file
      get_url:
        url: https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.rpm.sh
        dest: ./script.rpm.sh
        mode: '0700'

    - name: run script
      script: ./script.rpm.sh
      args:
        creates: /etc/yum.repos.d/gitlab_gitlab-ce.repo

    - name: install gitlab
      yum:
        name: gitlab-ce
        state: latest
    - name: copy config file
      copy:
        src: ./gitlab.rb
        dest: /etc/gitlab/gitlab.rb

    - name: configure gitlab ctl
      shell: "gitlab-ctl reconfigure"
```