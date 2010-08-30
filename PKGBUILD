# Maintainer: Hugo Doria <hugo@archlinux.org>

pkgname=namcap
pkgver=2.6
pkgrel=2
pkgdesc="A Pacman package analyzer"
arch=('any')
url="http://projects.archlinux.org/namcap.git/"
license=('GPL')
depends=('python2' 'licenses')
source=(ftp://ftp.archlinux.org/other/$pkgname/${pkgname}-${pkgver}.tar.gz)
md5sums=('4ea759bf0793ceb8342953f7520dc643')
sha256sums=('4d69ad723e7d0e9054c0031fec7f1586ccaf42f08bbb96308a93baae10d8e19d')

build() {
  cd ${srcdir}/${pkgname}-${pkgver}
  python2 ./setup.py install --root=${pkgdir}
  sed -i -e 's/^python/python2/' "$pkgdir"/usr/bin/namcap
  sed -i -e 's/env python/env python2/' "${pkgdir}"/usr/lib/python2.7/site-packages/namcap.py
}
