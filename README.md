## dockge

```shell
docker run -d \
--name louislam-dockge-nightly \
--restart always \
--pull always \
-v "$HOME/.docker:/root/.docker:ro" \
-v "/var/run/docker.sock:/var/run/docker.sock" \
-v "/var/lib/srv/$USER/docker/louislam/dockge/nightly/rootfs/data/dockge:/app/data" \
-v "/var/lib/srv/$USER/docker/louislam/dockge/nightly/rootfs/config/dockge:/opt/stacks" \
-p 172.17.0.1:50021:5001 \
-e DOCKGE_STACKS_DIR=/opt/stacks \
louislam/dockge:nightly 
```

