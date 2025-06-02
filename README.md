[![add-on registry](https://img.shields.io/badge/DDEV-Add--on_Registry-blue)](https://addons.ddev.com)
[![tests](https://github.com/Metadrop/ddev-selenium-video/actions/workflows/tests.yml/badge.svg?branch=main)](https://github.com/Metadrop/ddev-selenium-video/actions/workflows/tests.yml?query=branch%3Amain)
[![last commit](https://img.shields.io/github/last-commit/Metadrop/ddev-selenium-video)](https://github.com/Metadrop/ddev-selenium-video/commits)
[![release](https://img.shields.io/github/v/release/Metadrop/ddev-selenium-video)](https://github.com/Metadrop/ddev-selenium-video/releases/latest)

# DDEV Selenium Video

## Overview

This add-on integrates Selenium Video into your [DDEV](https://ddev.com/) project.

## Requirements
- [DDEV Aljibe] (https://www.github.com/metadrop/ddev-aljibe)
- [DDEV selenium] (https://www.github.com/metadrop/ddev-selenium)

## Installation

```bash
ddev add-on get Metadrop/ddev-selenium-video
```

After installation, make sure to commit the `.ddev` directory to version control.

## Usage

| Command                       | Description                            |
|-------------------------------|----------------------------------------|
| `ddev behat-video <env>`      | Run behat tests with recodings enabled |


## Recommended behat.yml Configurations
We recommend the use of https://github.com/Metadrop/behat-contexts to add steps and scenario info to the vídeos using VideoRecordingContext:
```
- Metadrop\Behat\Context\VideoRecordingContext:
    parameters:
        - Metadrop\Behat\Context\VideoRecordingContext:
            parameters:
              enabled: true
              show_test_info_screen: true
              show_test_info_screen_time: 2000
              show_green_screen: false
              show_green_screen_time: 1000
              show_step_info_bubble: true
              show_step_info_bubble_time: 2000
              show_error_info_bubble: true
              show_error_info_bubble_time: 2000
```


We advise implementing the following configurations within your **behat.yml** file. These should always be tailored to your specific requisites:
If you use NuvoleWeb\Drupal\DrupalExtension\Context\ResponsiveContext set the correct screen size for your devices:
```
  - NuvoleWeb\Drupal\DrupalExtension\Context\ResponsiveContext:
      devices:
        laptop: 1200x800
        desktop: 1920x1080
        mobile_portrait: 370x650
        mobile_landscape: 650x370
        tablet_portrait: 800x1024
        tablet_landscape: 1024x768
```

and adjust the Selenium2 config on Drupal\MinkExtension:
```
      javascript_session: selenium2
      selenium2:
        wd_host: http://hub:4444/wd/hub
        capabilities:
          browser: "chrome"
          extra_capabilities:
            chromeOptions:
              w3c: false
              args:
                - '--start-maximized'
                - '--disable-web-security'
                - '--ignore-certificate-errors'
```

## Credits

**Contributed and maintained by [@Metadrop](https://github.com/Metadrop)**
