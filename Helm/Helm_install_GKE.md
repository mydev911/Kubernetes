## Install helm on GKE
```
curl https://raw.githubusercontent.com/kubernetes/helm/master/scripts/get-helm-3 > get_helm.sh
chmod 700 get_helm.sh
./get_helm.sh
```

### Let's create our first Helm chart
```
helm repo add stable https://charts.helm.sh/stable
```
```
helm repo
```
```
helm repo list
```
#### TO remove this repo 
```
helm repo remove stable
```
### To search 
```
helm search repo jenkins
```
```
helm search repo tomcat
```
```
helm search repo apache
```
values
```
helm show values stable/tomcat
```
```
helm show chart request
```
### to see chart describe
```
helm show chart stable/tomcat
```
```
helm show all stable/tomcat
```







