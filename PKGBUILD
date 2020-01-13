# Maintainer: c0ldcat <firez199984@gmail.com>
pkgname=marvin
pkgver=20.1.0
_pkgver=$(echo $pkgver | sed 's/.[0-9]$//g')
pkgrel=1
pkgdesc="Intuitive applications and API for chemical sketching, visualization and data exploration"
arch=('any')
url="http://www.chemaxon.com"
license=('proprietary')
depends=('jre8-openjdk')
source=("marvin_linux_${pkgver}.rpm::http://dl.chemaxon.com/marvin/${pkgver}/marvin_linux_${_pkgver}.rpm"
        "MarvinSketch.desktop"
        "MarvinView.desktop")
md5sums=('13a1f615a899ea68b1242ac70c38666c'
         '3c47d9b0629e55cda2a48356cf1c61b6'
         'cb2d322b8a4832d41490879ae4879a3a')

package() {
    # Install desktop config files
    mkdir -p ${pkgdir}/usr/share/applications
    install -Dm755 MarvinSketch.desktop ${pkgdir}/usr/share/applications/MarvinSketch.desktop
    install -Dm755 MarvinView.desktop ${pkgdir}/usr/share/applications/MarvinView.desktop

    # Copy opt dir contents across
    mkdir -p ${pkgdir}/opt/chemaxon/marvinsuite/.install4j
    cp -R opt/chemaxon/marvinsuite/.install4j/{*.uuid,*.utf8,*.png,*.ico,*.jar,*.conf} ${pkgdir}/opt/chemaxon/marvinsuite/.install4j
    cp -R opt/chemaxon/marvinsuite/* ${pkgdir}/opt/chemaxon/marvinsuite

    # Create pixmaps dir
    mkdir -p ${pkgdir}/usr/share/pixmaps
    ln -sf /opt/chemaxon/marvinsuite/.install4j/MarvinSketch.png ${pkgdir}/usr/share/pixmaps/MarvinSketch.png
    ln -sf /opt/chemaxon/marvinsuite/.install4j/MarvinView.png ${pkgdir}/usr/share/pixmaps/MarvinView.png

    # Create bin dir
    mkdir -p ${pkgdir}/usr/bin
    ln -sf /opt/chemaxon/marvinsuite/bin/cxcalc ${pkgdir}/usr/bin/cxcalc
    ln -sf /opt/chemaxon/marvinsuite/bin/cxtrain ${pkgdir}/usr/bin/cxtrain
    ln -sf /opt/chemaxon/marvinsuite/bin/molconvert ${pkgdir}/usr/bin/molconvert
    ln -sf /opt/chemaxon/marvinsuite/bin/msketch ${pkgdir}/usr/bin/msketch
    ln -sf /opt/chemaxon/marvinsuite/bin/mview ${pkgdir}/usr/bin/mview
}
