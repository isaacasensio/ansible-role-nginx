Nginx
=========

Installs nginx docker container as a Linux service.


Role Variables
--------------

Available variables are listed below, along with default values (see defaults/main.yml):

```
nginx_image: "nginxinc/nginx-unprivileged:latest"
```
The version of the docker image to run as a container.

```
nginx_host_port: 80
```
Host exposed port from where to reach nginx.

```
nginx_host_config_path: /etc/nginx
```
nginx config path in the host machine.

```
nginx_container_user: nginx
```
user running the container 

```
nginx_conf: |
  pid  /tmp/nginx.pid;
  events {
    worker_connections  1024;  ## Default: 1024
  }
  http {
    server {
      listen 8080;
      return 200;
    }
  }
```
nginx config


Dependencies
------------

None

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - iasensio.nginx

License
-------

MIT

