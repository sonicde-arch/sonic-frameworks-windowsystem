# Maintainer: artist for Sonic-DE

pkgname=sonic-frameworks-windowsystem
pkgver=6.24.0.1
pkgrel=2
pkgdesc='Access to the windowing system for Sonic-DE'
arch=(x86_64)
url='https://github.com/Sonic-DE/sonic-frameworks-windowsystem'
license=(LGPL-2.0-only LGPL-3.0-only)
depends=(gcc-libs
         glibc
         libx11
         libxcb
         libxfixes
         qt6-base
         xcb-util-keysyms)
makedepends=(doxygen
             extra-cmake-modules
             qt6-declarative
             qt6-tools)
optdepends=('qt6-declarative: QML bindings')
conflicts=('kwindowsystem')
provides=('kwindowsystem')
replaces=('kwindowsystem')
groups=(sonicde-frameworks)
source=("$pkgname-$pkgver.tar.gz::${url}/archive/refs/tags/$pkgver.tar.gz")

build() {
  cmake -B build -S $pkgname-$pkgver \
    -DBUILD_TESTING=OFF
  cmake --build build
}

package() {
  DESTDIR="$pkgdir" cmake --install build
}

sha256sums=('e8474f23905c38e45e93ecbf2b99f1b88c6a48ea6531fcff1c5edb3703f212fb')

