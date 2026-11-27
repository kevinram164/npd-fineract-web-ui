@Library('platform@main') _

// UI Angular → Harbor npd-fineract/web-app → bump tag trong npd-fineract GitOps → Argo fineract-app
// Expect: npm ci + ng build ~10–25 phút, Kaniko heap lớn.

platformPipeline([
  project             : 'npd-fineract-web-ui',
  harborHost          : 'npd-harbor.co',
  harborProject       : 'npd-fineract',
  gitBranch           : 'main',
  gitRepoUrl          : 'https://github.com/kevinram164/npd-fineract-web-ui.git',
  gitopsRepoUrl       : 'https://github.com/kevinram164/npd-fineract.git',
  gitopsBranch        : 'dev-k8s',
  gitopsValuesFile    : 'deploy/dev-k8s/values/values-images.yaml',
  vaultAddr           : 'http://vault.vault.svc.cluster.local:8200',
  vaultRole           : 'jenkins-kaniko',
  vaultHarborPath     : 'fineract/harbor',
  vaultGithubPath     : 'platform/github',
  kanikoSkipTlsVerify : true,
  kanikoUseCache      : false,
  kanikoMemoryRequest : '4Gi',
  kanikoMemoryLimit   : '8Gi',
  kanikoCpuRequest    : '500m',
  kanikoCpuLimit      : '4',
])
