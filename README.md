# istio-proxy-demo
Check Source IP and Destination IP

## Setup

Enable istio injection in default namespace

```bash
kubectl label namespace default istio-injection=enabled
```

Deploy demo-app(nginx) to respond with request info.

```bash
kubectl deploy -f ./demo-app.yml
```

Deploy a client pod to send a request to demo-app

```bash
kubectl run tmp-shell --rm -i --tty --image nicolaka/netshoot -- /bin/bash
```

Send a request to demo-app

```text
bash-5.1# curl demo-app
Hostname: demo-app-87ccc8688-mq89x
User:
Protocol: HTTP/1.1
Method: GET
Path: /
Server: 127.0.0.1
Http_host: demo-app
user_agent: curl/7.75.0
Remote IP: 127.0.0.1
```