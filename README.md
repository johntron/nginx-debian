# nginx-debian

Debian package source for nginx.

Includes:
 * nginx from [nginx/nginx](https://github.com/nginx/nginx)
 * support for SPDY
 * [pagespeed](https://developers.google.com/speed/pagespeed/ngx)

See [debian/rules](debian/rules) for `./configure` options

## Building
 1. `sudo apt-get install devscripts debhelper libssl-dev libpcre3-dev zlib1g-dev`
 2. Download [_upstream_ tarball of nginx](http://nginx.org/packages/mainline/ubuntu/pool/nginx/n/nginx/nginx_1.5.2.orig.tar.gz)
 3. Ensure this tarball is named `nginx_<version>.orig.tar.gz`
 4. Extract tarball and rename extracted directory to `nginx-<version>` – make sure original tarball still exists
 5. `cd nginx-<version>`
 6. Clone this repository as: `git clone https://github.com/johntron/nginx-debian.git debian`
 7. Download and extract [ngx_pagespeed](https://github.com/pagespeed/ngx_pagespeed) to `debian/modules/ngx_pagespeed`
 8. `debuild -us -uc` - builds a source package and binary package (placed in parent directory)

## Installing
 1. `sudo dpkg -i nginx_<version>_<arch>.deb`
