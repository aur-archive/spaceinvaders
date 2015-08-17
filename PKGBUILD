# Maintainer: edoardo <edoardo.elidoro@gmail.com>  
# Contributor: Arch Haskell Team <arch-haskell@haskell.org>

_hkgname=SpaceInvaders
pkgname=spaceinvaders
pkgver=0.4.2
pkgrel=3
pkgdesc="Video game"
url="http://hackage.haskell.org/package/${_hkgname}"
license=('custom:BSD3')
arch=('i686' 'x86_64')
makedepends=('ghc' 'haskell-hgl' 'haskell-yampa>=0.9.2' 'haskell-array=0.3.0.1' 'haskell-random=1.0.0.2')
depends=('gmp')
options=('strip')
source=(http://hackage.haskell.org/packages/archive/${_hkgname}/${pkgver}/${_hkgname}-${pkgver}.tar.gz)
md5sums=('c37b5cbe0cbeacf0ad3adca6925911b1')

build() {
    cd ${srcdir}/${_hkgname}-${pkgver}
    runhaskell Setup configure --prefix=/usr --docdir=/usr/share/doc/${pkgname} -O
    runhaskell Setup build
}
package() {
    cd ${srcdir}/${_hkgname}-${pkgver}
    runhaskell Setup copy --destdir=${pkgdir}
    install -D -m644 LICENSE ${pkgdir}/usr/share/licenses/${pkgname}/LICENSE
    rm -f ${pkgdir}/usr/share/doc/${pkgname}/LICENSE
}
