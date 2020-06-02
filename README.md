# ports

This repo contains my commits to the FreeBSD ports tree.

* [lazylibrarian](https://lazylibrarian.gitlab.io/)

```bash
portsnap fetch && portsnap extract
mkdir /usr/ports/net-p2p/lazylibrian
cd /usr/ports/net-p2p/lazylibrian
touch Makefile pkg-descr
# Fill out Makefile and pkg-descr
make makesum
```

