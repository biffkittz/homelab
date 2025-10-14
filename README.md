Following this tutorial to install sealed-secrets-controller via FluxCD using Helm:
https://www.digitalocean.com/community/developer-center/implementing-gitops-using-flux-cd#step-1-bootstrapping-flux-cd

To get the pub cert from sealed-secrets-controller (pub-sealed-secrets-smerdth.pem), had to do the following on the controller node itself:

* > kubectl port-forward service/sealed-secrets-controller -n flux-system 8081:8080
* > curl 127.0.0.1:8081/v1/cert.pem
  ```
  -----BEGIN CERTIFICATE-----
  ...
  ...
  -----END CERTIFICATE-----
  ```

For installing cert-manager using FluxCD/Helm:
* https://blog.nishanthkp.com/docs/devsecops/gitops/flux/deploy-cert-manager/
* cert-manager is now running in the cluster
* next step is to configure cluster issuer with letsencrypt for the *.biffkittz.com domain