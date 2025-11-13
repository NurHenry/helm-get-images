# helm-get-images

A small and simple snippet to **extract all container images used in a Helm chart** without additional tooling.

```bash
helm template myrelease /path/to/your/chart \
  | grep -E '^\s*image:' \
  | awk '{print $2}' \
  | sort -u
