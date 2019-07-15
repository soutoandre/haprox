## Haproxy 2.0.1  compilied for Centos 7

### Install


yum install -y epel-release http://www.nosuchhost.net/~cheese/fedora/packages/epel-7/x86_64/cheese-release-7-1.noarch.rpm
yum update -y
yum groupinstall "Development Tools"
yum install -y inotify-tools wget tar gzip make gcc perl pcre-devel zlib-devel iptables \
openssl openssl-devel openssl-libs systemd-devel lua-5.3.0 lua-devel-5.3.0



```
install -d "/usr/sbin"
install -m 755 haproxy  "/usr/local/sbin"
install -d "/usr/share/man"/man1
install -m 644 man/haproxy.1 "/usr/local/share/man"/man1
```

[haproxy-2.0.1]# haproxy -vv

HA-Proxy version 2.0.1 2019/06/26 - https://haproxy.org/
Build options :
  TARGET  = linux-glibc
  CPU     = generic
  CC      = gcc
  CFLAGS  = -O2 -g -fno-strict-aliasing -Wdeclaration-after-statement -fwrapv -Wno-unused-label -Wno-sign-compare -Wno-unused-parameter -Wno-old-style-declaration -Wno-ignored-qualifiers -Wno-clobbered -Wno-missing-field-initializers -Wtype-limits
  OPTIONS = USE_PCRE=1 USE_OPENSSL=1 USE_LUA=1 USE_ZLIB=1 USE_SYSTEMD=1

Feature list : +EPOLL -KQUEUE -MY_EPOLL -MY_SPLICE +NETFILTER +PCRE -PCRE_JIT -PCRE2 -PCRE2_JIT +POLL -PRIVATE_CACHE +THREAD -PTHREAD_PSHARED -REGPARM -STATIC_PCRE -STATIC_PCRE2 +TPROXY +LINUX_TPROXY +LINUX_SPLICE +LIBCRYPT +CRYPT_H -VSYSCALL +GETADDRINFO +OPENSSL +LUA +FUTEX +ACCEPT4 -MY_ACCEPT4 +ZLIB -SLZ +CPU_AFFINITY +TFO +NS +DL +RT -DEVICEATLAS -51DEGREES -WURFL +SYSTEMD -OBSOLETE_LINKER +PRCTL +THREAD_DUMP -EVPORTS

Default settings :
  bufsize = 16384, maxrewrite = 1024, maxpollevents = 200

Built with multi-threading support (MAX_THREADS=64, default=2).
Built with OpenSSL version : OpenSSL 1.0.2k-fips  26 Jan 2017
Running on OpenSSL version : OpenSSL 1.0.2k-fips  26 Jan 2017
OpenSSL library supports TLS extensions : yes
OpenSSL library supports SNI : yes
OpenSSL library supports : SSLv3 TLSv1.0 TLSv1.1 TLSv1.2
Built with Lua version : Lua 5.3.0
Built with network namespace support.
Built with transparent proxy support using: IP_TRANSPARENT IPV6_TRANSPARENT IP_FREEBIND
Built with zlib version : 1.2.7
Running on zlib version : 1.2.7
Compression algorithms supported : identity("identity"), deflate("deflate"), raw-deflate("deflate"), gzip("gzip")
Built with PCRE version : 8.32 2012-11-30
Running on PCRE version : 8.32 2012-11-30
PCRE library supports JIT : no (USE_PCRE_JIT not set)
Encrypted password support via crypt(3): yes

Available polling systems :
      epoll : pref=300,  test result OK
       poll : pref=200,  test result OK
     select : pref=150,  test result OK
Total: 3 (3 usable), will use epoll.

Available multiplexer protocols :
(protocols marked as <default> cannot be specified using 'proto' keyword)
              h2 : mode=HTX        side=FE|BE     mux=H2
              h2 : mode=HTTP       side=FE        mux=H2
       <default> : mode=HTX        side=FE|BE     mux=H1
       <default> : mode=TCP|HTTP   side=FE|BE     mux=PASS

Available services : none

Available filters :
	[SPOE] spoe
	[COMP] compression
	[CACHE] cache
	[TRACE] trace
