!nstant-markdown-d
================
instant-markdown-d is a small Node.js server that enables instant compilation and previewing of Markup files. A plugin can easily be written for any text editor to interface with it. One currently exists for VIm: https://github.com/ahmadposten/vim-instant-markdown

Installation
------------
- `[sudo] npm -g install instant-markdown-previewer`

REST API
--------
| Action                   | HTTP Method   | Request URL                 | Request Body                          |
| ---------------------    | ------------- | --------------------------- | --------------------                  |
| Start a new session      | POST          | http://localhost:\<port\>   | bufferid`<separator>`markdown content |
| Refresh Markdown on page | PUT           | http://localhost:\<port\>   | bufferid`<separator>`markdown content |
| Close Webpage            | DELETE        | http://localhost:\<port\>   |                                       |


By default, `<port>` is 8090

Environment variables
---------------------

* `INSTANT_MARKDOWN_OPEN_TO_THE_WORLD=1` - by default, the server only listens
  on localhost. To make the server available to others in your network, set this
  environment variable to a non-empty value. Only use this setting on trusted
  networks!

* `INSTANT_MARKDOWN_ALLOW_UNSAFE_CONTENT=1` - by default, scripts are blocked.
  Use this preference to allow scripts.

* `INSTANT_MARKDOWN_BLOCK_EXTERNAL=1` - by default, external resources such as
  images, stylesheets, frames and plugins are *allowed*. Use this setting to
  *block* such external content.
* `DEFAULT_OPEN_COMMAND=xdg-open` - by default it uses open or xdg-open to start a browser session however you can set this variable to whataver command you choose. then you can for example set the browser of choice by setting this variable to it's executable.
