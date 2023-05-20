# Maintainer: Rémy Oudompheng <remy@archlinux.org>
# Maintainer: Caleb Maclennan <caleb@alerque.com>
# Contributor: Hugo Doria <hugo@archlinux.org>

pkgname=namcap
pkgver=3.4.1
pkgrel=1
pkgdesc="A Pacman package analyzer"
arch=(any)
url='https://gitlab.archlinux.org/pacman/namcap'
license=(GPL)
depends=(binutils
         elfutils
         licenses
         pkgconf
         pyalpm
         python
         python-pyelftools)
checkdepends=(python-pytest
              python-six
              systemd)
makedepends=(python-{build,installer,wheel}
            python-setuptools)
_archive="$pkgname-$pkgver"
source=("$url/-/archive/$pkgver/$_archive.tar.bz2")
sha512sums=('f83c799475c29ef031ad4274d66df4f30e425de2423df315591a38bec7b770fb68ae675b1622020029344e66b2169a7518b5783db725bdc88dc14ee3f5ead446')

build() {
  cd "$_archive"
  python -m build -wn
}

check() {
  cd "$_archive"
  env PARSE_PKGBUILD_PATH="$PWD" PATH="$PWD/scripts:$PATH" pytest
}

package() {
  cd "$_archive"
  python -m installer -d "$pkgdir" dist/*.whl
  local site_packages="$(python -c "import site; print(site.getsitepackages()[0])")"
  mv "$pkgdir/"{"$site_packages/usr/share",usr}
  rmdir "$pkgdir/$site_packages/usr"
}
