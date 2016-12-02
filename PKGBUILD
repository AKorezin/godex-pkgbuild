pkgname=godex-ppd
_pkgname=rastertoezpl
pkgver=1.1.0
pkgrel=1
pkgdesc='CUPS Printer Driver for Godex Models'
url='http://www.godexintl.com/global/download/downloads/list/Drivers'
arch=('i686' 'x86_64')
license=('GPL2')

# make dependancies
depends=(cups
         cups-filters)
# source download from git repo & prepare
source=(rastertoezpl-1.1.0.tar.gz::http://www.godexintl.com/global/download/downloads/Download/5597)
sha256sums=('a1ed3364fd6cf55268e3fc8ed3bd8290f9976a0df72d96cadb84a9d755d71953')

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
