# Maintainer: Hugo Doria <hugo@archlinux.org>

pkgname=namcap
pkgver=2.3
pkgrel=1
pkgdesc="A Pacman package analyzer"
arch=('i686' 'x86_64')
url="http://projects.archlinux.org/?p=namcap.git"
license=('GPL')
depends=('python>=2.6' 'licenses')
source=(ftp://ftp.archlinux.org/other/$pkgname/${pkgname}-${pkgver}.tar.gz)
md5sums=('753380f95218415a4768d63c167b6a83')

build() {
  cd ${srcdir}/${pkgname}-${pkgver}
  ./setup.py install --root=${pkgdir} || return 1
  ln -s namcap.py ${pkgdir}/usr/bin/namcap || return 1
}
