# vagrant-aspnet-rc1

Vagrant configuration for ASP.NET RC1 on Ubuntu Server

* ASP.NET RC1 installed according to the instructions in [http://docs.asp.net/en/latest/getting-started/installing-on-linux.html](http://docs.asp.net/en/latest/getting-started/installing-on-linux.html).

* Port forwarding from host:5000 to guest:5000.
    * Note that port forwarding will not work if the guest HTTP server listens on `localhost`. Change `project.json` to listen on `0.0.0.0` instead

```
"web": "Microsoft.AspNet.Server.Kestrel --server.urls http://0.0.0.0:5000"
``` 
