# docker-twitch-drops-miner

Based on this image: https://github.com/jlesage/docker-baseimage-gui

```
docker build -t c0rrre/twitch-drops-miner:latest .
docker push c0rrre/twitch-drops-miner:latest
```

Don't forget to mount `/config` to have data persistence.

You can also mount `/cache` to preserve cached images and mappings.

Available at: https://hub.docker.com/r/c0rrre/twitch-drops-miner

Example Docker Compose:

```yaml
twitch-drops-miner:
  image: c0rrre/twitch-drops-miner
  ports:
    - "5800:5800/tcp"
  volumes:
   - /usr/me/tdm/config:/config
   - /usr/me/tdm/cache:/cache
  environment:
    - USER_ID=568
    - GROUP_ID=568
```

See [Environment Variables](https://github.com/jlesage/docker-baseimage-gui?tab=readme-ov-file#environment-variables) for a list of all the supported ones.
