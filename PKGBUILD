# Contributor: Martin Tuma <tumic@tumic.wz.cz>

pkgname=hypercube
pkgver=1.6.3
pkgrel=1
pkgdesc="Graph visualizing tool"
url="http://tumic.wz.cz/hypercube"
arch=('i686' 'x86_64')
license=('GPL')
depends=('qt4')
source=('http://tumic.wz.cz/hypercube/data/hypercube-1.6.3.tar.gz')
md5sums=('07c1517468d69cf8eb71054d87242439')

build() {
  cd $srcdir/$pkgname-$pkgver
  lrelease-qt4 hypercube.pro
  qmake-qt4 hypercube.pro
  make
  strip hypercube
  make clean
  qmake-qt4 hypercube-cli.pro
  make
  strip hypercube-cli
  gzip hypercube.1
  ln -s hypercube.1.gz hypercube-cli.1.gz
}

package() {
  mkdir -p $pkgdir/usr/bin
  mkdir -p $pkgdir/usr/share/man/man1
  cp $srcdir/$pkgname-$pkgver/hypercube $pkgdir/usr/bin/
  cp $srcdir/$pkgname-$pkgver/hypercube-cli $pkgdir/usr/bin/
  cp $srcdir/$pkgname-$pkgver/hypercube.1.gz $pkgdir/usr/share/man/man1/
  cp -d $srcdir/$pkgname-$pkgver/hypercube-cli.1.gz $pkgdir/usr/share/man/man1/
}
