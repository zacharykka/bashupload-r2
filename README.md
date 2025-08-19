# BashUpload-R2

English | [中文](README-zh.md)

Simple file upload service based on Cloudflare Workers and Cloudflare R2 object storage for the command line and browser.

[![Deploy to Cloudflare](https://deploy.workers.cloudflare.com/button)](https://deploy.workers.cloudflare.com/?url=https://github.com/zacharykka/bashupload)


Directly Use: [bashupload.app](https://bashupload.app)

Thanks to [bashupload.com](https://bashupload.com) and its author [@mrcrypster](https://github.com/mrcrypster) for the inspiration.

## Quick Start

```sh
# Upload with normal URL
curl bashupload.app -T file.txt

# Upload with short URL
curl bashupload.app/short -T file.txt
```

Use `alias` in bash to set quick upload

```sh
alias bashupload='curl bashupload.app -T'
alias bashuploadshort='curl bashupload.app/short -T'
bashupload file.txt        # Returns normal URL
bashuploadshort file.txt     # Returns short URL
```

To make the alias persistent, add it to your shell configuration file.

```sh
echo "alias bashupload='curl bashupload.app -T'" >> ~/.bashrc
echo "alias bashuploadshort='curl bashupload.app/short -T'" >> ~/.bashrc
source ~/.bashrc
```

## Browser Upload

- Drag & drop files or click to select files (Max 5GB)
- Direct download links
- No registration required

## Features

- Simple command-line interface
- Browser-based drag & drop upload
- No registration required
- Direct download links
- Privacy-focused: Files are automatically deleted after download
- Secure file storage with one-time download
- Supports files up to 5GB in size (self-hosting can adjust this limit)


**Privacy Notice:** For your privacy and security, files are automatically deleted from our servers immediately after they are downloaded. Each file can only be downloaded once. Make sure to save the file locally after downloading, as the link will no longer work after the first download.

## Self-Hosting to Cloudflare

Click the "Deploy to Cloudflare" button above to modify the configuration.

`MAX_UPLOAD_SIZE` is in bytes (default is 5GB), and `MAX_AGE` is in seconds (default is 1 hour). You can adjust these values as needed.

`SHORT_URL_SERVICE` is the short URL service API endpoint (default is `https://suosuo.de/short`), you can change it to your own short URL service if needed. Only support [MyUrls](https://github.com/CareyWang/MyUrls).
