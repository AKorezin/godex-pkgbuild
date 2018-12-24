pkgname=godex-ppd
_pkgname=rastertoezpl
pkgver=1.1.2
pkgrel=1
pkgdesc='CUPS Printer Driver for Godex Models'
url='http://www.godexintl.com/global/download/downloads/list/Drivers'
arch=('i686' 'x86_64')
license=('GPL2')

# make dependancies
depends=(cups
         cups-filters)
# source download from git repo & prepare

source=("${_pkgname}-${pkgver}.tar.gz::https://godex.s3-accelerate.amazonaws.com/UNEA1AgmT_CxGlxZUzqnlQ.file?v01")
sha256sums=('8473c35f78debf808455e9c81b91ed064cc8110ec7b5f0a6eb949c18f1f0486a')

build() {
	cd ${srcdir}/${_pkgname}-${pkgver}
	./configure prefix='/usr' libdir='/usr/lib' libexecdir='/usr/bin'
	make 
}

package() {
	install -m755 -d "${pkgdir}/usr/lib/cups/filter"
	cd ${srcdir}/${_pkgname}-${pkgver}
	make INSTALL_ROOT="${pkgdir}" DESTDIR="${pkgdir}" install
} 
