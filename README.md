# Bertini and Paramotopy in a container

A singularity build script for creating a simple Ubuntu 18 container with [Bertini](https://www3.nd.edu/~sommese/bertini/) and [paramotopy](http://www.paramotopy.com/) built inside.

## Usage

```bash
$  singularity pull shub://ARCLeeds/paramotopy


$ ls
paramotopy.sif

# directly call paramotopy executeable from container
$ singularity run paramotopy.sif paramotopy
Enter the input file\'s name.       (% cancels when applicable)
: 
```