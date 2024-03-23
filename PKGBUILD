# SPDX-License-Identifier: AGPL-3.0
#
# Maintainer:  Pellegrino Prevete <cGVsbGVncmlub3ByZXZldGVAZ21haWwuY29tCg== | base -d>
# Maintainer:  Truocolo <truocolo@aol.com>
# Maintainer:  Rémy Oudompheng <remy@archlinux.org>
# Maintainer:  Caleb Maclennan <caleb@alerque.com>
# Contributor: Hugo Doria <hugo@archlinux.org>

_py="python"
pkgname=namcap
pkgver=3.5.2
pkgrel=1
pkgdesc='A Pacman package analyzer'
arch=(
  any
)
url="https://gitlab.archlinux.org/pacman/$pkgname"
license=(
  GPL-2.0-or-later
)
depends=(
  binutils
  elfutils
  licenses
  pkgconf
  pyalpm
  "${_py}"
  "${_py}-license-expression"
  "${_py}-pyelftools"
)
checkdepends=(
  "${_py}-pytest"
  "${_py}-six"
  systemd
)
makedepends=(
  "${_py}-"{"build","installer","wheel"}
  "${_py}-setuptools"
)
_archive="${pkgname}-${pkgver}"
source=(
  "${url}/-/releases/${pkgver}/downloads/${_archive}.tar.bz2"{,.asc}
)
sha256sums=(
  'fbd3b1f0777fe457afd3dbb1f55de8adbaeb50257492626bcffd1a3eef67d618'
  'SKIP'
)
validpgpkeys=(
  9F377DDB6D3153A48EB3EB1E63CC496475267693  # caleb@alerque.com
  CCB34EBBB9541EF3F7B366C1D4A753468A5A5B67) # alerque@archlinux.org

build() {
  cd \
    "${_archive}"
  "${_py}" \
    -m \
      build \
        -wn
}

check() {
  cd \
    "${_archive}"
  env \
    PARSE_PKGBUILD_PATH="${PWD}" \
    PATH="${PWD}/scripts:${PATH}" \
    pytest
}

package() {
  local \
    _site_packages \
    _cmd=()
  cd \
    "$_archive"
  "${_py}" \
    -m \
      installer \
    --destdir="${pkgdir}" \
    dist/*.whl
  _cmd=(
    "import site;"
    "print("
      "site.getsitepackages()[0])"
  )
  _site_packages="$( \
    "${_py}" \
      -c \
        "${_cmd[*]}")"
  mv \
    "${pkgdir}/"{"${_site_packages}/usr/share",usr}
  rmdir \
    "${pkgdir}/${_site_packages}/usr"
}

# vim:set sw=2 sts=-1 et:
