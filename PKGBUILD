# Maintainer : Rémy Oudompheng <remy@archlinux.org>
# Contributor: Hugo Doria <hugo@archlinux.org>

pkgname=namcap
pkgver=3.0.3
pkgrel=1
pkgdesc="A Pacman package analyzer"
arch=('any')
url="http://projects.archlinux.org/namcap.git/"
license=('GPL')
depends=('python' 'licenses')
makedepends=('python-distribute')
source=(ftp://ftp.archlinux.org/other/$pkgname/${pkgname}-${pkgver}.tar.gz)
md5sums=('16e13f59b156b647829fc9b16d8cc8be')

package() {
  cd ${srcdir}/${pkgname}-${pkgver}
  python ./setup.py install --root=${pkgdir}
}
