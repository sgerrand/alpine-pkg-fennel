# Contributor: Sasha Gerrand <alpine-pkgs@sgerrand.com>
# Maintainer: Sasha Gerrand <alpine-pkgs@sgerrand.com>
pkgname=fennel
pkgver=0.2.1
pkgrel=0
pkgdesc="Fennel programming language compiler"
url="https://fennel-lang.org/"
arch="all"
license="MIT"
depends="lua"
makedepends="luacheck make"
install=""
subpackages=""
source="fennel-$pkgver.tar.gz::https://github.com/bakpakin/Fennel/archive/$pkgver.tar.gz"
builddir="$srcdir/Fennel-$pkgver"

build() {
	cd "$builddir"
	# no-op
}

check() {
	cd "$builddir"

	./fennel -v

	echo '(print "Hello world!")' > test.fnl
	./fennel test.fnl
}

package() {
	cd "$builddir"

	install -Dm755 fennel \
		"$pkgdir"/usr/bin/fennel

	install -Dm755 fennel.lua \
		"$pkgdir"/usr/share/lua/5.1/fennel.lua

	install -Dm644 LICENSE \
		"$pkgdir"/usr/share/licenses/$pkgname/LICENSE
}

man() {
	cd "$builddir"
}

sha512sums="907ed9d966b501103cc9e642650b3319c36f18970a4d2ddc5358af71422056b443b0ef2e936f62d2831d5fce61e25dd158e5a98ef400900bfc0406fd0b61fdd5  fennel-0.2.1.tar.gz"
