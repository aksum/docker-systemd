# docker-systemd
Running systemd in a container.

## How
#### systemd-nginx-test

- Dockerfile in: `cd systemd-nginx-test`
- Build systemd-nginx image: `docker build -t systemd-nginx .`
- Run systemd-nginx: `docker run --name=systemdtest -ti --rm --cap-add=SYS_ADMIN --tmpfs /run --tmpfs /run/lock --tmpfs /tmp -p 8080:80 -v /sys/fs/cgroup:/sys/fs/cgroup:ro systemd-nginx`
- Monitor output: `docker exec systemdtest journalctl -f`
- Stop container: `docker stop systemdtest`

## Links

- https://developers.redhat.com/blog/2016/09/13/running-systemd-in-a-non-privileged-container/
- https://github.com/moby/moby/issues/28614#issuecomment-261724902
