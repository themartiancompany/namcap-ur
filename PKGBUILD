# Maintainer: Hugo Doria <hugo@archlinux.org>

pkgname=namcap
pkgver=2.7
pkgrel=1
pkgdesc="A Pacman package analyzer"
arch=('any')
url="http://projects.archlinux.org/namcap.git/"
license=('GPL')
depends=('python2' 'licenses')
source=(ftp://ftp.archlinux.org/other/$pkgname/${pkgname}-${pkgver}.tar.gz)
md5sums=('9b46dc3e4da5b72ed1fa584971046eb4')

build() {
  cd ${srcdir}/${pkgname}-${pkgver}
  python2 ./setup.py install --root=${pkgdir}
  sed -i -e 's/env python/env python2/' "${pkgdir}"/usr/lib/python2.7/site-packages/namcap.py
}
