# Maintainer: Philipp Wolfer <ph.wolfer@gmail.com>

pkgname=libdiscid-git
pkgver=v0.5.1.37.g274583a
pkgrel=1
pkgdesc="A Library for creating MusicBrainz DiscIDs (latest Git version)"
arch=('i686' 'x86_64')
url="http://musicbrainz.org/doc/libdiscid"
license=('LGPL')
provides=('libdiscid=0.5.0')
conflicts=('libdiscid')
depends=('glibc')
makedepends=('git' 'cmake')
options=('!libtool')
source=("git://github.com/metabrainz/libdiscid.git")
md5sums=('SKIP')
_gitname=libdiscid

build() {
  cd "$_gitname"
  cmake -DCMAKE_INSTALL_PREFIX:PATH=/usr .
  make
}

check() {
  cd "$_gitname"
  make check
}

package() {
  cd "$_gitname"
  make DESTDIR="${pkgdir}" install
}

pkgver() {
  cd "$_gitname"
  git describe --always | sed 's|-|.|g'
}
