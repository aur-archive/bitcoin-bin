## Maintainer : shahid <helllamer@gmail.com>
## Long PKGBUILD description, todo, wiki:
## * https://bitbucket.org/helllamer/archlinux-pkgbuild/wiki/pkgbuild/bitcoin

## Wanna take part on development my PKGBUILDs? Feel welcome on my repo:
## * https://bitbucket.org/helllamer/archlinux-pkgbuild/

prog=bitcoin
pkgname=${prog}-bin
pkgver=0.8.1
pkgrel=1
pkgdesc="Bitcoin is a peer-to-peer network based digital currency (precompiled binary official version, statically linked against libboost)"
arch=('i686' 'x86_64')
[ "$CARCH" = "i686"   ] && BTC_ARCH=32
[ "$CARCH" = "x86_64" ] && BTC_ARCH=64
url="http://www.bitcoin.org/"
depends=('expat' 'gcc-libs' 'freetype2' 'libpng' 'glib2' 'qt4>=4.6')
license=('MIT')
conflicts=('bitcoin')
# install=${prog}-bin.install
source=("http://downloads.sourceforge.net/sourceforge/${prog}/${prog}-${pkgver}-linux.tar.gz"
	"${prog}.desktop")
md5sums=('1f6698135cfab8695e0f826ffc428d4c'
	 '77139ce8a40f46bd7d7ad0a743672113')

package() {

	s1=$srcdir/${prog}-${pkgver}-linux
	src_qt=$s1/src
	src_d=$s1/src/src
	bin=$s1/bin/$BTC_ARCH

	mkdir -p $pkgdir/usr/bin
	mkdir -p $pkgdir/usr/share/pixmaps
	mkdir -p $pkgdir/usr/share/applications
	
	# pack pre-compiled binaries
	install -D -m755 $bin/* $pkgdir/usr/bin/
	
	# add icon and .desktop file to pkg
	install -D -m644 $src_qt/src/qt/res/icons/bitcoin.png $pkgdir/usr/share/pixmaps/
	install -D -m644 $srcdir/${prog}.desktop $pkgdir/usr/share/applications/ 
}
