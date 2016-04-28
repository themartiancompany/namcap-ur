# Maintainer : Rémy Oudompheng <remy@archlinux.org>
# Contributor: Hugo Doria <hugo@archlinux.org>

pkgname=namcap
pkgver=3.2.7
pkgrel=1
pkgdesc="A Pacman package analyzer"
arch=('any')
url="http://projects.archlinux.org/namcap.git/"
license=('GPL')
depends=('python' 'pyalpm>=0.5' 'licenses'
         'binutils' 'elfutils' 'python-pyelftools')
makedepends=('python-setuptools')
source=(https://sources.archlinux.org/other/${pkgname}/${pkgname}-${pkgver}.tar.gz)
sha1sums=('fa43c1f0d842a1b49bb14fe3418630e752f74c82')

prepare() {
  cd ${srcdir}/${pkgname}-${pkgver}
}

build() {
  cd ${srcdir}/${pkgname}-${pkgver}
  python setup.py build
}

check() {
  cd ${srcdir}/${pkgname}-${pkgver}
  env PARSE_PKGBUILD_PATH=${srcdir}/${pkgname}-${pkgver} \
      PATH=${srcdir}/${pkgname}-${pkgver}:$PATH \
      python setup.py test
}

package() {
  cd ${srcdir}/${pkgname}-${pkgver}
  python setup.py install --root=${pkgdir}
}

