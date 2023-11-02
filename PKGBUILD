pkgname=openfortivpn
pkgver=1.20.5
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
md5sums=('48e6b7c36345b7825ad43397a5ddb22e')

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
