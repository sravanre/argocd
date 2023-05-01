
## To setup ArgoCD environment

Run the following commands on your kubernetes cluster. 

```bash
kubectl create namespace argocd
```
If you are running on the cloud use this 
```bash
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```
If you are running on the local setup of kubernetes ,`minikube` `rancher-desktop` `docker-desktop` `lxc-setup`use this 
```bash
kubectl apply -n argocd -f https://raw.githubusercontent.com/sravanre/argocd/main/argocd.yaml
```
To retrive the password of the UI ( username `admin`)
```
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d; echo
```
## Deployment

To deploy this project run the following on the working ArgoCD 
cloned folder. 

```bash
git checkout feature/nginx/v3
  
```
Create a new application on the argo cd , with the git url pointing to this folder # argocd
