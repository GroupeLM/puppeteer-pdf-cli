# puppeteer-pdf-cli

A command-line wrapper for generating PDF prints and PNG screenshots with [Puppeteer](https://developers.google.com/web/tools/puppeteer). Aims to be a easy replacement for the deprecated wkhtmltopdf.

## Install

```bash
npm install -g puppeteer-pdf-cli
```

## Usage

```bash
puppeteer print <url> [output]

Print an HTML file or URL to PDF

Options:
  --version                Show version number                         [boolean]
  --help                   Show help                                   [boolean]
  --sandbox                                            [boolean] [default: true]
  --timeout                                            [number] [default: 30000]
  --wait-until                                        [string] [default: "load"]
  --cookie                 Set a cookie in the form "key:value". May be repeated
                           for multiple cookies.                        [string]
  --background                                         [boolean] [default: true]
  --margin-top                                               [default: "6.25mm"]
  --margin-right                                             [default: "6.25mm"]
  --margin-bottom                                           [default: "14.11mm"]
  --margin-left                                              [default: "6.25mm"]
  --format                                                   [default: "Letter"]
  --landscape                                         [boolean] [default: false]
  --display-header-footer                             [boolean] [default: false]
  --header-template                                       [string] [default: ""]
  --footer-template                                       [string] [default: ""]
```

```bash
puppeteer screenshot <url> [output]

Take screenshot of an HTML file or URL to PNG

Options:
  --version          Show version number                               [boolean]
  --help             Show help                                         [boolean]
  --sandbox                                            [boolean] [default: true]
  --timeout                                            [number] [default: 30000]
  --wait-until                                        [string] [default: "load"]
  --cookie           Set a cookie in the form "key:value". May be repeated for
                     multiple cookies.                                  [string]
  --full-page                                          [boolean] [default: true]
  --omit-background                                   [boolean] [default: false]
  --viewport         Set viewport to a given size, e.g. 800x600         [string]
```

## Example

``` shell
echo "<h1>Hello world!</h1>" > mypage.html
puppeteer print mypage.html myprint.pdf # local file
puppeteer print https://github.com/JarvusInnovations/puppeteer-cli puppeteer-cli.pdf # url
puppeteer screenshot mypage.html myscreenshot.png # local file
puppeteer screenshot https://jarv.us myscreenshot.png # url
puppeteer screenshot https://jarv.us myscreenshot.png --viewport 300x200
```
