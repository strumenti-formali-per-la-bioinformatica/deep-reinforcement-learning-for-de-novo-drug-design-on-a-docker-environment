# Deep reinforcement learning for de novo drug design: a ReLeaSe method execution on a Docker Environment

## Citation

This work runs the developed [ReLeaSE](https://github.com/isayev/ReLeaSE/) method on a Docker Environment. Further details about the method can be found in this paper: Mariya Popova, Olexandr Isayev, Alexander Tropsha. _Deep Reinforcement Learning for de-novo Drug Design_. Science Advances, 2018, Vol. 4, no. 7, eaap7885. DOI: [10.1126/sciadv.aap7885](http://dx.doi.org/10.1126/sciadv.aap7885)

## Tutorial Structure

- **[Installation](#installation)**
  - **[Prerequisites](#prerequisites)**
  - **[Repository](#repository)**
  - **[Environment Variables](#environment-variables)**
  - **[Build](#build)**
  - **[Run Docker Services](#run-docker-services)**

## Installation

### Prerequisites

- Linux OS or WSL 2 on a Windows 10 (or higher) machine. If you use WSL 2, follow the [official guide](https://docs.nvidia.com/cuda/wsl-user-guide/index.html#getting-started-with-cuda-on-wsl).
- A Modern NVIDIA GPU, compatible with [CUDA 11.3](https://developer.nvidia.com/cuda-11.3.0-download-archive).
- Docker and Docker Compose (Application containers engine). Install it from [here](https://www.docker.com).
- The Docker GPU Support enabled on the machine; check it out [here](https://docs.docker.com/compose/gpu-support/).
- The Nvidia Container Toolkit. Install it from [here](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/install-guide.html#install-guide).

Note that you do not need to install the CUDA Toolkit on the host system.

Note that you have to install the NVIDIA drivers on your system.

### Repository

Clone the repository:

```sh
$ git clone https://github.com/IvanBuccella/SF2Bio
$ cd docker
```

### Environment Variables

Set your own environment variables (the jupyter notebook port) by using the `.env-sample` file. You can just duplicate and rename it in `.env`.

### Build

Build the local environment with Docker:

```sh
$ docker-compose build
```

### Run Docker Services

```sh
$ docker-compose up
```

### Enjoy :-)

You can execute an example that uses method by visiting the `http://localhost:${HTTP_PORT}/LogP_optimization_demo.ipynb ` URL.
