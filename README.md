# UWU OrangeFox Builder
🦊 A Workflow to build OrangeFox recovery automatically

![banner](https://i.imgur.com/hdLJ3Hi.png "banner")

[![](https://img.shields.io/github/actions/workflow/status/UWU-TEAM/UWU-OrangeFox-Builder/test.yml?style=for-the-badge&color=fee4d0&logo=githubactions&logoColor=fee4d0)](https://github.com/UWU-TEAM/UWU-OrangeFox-Builder/actions/workflows/test.yml)
[![](https://img.shields.io/github/issues/UWU-TEAM/UWU-OrangeFox-Builder?style=for-the-badge&color=fee4d0&logo=files&logoColor=fee4d0)](https://github.com/UWU-TEAM/UWU-OrangeFox-Builder/issues)
[![](https://img.shields.io/github/stars/UWU-TEAM/UWU-OrangeFox-Builder?style=for-the-badge&color=fee4d0&logo=starship&logoColor=fee4d0)](https://github.com/UWU-TEAM/UWU-OrangeFox-Builder/stargazers)
[![](https://img.shields.io/github/forks/UWU-TEAM/UWU-OrangeFox-Builder?style=for-the-badge&color=fee4d0&logo=git&logoColor=fee4d0)](https://github.com/UWU-TEAM/UWU-OrangeFox-Builder/forks)
[![](https://img.shields.io/github/license/UWU-TEAM/UWU-OrangeFox-Builder?style=for-the-badge&color=fee4d0&logo=apache&logoColor=fee4d0)](https://github.com/UWU-TEAM/UWU-OrangeFox-Builder/blob/main/LICENSE)
[![](https://img.shields.io/github/v/release/UWU-TEAM/UWU-OrangeFox-Builder?style=for-the-badge&color=fee4d0&logo=github&logoColor=fee4d0)](https://github.com/UWU-TEAM/UWU-OrangeFox-Builder/releases/latest)
[![](https://img.shields.io/github/last-commit/UWU-TEAM/UWU-OrangeFox-Builder?style=for-the-badge&color=fee4d0&logo=codeigniter&logoColor=fee4d0)](https://github.com/UWU-TEAM/UWU-OrangeFox-Builder/commits/main/)

> [!WARNING]
>
> These workflows are designed only for building orangefox recovery 12.1

> [!IMPORTANT]
> This workflow is universal. You need to have a certain foundation in writing github workflows and a little knowledge of the OrangeFox device tree to use this.

## How to use?
- Find your kernel source || orf common tree || orf device tree repository and configure the workflow file according to the following example and README.md:

```yml
name: OrangeFox - Builder

on:
  workflow_dispatch:

jobs:
  build:
    name: 🦊 Building OrangeFox Recovery
    runs-on: ubuntu-latest
    env:
      GITHUB_TOKEN: ${{ secrets.GH_TOKEN }}
    permissions: write-all
    steps:
    - name: Checkout
      uses: actions/checkout@v4

    - name: OrangeFox Build
      uses: UWU-TEAM/UWU-OrangeFox-Builder@v1.0.0
      with:
        USER_NAME: 'YourName'
        USER_EMAIL: 'YourE-mail@gmail.com'
        DEVICE_TREE: 'https://github.com/UntuKemeng/ORF_device_vivo_1938'
        DEVICE_TREE_BRANCH: '12.1'
        DEVICE_PATH: 'device/vivo/1938'
        DEVICE_NAME: '1938'
        BUILD_TARGET: 'recovery'
        TG_CHAT_ID: '${{ secrets.TG_CHAT_ID }}'
        TG_TOKEN: '${{ secrets.TG_TOKEN }}'
        MAINTAINER_URL: 'https://i.ibb.co.com/8gyjXq06/maintainer.png'
        GH_RELEASE: 'true'
```

> [!NOTE]
> You do not need to fork this repository.
>
> If you just want to compile the Orangefox recovery, please do not submit PR after modification!

- Finally, run the workflow you just wrote.
## Inputs
| input               | required | description | example value |
|---------------------|----------|-------------|---------|
| USER_NAME | true | Name in GitHub Account | Your Name |
| USER_EMAIL | true | E-mail in GitHub Account | abcdefg@gmail.com |
| KERNEL_TREE | false | URL of Android kernel source code for your phone | https://github.com/username/project |
| KERNEL_BRANCH | false | Branch On Your Kernel Tree | 12.1 |
| KERNEL_PATH | false | Path On Your Kernel Directory | kernel/vivo/1938 |
| DEVICE_TREE | true | URL of Orangefox device tree in your phone | https://github.com/username/project |
| DEVICE_TREE_BRANCH | true | OrangeFox Device Tree Branch | 12.1 |
| DEVICE_PATH | true | Specify Your Device Path | device/vivo/1938 |
| DEVICE_NAME | true | Specify Your Device Codename | 1938 |
| BUILD_TARGET | true | Specify Your Build Target [boot, recovery, vendorboot] | recovery |
| COMMON_TREE | false | URL Common Tree On Your Device | https://github.com/username/project |
| COMMON_BRANCH | false | Branch On Your Common Tree | 12.1 |
| COMMON_PATH | false | Path On Your Common Directory | common/vivo/1938 |
| MAINTAINER_URL | false | Image size must be 192x192 | https://github.com/username/project |
| GH_RELEASE | true | Upload Build To Github Release | Default is [false] |
| TG_CHAT_ID | false | Telegram Chat ID (secrets) | -123456789 |
| TG_TOKEN | false | Telegram Bot Token (secrets) | 123456:12345678987654321 |
| GH_TOKEN | env | Your token on github (secrets) | gpgxxxxxxxxxxd |

## Credits
- [slimhub_actions](https://github.com/rokibhasansagar/slimhub_actions)
- [carlodandan](https://github.com/carlodandan/UWU-OrangeFox-Builder)
- [kinguser981](https://github.com/kinguser981/OrangeFox-Recovery-Builder-2024)
- [azwhikaru](https://github.com/azwhikaru/Action-OFRP-Builder)
- [dabao1955](https://github.com/dabao1955/kernel_build_action)
