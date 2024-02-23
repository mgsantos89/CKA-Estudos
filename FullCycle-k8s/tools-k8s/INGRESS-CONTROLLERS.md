Quick start¶
If you have Helm, you can deploy the ingress controller with the following command:

helm upgrade --install ingress-nginx ingress-nginx \
  --repo https://kubernetes.github.io/ingress-nginx \
  --namespace ingress-nginx --create-namespace
  
It will install the controller in the ingress-nginx namespace, creating that namespace if it doesn't already exist.