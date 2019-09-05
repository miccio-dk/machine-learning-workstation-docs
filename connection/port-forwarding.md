# Port forwarding

Sometimes it is necessary to access a service which is running remotely on the workstation \(e.g. tensorboard, jupyter, any kind of web service, etc\). This is what port forwarding is for!

According to [Wikipedia](https://en.wikipedia.org/wiki/Port_forwarding), port forwarding "redirects a communication request from one address and port number combination to another while the packets are traversing a network gateway".

In order to set up port forwarding for a given service or application, you need the following information:

* `REMOTE_PORT`: the port on the workstation, where the service is already running; this is usually 6006 for tensorboard, 8888 for jupyter, or can be found in the logs or documentation for the given service or application
* `LOCAL_PORT`: the port on your local machine where you want to forward the service to; any number between 8000 and 9000 should work

With this information in mind, you can type on a local terminal:

```bash
ssh -N -f -L localhost:LOCAL_PORT:localhost:REMOTE_PORT ml_workstation
```

The command will ask for your AAU mail password and quit silently, but it will still be running in the background.

In order to use the remote service locally, just point your browser to `localhost:LOCAL_PORT` and your service or application should appear.

You can have multiple port forwardings active at a given time, and they will all act independently. Just make sure to use different local ports for different remote services.

