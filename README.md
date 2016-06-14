# veq

Stupid wrapper around `vim` and `entr` to create something similar to Burp
Repeater.

[![asciicast](https://asciinema.org/a/d22yh6b6nnef6fxj5l8af61af.png)](https://asciinema.org/a/d22yh6b6nnef6fxj5l8af61af)

## Usage

```bash
$ git clone --depth 1 https://github.com/0x6c7862/veq
$ ./veq/veq www.google.com
```

The `-f` flag takes a filename. If the file is a raw request then it will be
used verbatim, otherwise it will be used as the body of a `POST` request. In
the first case, `{{ host }}` will be replaced with the target's hostname.

## Installation

### Typical

```bash
for f in veq veq-client; do sudo cp "${f}" /usr/local/bin; done
```

`veq` depends on [`entr`](http://entrproject.org/). See website for details on
installation.

### Custom

`veq` will fall back to using `veq-client` from your `PATH`, but an alternative
client can be used via the `-c` flag. To write an alternative client, create a
binary that can be called in the following manner:

```bash
$CLIENT $VIM_SESSION $TARGET $REQUEST_FILENAME $RESPONSE_FILENAME
```

The client is responsible for making the request and updating the `vim` server
with the response. See `veq-client` for details.

## Contributing

### Bug Reports & Feature Requests

Please use the [issue tracker](https://github.com/0x6c7862/veq/issues) to report any bugs or file feature requests.

### Developing

Pull requests are welcome!

### License

This is free and unencumbered software released into the public domain.

Anyone is free to copy, modify, publish, use, compile, sell, or
distribute this software, either in source code form or as a compiled
binary, for any purpose, commercial or non-commercial, and by any
means.

In jurisdictions that recognize copyright laws, the author or authors
of this software dedicate any and all copyright interest in the
software to the public domain. We make this dedication for the benefit
of the public at large and to the detriment of our heirs and
successors. We intend this dedication to be an overt act of
relinquishment in perpetuity of all present and future rights to this
software under copyright law.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS BE LIABLE FOR ANY CLAIM, DAMAGES OR
OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE,
ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR
OTHER DEALINGS IN THE SOFTWARE.

For more information, please refer to <http://unlicense.org/>
