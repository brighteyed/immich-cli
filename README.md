> [!warning]
> This tool is officially retired in favour of the [new CLI](https://immich.app/docs/features/command-line-interface). This repo tries to keep up with the latest changes in the Immich API, but it is not guaranteed to work. Please use the new CLI instead.
- - - -

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

# Install from source

1 - Clone Repository

```
git clone https://github.com/brighteyed/immich-cli
```

2 - Install dependencies

```
npm install
```

3 - Run

```
npm run build
```

# Getting Started

Specify user's credential, Immich's server address and port and the directory you would like to upload videos/photos from.

```
immich upload --key HFEJ38DNSDUEG --server http://192.168.1.216:2283/api -d your/target/directory
```

---

## Parameters

| Parameter        | Description                                                         |
| ---------------- | ------------------------------------------------------------------- |
| --yes / -y       | Assume yes on all interactive prompts                               |
| --delete / -da   | Delete local assets after upload                                    |
| --key / -k       | User's API key                                                      |
| --server / -s    | Immich's server address                                             |
| --directory / -d | Directory to upload from                                            |
| --threads / -t   | Number of threads to use (Default 5)                                |
| --album/ -al     | Create albums for assets based on the parent folder or a given name |
