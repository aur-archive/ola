pkgname=ola
pkgver=0.9.5
pkgrel=1
pkgdesc="Open Lighting Architecture provides a plugin framework for distributing DMX512 control signals on Mac and Linux"
arch=(i686 x86_64)
url="https://www.openlighting.org/ola/"
license=('GPL')
groups=
provides=
depends=('libmicrohttpd' 'libusbx' 'protobuf' 'util-linux')
makedepends=('cppunit')
options=(libtool)
source=("https://github.com/OpenLightingProject/ola/releases/download/$pkgver/ola-$pkgver.tar.gz")
sha1sums=('e9b0d8e4e3e4acd696cd7a0877d72d593727a7bc')

build() {
  cd $srcdir/$pkgname-$pkgver

  ./configure --prefix=/usr --enable-http CXXFLAGS="-Wno-conversion -O"
  make || return 1
}
package() {
  cd $srcdir/$pkgname-$pkgver
  make DESTDIR=$pkgdir install || return 1
}
