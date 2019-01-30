# Maintainer : Bernhard Landauer <oberon@manjaro.org>

pkgname=clipit
_pkgname=ClipIt
pkgver=1.4.4
pkgrel=2
pkgdesc="Lightweight GTK+ clipboard manager (fork of Parcellite)"
arch=('i686' 'x86_64')
url="https://github.com/CristianHenzel/ClipIt"
#_snapshot=722fcf73fa0ce8430208c986e50b1c82975de69c
license=('GPL3')
depends=('gtk2' 'libappindicator-gtk2')
makedepends=('intltool')
optdepends=('xdotool: for automatic paste')
source=("${_pkgname}-${pkgver}.tar.gz::${url}/archive/v${pkgver}.tar.gz")
md5sums=('d49b9171c0b81269deafab9d6ecc7610')

build() {
  cd "${srcdir}/${_pkgname}-${pkgver}"
  ./autogen.sh
  ./configure \
    --prefix=/usr \
    --sysconfdir=/etc \
    --enable-appindicator
  make
}

package() {
  cd "${srcdir}/${_pkgname}-${pkgver}"
  make DESTDIR=${pkgdir} install
}
