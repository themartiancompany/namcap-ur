# Maintainer: Hugo Doria <hugo@archlinux.org>

pkgname=namcap
pkgver=2.6
pkgrel=1
pkgdesc="A Pacman package analyzer"
arch=('any')
url="http://projects.archlinux.org/namcap.git/"
license=('GPL')
depends=('python>=2.6' 'licenses')
source=(ftp://ftp.archlinux.org/other/$pkgname/${pkgname}-${pkgver}.tar.gz)
md5sums=('4ea759bf0793ceb8342953f7520dc643')
sha256sums=('4d69ad723e7d0e9054c0031fec7f1586ccaf42f08bbb96308a93baae10d8e19d')

build() {
  cd ${srcdir}/${pkgname}-${pkgver}
  ./setup.py install --root=${pkgdir} || return 1
}
