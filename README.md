# **Title**

**Docker Practice**

---

## Check Docker Instance

run a command like

```
docker run hello-world
```

---

## Docker vs. VM

Why Docker over a VM?

Dockers performance as often 1-5 ms, while a VM takes 100+ ms to boot  
VMs take GBs of storage, docker takes mbs, 

---

## Commands

```
docker run, logs, rm, update (container), wait, commit, cp, create, events, builder 
```

---

## Tags

```
-p port tag (average port is 80:80 or 5000:80)
-d detach
-v version
--digest to check for other digest ver of an image
-e (environment)

```

---

## Good Practices

Work on using digests, and make sure to check for a set version of an image  
Image size matters a lot. To check for this pull Alpine images (linux distros) or  
Slim images, (smaller, more barebones a version to run a docker container faster, and more reliable)  
Try to run

```bash
#!/bin/bash

docker run python:3.12 python -c 'f="/data.txt";open(f, "a").write(f"Ran!\n");print(open(f).read())'
```

That’s where **Mounts** come in.  
Mounts are as follows:                            Persistance  
> Bind-Mounts                                         Yes  
> Volumes                                             Yes   
> Tempfs mounts                                        No

Bind-mounts, though dated, with older features, offers mounts by hosting  
file/dir into computer  
> Syntax  
>     > -v ./mydata:/path/in/container  
>     >-v /mydata:/path/in/container  
>     > --mount lowkey works but wouldn't reccomend

For Volumes, which is a newer mount, more features, and managed by Docker daemon
> Syntax
>     > -v mydata:/path/in/container
>     > --mount also works but ehhhhhhhh

