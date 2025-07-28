# Maintainer: Miodrag Tokić

pkgname=python-sqlglot
pkgver=26.29.0
pkgrel=1
pkgdesc='An easily customizable SQL parser and transpiler'
arch=('any')
url='https://github.com/tobymao/sqlglot'
license=('MIT')
depends=('python')
makedepends=(
    'python-build'
    'python-installer'
    'python-wheel'
    'python-setuptools'
    'python-setuptools-scm'
)
options=(!emptydirs)
source=("$pkgname-$pkgver.tar.gz::https://github.com/tobymao/sqlglot/archive/v${pkgver}.tar.gz")
sha256sums=('4a9e06f0a034fc2b7e3248d3f511e1e8a9598cb9e161df2aba795bceaed34612')

build() {
    cd "$srcdir/sqlglot-${pkgver}"
    python -m build --wheel --no-isolation
}

package() {
    cd "$srcdir/sqlglot-${pkgver}"
    install -D -m 644 LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
    python -m installer --destdir="$pkgdir" dist/*.whl
}
