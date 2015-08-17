# Contributor: dragonn <dragonn at op dot pl>

pkgname=tkgate-beta
_realpkgname=tkgate
pkgver=2.0
pkgrel=3
license=('GPL')
pkgdesc="A digital circuit simulator with a tcl/tk-based graphical editor. Beta version"
depends=('tcl' 'tk')
url="http://www.tkgate.org"
arch=('i686' 'x86_64')
install=tkgate-beta.install
source=("http://www.tkgate.org/downloads/$_realpkgname-$pkgver-b10.tgz")
md5sums=('84ffe959868d39ec856b5ff1c70136c3')

build() {
    cd ${srcdir}/${_realpkgname}-${pkgver}-b10
    CPPFLAGS="-DUSE_INTERP_RESULT" LDFLAGS='-lm' ./configure --prefix=/usr

    make  || return 1
    make DESTDIR=${pkgdir} install || return 1
    rm ${pkgdir}/usr/share/tkgate/libexec/verga
    rm ${pkgdir}/usr/share/tkgate/libexec/tkgate

}
