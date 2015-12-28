# sinister

<img src="http://i.imgur.com/K5WhqMW.png" width="25%"/>

[![](https://img.shields.io/travis/jamesqo/sinister.svg?style=flat-square)]() [![](https://img.shields.io/badge/license-BSD-blue.svg?style=flat-square)](LICENSE)

Sinister is a simple, robust installer for your shell scripts.

## Features

- Cross platform: Works on both Unix and Windows
- chmods your script so it's executable from the get-go
- Adds your script to $PATH so you can use it right away
- Install-free: Your user doesn't need to install anything (besides your script)
- Supports both per-user and machine-wide installation
- Can use Wget or cURL as its backend
- Customizable and easily overridable behavior

## Usage

Copy and paste this into your project's README:

> To install \<my awesome script>, run

```sh
sh <(curl -sSL http://git.io/sinister) -u http://url.to/your/script
```

Alternatively, if you're targeting systems that don't have Bash/cURL installed, you can replace that with this ugly mess:

```sh
wget -q -O - http://git.io/sinister | xargs -0 -i sh -c '{}' - -u http://url.to/your/script
```

Sinister is written in pure sh so it's completely fine without Bash.

### How do I control the output location of Sinister?

Specify the `-o` and `-n` options:

```sh
sinister -o output/dir -n file.name
```

### How do I install my script for just the current user?

```sh
sinister --local
```

### Can I change the mode my script is chmodded with?

Yes, you can. Pass in the `--chmod` flag:

```sh
sinister --chmod 755
```

## Examples

Here are some example projects that use Sinister:

- [bomr](https://github.com/jamesqo/bomr), a UTF-8 BOM autoremover
- [gid](https://github.com/jamesqo/gid), an automator for common Git commands

## Contributing

Contributors are welcome! Please feel free to report bugs or make pull requests to this repo.

## License

Sinister is licensed under the [BSD simplified license](LICENSE).
