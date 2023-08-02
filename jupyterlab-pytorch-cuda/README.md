# JuypterLab PyTorch CUDA package

## What is this image
* This image runs JupyterLab service and includes support for PyTorch and CUDA support.
* This image closely follows the official PyTorch Docker image.
* Virtual machines and cloud images use the same components and configuration approach. 

## Get this image
The recommended way to get this image is to pull the prebuilt image from Docker Hub.

```
docker pull ninthkat/jupyterlab-pytorch-cuda:latest
```

To use specific version of this image, you can pull a versioned tag. You can view the list of available versions in the Docker Hub.
```
docker pull ninthkat/jupyterlab-pytorch-cuda:[TAG]
```

If you wish, you can also build the image yourself.
```
git clone https://github.com/ninthcat/containers.git
cd containers/jupyterlab-pytorch-cuda
docker build . -t YOURNAME/YOUAPP:TAG
```

## Presistent your data
You can mount a volume to the container to persist your data. For example, you can mount the current directory to the container's `/home/jovyan/work` directory.

```
docker run -v /path/to/jovyan-persistence:/home/jovyan/work --rm --name jupyterlab-pytorch-cuda -p 8888:8888 ninthkat/jupyterlab-pytorch-cuda:latest
```

## Use Nvidia GPU
For using Nvidia GPU, you need to install the NVIDIA driver and nvidia-docker on host machine. You can refer to the official documentation for more information.
```
docker run -v /path/to/jovyan-persistence:/home/jovyan/work --rm --name jupyterlab-pytorch-cuda -p 8888:8888 --gpus all ninthkat/jupyterlab-pytorch-cuda:latest
```

## Configuaration
This image is configured to run JupyterLab service on port 8888. You can change the port number by setting the environment variable `JUPYTER_PORT` to the desired port number.