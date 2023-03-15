# IMMICH CLI

CLI utilities to help with some operations with the Immich app

# Features

- Upload assets (videos/images) from a directory to IMMICH server

## Supported file type

### Image

- heif
- heic
- jpeg
- png
- jpg
- gif
- heic
- heif
- dng
- x-adobe-dng
- webp
- tiff
- nef

### Video

- mp4
- webm
- quicktime
- x-msvideo
- 3gpp

# Getting Started

### Install from NPM

1 - Install from NPM repository

```
npm i -g immich
```

2 - Run

Specify user's credential, Immich's server address and port and the directory you would like to upload videos/photos from.

```
immich upload --key HFEJ38DNSDUEG --server http://192.168.1.216:2283/api file1.jpg file2.jpg
```

By default, subfolders are not included. To upload a directory including subfolder, use the --recursive option:

```
immich upload --key HFEJ38DNSDUEG --server http://192.168.1.216:2283/api --recursive directory/
```

---

### Options

| Option           | Description                                                         |
| ---------------- | ------------------------------------------------------------------- |
| --yes / -y       | Assume yes on all interactive prompts                               |
| --recursive / -r | Include subfolders                                                  |
| --delete / -da   | Delete local assets after upload                                    |
| --key / -k       | User's API key                                                      |
| --server / -s    | Immich's server address                                             |
| --threads / -t   | Number of threads to use (Default 5)                                |
| --album/ -al     | Create albums for assets based on the parent folder or a given name |

### Deprecated options

| Option           | Description                                                         |
| ---------------- | ------------------------------------------------------------------- |
| --directory / -d | Directory to upload from (including subfolders)                     |

### Run via Docker

Be aware that as this runs inside a container, you need to mount the folder from which you want to import into 
the container. The below command uses `$(pwd)` to mount the folder you are currently in.

```
docker run -it --rm -v "$(pwd)":/import ghcr.io/immich-app/immich-cli:latest upload --key HFEJ38DNSDUEG --server http://192.168.1.216:2283/api file.jpg
```

Optionally, you can create an alias:

```
alias immich="docker run -it --rm -v '$(pwd)':/import ghcr.io/immich-app/immich-cli:latest"
immich upload --key HFEJ38DNSDUEG --server http://192.168.1.216:2283/api file.jpg
```

### Install from source

1 - Clone Repository

```
git clone https://github.com/immich-app/CLI
```

2 - Install dependencies

```
npm install
```

3 - Run

```
npm run build
```

4 - Run

```
node bin/index.js upload --key HFEJ38DNSDUEG --server http://192.168.1.216:2283/api --recursive your/asset/directory
```
