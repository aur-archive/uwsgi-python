# Contributor: Kevin Zuber <uKev@knet.eu>
# Maintainer: Kevin Zuber <uKev@knet.eu>
pkgname=('uwsgi-python')
_pkgbase=uwsgi
pkgver=1.4.9
pkgrel=1
epoch=
pkgdesc="uWSGI is a fast, self-healing and developer/sysadmin-friendly application container server coded in pure C. Splitted package to support python, python2, ruby (rack), ... "
arch=(i686 x86_64 arm armv6h)
url="http://projects.unbit.it/uwsgi/"
license=('GPL2')
groups=()
depends=(libyaml jansson uwsgi-core python)
makedepends=(python)
checkdepends=()
provides=()
conflicts=()
replaces=()
backup=()
options=()
install=
changelog=
source=(http://projects.unbit.it/downloads/$_pkgbase-$pkgver.tar.gz)
noextract=()
md5sums=('3fe995a39e0489621ddcc7acfbd49171')


build() {
  cd "$srcdir/$_pkgbase-$pkgver"
  python uwsgiconfig.py --plugin plugins/python core python32

}

package() {

  cd "$srcdir/$_pkgbase-$pkgver"
  mkdir -p "$pkgdir/usr/lib/uwsgi/"
  mkdir -p "$pkgdir/usr/bin/"
  install -Dm555 python32_plugin.so "$pkgdir/usr/lib/uwsgi"
  ln -s "/usr/bin/uwsgi" "$pkgdir/usr/bin/uwsgi_python32"
}
