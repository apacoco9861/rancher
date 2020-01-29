# rancher
#windows 10 with docker preinstalled with kubectl
https://helm.sh/docs/intro/install/
choco install kubernetes-helm

#Apply CRDS before self-signed cert
kubectl apply -f https://raw.githubusercontent.com/jetstack/cert-manager/release-0.6/deploy/manifests/00-crds.yaml

#create ns
kubectl create ns cattle-system

#helm install
helm install rancher rancher-stable/rancher --namespace cattle-system --set hostname=rancher.my.org

#set windows hosts file 
127.0.0.1 rancher.my.org
