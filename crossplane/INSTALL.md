helm repo add crossplane-stable https://charts.crossplane.io/stable

helm repo update

helm install crossplane \
--namespace crossplane-system \
--create-namespace crossplane-stable/crossplane --values values.yaml --version 1.15.1

# Crossplane CLI (maybe it doesn't works for Mac OS)
curl -sL "https://raw.githubusercontent.com/crossplane/crossplane/master/install.sh" | sh

# Install k8s provider via CLI
kubectl crossplane install provider crossplanecontrib/provider-kubernetes:main

# Or install manually
kubectl -f k8s-provider.yaml apply

