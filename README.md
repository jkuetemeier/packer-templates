## Archived

This code is just for your reference. Enjoy :-)

# Packer Templates for building images

This templates are actually used to build [CentOS](https://www.centos.org/) [VAGRANT](https://www.vagrantup.com/) images. More to come soon.

## How to build an image

### 1. Clone or update this repo

#### First time clone

    git clone --recursive git@github.com:jkuetemeier/packer-templates.git

#### How to update this repo

    git pull --recursive-submodules

Note: you need git 1.7.3 or higher for <code>--recursive-submodules</code>.

### 2. Install Packer

This describes how to install [Packer](https://www.packer.io/) on OS X. you can install Packer on many other unix like operating systems, just check the [docs](https://www.packer.io/docs/installation.html) and adopt the commands to your system.

#### Install from source

Go to https://www.packer.io/downloads.html and find your installation package and download it.

    mkdir -p ~/projects/packer
    cd ~/projects/packer
    curl -O https://releases.hashicorp.com/packer/0.8.6/packer_0.8.6_darwin_amd64.zip

    unzip packer_0.8.6_darwin_amd64.zip

This unzips all necessary binary files in the <code>projects/packer</code> directory. Just add this to your path - add this to your shell start script.

    export PATH=~/projects/packer:$PATH

#### Install with homebrew

If you have installed [Homebrew](http://brew.sh/) (The missing package manager for OS X), than you can easily install Packer with it:

    brew update
    brew install packer

### 3. Choose your Template

Choose the template you want to build an go into that directory, than just execute the build command.

    packer build -only=virtualbox-iso template.json

## Use your image in VAGRAT

    vagrant box add foo-box /path/to/vagrant-box.box
    vagrant init foo-box
    vagrant up

    vagrant ssh

## LICENSE

Copyright 2015 Jörg Kütemeier

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
 limitations under the License.

