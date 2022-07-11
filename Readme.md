## Build

```
sudo su
cd /tmp

sudo yum install jemalloc-devel
wget https://cache.ruby-lang.org/pub/ruby/2.5/ruby-2.5.3.tar.gz
tar xvzf ruby-2.5.3.tar.gz
cd ruby-2.5.3
LDFLAGS=-L/opt/rubies/ruby-2.5.3/lib CPPFLAGS=-I/opt/rubies/ruby-2.5.3/include ./configure --prefix=/opt/rubies/ruby-2.5.3 --with-jemalloc --disable-install-doc
make
make install
```

## Verification

Check if ruby has `-ljemalloc`

```
ruby -r rbconfig -e "puts RbConfig::CONFIG['MAINLIBS']"
```
