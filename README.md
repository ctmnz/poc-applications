# poc-applications


argocd app create apps \
    --dest-namespace argocd \
    --dest-server https://kubernetes.default.svc \
    --repo https://github.com/ctmnz/poc-applications.git \
    --path apps

argocd app sync apps

argocd app sync -l app.kubernetes.io/instance=apps

kubectl get secret wp-dev-wordpress -n wp-dev -o jsonpath="{.data.wordpress-password}" | base64 --decode
kubectl get secret wp-prod-wordpress -n wp-prod -o jsonpath="{.data.wordpress-password}" | base64 --decode
kubectl get secret wp-staging-wordpress -n wp-staging -o jsonpath="{.data.wordpress-password}" | base64 --decode
