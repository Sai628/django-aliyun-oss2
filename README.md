## Django aliyun OSS2

Django storage for [aliyun OSS](https://www.aliyun.com/product/oss)


## Features

- Django file storage for aliyun OSS
- Django static file storage for aliyun OSS
- Works in Python 3+

## Install

```bash
$ pip install django-aliyun-oss2
```

## Configurations

put the following config in your `settings.py` file:

```python
ACCESS_KEY_ID = "<your access key id>"
ACCESS_KEY_SECRET = "<your access key secret>"

# The URL of AliCloud OSS endpoint
# Refer https://www.alibabacloud.com/help/zh/doc-detail/31837.htm for OSS Region & Endpoint
END_POINT = "<your access endpoint>"
BUCKET_NAME = "<your bucket name>"  # if not exist in aliyun oss platform, it will created automatically
ALIYUN_OSS_CNAME = ""  # custom domain. optional
BUCKET_ACL_TYPE = "private"  # bucket access type. available value: private, public-read, public-read-write
ALIYUN_OSS_HTTPS = False  # optional config. determine use https or not. if not declare, this value will be False by default.

# storage media file
DEFAULT_FILE_STORAGE = 'django_aliyun_oss2.backends.AliyunMediaStorage'
# storage static file
STATICFILES_STORAGE = 'django_aliyun_oss2.backends.AliyunStaticStorage'
```

## Usage

All of the static file storage settings are available for the staticfiles storage.

```python
# The default location for your static files
STATIC_URL = '/static/'
```

Run following command to collect all sub-folder `static` of each app and upload to STATIC_URL:

```bash
$ python manage.py collectstatic
```

## License

MIT LICENSE
