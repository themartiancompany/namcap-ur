# Maintainer : Rémy Oudompheng <remy@archlinux.org>
# Contributor: Hugo Doria <hugo@archlinux.org>

pkgname=namcap
pkgver=3.2.2
pkgrel=1
pkgdesc="A Pacman package analyzer"
arch=('any')
url="http://projects.archlinux.org/namcap.git/"
license=('GPL')
depends=('python' 'pyalpm>=0.5' 'licenses'
         # Utilities for executable analysis.
         'binutils' 'elfutils' 'prelink')
makedepends=('python-distribute')
source=(ftp://ftp.archlinux.org/other/$pkgname/${pkgname}-${pkgver}.tar.gz)
sha1sums=('2d5a8111cbdf64a3e52ab15fe6c5ef52de515f02')

build() {
  cd ${srcdir}/${pkgname}-${pkgver}
  python setup.py build
}

check() {
  cd ${srcdir}/${pkgname}-${pkgver}
  env PARSE_PKGBUILD_PATH=${srcdir}/${pkgname}-${pkgver} \
      PATH=${srcdir}/${pkgname}-${pkgver}:$PATH \
      python setup.py test || true
}

package() {
  cd ${srcdir}/${pkgname}-${pkgver}
  python setup.py install --root=${pkgdir}
}
