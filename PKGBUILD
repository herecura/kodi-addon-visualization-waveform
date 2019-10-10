# Maintainer: BlackEagle <ike.devolder@gmail.com>>

pkgname=kodi-addon-visualization-waveform
epoch=1
pkgver=3.1.0
_codename=Leia
pkgrel=1
pkgdesc="Waveform visualizer for Kodi"
arch=('x86_64')
url='https://github.com/xbmc/visualization.waveform'
license=('GPL')
groups=('kodi-addons' 'kodi-addons-visualization')
depends=('kodi' 'glu' 'glm')
makedepends=('cmake' 'kodi-dev')
source=("$pkgname-$pkgver.tar.gz::https://github.com/xbmc/visualization.waveform/archive/$pkgver-$_codename.tar.gz")
sha512sums=('a1204ed4d17e021508e969a522c2631a020b469cf24e6a2fcf5e586f8fbc2369b5499df8153cf984a15b570045e0f03fffefbb21d5a112a1ab3788bc35024d63')

build() {
    cd "visualization.waveform-$pkgver-$_codename"
    cmake \
        -DCMAKE_INSTALL_PREFIX=/usr \
        -DCMAKE_BUILD_TYPE=Release \
        -DBUILD_SHARED_LIBS=1 \
        -DUSE_LTO=1 \
        .
    make
}

package() {
    cd "visualization.waveform-$pkgver-$_codename"
    make DESTDIR="$pkgdir/" install
}

