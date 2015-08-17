# Maintainer: Michael Düll <mail@akurei.me> PGP-Key: AAAEE882
# Contributor: Dan Serban
# Contributor: Niklas Schmuecker (IRC: nisc) <nschmuecker (gmail)>

pkgname=proxychains
pkgver=3.1
pkgrel=5
pkgdesc='A program proxifier: Runs programs from behind a proxy server, similar to tsocks. TCP & DNS tunneling. HTTP, SOCKS4 & SOCKS5.'
url='http://proxychains.sourceforge.net/'
arch=('i686' 'x86_64')
license=('GPL')
depends=('dnsutils')
options=('!libtool')
backup=('etc/proxychains.conf')
source=("http://downloads.sourceforge.net/sourceforge/proxychains/proxychains-${pkgver}.tar.gz")

build()
{
  cd proxychains-${pkgver}
  sed -i 's/servlen, unsigned int/servlen, int/' proxychains/libproxychains.c
#  sed -i 's#export LD_PRELOAD=libproxychains.so#export LD_PRELOAD=/usr/lib/libproxychains.so#' proxychains/proxychains
  ./configure --prefix=/usr
  make
  make DESTDIR="${pkgdir}" install
  cd "${pkgdir}"
  mv usr/etc .
}

sha512sums=('7ec7be851d956070fe28bdd3bd7c1a7dc442c054e6487868672ba27490c9b0b6aaa061504c9e1933feccb40ca1996123d202df449eac4251d9582a0ba73c7061')
