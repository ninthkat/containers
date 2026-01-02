# AGENTS

This repository hosts container images for Ninthkat. Each image lives in its own
folder and is built/published independently.

## Repository Layout
- `<image-name>/Dockerfile`: image definition.
- `<image-name>/README.md`: what the image is, how to pull/build/run.
- `<image-name>/meta.yaml`: publish metadata (image names and tags).

## Adding or Updating an Image
1. Create or update a folder named after the image.
2. Keep the Dockerfile minimal and reproducible.
   - Prefer official upstream base images.
   - Combine `apt-get update` and `apt-get install` in one layer.
   - Avoid embedding secrets or tokens.
3. Update the image README with usage examples (pull, build, run).
4. Update `meta.yaml` with the canonical image names and tags.
5. If a root image list exists in `README.md`, keep it in sync.

## Build and Verify (local)
From the image folder:
- `docker build -t <name>:<tag> .`
- Optional smoke test: `docker run --rm <name>:<tag> <command>`

## Conventions
- Use ASCII in repo docs unless the existing file already uses other characters.
- Prefer non-root users in containers when practical.
- Keep tags stable; avoid removing published tags without a migration plan.
