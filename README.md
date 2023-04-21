## Usage

1. Use this git template when you create a new project like this
    1. public repo
    2. With all branches
2. Add your chart under the charts folder and update README.md
3. Push changes to main

How to install:

```shell
    export CHART_NAME=kafka
    helm repo add victor-common-infrastructure-charts https://victorgetz.github.io/common-infrastructure-charts/
    helm search repo $CHART_NAME
    helm install $CHART_NAME victor-common-infrastructure-charts/$CHART_NAME
```

## acceptance criteria

Any helm chart provided by iits-consulting needs to adhere to the following acceptance criteria:

* The README.md has to contain a description about the chart
* Enable custom annotations in values.yaml
* Define common labels for better separation of concerns
* Configuration changes have to cause a pod restart
* Whenever possible, sensitive information should be injected by something like
  a [mutating webhook](https://banzaicloud.com/docs/bank-vaults/mutating-webhook/) rather than be part of your chart
* Container health checks need to be present
* Use subcharts to manage dependencies whenever possible
* **Document** every values.yaml variable that is meant to be adjusted
* Specify a license
* Provide a default .helmignore
* HorizontalPodAutoscaler should be present
* Have a NOTES.txt that provides information about the deployment
