# Rig Platform Demo

This is a simple guide for getting 3 services up and running in the Rig Platform.

The 3 services can be seen here: https://github.com/BuoyantIO/emojivoto.

## Install

After the Rig CLI has been configured ([see here](https://docs.rig.dev/overview/guides/getting-started)), you can apply the
3 files as attached here:

```sh
rig project create emojivoto
rig deploy -f emojivoto-emoji.yaml
rig deploy -f emojivoto-voting.yaml
rig deploy -f emojivoto-web.yaml
```

With that, you can now access the portal on port `emojivoto-web:80` in the cluster.

## With port-forward

Run the following command (assuming the relevant Kubenetes context is activated):

```sh
kubectl port-forward svc/emojivoto-web -n emojivoto-prod 8080:80
```

And the page is now available at http://localhost:8080/
