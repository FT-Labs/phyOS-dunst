# Maintainer: Johannes Löthberg <johannes@kyriasis.com>
# Maintainer: Daniel M. Capella <polyzen@archlinux.org>
# Contributor: Daniel Wallace <danielwallace at gtmanfred dot com>
# Contributor: Arda Atci <arda@phytech.io>

pkgname=dunst-phyOS
pkgver=1.7.3
pkgrel=1
pkgdesc="Customizable and lightweight notification-daemon"
url="https://dunst-project.org/"
arch=('x86_64')
license=('BSD')
conflicts=('dunst')
depends=('libxinerama' 'dbus' 'systemd' 'wayland' 'libxss' 'pango' 'gdk-pixbuf2' 'libxrandr' 'glib2')
makedepends=('libnotify')
optdepends=('libnotify: dunstify')
backup=('etc/dunst/dunstrc')
provides=('notification-daemon')
options=('debug')
source=("git://github.com/PhyTech-R0/dunst-phyOS")
md5sums=('SKIP')

build() {
  cd dunst-phyOS

  make PREFIX=/usr SYSCONFDIR=/etc X11INC=/usr/include/X11 X11LIB=/usr/lib/X11 all
}

package() {
  cd dunst-phyOS

  make DESTDIR="$pkgdir" SYSCONFDIR=/etc PREFIX=/usr install
  install -Dm755 dunstify "$pkgdir"/usr/bin/dunstify
  install -Dm644 LICENSE "$pkgdir"/usr/share/licenses/$pkgname/LICENSE
}
