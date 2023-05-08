# poc-applications


argocd app create apps \
    --dest-namespace argocd \
    --dest-server https://kubernetes.default.svc \
    --repo https://github.com/ctmnz/poc-applications.git \
    --path apps
