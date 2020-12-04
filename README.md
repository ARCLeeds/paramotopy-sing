# Bertini and Paramotopy in a container

A singularity build script for creating a simple Ubuntu 18 container with [Bertini](https://www3.nd.edu/~sommese/bertini/) and [paramotopy](http://www.paramotopy.com/) built inside.

## Usage

```bash
$  singularity pull --name shub://ARCLeeds/paramotopy-sing

$ ls
paramotopy-sing.sif

# directly call paramotopy executeable from container
$ singularity run paramotopy-sing.sif paramotopy
Enter the input file's name.       (% cancels when applicable)
: 
```