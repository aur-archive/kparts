# Maintainer: Andrea Scarpino <andrea@archlinux.org>

pkgname=kparts
pkgver=4.99.0
pkgrel=1
pkgdesc='KParts'
arch=('i686' 'x86_64')
url='https://projects.kde.org/projects/frameworks/kparts'
license=('LGPL')
depends=('kio')
makedepends=('extra-cmake-modules')
groups=('kf5')
source=("http://download.kde.org/unstable/frameworks/${pkgver}/${pkgname}-${pkgver}.tar.xz")
md5sums=('0d758db47b046bbad8db3d7eb1039cdc')

prepare() {
  mkdir -p build
}

build() {
  cd build
  cmake ../${pkgname}-${pkgver} \
    -DCMAKE_BUILD_TYPE=Release \
    -DCMAKE_INSTALL_PREFIX=/opt/kf5 \
    -DLIB_INSTALL_DIR=lib \
    -DBUILD_TESTING=OFF
  make
}

package() {
  cd build
  make DESTDIR="${pkgdir}" install
}
