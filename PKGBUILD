# Maintainer: Sergey Dovgal <arcadoss-f@ya.ru>
# Contributor: Gerardo Exequiel Pozzi <vmlinuz386@yahoo.com.ar>

pkgname=fakeroot-ng
pkgver=0.18
pkgrel=1
pkgdesc="Runs a program while fooling it into thinking it is running with root privileges (with ptrace syscall)"
arch=('i686' 'x86_64')
url="http://sourceforge.net/projects/fakerootng"
license=('GPL2')
depends=('gcc-libs')
source=(
http://downloads.sourceforge.net/project/fakerootng/fakeroot-ng/$pkgname-$pkgver.tar.gz
fixBroken32bit.patch
)
md5sums=('7bdfd3a72d00b4847e2023d922c289fa'
         'f42bb870f3414d5efeff25ce287e4af4')

prepare() {
  cd $srcdir/$pkgname-$pkgver
  patch -p1 < $srcdir/fixBroken32bit.patch
}

build() {
  cd $srcdir/$pkgname-$pkgver

  ./configure \
    --prefix=/usr

  make
}

package() {
  cd $srcdir/$pkgname-$pkgver
  make DESTDIR=$pkgdir install
}

# vim:set ts=2 sw=2 et:
