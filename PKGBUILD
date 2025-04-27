# Maintainer: Miodrag Tokić
# Contributor: Yuanji <self@gimo.me>
# Contributor: Aaron Abbott <aabmass at gmail dot com>

pkgname=mycli
pkgver=1.31.0
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
sha256sums=('d3fbf3dfc30f549f6d35a321ec83a8504f863ff29dbf789928602cc1eba44d67')

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
