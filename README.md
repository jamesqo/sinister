# sinister

Sinister is a simple, robust installer for your shell scripts.

## Features

- Cross platform: Works on both Unix and Windows
- chmods your script so it's executable from the get-go
- Customizable and easily overridable behavior

## Usage

Copy and paste this into your project's README:

> To install [my awesome script], run

```sh
sh <(curl -sSL http://git.io/sinister) -u http://url.to/your/script
```

Alternatively, if you're targeting systems that don't have Bash/cURL installed, you can replace that with this ugly mess:

```sh
wget -q -O - http://git.io/sinister | xargs -0 -i sh -c '{}' -u http://url.to/your/script
```

Sinister is written in pure sh so it's completely fine without Bash.
