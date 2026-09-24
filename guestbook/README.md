# Guestbook (Kargo lab)

Kustomize layout used by the Kind/Argo/Skupper/Kargo lab.

## Layout

- `base/` — shared Deployment and Service (`gcr.io/google-samples/gb-frontend`)
- `stages/test|uat|prod/` — stage overlays (replica counts)

## Stage branches

Kargo owns these branches and writes rendered manifests to each:

- `stage/test`
- `stage/uat`
- `stage/prod`

Source-of-truth for overlays lives on branch `kargo-guestbook`. Argo CD
Applications sync from the stage branches (path `.`). Do not hand-edit
stage branches; promote through Kargo instead.
