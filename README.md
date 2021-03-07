# ipfs-cluster-private

IPFS cluster setup: 3 nodes

```bash
go get github.com/Kubuxu/go-ipfs-swarm-key-gen/ipfs-swarm-key-gen # IPFS private secret shared key generation tool
ipfs-swarm-key-gen > swarm.key # Generate secret key
mkdir compose/ipfs0 compose/ipfs1 compose/ipfs2 compose/cluster0 compose/cluster1 compose/cluster2  # Create IPFS directories
tee compose/ipfsA/swarm.key compose/ipfsB/swarm.key compose/ipfsC/swarm.key < swarm.key # All nodes configs should have same secret keys
docker-compose up -d ipfs0 ipfs1 ipfs2 # Start ipfs service
docker-compose up -d cluster0 cluster1 cluster2 # start cluster service
```
