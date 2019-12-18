# nexus
## Quick Start
```
git clone https://github.com/bharatmicrosystems/nexus.git
cd nexus
kubectl apply -f nexus.yaml
```

This would perform the following steps

Create a persistent volume called nexus-pv-volume with a path to /kubevolumes/nexus_data. This would ensure that the nexus-data is persisted on disk even if the nexus container goes down. The disk is replicated across all the nodes so the container can be scheduled to any of the nodes in the cluster

Create a persistent volume claim called nexus-pv-claim which binds with nexus-pv-volume

Create the nexus deployment which contains a reference to the official nexus container provided by sonatype and the /nexus-data volume mounted to nexus-pv-claim.

Create a cluster IP service to expose the Nexus UI and docker ports to the kubernetes cluster

Create an ingress service to expose the Nexus UI and Docker ports to the outside world on nexus.example.com and docker.example.com on port 80.
