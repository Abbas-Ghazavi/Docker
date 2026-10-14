# 🐳 Docker Registry Mirror - ابر آروان

## روش ۱: راه‌اندازی Mirror

```bash
sudo bash -c 'cat > /etc/docker/daemon.json <<EOF
{
  "insecure-registries" : ["https://docker.arvancloud.ir"],
  "registry-mirrors": ["https://docker.arvancloud.ir"]
}
EOF'
```

```bash
docker logout
sudo systemctl restart docker
```

```bash
docker pull <ImageName>
```

## روش ۲: استفاده مستقیم

```bash
docker pull docker.arvancloud.ir/<ImageName>
```

## تست

```bash
docker info
```
