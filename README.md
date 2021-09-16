# Easy Podman
The goal of this project is an example of how you can use Vagrant to launch a VM that can build and run a container for you.  This is useful if you cannot install Docker or Podman locally on your machine.

This demo has a python application serving a static html.  You could easily replace the python app with any other application (eg. Java, Ruby, .Net, Golang, etc.) as it's just a container (as defined in the `app/Dockerfile`).


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


## Testing
We can spin up an AWS Windows EC2 instance to test this script.

1.  `cd terraform`
2.  `terraform init`
3.  Verify terraform information, like keys and region
4.  `terraform apply`

It will take roughly 15 minutes.  Next, to connect to the instance, see the [sample documentation](https://github.com/ravsau/aws-labs/blob/master/terraform-aws/lesson2-windows-and-linux-login.MD) here on how to get the password.

Once connected, all downloads are default blocked.  To unblock, follow the [documentation here](https://aws.amazon.com/premiumsupport/knowledge-center/ec2-windows-file-download-ie/).

Next we'll use Chocolately to install all necessary prerequisites.  If you are unable to use Chocolately, just download each manually by going to the appropriate website and downloading as per their instructions.

1.  Git
2.  Virtualbox
3.  Vagrant
4.  Firefox (optional)

If you want to use Chocolately, you can run these.

1.  Install Chocolately using Powershell
```
Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))
```

2.  Install prerequisites
```
choco install firefox  # optional
choco install git
choco install virtualbox
choco install vagrant
```

3.  Restart machine after vagrant installation.  Warning will take ~15min.

4.  Configure virtualization tooling
```
```

5.  Install code
```
mkdir C:\dev
cd C:\dev
git clone https://github.com/jkeam/easy-podman.git
cd easy-podman
```

6.  Start it
```
vagrant up --provider virtualbox
```

7.  Open Firefox or other web browser to [http://localhost:8000](http://localhost:8000) and you should see the test html page being served by the built and running container
