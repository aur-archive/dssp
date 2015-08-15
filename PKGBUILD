# Maintainer: Patrice Peterson <runiq at archlinux dot us>

pkgname=dssp
pkgver=2.2.1
pkgrel=2
pkgdesc="Secondary structure assignment for proteins"
arch=('i686' 'x86_64')
url="http://swift.cmbi.ru.nl/gv/dssp/HTML/distrib.html"
license=('custom')
depends=('boost-libs')
source=("$pkgname-$pkgver.tar.gz::ftp://ftp.cmbi.ru.nl/pub/software/$pkgname/$pkgname-$pkgver.tgz")
md5sums=('0faa63ea1f0c69def077530de0cf84c1')

prepare() {
	cd "$srcdir/$pkgname-$pkgver"
        sed -i 's/-static//' makefile
}

build() {
	cd "$srcdir/$pkgname-$pkgver"
	make
}

package() {
	cd "$srcdir/$pkgname-$pkgver"
	make DEST_DIR="$pkgdir" install
        install -D -m0644 LICENSE_1_0.txt "$pkgdir/usr/share/licenses/LICENSE"
}
