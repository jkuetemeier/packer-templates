# Packer Templates for building images

This templates are actually used to build CentOS VAGRANT images. More to come soon.

## How to build an image

### Install packer

This describes how to install packer on OS X - for more informations to install it on other operating systems please refer to the original docs.

#### Install from source (what I prefer)

Go to https://www.packer.io/downloads.html and find your installation package and download it.

    mkdir -p ~/projects/packer
    cd ~/projects/packer
    curl -O https://releases.hashicorp.com/packer/0.8.6/packer_0.8.6_darwin_amd64.zip

    unzip packer_0.8.6_darwin_amd64.zip

This unzips all necessary binary files in the <code>projects/packer</code> directory. Just add this to your path - add this to your shell start script.

    export PATH=~/projects/packer:$PATH

#### Install with homebrew

    brew update
    brew install packer


    packer build -only=virtualbox-iso template.json
