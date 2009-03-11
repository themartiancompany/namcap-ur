# Maintainer: Jason Chu <jason@archlinux.org>

pkgname=namcap
pkgver=2.2
pkgrel=1
pkgdesc="A Pacman package analyzer"
arch=(i686 x86_64)
url="http://projects.archlinux.org/?p=namcap.git"
license=('GPL')
depends=('python' 'licenses')
source=(ftp://ftp.archlinux.org/other/$pkgname/$pkgname-$pkgver.tar.gz)
md5sums=('6266a017431a77a0ef50dbe0ff5719e5')

build() {
  cd $startdir/src/$pkgname-$pkgver
  ./setup.py install --root=$startdir/pkg || return 1
  ln -s namcap.py $startdir/pkg/usr/bin/namcap
}
