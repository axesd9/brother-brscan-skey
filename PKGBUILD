# Maintainer: Chanathip Srithanrat <axesd9@gmail.com>

pkgname=brother-brscan-skey
pkgver=0.2.4_1
pkgrel=1
pkgdesc='Brother scan-skey-tool'
arch=('x86_64')
url='http://support.brother.com/g/s/id/linux/en/'
license=('custom:brother')
depends=('sane')
optdepends=('sendmail: Scan to E-mail support'
            'gimp: Scan to Image support')
install="$pkgname.install"
source=("http://download.brother.com/welcome/dlf006652/${pkgname#brother-}-${pkgver/_/-}.amd64.deb"
        "http://support.brother.com/g/s/agreement/English_lpr/agree.html"
        "brscan-skey.service"
        "brscan-skey-user.service")
md5sums=('8dfae9b3eb7b4e468e6175558d207f80'
         '5a4a3172f6278922062aa6e1f43b0d92'
         'fa94f7919705d924e08f1fc8c74653c4'
         'bb76525d0a7cf43abdd2bcb610c11ab7')

prepare() {
    bsdtar xf data.tar.gz
}

package() {
    cp -r opt $pkgdir
    install -Dm644 brscan-skey.service $pkgdir/usr/lib/systemd/system/brscan-skey.service
    install -Dm644 brscan-skey-user.service $pkgdir/usr/lib/systemd/user/brscan-skey.service
    install -Dm644 agree.html $pkgdir/usr/share/licenses/$pkgname/LICENSE.html
    install -dm775 -o 289 -g 289 $pkgdir/srv/brscan-skey
}
