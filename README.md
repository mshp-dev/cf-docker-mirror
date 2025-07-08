# 🐳 Docker Personal Proxy Tool / ابزاری برای راه اندازی پروکسی شخصی داکر!

![CF-Workers-docker.io](./iran-mirror-docker.png)

## English

This project is a tool for setting up a Docker image proxy on Cloudflare Workers platform.

> [!WARNING]
> Please note that setting up VPN and any kind of proxy on Cloudflare platform violates Cloudflare's terms of service.
> Please consider this issue when using and do not deploy this service on your main accounts.

### 🚀 Deployment and Implementation

- **Workers**: Deploy the contents of the `_workers.js` file in your Worker
- **Pages**: Fork this project for yourself and easily deploy by connecting your account to Cloudflare

### ⚙️ Usage Instructions [YouTube](https://www.youtube.com/)

Assume your Worker app domain is: `myapp.account.workers.dev`

#### 1. Add your Worker domain to the beginning of the image name

```shell
docker pull myapp.account.workers.dev/grafana/grafana:12.0.1
```

```shell
docker pull docker.fxxk.dedyn.io/library/nginx:stable-alpine3.19-perl
```

#### 2. Set up Docker mirror configuration

Create the `/etc/docker/daemon.json` file if it doesn't exist and set your mirror there:

```shell
sudo tee /etc/docker/daemon.json <<-'EOF'
{
  "registry-mirrors": ["https://myapp.account.workers.dev"]
}
EOF
sudo systemctl restart docker
```

---

## فارسی

این پروژه ابزاری هست برای راه اندازی پروکسی ایمیج های داکر بر بستر ورکر های کلاودفلر

> [!WARNING]
> توجه داشته باشید که راه اندازی وی پی ان و هرگونه پروکسی بر بستر کلاودفلر خلاف سیاست های استفاده از کلاودفلر هست
> لطفا در هنگام استفاده به این مسئله توجه داشته باشید و این سرویس رو روی اکانت های اصلی خود راه اندازی نکنید

### 🚀 نحوه ی استقرار و پیاده سازی

- **Workers**: محتویات فایل `_workers.js` رو توی ورکر پیاده سازی کنید
- **Pages**: پروژه رو برای خودتون فورک کنید و با اتصال اکانت به کلاودفلر به سادگی پیاده سازی کنید

### ⚙️ نحوه استفاده [YouTube](https://www.youtube.com/)

فرض کنید دامنه ی اپ شما در ورکر این باشه: `myapp.account.workers.dev`

#### 1. دامنه ی ورکر خودتون رو به ابتدای اسم ایمیج اضافه کنید

```shell
docker pull myapp.account.workers.dev/grafana/grafana:12.0.1
```

```shell
docker pull docker.fxxk.dedyn.io/library/nginx:stable-alpine3.19-perl
```

#### 2. تنظیم میرور در داکر

فایل `/etc/docker/daemon.json` رو در صورت موجود نبودن ایجاد کنید و میرور خودتون رو اونجا ست کنید:

```shell
sudo tee /etc/docker/daemon.json <<-'EOF'
{
  "registry-mirrors": ["https://myapp.account.workers.dev"]
}
EOF
sudo systemctl restart docker
```




### Original Repo -> https://github.com/cmliu/CF-Workers-docker.io