# swift-docker

This repository publishes two base images to GHCR:

-   `ghcr.io/eriksargent/swift-vapor-runtime-base` from `./Dockerfile` (runtime image for app deploys)
-   `ghcr.io/eriksargent/swift-vapor-build-base` from `./build/Dockerfile` (build/CI image with Docker CLI + Buildx)

Both images are published with these tags on each push to `main`:

-   `latest`
-   commit SHA tag

The workflow also pushes separate BuildKit cache tags (`:buildcache`) per image to speed up rebuilds.
