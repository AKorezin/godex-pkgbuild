pkgname=godex-ppd
_pkgname=rastertoezpl
pkgver=1.0.6
pkgrel=1
pkgdesc='CUPS Printer Driver for Godex Models'
url='http://www.godexintl.com/global/download/downloads/list/Drivers'
arch=('i686' 'x86_64')
license=('GPL2')

# make dependancies
depends=(cups
         cups-filters)
# source download from git repo & prepare
source=(rastertoezpl-1.0.6.tar.gz::http://www.godexintl.com/global/download/downloads/Download/5597)
sha256sums=('a9fef5091455a9f620ec36d4794cad816b1a39335171aa320d35efdc1a14f4ad')

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
