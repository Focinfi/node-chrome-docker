Docker ready for using [puppeteer](https://github.com/GoogleChrome/puppeteer)@0.12.0

### Softwares

1. Chrome@64
2. Node@8.4
3. Yarn@1.2.1

### Usage

```Dockerfile
From focinfi/node-chrome:latest
```

### Note

1. Set environment `PUPPETEER_SKIP_CHROMIUM_DOWNLOAD` to be `true` to skip download chromium when install puppeteer.

2. Example for launching a browser:
```js
  const puppeteer = require('puppeteer');
  (async () => {
    await browser = puppeteer.launch({
      launchOption.executablePath = 'google-chrome',
      args: [
        '--headless',
        '--hide-scrollbars',
        '--disable-gpu',
        '--remote-debugging-address=0.0.0.0',
        '--remote-debugging-port=9222',
        '--no-sandbox',
        '--disable-setuid-sandbox'
      ]
    });
  });
```