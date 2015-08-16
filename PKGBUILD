# Maintainer ava1ar <mail(dot)avatar(at)gmail(dot)com>

pkgname=md4sum
pkgver=0.02.03
pkgrel=1
pkgdesc="Generator and checker of MD4 message digests"
arch=('i686' 'x86_64')
url="http://linux.xulin.de/c"
license=('GPL')
source=(http://linux.xulin.de/c/$pkgname-$pkgver.tar.gz)
sha1sums=('a135241129218d2aea5d483eeb7cd47bd4c14bc3')

build() {
  cd "${srcdir}"/$pkgname-$pkgver
  # patch destdir and mandir locations
  sed 's|/usr/local|$(DESTDIR)|;s|${prefix}/man|$(MANDIR)|' ./Makefile.Linux > ./Makefile
  make
}

package() {
  cd "${srcdir}"/$pkgname-$pkgver
  # create required filders
  install -d -m 755 "${pkgdir}"/usr/bin
  install -d -m 755 "${pkgdir}"/usr/share/man/man1
  make DESTDIR="${pkgdir}"/usr MANDIR="${pkgdir}"/usr/share/man install
}
