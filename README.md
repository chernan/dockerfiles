Dockerfiles
===========

Dockerfiles for miscellaneous tools.

Install Docker on MacOS X
-------------------------

Docker can't run directly on Mac but a solution exists using VirtualBox: boot2docker.
https://docs.docker.com/installation/mac/

Summary:

* Download boot2docker from https://github.com/boot2docker/osx-installer/releases
* Click to open the archive. This will start the installation process.
* When finished, just click on Boot2Docker in folder Applications to start it.
* A terminal will open, where you can type your docker commands.

Installation tested: Boot2Docker version 1.1.2



Enable folder sharing with your docker images
---------------------------------------------

See this page for a step-by-step "how to" to enable folder sharing with your images
https://github.com/boot2docker/boot2docker#folder-sharing

Just copy all suggested commands in a boot2docker terminal, as described. 



Description
-----------

### SamTools version 0.1.19

Build image

    docker build -t samtools:0.1.19 .

Run samtools through the image
(assuming that you followed the "How to" described above, and that you copied a file named `my_test_file.bam` in your shared partition (/Volumes/data on host).

    docker run -it --volumes-from my-data samtools:0.1.19 samtools index /data/my_test_file.bam

