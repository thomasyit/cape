<p align="center" style="background-color:#23327c">
  <img src="assets/logo.png" height="250px" width="400px"/>
</p>

<p align="center">
  <a href="#features">Features</a> •
  <a href="#download">Download</a> •
  <a href="#platforms">Platforms</a> •
  <a href="#license">License</a> •
  <a href="#support">Support</a> 

</p>

# CAPE is an advanced Kubernetes multi-cluster application and data management tool

CAPE is designed with an elegant simplicity intuitive interface which simplifies your kubernetes desires.
<hr/>

<p align="center" style="background-color:#23327c">
  <img src="https://github.com/biqmind/cape-docs/blob/master/docs/assets/ReadmeDashboard.png" />
</p>

<b>Isn't she gorgeous with those sexy rounded curves of statistics that warms the cockles of your heart? Why not catch her in action.</b>

[![CAPE](assets/youtube-cape.png)](https://youtu.be/4KJt8NXTO8E "CAPE INTRO")


## Features
### Cluster
- Configuration of cluster using the Kubernetes cluster setup wizard
- Installation of Biqmind components using Biqmind CAPE user interface
    - BiqOperator — The main control plane that acts as an orchestrator connecting different clusters (host & child clusters) from different cloud service providers with Kubernetes Engine. It consist the following components - 
    - Kubernetes Backup
    - Kubernetes Restore
    - Multi-cluster Deployer
    - BiqVeleroOperator — to manage backup and restoration of cluster components (pv, pvc, deployments, etc.) to aid in disaster recovery.
- Federation enables you to federate multiple Kubernetes clusters for resources distribution, service    discovery, high availability etc across multiple clusters.

### Backup and Restore 
- Creation of backup location
- Creation of one-time cluster backup or scheduling a recurring cluster backup
- Selection of backing up either of application, data or both
- Restoration of cluster backup

### Multi-Application Deployment
- CAPE control plane to federate clusters, manage application and services​
- Use Kubernetes manifest for multi-cluster application deployment* Multi-cluster Data Management

<hr /> 

## Download

Let's walk the talk

### Start k3d local instance
Prerequisites: [docker](https://docs.docker.com/get-docker/), [k3d](https://github.com/rancher/k3d)
```sh
k3d create -n dev -p 80:80 -p 443:443 --wait=0
export KUBECONFIG="$(k3d get-kubeconfig --name='dev')"
kubectl cluster-info
````
Note: The Kubernetes cluster "dev" has been created locally

### Install CAPE
> By running the following command, I have read and agree to CAPE [privacy policy](https://biqmind.com/privacy-policy/), [terms of service](https://biqmind.com/terms-of-service/) and [end user license agreement](https://biqmind.com/end-user-license-agreement/:
```
kubectl apply -f https://cape.sh/install/simple.yaml

kubectl set env deploy/web CAPE_ACCEPT_TOS=true -n cape
```

### Access CAPE UI
> Enter the following command:
```
kubectl -n cape wait --for=condition=available --timeout=600s deployment/web
#wait for completion of CAPE deployment
open http://127.0.0.1.nip.io
```
Please wait for CAPE deployment to complete and open a new tab with the following URL: http://127.0.0.1.nip.io

<hr />

## License
CAPE will always be FREE for you but only for the first 10 nodes. If you need more than 10 nodes,contact connect@biqmind.com for a trial license key.

## Kubernetes Versions Compatibility

CAPE Version V1.0.0
- AWS
- DigitalOcean
- GCE
- Azure
- Alibaba Cloud
- Huawei Cloud
- Tencent Cloud

## Platforms
CAPE is also avaliable for the following deployment platforms:
- [Ansible](https://github.com/cape-sh/cape-ansible)
- [Helm Charts](https://github.com/biqmind/cape-saas-operator/tree/master/helm/cape)
- [Docker Hub](https://hub.docker.com/u/biqmind)
- [OperaterHub]-> Coming soon

## Support
If you like our project,
![Twitter Follow](https://img.shields.io/twitter/follow/CapeSuperhero?style=social) and 
![GitHub stars](https://img.shields.io/github/stars/cape-sh/cape?style=social)

Documentation is available [here](https://docs.cape.sh/docs/).

We welcome contributions from the community:
- Bug reports and feature requests through [Github issues](https://github.com/cape-sh/cape/issues/new)

Connect with us over on our mailing list or Slack:
- [<img src="https://img.shields.io/badge/Slack-CAPE-brightgreen">](https://capesh.slack.com)

Our Youtube channel:
- [<img src="https://img.shields.io/badge/Youtube-Biqmind-blue">](https://www.youtube.com/channel/UCSXtrXokSgbZuSz7qgu3VHw)


