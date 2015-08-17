# Maintainer: trya <tryagainprod@gmail.com>

pkgname=quazip
pkgver=0.5.1
pkgrel=2
pkgdesc="C++ wrapper for the Gilles Vollant's ZIP/UNZIP C package"
url="http://sourceforge.net/projects/quazip/"
arch=('i686' 'x86_64')
depends=('qt4')
source=("http://downloads.sourceforge.net/project/quazip/quazip/$pkgver/quazip-$pkgver.tar.gz")
license=('LGPL')
md5sums=('eec6b9b6f19654230dfcd158f29ea9d0')

build() {
  cd "$srcdir/quazip-$pkgver/quazip"
  qmake-qt4 PREFIX="$pkgdir/usr"
  make
  make staticlib
}

package() {
  cd "$srcdir/quazip-$pkgver/quazip"
  make install
  install -m644 libquazip.a "$pkgdir/usr/lib"
  install -Dm644 ../FindQuaZip.cmake "$pkgdir/usr/share/apps/cmake/modules/FindQuaZip.cmake"
}
