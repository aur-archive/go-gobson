pkgname=go-gobson
pkgver=r20120304
pkgrel=5
pkgdesc="BSON serialization for Go"
arch=('x86_64' 'i686')
url="http://labix.org/gobson"
license=('GPL')
makedepends=('go' 'go-check')
options=('!strip' '!emptydirs')
_gourl=launchpad.net/mgo/bson

build() {
  cd "$srcdir"
  GOPATH="$srcdir" go get -v -x ${_gourl}/...
}

check() {
  source /etc/profile.d/go.sh
  GOPATH="$GOPATH:$srcdir" go test -v -x ${_gourl}/...
}

package() {
  source /etc/profile.d/go.sh
  mkdir -p "${pkgdir}/$GOPATH"
  cp -Rv --preserve=timestamps ${srcdir}/{src,pkg} "${pkgdir}/$GOPATH"
}

# vim:set ts=2 sw=2 et:
