# Mantainer: Franco Tortoriello

pkgname=munt-git
pkgdesc="Software synthesiser emulating pre-GM MIDI devices, such as the Roland MT-32"
pkgver=1.3.0_26
pkgrel=2
arch=(i686 x86_64)
url="http://munt.sourceforge.net"
license=(LGPL2.1)
depends=(qt4)
makedepends=(git cmake)
options=(staticlibs)
source=(git+https://github.com/munt/munt.git)
md5sums=(SKIP)

pkgver() {
  cd "$srcdir/munt"
  git describe --always |cut -d- -f1,2 |sed -e 's/munt_//g' -e 's/_/./g' -e 's/-/_/g'
}

build() {
  cd "$srcdir/munt"
  cmake -DCMAKE_INSTALL_PREFIX=/usr .
  make
}

package() {
  cd "$srcdir/munt"
  make DESTDIR="$pkgdir" install
}

