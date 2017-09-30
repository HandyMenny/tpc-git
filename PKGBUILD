# Maintainer: <kfgz at interia dot pl>

pkgname=tpc-git
_pkgname=tpc
pkgver=2015.02.03
pkgrel=2
pkgdesc="Tool for undervolting/overclocking Family 10h, 11h, 12h, 14h and 15h AMD processors."
arch=('i686' 'x86_64')
url="https://github.com/turionpowercontrol/tpc/"
license=('unknown')
depends=('gcc-libs' 'ncurses')
provides=('tpc')
conflicts=('tpc')
install=tpc.install
source=('git://github.com/turionpowercontrol/tpc.git'
        tpc.conf)
sha1sums=('SKIP'
          'da954dbece5ea85cbee4ec1fdf32f4e144b538d3')

pkgver() {
  cd "$_pkgname"
  git log -1 --format=format:%cd --date=short | sed 's|-|.|g'
}

build() {
  cd "$_pkgname"
  make 
}

package() {
  install -Dm755 "$srcdir/$_pkgname"/TurionPowerControl "${pkgdir}"/usr/bin/tpc
  install -Dm644 "$srcdir"/tpc.conf "${pkgdir}"/etc/modules-load.d/tpc.conf 
}
