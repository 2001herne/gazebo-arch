pkgname=sdformat
pkgver=4.1.0
pkgrel=1
pkgdesc="SDF Converter for gazebo"
arch=('i686' 'x86_64')
url="http://sdformat.org/"
license=('Apache')
depends=('boost' 'tinyxml' 'ignition-math>=2')
makedepends=('cmake' 'doxygen' 'ruby>=1.9.1')

source=("http://osrf-distributions.s3.amazonaws.com/${pkgname}/releases/${pkgname}-${pkgver}.tar.bz2")
sha256sums=('0f63e446a29073affed2427214aa04d23c1cb8331cdd1bd7d48768d7eee5862a')

prepare(){
  cd "${srcdir}/${pkgname}-${pkgver}"
  mkdir -p build && cd build

  cmake .. -DCMAKE_BUILD_TYPE="Release" \
           -DCMAKE_INSTALL_PREFIX=/usr \
           -DCMAKE_INSTALL_LIBDIR=lib
}

build() {
  cd "${srcdir}/${pkgname}-${pkgver}/build"
  make
}

# check() {
#   cd "${srcdir}/${pkgname}-${pkgver}/build"
#   make test
# }

package() {
  cd "${srcdir}/${pkgname}-${pkgver}/build"
  make DESTDIR="$pkgdir/" install
}
