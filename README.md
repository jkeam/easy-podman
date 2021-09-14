# Easy Podman
The goal of this project is an example of how you can use Vagrant to launch a VM that can build and run a container for you.  This is useful if you cannot install Docker or Podman locally on your machine.

## Prerequisites
1.  Vagrant 2.2.x - [Installation notes](https://www.vagrantup.com/docs/installation)

## Running
1.  Start Vagrant
```
vagrant up
```

2.  Reload and provision
```
vagrant reload --provision
```

3.  Navigate to [http://localhost:8000](http://localhost:8000)
