# Vendor Envoy Gateway Global

Cluster-scoped [Envoy Gateway](https://gateway.envoyproxy.io/) CRD manifests
for use in Kaptain deployments.

These CRDs are extracted from the upstream Envoy Gateway helm chart and
packaged separately so they can be installed once per cluster, independent
of namespace-scoped Envoy Gateway instances.


## Contents

Individual CRD manifests from the upstream helm chart's `crds/generated/`
directory, committed to `src/kubernetes/` with consistent naming in the form
of: `customresourcedefinition-<resource-short-name>.yaml` where short name is
the `metadata.name` prefix before `.gateway.envoyproxy.io`.


## Versioning

Version tracks upstream Envoy Gateway releases with an additional patch part
for packaging iterations. For example, `1.7.1.1` is the first packaging of
upstream `v1.7.1`, `1.7.1.2` would be a packaging improvement without an
upstream change.

The upstream version is stored in `src/config/VendorHelmRenderedVersion`.


## Upstream

- Project: https://gateway.envoyproxy.io/
- Chart: `oci://docker.io/envoyproxy/gateway-helm`
- CRDs sourced from: `crds/generated/` in the rendered chart output
