# Maintainer: Chris Harvey <chris@chrisnharvey.com>

pkgname=slingscold
pkgver=1.2.1
pkgrel=1
pkgdesc="A light, full screen application launcher"
arch=('i686' 'x86_64')
url="https://gitlab.com/chrisnharvey/slingscold"
license=('GPL3')
depends=('libunique' 'libgee06' 'gnome-menus2' 'libwnck' 'gtk2' 'cairo')
makedepends=('cmake' 'vala')
source=()
sha256sums=()

prepare() {
  ln -snf "$startdir" "$srcdir"/slingscold
  cd "$srcdir"
  rm -rf build && mkdir build
}

build() {
  cd "$srcdir"/build
  cmake ../slingscold \
    -DCMAKE_BUILD_TYPE=Release \
    -DCMAKE_INSTALL_PREFIX=/usr
  make
}

package() {
  cd "$srcdir"/build
  make DESTDIR="$pkgdir" install
}
