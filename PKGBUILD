# Maintainer: robertfoster
# Contributor: Andy Weidenbaum <archbaum@gmail.com>

pkgbase=python-base58
pkgname=("$pkgbase" "${pkgbase/-/2-}")
pkgver=0.2.5
pkgrel=1
pkgdesc="Bitcoin-compatible Base58 and Base58Check implementation"
arch=('any')
depends=('python' 'python2')
makedepends=('python-setuptools')
url="https://github.com/keis/base58"
license=('MIT')
options=(!emptydirs)
source=("https://github.com/keis/base58/archive/v$pkgver.tar.gz")

package_python-base58() {
	depends=('python')

	cd ${pkgbase##python-}-$pkgver

	python setup.py install --root="$pkgdir" --optimize=1
	install -Dm644 COPYING "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}

package_python2-base58() {
	depends=('python2')

	cd ${pkgbase##python-}-$pkgver

	python2 setup.py install --root="$pkgdir" --optimize=1
	install -Dm644 COPYING "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}

md5sums=('ab8292c222d99a542c56ae910bdfd503')
