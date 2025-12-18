pkgname=kanata-bin
pkgver=1.10.1
pkgrel=1
pkgdesc="Improve keyboard comfort and usability with advanced customization"
arch=('x86_64')
url="https://github.com/jtroo/kanata"
license=('LGPL-3.0-only')
depends=('glibc' 'gcc-libs')
install=kanata.install
options=('!debug' 'strip')

source=(
  "https://github.com/jtroo/kanata/releases/download/v$pkgver/kanata-linux-binaries-v$pkgver-x64.zip"
  "kanata.service"
  "uinput.sysusers"
  "uinput.modules-load"
  "99-uinput.rules"
  "LICENSE"
)

# updpkgsums
sha256sums=('f755a4bdeb26821893ef954732db34eda845dcecd421c6f06a8b4b280ea38a39'
            'e2524d855826e645a11cc6871956f41c524dd2b80b370130cbbe2c8f87a2aa02'
            '132b79d2d3c48c8c876864f8165768bb29f1b558c4506946854d44621d5e12a3'
            'b9511609e10ef14e5f238fcba983860078bb3a71d0ccc649f5cdd6d71aed607d'
            '00ea191bc91c06684aa764cb682d18f5b5c759fabd2abfadd08e63b8798ff860'
            'e3a994d82e644b03a792a930f574002658412f62407f5fee083f2555c5f23118')

package() {
  install -Dm755 "${srcdir}/kanata_linux_cmd_allowed_x64" "${pkgdir}/usr/bin/kanata"

  install -Dm644 "${srcdir}/LICENSE" "${pkgdir}/usr/share/licenses/$pkgname/LICENSE"
  install -Dm644 "${srcdir}/kanata.service" "${pkgdir}/usr/lib/systemd/user/kanata.service"
  install -Dm644 "${srcdir}/99-uinput.rules" "${pkgdir}/usr/lib/udev/rules.d/99-uinput.rules"
  install -Dm644 "${srcdir}/uinput.sysusers" "${pkgdir}/usr/lib/sysusers.d/uinput.conf"
  install -Dm644 "${srcdir}/uinput.modules-load" "${pkgdir}/usr/lib/modules-load.d/uinput.conf"
}
