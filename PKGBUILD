# Maintainer: CyrIng <xfreq[at]cyring.fr>
# Contributor: CyrIng <xfreq[at]cyring.fr>
pkgname=xfreq
_pkgname=xfreq
_branch=master
pkgver=2.1
pkgrel=1
pkgdesc="Intel Core Monitoring"
arch=('x86_64')
url="http://code.google.com/p/xfreq/"
license=('GPL2')
makedepends=('git' 'libx11')
conflicts=('xfreq-2.0-git')
replaces=('xfreq-git')
source=("git+https://code.google.com/p/xfreq#branch=$_branch")
md5sums=('SKIP')
install=readme.install
 
pkgver() {
	cd "$srcdir/$_pkgname"
	echo $(git rev-list --count master).$(git rev-parse --short master)
}
 
build() {
	cd "$srcdir/$_pkgname"
	make -j 1
}
 
package() {
	cd "$srcdir/$_pkgname"
	install -Dm755 svr/bin/xfreq-intel "${pkgdir}/usr/bin/xfreq-intel"
	install -Dm644 svr/xfreq-intel.service "${pkgdir}/usr/lib/systemd/system/xfreq-intel.service"
	install -m755 cli/bin/xfreq-cli "${pkgdir}/usr/bin/xfreq-cli"
	install -m755 gui/bin/xfreq-gui "${pkgdir}/usr/bin/xfreq-gui"
}
