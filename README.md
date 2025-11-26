# Graylogolas

Docker logging to Seq via GELF.

![Aye, I Could Do That Meme](graylogolas.png)

## Setup

```shell
docker compose up -d
```

> [!IMPORTANT]
> `SEQ_FIRSTRUN_NOAUTHENTICATION` is set for local development -- if you want to
> setup something similar in a deployed environment, please use authentication.

Set the following in your Docker config / `daemon.json`:

```json
{
  "log-driver": "gelf",
  "log-opts": {
    "gelf-address": "udp://127.0.0.1:12201"
  }
}
```

Apply and restart. See Seq running at [localhost:5341](http://localhost:5341).

## Troubleshooting

If you don't see logs in Seq, try recreating containers so they pull in the new
default logging settings you set above.

## Additional Info
- https://datalust.co/docs/environment-variables
  - includes steps for adding authentication
- https://docs.datalust.co/docs/using-gelf
- https://docs.datalust.co/docs/collecting-docker-container-logs