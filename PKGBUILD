# Maintainer: Miodrag Tokić
# Contributor: Yuanji <self@gimo.me>
# Contributor: Aaron Abbott <aabmass at gmail dot com>

pkgname=mycli
pkgver=1.29.1
pkgrel=1
pkgdesc='A Terminal Client for MySQL with AutoCompletion and Syntax Highlighting'
arch=('any')
url='https://github.com/dbcli/mycli'
license=('BSD')
depends=(
    'python'
    'python-click'
    'python-cryptography'
    'python-pygments'
    'python-prompt_toolkit'
    'python-pymysql'
    'python-sqlparse'
    'python-sqlglot'
    'python-configobj'
    'python-cli_helpers'
    'python-pyperclip'
    'python-pyaes'
    'python-pyfzf'
)
makedepends=(
    'python-build'
    'python-installer'
    'python-wheel'
    'python-setuptools'
    'python-setuptools-scm'
)
optdepends=(
    'python-paramiko: SSH support'
)
options=(!emptydirs)
source=("$pkgname-$pkgver.tar.gz::https://github.com/dbcli/mycli/archive/v${pkgver}.tar.gz")
sha256sums=('f6ccbce80ed2b69d06ee7da58f5b79117973c9e219a9ad7ea1e2625da9f34439')

build() {
    export SETUPTOOLS_SCM_PRETEND_VERSION="$pkgver"
    cd "$srcdir/$pkgname-$pkgver"
    python -m build --wheel --no-isolation
}

package() {
    cd "$srcdir/$pkgname-$pkgver"
    install -D -m 644 LICENSE.txt "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
    python -m installer --destdir="$pkgdir" dist/*.whl
}
