# Existing File Overlay

This example serves as a refrence to overlaying a specific value parameter, ontop of an exisiting `values.yaml` file.

This comes handy when templating a `values.yaml` file for Helm using YTT.

## Usage example:
Assume a given YAML values file (`values.yaml` file under root directory)
```yaml
# values.yaml file in root directory
image:
  repository: docker.io/some-irrelevant-repo/my-old-image
  tag: latest
some:
  additional_values: true
  some_more: 123
```

Triggering the function 
```bash
#@ overlay_values_file()
```

Will result in the following output:
```yaml
image:
  repository: my-image-repo/my-image-name       # overlayed
  tag: latest
  digest: sha256:123456789                      # overlayed
some:
  additional_values: true
  some_more: 123
```

## Insert into a ConfigMap
Usage example:
```yaml
---
apiVersion: v1
kind: ConfigMap
metadata:
  name: #@ "{}-app-values-app".format(data.values.workload.metadata.name)
  labels: #@ merge_labels({ "app.kubernetes.io/component": "config" })
data: 
  values.yaml: #@ overlay_values_file()
```

Will result in the kubernetes manifest generated:
```yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: my-application-name-app-values-app
  labels:
    app.kubernetes.io/component: config
data:
  values.yaml:
    image:
      repository: my-image-repo/my-image-name
      tag: latest
      digest: sha256:123456789
    some:
      additional_values: true
      some_more: 123
```
