This Docker image helps you start your own proxy server, with HTTP Basic
authorization. You may need this if you want your crawling/scaping software
to look like constantly going to the Network from the same IP address. You
rent a VPS, start a Squid server there and configure your software to
go everywhere through an explicit HTTP(S) proxy.

First, you pull it:

```bash
$ docker pull yegor256/squid-proxy
```

Then, you run it:

```
$ docker run --name proxy -d --restart=always --publish 3128:3128 \
  -e USERNAME=jeffrey -e PASSWORD=swordfish \
  yegor256/squid-proxy
```

Now you can connect to `localhost:3128` with `jeffrey:swordfish` credentials.

Here is how you [install](https://docs.docker.com/install/) Docker.
