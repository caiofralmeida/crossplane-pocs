kubectl delete configmap templates -n crossplane-system
kubectl apply configmap templates --from-file=templates/configmap.tmpl -n crossplane-system
