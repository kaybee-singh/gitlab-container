```bash
mkdir -p /srv/gitlab/config
mkdir -p /srv/gitlab/logs
mkdir -p /srv/gitlab/data
```
```bash
podman run -d   --name gitlab   --hostname gitlab.example.com   -p 80:80 -p 443:443   -v /srv/gitlab/config:/etc/gitlab:Z   -v /srv/gitlab/logs:/var/log/gitlab:Z   -v /srv/gitlab/data:/var/opt/gitlab:Z   --env GITLAB_OMNIBUS_CONFIG="external_url 'https://gitlab.example.com'"   gitlab/gitlab-ce:latest
```
```bash
podman exec -it gitlab grep 'Password:' /etc/gitlab/initial_root_password
```
