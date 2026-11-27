# NPD Fineract Web UI — GitOps

Image: `npd-harbor.co/npd-fineract/web-app:<sha>`  
Deploy: chart `npd-fineract` → Deployment `mifos-webapp` (Argo `fineract-app`).

## Jenkins

1. Multibranch Pipeline trỏ repo `npd-fineract-web-ui`, branch `main`, credential GitHub PAT (Vault `platform/github`).
2. Build → Kaniko push Harbor → bump `webapp.image.tag` trong `npd-fineract` `deploy/dev-k8s/values/values-images.yaml`.
3. Argo sync → UI tại https://npd-mifos.co (API https://npd-fineract.co).

```bash
# Force
BUILD_TARGET=web-app
```
