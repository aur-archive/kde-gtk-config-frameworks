# Maintainer: Antonio Rojas <nqn1976 @ gmail.com>

pkgname=kde-gtk-config-frameworks
pkgver=5.1.95
pkgrel=1
pkgdesc='GTK2 and GTK3 Configurator for KDE'
arch=('i686' 'x86_64')
url='https://projects.kde.org/projects/kde/workspace/kde-gtk-config'
license=('LGPL')
groups=('plasma-next')
depends=('kcmutils' 'knewstuff')
makedepends=('extra-cmake-modules' 'gtk2' 'gtk3')
conflicts=('kde-gtk-config')
source=("http://download.kde.org/unstable/plasma/$pkgver/kde-gtk-config-$pkgver.tar.xz")
install=$pkgname.install
md5sums=('79bdd649e52167b89703421b123d09b1')

prepare() {
  mkdir -p build
}

build() {
  cd build
  cmake ../kde-gtk-config-$pkgver \
    -DCMAKE_BUILD_TYPE=Release \
    -DCMAKE_INSTALL_PREFIX=/usr \
    -DLIB_INSTALL_DIR=lib \
    -DLIBEXEC_INSTALL_DIR=lib \
    -DSYSCONF_INSTALL_DIR=/etc \
    -DKDE_INSTALL_USE_QT_SYS_PATHS=ON \
    -DBUILD_TESTING=OFF
  make
}

package() {
  cd build
  make DESTDIR="$pkgdir" install
}
