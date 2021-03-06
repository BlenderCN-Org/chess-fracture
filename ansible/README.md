# Server setup
```
virtualenv venv
. ./venv/bin/activate
pip install -r requirements.txt
```

```
cp inventory_sample.yml inventory.yml
```
Edit `inventory.yml` so the host `chessfracture` resolves to a CentOS 7 server (minimal installation)

# Client setup
visudo

```
ansible ALL=(ALL)       NOPASSWD:ALL
Defaults:ansible !requiretty
```

```
ssh-copy-id ...
```

To speedup the initial setup, you can also:
```
/home/
├── ansible
└── chessfracture
    ├── blender-2.79b-linux-glibc219-x86_64
    └── blender-2.79b-linux-glibc219-x86_64.tar.bz2
```

# PROD usage
```
ansible-playbook setup.yml
```

# DEV usage
```
ansible-playbook setup.yml --extra-vars "certbot_staging="
```

## URLs
Main site
https://chessfracture.net

Prometheus
http://chessfracture.net:9090

Grafana
http://chessfracture.net:3000

