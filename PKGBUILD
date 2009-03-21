# Maintainer: Hugo Doria <hugo@archlinux.org>

pkgname=namcap
pkgver=2.2
pkgrel=2
pkgdesc="A Pacman package analyzer"
arch=('i686' 'x86_64')
url="http://projects.archlinux.org/?p=namcap.git"
license=('GPL')
depends=('python>=2.6' 'licenses')
source=(ftp://ftp.archlinux.org/other/$pkgname/${pkgname}-${pkgver}.tar.gz)
md5sums=('6266a017431a77a0ef50dbe0ff5719e5')

build() {
  cd ${srcdir}/${pkgname}-${pkgver}
  ./setup.py install --root=${pkgdir} || return 1
  ln -s namcap.py ${pkgdir}/usr/bin/namcap || return 1
}
