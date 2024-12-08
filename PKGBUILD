# SPDX-License-Identifier: AGPL-3.0
#
# Maintainer: Truocolo <truocolo@aol.com>
# Maintainer: Pellegrino Prevete (tallero) <pellegrinoprevete@gmail.com>
# Maintainer: robertfoster
# Contributor: Andy Weidenbaum <archbaum@gmail.com>
# Contributor: redfish

_py="python"
_pyver="$( \
  "${_py}" \
    -V | \
    awk \
      '{print $2}')"
_pymajver="${_pyver%.*}"
_pyminver="${_pymajver#*.}"
_pynextver="${_pymajver%.*}.$(( \
  ${_pyminver} + 1))"
_pkg="base58"
pkgname="${_py}-${_pkg}"
pkgver=2.1.1
pkgrel=1
pkgdesc="Bitcoin-compatible Base58 and Base58Check implementation"
arch=(
  'any'
)
depends=(
  "${_py}>=${_pymajver}"
  "${_py}<${_pynextver}"
)
makedepends=(
  "${_py}-setuptools"
)
_http="https://github.com"
_ns="keys"
url="${_http}/${_ns}/${_pkg}"
license=(
  'MIT'
)
options=(
  !emptydirs
)
source=(
  "${_pkg}-${pkgver}.tar.gz::${url}/archive/v${pkgver}.tar.gz"
)
sha256sums=(
  '5df25ce3b3d2f7e9d5289b2c75ba9e5291b59b1c34f4f7c90df5ae5f87fe5fb9'
)

package() {
  cd \
    "${_pkg}-${pkgver}"
  "${_py}" \
    setup.py \
      install \
        --root="${pkgdir}" \
	--optimize=1
  install \
    -Dm644 \
    "COPYING" \
    "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}
