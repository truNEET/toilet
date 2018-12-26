# Maintainer:  Eric Bailey <nerflad@gmail.com>
# Contributor: Bruno Pagani <bruno.n.pagani@gmail.com>
pkgname=toilet
_commit=a7606c6424ba25b5380765df949cf768991e24be
pkgver=0.3.r155.${_commit:0:7}
pkgrel=1
pkgdesc="free replacement for the FIGlet utility."
arch=('i686' 'x86_64' 'armv7h')
url="https://github.com/truneet/toilet"
license=('custom:WTFPL')
depends=('libcaca')
source=(${pkgname}-${pkgver}.tar.gz::"${url}/archive/${_commit}.tar.gz")
sha256sums=('f29305d53437737c3919e1182808868f4a84035245a71e932463f058a5f9856a')

build() {
    cd $pkgname-${_commit}
    ./bootstrap
    ./configure --prefix=/usr
    make
}

package() {
    cd $pkgname-${_commit}
    make DESTDIR="$pkgdir" install
    install -Dm644 COPYING "$pkgdir"/usr/share/licenses/${pkgname}/COPYING
}
