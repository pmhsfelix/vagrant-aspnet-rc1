# vagrant-aspnet-rc1

Vagrant configuration for ASP.NET RC1 on Ubuntu Server

* ASP.NET RC1 installed according to the instructions in [http://docs.asp.net/en/latest/getting-started/installing-on-linux.html](http://docs.asp.net/en/latest/getting-started/installing-on-linux.html).

* Port forwarding from host:5000 to guest:5000.
    * Note that port forwarding will not work if the guest HTTP server listens on `localhost`. Change `project.json` to listen on `0.0.0.0` instead

```
"web": "Microsoft.AspNet.Server.Kestrel --server.urls http://0.0.0.0:5000"
``` 

## Usage

Ensure [Vagrant](http://www.vagrantup.com/downloads) and [VirtualBox](https://www.virtualbox.org) are installed on your host machine.

```
git clone https://github.com/pmhsfelix/vagrant-aspnet-rc1.git (or a fork url instead)
cd vagrant-aspnet-rc1
vagrant up
vagrant ssh
```

Congratulations! You have a SSH session into a Ubuntu Server with ASP.NET RC1 installed. Port `5000` on the host is mapped into port `5000` on the guest.

The `vagrant-aspnet-rc1` host folder is mounted into the `/vagrant` guest folder, so you can use this to share files between host and guest.
For instance, a ASP.NET project published to `vagrant-aspnet-rc1/published` on the host will be visible on the `/vagrant/published` guest path.
