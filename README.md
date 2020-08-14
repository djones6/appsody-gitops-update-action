# appsody-gitops-update-action

Github Action to replace all occurrences of an `app-deploy.yaml` within a GitOps repo for a named service. The existing file will be replaced with the new one, and the resulting changes pushed.

### Required inputs:
- `service-name`: The name of the service being updated.
- `github-org`: Name of Github Organization containing GitOps repo.
- `gitops-repo-name`: Name of GitOps repo within that org.

### Optional inputs:
- `branch`: The branch to update. Defaults to `master`

### Prerequisites:
- The source file `service-name/app-deploy.yaml` must exist. The contents of this file are what will be placed into the GitOps repo.
- The git configuration should already have been set up to give permission to clone and push using the `https://github.com/` scheme.  The [github-config-action](../github-config-action/) can help with this.

### Assumptions:
- The GitOps layout matches the hard-coded layout expected here:
```
/environments/*/services/<service-name>/base/config/app-deploy.yaml
```
