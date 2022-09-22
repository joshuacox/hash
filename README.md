# hash

```
./hash.sh`
```

And it will build the image and prompt you for a password.

e.g.


```
./hash.sh
+ docker build -t hash -f Dockerfile.openldap .
Sending build context to Docker daemon  64.51kB
Step 1/4 : FROM archlinux:latest
 ---> ec4c97123c01
Step 2/4 : RUN pacman -Syu --noconfirm --color always openldap sudo && pacman -Scc --noconfirm
 ---> Using cache
 ---> 98252762f094
Step 3/4 : COPY start.sh /usr/local/bin/start.sh
 ---> Using cache
 ---> 18fcfd871b2b
Step 4/4 : ENTRYPOINT [ "start.sh" ]
 ---> Using cache
 ---> ed53ff14b252
Successfully built ed53ff14b252
Successfully tagged hash:latest
+ docker run -it --rm hash
New password: 
Re-enter new password: 
{ARGON2}$argon2id$v=19$m=65536,t=2,p=1$9+WXOdSmGGRjY$6ApjnEteH+qjIZgVaj8FIxL9CnbL7C3rqYO0
```
