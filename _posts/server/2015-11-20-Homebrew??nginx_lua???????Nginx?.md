---
layout: post
title: Homebrew??nginx_lua???????Nginx?
category: ???
tags: ???,Nginx,lua
keywords: ???,Nginx,lua
description: 
---

????Homebrew??lua_nginx????????????lua??????Nginx??Nginx??????????????????PS?????????????????????Nginx??lua_nginx???

?????????????????lua5.1?5.2????nginx

        brew install lua51 #5.1
        brew install luajit #2.03


??????????????nginx???

        cd /usr/local/Cellar/nginx/
        git clone https://github.com/simpl/ngx_devel_kit.git
        git clone https://github.com/chaoslawful/lua-nginx-module.git
        git clone https://github.com/agentzh/echo-nginx-module.git


?????????????Nginx????Homebrew??????????

        /Library/Caches/Homebrew/


??????????????Homebrew???????

        ls -lh /Library/Caches/Homebrew/
        total 20896
        drwxr-xr-x  10 root  admin   340B Nov 19 11:52 Formula
        -rw-r--r--   1 root  admin   3.8M Nov 19 10:46 lua--luarocks-2.2.1.tar.gz
        -rw-r--r--   1 root  admin   1.2K Nov 19 10:45 lua--patch-f2e77f73791c08169573658caa3c97ba8b574c870a0a165972ddfbddb948c164.patch
        -rw-r--r--   1 root  admin   245K Nov 19 10:45 lua-5.2.3.tar.gz
        -rw-r--r--   1 root  admin   3.8M Nov 19 11:26 lua51--luarocks-2.2.1.tar.gz
        -rw-r--r--   1 root  admin   216K Nov 19 11:25 lua51-5.1.5.tar.gz
        -rw-r--r--   1 root  admin   825K Nov 19 11:39 luajit-2.0.3.tar.gz
        -rw-r--r--   1 root  admin    76K Nov 19 11:52 makedepend--xorg-macros-1.18.0.tar.bz2
        -rw-r--r--   1 root  admin   289K Nov 19 11:52 makedepend--xproto-7.0.25.tar.bz2
        -rw-r--r--   1 root  admin   140K Nov 19 11:52 makedepend-1.0.5.tar.bz2
        -rw-r--r--   1 root  admin   813K Nov 19 11:53 nginx-1.8.0.tar.gz


??nginx-1.8.0.tar.gz???????Nginx?????tar????

        cd /Library/Caches/Homebrew/
        tar -zxvf nginx-1.8.0.tar.gz 
        cd nginx-1.8.0


???????????Nginx???Nginx???????????????Nginx???????????

        $ nginx -V
        
        nginx version: nginx/1.8.0
        built by clang 7.0.0 (clang-700.1.76)
        built with OpenSSL 1.0.2a 19 Mar 2015
        TLS SNI support enabled
        configure arguments: --prefix=/usr/local/Cellar/nginx/1.8.0 --with-http_ssl_module --with-pcre --with-ipv6 --sbin-path=/usr/local/Cellar/nginx/1.8.0/bin/nginx --with-cc-opt='-   I/usr/local/Cellar/pcre/8.37/include -I/usr/local/Cellar/openssl/1.0.2a-1/include' --with-ld-opt='-L/usr/local/Cellar/pcre/8.37/lib -L/usr/local/Cellar/openssl/1.0.2a-1/lib' --conf-path=/usr/local/etc/nginx/nginx.conf --pid-path=/usr/local/var/run/nginx.pid --lock-path=/usr/local/var/run/nginx.lock --http-client-body-temp-path=/usr/local/var/run/nginx/client_body_temp --http-proxy-temp-path=/usr/local/var/run/nginx/proxy_temp --http-fastcgi-temp-path=/usr/local/var/run/nginx/fastcgi_temp --http-uwsgi-temp-path=/usr/local/var/run/nginx/uwsgi_temp --http-scgi-temp-path=/usr/local/var/run/nginx/scgi_temp --http-log-path=/usr/local/var/log/nginx/access.log --error-log-path=/usr/local/var/log/nginx/error.log --with-http_gzip_static_module


??????configure arguments????????????????????nginx?1.8.0????configure?????????Nginx?????????????

        ./configure --prefix=/usr/local/Cellar/nginx/1.8.0 --with-http_ssl_module --with-pcre --with-ipv6 --sbin-path=/usr/local/Cellar/nginx/1.8.0/bin/nginx --with-cc-opt='-I/usr/local/Cellar/pcre/8.37/include -I/usr/local/Cellar/openssl/1.0.2a-1/include' --with-ld-opt='-L/usr/local/Cellar/pcre/8.37/lib -L/usr/local/Cellar/openssl/1.0.2a-1/lib' --conf-path=/usr/local/etc/nginx/nginx.conf --pid-path=/usr/local/var/run/nginx.pid --lock-path=/usr/local/var/run/nginx.lock --http-client-body-temp-path=/usr/local/var/run/nginx/client_body_temp --http-proxy-temp-path=/usr/local/var/run/nginx/proxy_temp --http-fastcgi-temp-path=/usr/local/var/run/nginx/fastcgi_temp --http-uwsgi-temp-path=/usr/local/var/run/nginx/uwsgi_temp --http-scgi-temp-path=/usr/local/var/run/nginx/scgi_temp --http-log-path=/usr/local/var/log/nginx/access.log --error-log-path=/usr/local/var/log/nginx/error.log --with-http_gzip_static_module --add-module=/usr/local/Cellar/nginx/ngx_devel_kit --add-module=/usr/local/Cellar/nginx/lua-nginx-module --add-module=/usr/local/Cellar/nginx/echo-nginx-module


??make &amp;&amp; make install

????Nginx????????

        nginx -s reload


