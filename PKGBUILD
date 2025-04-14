# Maintainer: Bernhard Beschow <shentey at gmail dot com>

pkgname=qtcreator-plugin-qodeassist
pkgver=0.5.7
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
sha256sums=('a2f24c20ce356e2873cbb2b815503aa1b3a0bb19d5cfe883e70e68e5435be415')

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
