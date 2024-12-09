# Maintainer: SanskritFritz (gmail)
# Contributor: bidulock (AUR)

pkgname=wmmp
pkgver=0.10.0
pkgrel=3
pkgdesc="Dockapp for interfacing MPD."
url="http://mpd.wikia.com/wiki/Client:WMmp"
arch=('i686' 'x86_64' 'aarch64')
license=('GPLv2')
source=("http://www.musicpd.org/download/WMmp/$pkgver/WMmp-$pkgver.tar.gz")

build() {
	cd "$srcdir/WMmp-$pkgver"
	rm config.guess
    rm config.sub
    wget -O config.guess 'https://git.savannah.gnu.org/gitweb/?p=config.git;a=blob_plain;f=config.guess;hb=HEAD'
    wget -O config.sub 'https://git.savannah.gnu.org/gitweb/?p=config.git;a=blob_plain;f=config.sub;hb=HEAD'
	./configure --with-default-port=6600 --prefix=/usr
	make PREFIX="/usr"
}

package() {
	cd "$srcdir/WMmp-$pkgver"
	make DESTDIR="$pkgdir" install
}

md5sums=('846c3d66d360d50e792377cdb5f0b572')
