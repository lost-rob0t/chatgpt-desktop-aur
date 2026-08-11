# Maintainer: lost-rob0t

pkgname=chatgpt-desktop
pkgver=26.803.81509
pkgrel=1
pkgdesc='Official ChatGPT desktop app for Linux'
arch=('x86_64')
url='https://chatgpt.com/'
license=('custom')
options=('!strip' '!debug')
depends=(
  'alsa-lib'
  'at-spi2-core'
  'cairo'
  'cups'
  'dbus'
  'expat'
  'gcc-libs'
  'gdk-pixbuf2'
  'glib2'
  'glibc'
  'gtk3'
  'libdrm'
  'libglvnd'
  'libnotify'
  'libusb'
  'libx11'
  'libxcb'
  'libxcomposite'
  'libxdamage'
  'libxext'
  'libxfixes'
  'libxkbcommon'
  'libxrandr'
  'mesa'
  'nss'
  'openssl'
  'pango'
  'systemd-libs'
  'tar'
  'xdg-utils'
  'xz'
)
optdepends=('apparmor: load the upstream ChatGPT AppArmor profile')
provides=('chatgpt')
conflicts=('chatgpt')
source_x86_64=(
  "chatgpt-${pkgver}-${pkgrel}.${CARCH}.rpm::https://persistent.oaistatic.com/codex-app-prod/linux/rpm/latest/chatgpt.x86_64.rpm"
)
sha256sums_x86_64=('4d34fd4bb1122b7f2445f6a1bbc7c869cd3724c9f71aee3802795272c0b10702')

package() {
  install -d "$pkgdir/usr/bin" "$pkgdir/usr/lib" "$pkgdir/usr/share"
  cp -a "$srcdir/usr/bin/chatgpt" "$pkgdir/usr/bin/"
  cp -a "$srcdir/usr/lib/chatgpt" "$pkgdir/usr/lib/"
  cp -a "$srcdir/usr/share/applications" "$pkgdir/usr/share/"
  cp -a "$srcdir/usr/share/pixmaps" "$pkgdir/usr/share/"
  cp -a "$srcdir/usr/share/doc" "$pkgdir/usr/share/"

  if [[ -f "$srcdir/etc/apparmor.d/chatgpt" ]]; then
    install -Dm644 "$srcdir/etc/apparmor.d/chatgpt" \
      "$pkgdir/etc/apparmor.d/chatgpt"
  fi

  install -Dm644 "$srcdir/usr/lib/chatgpt/LICENSE" \
    "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}
