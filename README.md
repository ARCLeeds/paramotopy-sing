[![https://www.singularity-hub.org/static/img/hosted-singularity--hub-%23e32929.svg](https://www.singularity-hub.org/static/img/hosted-singularity--hub-%23e32929.svg)](https://singularity-hub.org/collections/5021)
# Bertini and Paramotopy in a container

A singularity build script for creating a simple Ubuntu 18 container with [Bertini](https://www3.nd.edu/~sommese/bertini/) and [paramotopy](http://www.paramotopy.com/) built inside.

## Usage

```bash
$  singularity pull --name shub://ARCLeeds/paramotopy-sing

$ ls
paramotopy-sing.sif

# directly call paramotopy executeable from container and mount a specific directory as container HOME
$ singularity run -H /path/to/file paramotopy-sing.sif paramotopy file
```