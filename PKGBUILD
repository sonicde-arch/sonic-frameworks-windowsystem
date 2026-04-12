# Maintainer: artist for Sonic-DE

pkgname=sonic-frameworks-windowsystem
pkgver=6.25.0
pkgrel=1
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

sha256sums=('1e721c6e45ac3aed83b105397b20fbdce30954e0ef6fd390b742e1548ec0f8d0')
