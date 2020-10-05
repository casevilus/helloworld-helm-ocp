### Sample node.js hello world application packaged as a container with a Helm Chart

Try to deploy it to Kubernetes

Note: The Helm chart was created using a 'helm create hello' command, then altered to pass an image pull secret (to enable later deployments from private image registries), i.e.  

- in [/chart/hello/templates/deployment.yaml](https://github.com/casevilus/helloworld-helm/blob/master/chart/hello/templates/deployment.yaml#L22):
```
imagePullSecrets:
- name: {{ .Values.image.pullSecret }}
```

- and corresponding addition in [/chart/hello/values/yaml](https://github.com/casevilus/helloworld-helm/blob/master/chart/hello/values.yaml#L8) as a placeholder for receiving an actual pull secret during deployment automatically.
```
pullSecret: regsecret
```

