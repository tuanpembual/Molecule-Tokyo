## Molecule
============
Using Molecule to create and testing ansible role

## Dependency
============
* virtualbox
* vagrant
* python pip
* ansible
* serverspec (verifier)

## Install molecule-dep
============
```
$ zypper in gcc python-pip python-vagrant libssl-dev libffi-dev
```

## Install Molecule using pip:
```$ pip install ansible
$ pip install docker-py
$ pip install molecule```

## How to use
`molecule --help` | to show others command  
`molecule init --role trunx --verifier serverspec` | create new rule from scratch using serverspec for verifier  
`bundle install`

## Addition setup
We using Development for testing molecule.
```ansible:
  group_vars:
    development:
      env_name: Development
```
We using openSUSE Leap, so please edit platform section in molecule.yml  
```platforms:
    - name: opensuse/openSUSE-42.3-x86_64
      box: opensuse/openSUSE-42.3-x86_64
      box_url: https://vagrantcloud.com/opensuse/boxes/openSUSE-42.3-x86_64/versions/1.0.4.20170929/providers/virtualbox.box
```

## Testing
`molecule test` | start testing

## Debug  
`molecule login`

## Implement v2
`ansible-playbook trunx/playbook.yml -i trunx/environment/staging --user ubuntu`

## Documentations
============
* https://github.com/metacloud/molecule
* https://molecule.readthedocs.io
