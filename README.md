## dockge

```shell
docker run -d \
--name dockge-app \
-h ${BASE_HOST_NAME:-$HOSTNAME} \
--restart always \
--pull always \
--log-driver json-file \
--log-opt max-size=5m,max-file=1 \
-e TZ=${TZ:-America/New_York} \
-e DOCKGE_STACKS_DIR=/opt/stacks \
-p 172.17.0.1:59069:5001 \
-v $HOME/.docker/:/root/.docker:ro \
-v /var/run/docker.sock:/var/run/docker.sock \
-v /var/lib/srv/$USER/docker:/var/lib/srv/$USER/docker \
-v /var/lib/srv/$USER/docker/dockge/rootfs/data/dockge:/app/data \
-v /var/lib/srv/$USER/docker/dockge/rootfs/config/dockge:/opt/stacks \
louislam/dockge:nightly
```
