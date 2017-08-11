# Maintainer: c0ldcat <firez199984@gmail.com>
pkgname=marvin
pkgver=17.20.0
pkgrel=1
pkgdesc="Intuitive applications and API for chemical sketching, visualization and data exploration"
arch=('any')
url="http://www.chemaxon.com"
license=('proprietary')
depends=('jre8-openjdk')
source=("http://dl.chemaxon.com/marvin/${pkgver}/Marvin_linux_$pkgver.rpm"
        "MarvinSketch.desktop"
        "marvin-sketch-symbolic.svg")
md5sums=('f31a416f2a1e85c31bce879072593f6a'
         'fcf6e668a13ddb2fa55b790b132a2ab2'
         'e6758f94b843b97804112fa0420ba1bb')

package() {
    install -Dm755 MarvinSketch.desktop ${pkgdir}/usr/share/applications/MarvinSketch.desktop

    cp -R opt ${pkgdir}/opt

    install -Dm644 opt/chemaxon/marvinsuite/.install4j/MarvinSketch.png ${pkgdir}/usr/share/pixmaps/marvin-sketch.png
    install -Dm644 marvin-sketch-symbolic.svg ${pkgdir}/usr/share/pixmaps/marvin-sketch-symbolic.svg
    mkdir -p ${pkgdir}/usr/bin
    ln -sf /opt/chemaxon/marvinsuite/bin/cxcalc ${pkgdir}/usr/bin/cxcalc
    ln -sf /opt/chemaxon/marvinsuite/bin/cxtrain ${pkgdir}/usr/bin/cxtrain
    ln -sf /opt/chemaxon/marvinsuite/bin/molconvert ${pkgdir}/usr/bin/molconvert
    ln -sf /opt/chemaxon/marvinsuite/bin/msketch ${pkgdir}/usr/bin/msketch
    ln -sf /opt/chemaxon/marvinsuite/bin/mview ${pkgdir}/usr/bin/mview
}
