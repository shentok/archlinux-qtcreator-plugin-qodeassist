# Maintainer: Bernhard Beschow <shentey at gmail dot com>

pkgname=qtcreator-plugin-qodeassist
pkgver=0.5.9
pkgrel=1
pkgdesc="AI-powered coding assistant plugin for Qt Creator"
groups=('qt')
arch=('x86_64')
url="https://github.com/Palm1r/QodeAssist"
license=('GPL-3.0-only')
depends=(
    'qtcreator>=16.0.0' 'qtcreator<17.0.0'
)
makedepends=(
    'cmake'
    'qtcreator-devel>=16.0.0' 'qtcreator-devel<17.0.0'
)
optdepends=(
    'ollama'
)
source=("$pkgname-$pkgver.tar.gzr::${url}/archive/v$pkgver.tar.gz")
sha256sums=('f12e6ad89c63ffbc78646ab838a621ec59e07689b9603dd13f1f826ef85a5244')

build() {
    cmake \
        -S "$srcdir/QodeAssist-$pkgver" -B build \
        -DCMAKE_BUILD_TYPE='Release' \
        -DCMAKE_INSTALL_PREFIX='/usr' \
        -DCMAKE_PREFIX_PATH="/usr/lib/cmake/Qt6" \
        -Wno-dev
    cmake --build build
}

package() {
    DESTDIR="$pkgdir" cmake --install build
}
