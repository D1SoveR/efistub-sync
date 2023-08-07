# Maintainer: Mikołaj "D1SoveR" Banasik <d1sover@gmail.com>

pkgname="$(grep -Po '^PROGNAME="?\K([^"]+)' efistub-sync)"
pkgver="$(grep -Po '^VERSION="?\K([^"]+)' efistub-sync)"
pkgrel=1
epoch=

pkgdesc="Tool to synchronise EFI Unified Kernel Images with currently installed kernels"
arch=('any')
url="https://github.com/D1SoveR/efistub-sync"
license=('GPL3')

depends=('mkinitcpio' 'systemd-ukify')
optdepends=('sbsigntools: To automatically sign images for Secure Boot')
backup=('etc/efistub-sync.conf')

source=('efistub-sync'
        'efistub-sync-install'
        'efistub-sync.conf'
        '98-efistub-sync-install.hook')
sha256sums=('d5b2145091788b1ef1816105169a388ab5f557138198e4676be1aae85bfb8eb3'
            '2641331e2839b39ef97a9b9edb8facdda73269b7c08707f1f021082807a1ffd5'
            '3f70f0753e0dcc13804b1bc282f9af4de31e7a5c51b40d9df228ebf497ef0371'
            '81f14ee8664f0402b17093ee544479119da88800cd828b111724eddfdf78376a')

package() {
	install -Dm755 efistub-sync "${pkgdir}/usr/bin/efistub-sync"
	install -Dm755 efistub-sync-install "${pkgdir}/usr/share/libalpm/scripts/efistub-sync-install"
	install -Dm644 98-efistub-sync-install.hook "${pkgdir}/usr/share/libalpm/hooks/98-efistub-sync-install.hook"
	install -Dm644 efistub-sync.conf "${pkgdir}/etc/efistub-sync.conf"
}
