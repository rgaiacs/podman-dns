# Podman and DNS

## Configuration

1.  Install Podman
2.  Make port 80 unprivileged

    ```bash
    sudo sysctl net.ipv4.ip_unprivileged_port_start=80
    ```
3.  Add

    ```
    127.0.0.1 lorem.ipsum
    ```
    
    to `/etc/hosts`

## Usage

```bash
podman kube play https://raw.githubusercontent.com/rgaiacs/podman-dns/refs/heads/main/play.yml
```

## Observed

### From WSL

```bash
curl http://lorem.ipsum
```

```
<!DOCTYPE html>
<html>
<head>
<title>Welcome to nginx!</title>
<style>
html { color-scheme: light dark; }
body { width: 35em; margin: 0 auto;
font-family: Tahoma, Verdana, Arial, sans-serif; }
</style>
</head>
<body>
<h1>Welcome to nginx!</h1>
<p>If you see this page, the nginx web server is successfully installed and
working. Further configuration is required.</p>

<p>For online documentation and support please refer to
<a href="http://nginx.org/">nginx.org</a>.<br/>
Commercial support is available at
<a href="http://nginx.com/">nginx.com</a>.</p>

<p><em>Thank you for using nginx.</em></p>
</body>
</html>
```

### From Windows

```cmd
curl.exe http://methodshub.gesis
```

```
curl: (7) Failed to connect to methodshub.gesis port 80 after 2044 ms: Could not connect to server
```

## Expected

`curl` from Windows and from WSL to behave the same way.