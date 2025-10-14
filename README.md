Following this tutorial to install sealed-secrets-controller via FluxCD using Helm:
https://www.digitalocean.com/community/developer-center/implementing-gitops-using-flux-cd#step-1-bootstrapping-flux-cd

To get the pub cert from sealed-secrets-controller (pub-sealed-secrets-smerdth.pem), had to do the following on the controller node itself:

1. > kubectl port-forward service/sealed-secrets-controller -n flux-system 8081:8080
2. > curl 127.0.0.1:8081/v1/cert.pem
  ```
  -----BEGIN CERTIFICATE-----
  ...
  ...
  -----END CERTIFICATE-----
  ```
