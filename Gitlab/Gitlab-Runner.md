```
# register
docker run --rm -it -v /opt/gitlab-runner/config:/etc/gitlab-runner --net host gitlab/gitlab-runner register --url https://gitlab.skycalhl.duckdns.org --token glrt-BUc8xh_3YKycyjHrhpVm

# run
docker run -d --name gitlab-runner --restart always  -v /var/run/docker.sock:/var/run/docker.sock -v /opt/gitlab-runner/config:/etc/gitlab-runner gitlab/gitlab-runner:latest

```

config 
```
concurrent = 1
check_interval = 0
shutdown_timeout = 0

[session_server]
  session_timeout = 1800

[[runners]]
  name = "backstage01"
  url = "https://gitlab.skycalhl.duckdns.org"
  id = 1
  token = "glrt-BUc8xh_3YKycyjHrhpVm"
  token_obtained_at = 2024-01-17T02:44:38Z
  token_expires_at = 0001-01-01T00:00:00Z
  executor = "docker"
  [runners.cache]
    MaxUploadedArchiveSize = 0
  [runners.docker]
    tls_verify = false
    image = "alpine:latest"
    privileged = false
    disable_entrypoint_overwrite = false
    oom_kill_disable = false
    disable_cache = false
    volumes = ["/cache"]
    shm_size = 0
    network_mtu = 0
    extra_hosts = ["gitlab.skycalhl.duckdns.org:192.168.20.36"] # to help additional containers resolve records
```