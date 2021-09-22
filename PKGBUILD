# Maintainer: Spencer Muise <smuise@spencermuise.ca>
pkgname=remontoire-git
_name=remontoire
pkgver=r54.96090d5
pkgrel=1
pkgdesc="A keybinding viewer for i3 and other programs."
arch=('any')
url="https://github.com/regolith-linux/remontoire"
license=('GPL3')
makedepends=(
  'git'
  'meson'
  'vala'
)
depends=(
  'json-glib'
  'gtk3'
  'libgee'
)
source=("git+https://github.com/regolith-linux/$_name.git")
md5sums=('SKIP')

pkgver() {
  cd "$_name"
  printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}


build() {
  meson --prefix /usr --buildtype=plain $_name build
  ninja -C build
}

package() {
  DESTDIR="$pkgdir" ninja -C build install
}

