# Infrakit MaaS Instance Plugin
An example of [Infrakit](https://github.com/docker/infrakit) Instance Pluging for [Canonical MaaS](https://maas.io/) node.
Purpose of this plugin is to support Bare metal deploy with Infrakit.
## Go get 
`$go get github.com/YujiOshima/infrakit-maas-plugin`

## Get start
Requires:
* MaaS Server
* API Key ( See https://maas.ubuntu.com/docs/maascli.html )
* MaaS Nodes (You need all node be `Ready` state. Register and commision manually.)
* Spec file ( example: maas-vanilla.yml

Run Infrakit group, vanilla flavor plugin.

```
$ build/infrakit-group-default
```

```
$ build/infrakit-flavor-vanilla
```

Run MaaS instance plugin.

```
$ $GOPATH/bin/infrakit-maas-plugin --apikey <MaaS API key> --url http://<MaaS server url>/MAAS 
INFO[0000] Listening at: /home/ubuntu/.infrakit/plugins/instance-maas
```
Group commit!

```
$ build/infrakit group commit $GOPATH/src/github.com/YujiOshima/infrakit-maas-plugin/maas-vanilla.yml
```

