# Maintainer: Hugo Doria <hugo@archlinux.org>

pkgname=namcap
pkgver=2.8
pkgrel=1
pkgdesc="A Pacman package analyzer"
arch=('any')
url="http://projects.archlinux.org/namcap.git/"
license=('GPL')
depends=('python2' 'licenses')
makedepends=('python2-distribute')
source=(ftp://ftp.archlinux.org/other/$pkgname/${pkgname}-${pkgver}.tar.gz)
md5sums=('1950f7e4ed74e97297193f534e9c4e70')

build() {
  cd ${srcdir}/${pkgname}-${pkgver}
  python2 ./setup.py install --root=${pkgdir}
}
