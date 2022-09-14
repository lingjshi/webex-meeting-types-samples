# webex-meeting-types-samples

[![published](https://static.production.devnetcloud.com/codeexchange/assets/images/devnet-published.svg)](https://testing-developer.cisco.com/codeexchange/github/repo/lingjshi/DNAC-Webex-Teams-Bot-App)  [![Run in DevEnv](https://img.shields.io/static/v1.svg?label=DevNet&message=Run%20In%20DevEnv&color=42b983)](https://testing-developer.cisco.com/codespace/?id=devenv-base-bootstrap&community=true&GITHUB_SOURCE_REPO=https://github.com/lingjshi/webex-meeting-types-samples)  [![Run in VSCode](https://img.shields.io/static/v1.svg?label=DevNet&message=Run%20In%20VSCode&color=C623D8)](https://testing-developer.cisco.com/codespace/?id=devenv-vscode-base&community=true&type=vscode&GITHUB_SOURCE_REPO=https://github.com/lingjshi/webex-meeting-types-samples)

## Overview

Demonstrates 'webpack' bundling of the Webex JavaScript SDK and [Momentum-UI](https://github.com/momentum-design/momentum-ui/) style assets for use in browser voice/video meeting application integrations.  The resulting page/bundle is served via a simple light web server as a single-page app.

Includes examples of accessing/joining various meeting types, including:

* 1:1 Webex cloud calling
* Space multi-user cloud calling
* Scheduling and joining Webex scheduling meetings
* PMR meetings
* Webex Calling/PSTN dialing
* SIP calling/meetings

Bundling framework demonstrated:

* [Webpack](https://webpack.js.org/)

>This project was built/tested using:

>* [Visual Studio Code](https://code.visualstudio.com/)
>* Ubuntu 22.04
>* Node 16.14.2

[https://developer.webex.com/docs/sdks/browser](https://developer.webex.com/docs/sdks/browser)

## Getting started

1. From a terminal, clone this repo using `git`:

    ```bash
    git clone https://github.com/CiscoDevNet/webex-meeting-types-samples.git
    ```

1. Install dependencies:

    ```bash
    cd webex-meeting-types-samples
    npm install
    ```

1. Open the project in VS Code:

    ```bash
    code .
    ```

1. In VS Code from the **Run and Debug** tab, select "Build" from the dropdown menu and click the green run button.

   Or, from the terminal:

   ```bash
   npm run build
   ```

1. To launch the webserver, use the "Launch" dropdown option from the **Run and Debug** tab.

   Or, from the terminal:

   ```bash
   npm run launch
   ```

   This should open the target page in your default browser.  If not, browse to [https://localhost:3000](https://localhost:3000)

1. You can test the sample by logging into [developer.webex.com](https://developer.webex.com) and grabbing a Personal Access Token from the [Getting Started](https://developer.webex.com/docs/api/getting-started) page, then dialing another Webex Teams user via their Webex Id/email

   >**Note:** Don't connect and dial based on the same user - that won't work!

## Hints

* There is a workaround in webpack/webpack.config.js for an [issue](https://github.com/webpack-contrib/css-loader/issues/447) Webpack has with the `fs` module that's a dependency of `webex`, but not actually needed in browser usage:

```javascript
    ...
    node: {
    fs: 'empty'
    }
    ...
```

* See `package.json` for the `browserlists` array of target browsers/versions

