## VS Code Dev Container

> Basic dev container for running Instant Neural Graphics Primitives without GUI.

### Requirements

-   #### **[Docker](https://www.docker.com/get-started)**

-   #### **[VS Code](https://code.visualstudio.com/Download)**

-   #### **[Docker VS Code Extension](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-docker)**

### How to build
```sh
docker build -t containers.rc.northeastern.edu/rc/instantngp:<commit-hash-code> -f .devcontainer/Dockerfile .
```

### How to push to Harbor
```sh
docker login containers.rc.northeastern.edu 
docker push containers.rc.northeastern.edu/rc/instantngp:<commit-hash-code>
```

### How to pull container from Harbor in Discovery
```sh
module load singularity/3.5.3
singularity pull --docker-login instant-ngp.sif docker://containers.rc.northeastern.edu/rc/instant-ngp:<tag>
```

### How to run container in Discovery
```sh
singularity run --nv -B "/shared:/shared,/scratch:/scratch,/work:/work" ${SIF-FILE_DIR}/instant-ngp.sif
```

