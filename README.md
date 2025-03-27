# Podman and DNS

## Usage

```bash
sudo sysctl net.ipv4.ip_unprivileged_port_start=80
```

```bash
podman kube play https://raw.githubusercontent.com/rgaiacs/podman-dns/refs/heads/main/play.yml
```