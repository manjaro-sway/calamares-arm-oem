# Maintainer: Dan Johansen <strit@manjaro.org>
# Contributor: Philip Müller <philm@manjaro.org>
# Contributor: Bernhard Landauer <oberon@manjaro.org>

pkgname="calamares-arm-oem"
pkgver=20210621
pkgrel=1
arch=('any')
pkgdesc="Manjaro ARM OEM Modules"
depends=('calamares' 'kde-cli-tools' 'manjaro-system')
install=calamares-arm-oem.install
url="https://github.com/Strit/calamares-arm-oem"
license=('GPL3')
makedepends=('git')
source=("git+$url.git")
md5sums=('SKIP')

pkgver() {
    date +%Y%m%d
}

package() {
    cd "${pkgname}"
    install -d "${pkgdir}"/usr/lib/calamares
    cp -r modules "${pkgdir}"/usr/lib/calamares
    install -Dm644 postinstall-settings/settings.conf "${pkgdir}"/etc/calamares/settings.conf
    install -Dm644 postinstall-settings/welcome.conf "${pkgdir}"/etc/calamares/modules/welcome.conf
    install -Dm644 postinstall-settings/users.conf "${pkgdir}"/etc/calamares/modules/users.conf
    install -Dm644 postinstall-settings/finished.conf "${pkgdir}"/etc/calamares/modules/finished.conf
    install -Dm644 cleanupoem.service -t "${pkgdir}"/opt/calamares/
    install -Dm644 calamares.desktop -t "${pkgdir}"/etc/skel/.config/autostart/
    install -Dm644 resize.service -t "${pkgdir}"/usr/lib/systemd/system/
    install -Dm644 manjaro/* -t "${pkgdir}/etc/calamares/branding/manjaro/"
}
