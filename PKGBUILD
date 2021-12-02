# Maintainer: Mikołaj "D1SoveR" Banasik <d1sover@gmail.com>

pkgname="$(grep -Po '^PROGNAME="?\K([^"]+)' efistub-sync)"

pkgver="$(grep -Po '^VERSION="?\K([^"]+)' efistub-sync)"
pkgrel=1
epoch=

pkgdesc="Tool to synchronise EFI Unified Kernel Images with currently installed kernels"
arch=('any')
url=""
changelog=
license=('WTFPL')

depends=('mkinitcpio' 'efi-mkuki')
backup=('etc/efistub-sync.conf')

source=('efistub-sync'
        'efistub-sync-install'
        'efistub-sync.conf'
        '98-efistub-sync-install.hook')
sha256sums=('25eca062817fee6a7600d54fcd40ee963dc2c29e7b3e069a1679c99f4489812e'
            '2641331e2839b39ef97a9b9edb8facdda73269b7c08707f1f021082807a1ffd5'
            '2b73a671b67cb53a52f12431400526a53c95f46d5893a37a344c3d1b4b519138'
            '81f14ee8664f0402b17093ee544479119da88800cd828b111724eddfdf78376a')

package() {
	install -Dm755 efistub-sync "${pkgdir}/usr/bin/efistub-sync"
	install -Dm755 efistub-sync-install "${pkgdir}/usr/share/libalpm/scripts/efistub-sync-install"
	install -Dm644 98-efistub-sync-install.hook "${pkgdir}/usr/share/libalpm/hooks/98-efistub-sync-install.hook"
	install -Dm644 efistub-sync.conf "${pkgdir}/etc/efistub-sync.conf"
}
