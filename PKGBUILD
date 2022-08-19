pkgname=openfortivpn
pkgver=1.17.3
pkgrel=1
pkgdesc="Client for PPP+SSL VPN tunnel services"
arch=(x86_64)
url=https://github.com/adrienverge/openfortivpn
license=(GPL3)
depends=(
  glibc
  openssl
  ppp
  openresolv
)
makedepends=(
  systemd
)
backup=(etc/openfortivpn/config)
source=(https://github.com/adrienverge/openfortivpn/archive/refs/tags/v${pkgver}.tar.gz)
md5sums=('e4b9da5b3828741731f2010606df9849')

prepare() {
  cd openfortivpn-${pkgver}
  ./autogen.sh
}

build() {
  cd openfortivpn-${pkgver}
  ./configure \
    --prefix=/usr \
    --sysconfdir=/etc
  make
}

package() {
  cd openfortivpn-${pkgver}
  make DESTDIR="${pkgdir}" install
}
