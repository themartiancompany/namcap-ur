# Maintainer : Rémy Oudompheng <remy@archlinux.org>
# Contributor: Hugo Doria <hugo@archlinux.org>

pkgname=namcap
pkgver=2.8.2
pkgrel=1
pkgdesc="A Pacman package analyzer"
arch=('any')
url="http://projects.archlinux.org/namcap.git/"
license=('GPL')
depends=('python2' 'licenses')
makedepends=('python2-distribute')
source=(ftp://ftp.archlinux.org/other/$pkgname/${pkgname}-${pkgver}.tar.gz)
md5sums=('67d5c3a32b1d658219d502ed4513249f')

build() {
  cd ${srcdir}/${pkgname}-${pkgver}
  python2 ./setup.py install --root=${pkgdir}
}
