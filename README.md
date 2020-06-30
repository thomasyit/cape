# Welcome to CAPE
<p align="center" style="background-color:#23327c">
  <img src="https://raw.githubusercontent.com/cape-sh/cape/master/assets/logo.png" height="125px" width="200px"/>
</p>

**About**

Organizations struggle to manage their Kubernetes clusters at a level expected by various stakeholders; they are debilitated by a lack of resources, expertise and tools. Organizations need to overcome these obstacles and become Kubernetes-ready. CAPE will provide organizations with the tooling and ability to perform:

- Disaster Recovery
  - Utilize Velero, an open source Kubernetes tool for backup & restore
  - Perform single scheduled backup & restore
  - Perform multi-cluster & multi-cloud backup & restore
- Multi-cluster application deployment
- Multi-cluster DNS and ingress

CAPE enables you to manage Kubernetes clusters on day one without specialized knowledge or proprietary API/CLI experience.

---

**Find out more about CAPE:**

[![](http://img.youtube.com/vi/4KJt8NXTO8E/0.jpg)](http://www.youtube.com/watch?v=4KJt8NXTO8E "Biqmind Cape")


---

## Try CAPE SAAS for FREE

<hr /> 

## Installing CAPE

### Downloading a binary from GitHub Releases 

#### Start k3d local instance
Prerequisites: [docker](https://docs.docker.com/get-docker/), [k3d](https://github.com/rancher/k3d)
```sh
k3d create -n dev -p 80:80 -p 443:443 --wait=0
export KUBECONFIG="$(k3d get-kubeconfig --name='dev')"
kubectl cluster-info
````

#### Installing CAPE
> Enter the following command:
```
kubectl apply -f https://cape.sh/install/simple.yaml
```

#### Accessing CAPE UI
> Enter the following command:
```
kubectl -n cape wait --for=condition=available --timeout=600s deployment/web
#wait for completion of CAPE deployment
open http://127.0.0.1.nip.io
```
<hr />

## CAPE in Action

[![CAPE](assets/youtube-cape.png)](https://youtu.be/4KJt8NXTO8E "CAPE INTRO")


## Kubernetes Versions Compatibility

| CAPE Version | 1.18 | 1.17 | 1.16 | 1.15 | 1.14  | Supported providers|
| --------------- | ---- | ---- | ---- | ---- | ----  | -----------------|
| v1.0.0        | +    | +    | +    | +    | +        | AWS, DigitalOcean, GCE,  |



## Getting Started
Get started quickly using this [tutorial](https://docs.cape.sh/docs/simple-install)


## Getting Involved

We appreciate your feedback and active participation.

If you want to get in touch with us to discuss improvements and new
features, please [create a new issue on GitHub](https://github.com/cape-sh/cape/issues/new) or connect with us over on our
mailing list or Slack:

* [`#general` Slack channel](https://capesh.slack.com)




[1]: https://github.com/cape-sh/cape/issues/new
[2]: https://github.com/cape-sh/cape#features
[3]: https://groups.google.com/forum/#!forum/cape-sh
[4]: http://capesh.slack.io/
[5]: https://docs.cape.sh/blog/2020/06/01/Introducing-CAPE-v1.0.0

