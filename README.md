Daplie is Taking Back the Internet!
--------------

[![](https://daplie.github.com/igg/images/ad-developer-rpi-white-890x275.jpg?v2)](https://daplie.com/preorder/)

Stop serving the empire and join the rebel alliance!

* [Invest in Daplie on Wefunder](https://daplie.com/invest/)
* [Pre-order Cloud](https://daplie.com/preorder/), The World's First Home Server for Everyone

You Got ServeD!
===

`served` is a stand-alane command-line webserver

Think `python -m SimpleHTTPServer 3000`,
but it can also handle streaming media (via `Content-Range` header)
and accepts file uploads (very safely, see below).

Installation
===

    npm install -g served

Usage
===

    served [port] [/path/to/serve] # defaults to 3000 and the current directory

example:

    cd ~/Downloads
    served 5555

Note: If `/path/to/serve` can be loaded as a connect module with `require()`, it will be. For example:

    served 5555 /path/to/myapp.js

**Note**: Due to connectjs' security policy, you may not use relative paths to parent directories `../`!
Use either absolute or child-relative paths.

Receiving Files
---

Files will NOT be overwritten.

Files will be received to the filename they were posted as.

    cd /tmp
    served 5555 &

    cd ~/
    echo 'Hello Test World!' > hello-test.txt
    curl http://localhost:5555/ignored-path/hello.txt \
      -X POST \
      --data-binary @hello-test.txt

    cat /tmp/hello.txt
    > Hello Test World!

License
===

Copyright (c) 2011 AJ ONeal under the MIT and Apachev2 Licenses.

See LICENSE.MIT
