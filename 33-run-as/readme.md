# Create a busybox pod called myuserpod that runs as UID=4242 and GID=4242

`kubectl run myuserpod --image=busybox -o yaml --dry-run`

edit yaml, add:
```
securityContext:
  runAsUser: 4242
  runAsGroup: 4242
```

Bonus: repeat the above task changing the image for nginx. (there are additional configurations to be considered.
The user will not have permission to bind to port 80. Use a configmap to override the listen port for nginx to 8000. hint: /etc/nginx/conf.d/default.conf
Nginx has needs to write to two additional paths (owned by root).
	1: /var/cache/nginx
	2: /var/run
