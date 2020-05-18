# Best-practice CI workflow



**Platform Admin**

```bash
kpt pkg get \
  https://source.developers.google.com/p/anthos-cli-alpha/r/onboarding-blueprints.git/blueprint-ci/ci ci
```

```bash
kpt cfg set ./ci namespace cicd 
kpt cfg set ./ci gcr_img_1 gcr.io/yuwen-cicd-demo2/ci-redisslave
kpt cfg set ./ci gcr_img_2 gcr.io/yuwen-cicd-demo2/ci-frontend
kpt cfg set ./ci src_repo  https://github.com/yuwenma/app-cicd-demo
kpt cfg set ./ci gsa-key-file kaniko-secret
```

**App Developer**

Make code changes.








# Best-Practice CD workflow 




**Platform Admin**


``` bash
kpt pkg get \
  https://source.developers.google.com/p/anthos-cli-alpha/r/onboarding-blueprints.git/blueprint-cd/cd .
```

``` bash
kpt cfg set ./cd app-name  ${APPLICATION_NAME}
kpt cfg set ./cd config-repo ${CONFIG_REPO}
kpt cfg set ./cd global-appctl-secret ${APPCTL_SECRET}
kpt cfg set ./cd ksa ${KSA_NAME}
kpt cfg set ./cd namespace ${NAMESPACE} 
```

**App Operator**

  Tag the release candidate;
  Manual push to prod







