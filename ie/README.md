helm --kubeconfig=./ie/ie-mx-kubeconfig.yaml repo add bitnami https://charts.bitnami.com/bitnami

kubectl --kubeconfig=./ie/ie-mx-kubeconfig.yaml -n grafana port-forward svc/prometheus-service 9090:9090


kubectl --kubeconfig=./ie/ie-mx-kubeconfig.yaml -n grafana exec -it prometheus-deployment-b889c4b78-gbpr4 -- /bin/sh

kubectl --kubeconfig=./ie/ie-mx-kubeconfig.yaml -n nifi exec -it nifi-deployment-794c59885d-gx4vw -- /bin/sh

kubectl --kubeconfig=./ie/ie-mx-kubeconfig.yaml get clusterroles

kubectl --kubeconfig=./ie/ie-mx-kubeconfig.yaml -n argocd patch role argocd-prod-argo-cd-server -type='json' -p='[{"op": "add", "path": "/rules/-", "value": {"apiGroups": ["*"], "resources": ["pods/exec"], "verbs": ["create"]}}]'

kubectl --kubeconfig=./ie/ie-mx-kubeconfig.yaml get cm -n argocd | grep rbac


kubectl --kubeconfig=./ie/ie-mx-kubeconfig.yaml -n argocd describe role argocd-prod-argo-cd-server
kubectl --kubeconfig=./Buendata/buendatamx-kubeconfig.yaml -n argocd describe role argocd-prod-argo-cd-server