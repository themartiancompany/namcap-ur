# Maintainer : Rémy Oudompheng <remy@archlinux.org>
# Contributor: Hugo Doria <hugo@archlinux.org>

pkgname=namcap
pkgver=3.0.4
pkgrel=1
pkgdesc="A Pacman package analyzer"
arch=('any')
url="http://projects.archlinux.org/namcap.git/"
license=('GPL')
depends=('python' 'licenses')
makedepends=('python-distribute')
source=(ftp://ftp.archlinux.org/other/$pkgname/${pkgname}-${pkgver}.tar.gz)
md5sums=('c643b5b74f0cb50a44a9e65b873cceb5')

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
