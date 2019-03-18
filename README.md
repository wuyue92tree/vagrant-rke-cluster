# vagrant-rke-cluster

## Vagrantfile

[vagrant](https://www.vagrantup.com/)

```
vagrant up
```

Notice: after create vm, you should setup ssh-key yourself.

## rke-cluster.yaml

[rke download](https://rancher.com/docs/rke/v0.1.x/en/installation/#download-the-rke-binary)

```
rke up --config rke-cluster.yaml
```

## use libvirt

[libvirt](https://github.com/vagrant-libvirt/vagrant-libvirt)

Notice: install libvirt depends first.

```
vagrant plugin install vagrant-libvirt
```
