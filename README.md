[![https://www.singularity-hub.org/static/img/hosted-singularity--hub-%23e32929.svg](https://www.singularity-hub.org/static/img/hosted-singularity--hub-%23e32929.svg)](https://singularity-hub.org/collections/5021)
# Bertini and Paramotopy in a container

A singularity build script for creating a simple Ubuntu 18 container with [Bertini](https://www3.nd.edu/~sommese/bertini/) and [paramotopy](http://www.paramotopy.com/) built inside.

## Usage

```bash
$  singularity pull shub://ARCLeeds/paramotopy-sing

$ ls
paramotopy-sing.sif

# directly call paramotopy executeable from container and mount a specific directory as container HOME
$ singularity run -H /path/to/file paramotopy-sing.sif paramotopy file
```

### Example usage on ARC4

To use this container with the [batch scheduling system](https://arcdocs.leeds.ac.uk/usage/batchjob.html) on Leeds HPC you will need to do the following:

Create a text file containing the number of the paramotopy commands you wish to run:

```commands.txt
5
6
0
```

Use a line similar to the one used below in your job submission script:

```bash
# rest of normal job script above here

cat commands.txt | singularity run -H $PWD --bind /var/spool:/var/spool,/local:/local paramotopy-sing_latest.sif paramotopy input 

```

In this call we `cat` the `commands.txt` and pipe this into our invocation of the paramotopy executeable within the singularity container. We bind our current direction (`-H $PWD`) as the containers home directory to give it access to the `input` file on the host system and bind a series of other host directories (`/var/spool,/local`) into the container to ensure proper pass through of batch scheduler variables.
