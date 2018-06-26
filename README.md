# Helm chart for installing ace apps into the cluster

This chart will allow you to deploy your ace app into your ace cluster.
The chart will allow you to set values that match your app without adding the yaml-files to your project.

## Add the chart to your available repos

```
helm repo add evry-ace https://evry-ace.github.io/ace-app-chart/
helm repo update
```

Test it by running
```
helm inspect evry-ace/ace-app-chart
```

Create the chart distribution
```
helm package .
```

Update index.yaml file
```
helm repo index .
```

Check the chart
```
helm lint
```

## Override the default values

### Use the values.yaml

Have a look at the values.yaml in this github project.
You can download the values.yaml file and add it to your project.

Override the values you need to change for your deployment.


#### Install your application

```
helm upgrade --install <release name> --values <values file> evry-ace/ace-app-chart
```

### Set the values on the command

To override the default values you can set the value on the command directly

```
helm upgrade --install <release name> --set ingress.enabled=false evry-ace/ace-app-chart
```

