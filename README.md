[![add-on registry](https://img.shields.io/badge/DDEV-Add--on_Registry-blue)](https://addons.ddev.com)
[![tests](https://github.com/Metadrop/ddev-selenium-video/actions/workflows/tests.yml/badge.svg?branch=main)](https://github.com/Metadrop/ddev-selenium-video/actions/workflows/tests.yml?query=branch%3Amain)
[![last commit](https://img.shields.io/github/last-commit/Metadrop/ddev-selenium-video)](https://github.com/Metadrop/ddev-selenium-video/commits)
[![release](https://img.shields.io/github/v/release/Metadrop/ddev-selenium-video)](https://github.com/Metadrop/ddev-selenium-video/releases/latest)

# DDEV Selenium Video

## Overview

This add-on integrates Selenium Video into your [DDEV](https://ddev.com/) project.

## Installation

```bash
ddev add-on get Metadrop/ddev-selenium-video
ddev restart
```

After installation, make sure to commit the `.ddev` directory to version control.

## Usage

| Command | Description |
| ------- | ----------- |
| `ddev describe` | View service status and used ports for Selenium Video |
| `ddev logs -s selenium-video` | Check Selenium Video logs |

## Advanced Customization

To change the Docker image:

```bash
ddev dotenv set .ddev/.env.selenium-video --selenium-video-docker-image="busybox:stable"
ddev add-on get Metadrop/ddev-selenium-video
ddev restart
```

Make sure to commit the `.ddev/.env.selenium-video` file to version control.

All customization options (use with caution):

| Variable | Flag | Default |
| -------- | ---- | ------- |
| `SELENIUM_VIDEO_DOCKER_IMAGE` | `--selenium-video-docker-image` | `busybox:stable` |

## Credits

**Contributed and maintained by [@Metadrop](https://github.com/Metadrop)**
