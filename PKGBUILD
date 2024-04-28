# Maintainer: Miodrag Tokić

pkgname=python-sqlglot
pkgver=23.11.2
pkgrel=1
pkgdesc='An easily customizable SQL parser and transpiler'
arch=('any')
url='https://github.com/tobymao/sqlglot'
license=('MIT')
depends=('python')
makedepends=('python-setuptools')
options=(!emptydirs)
source=("$pkgname-$pkgver.tar.gz::https://github.com/tobymao/sqlglot/archive/v${pkgver}.tar.gz")
sha256sums=('962c4a75f2cf267395a164d08e558ad0c5ce71ca89aa53ff885dfb726fd3958d')

build() {
    cd "$srcdir/sqlglot-${pkgver}"
    python setup.py build
}

package() {
    cd "$srcdir/sqlglot-${pkgver}"
    install -D -m 644 LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
    python setup.py install --root="$pkgdir" --optimize=1
}
