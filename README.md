# restart-kubectl
A GitHub Action for restarting a Kubernetes deployment.

## How to use
You may call this action on a workflow job as such:

```yml
...
service_service:
    name: Restart Service
    runs-on: ubuntu-latest
    needs: ...
    if: ...
    steps:
        - name: Checkout
          uses: actions/checkout@v2
        - name: Deploy Staging
          uses: .zapay-pagamentos/restart-kubectl@v0
          with:
              namespace: servicename
              deployment: deploymentname
          env:
              AWS_ACCESS_KEY_ID: ${{ secrets.AWS_ACCESS_KEY_ID }}
              AWS_SECRET_ACCESS_KEY: ${{ secrets.AWS_SECRET_ACCESS_KEY }}
              KUBE_CONFIG_DATA: ${{ secrets.KUBE_CONFIG_DATA }}
...
...
