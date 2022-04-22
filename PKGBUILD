# Maintainer: Jose Riha < jose 1711 gmail com >
# Contributor: twiggers
# Contributor: Cimbali

pkgname=python-pympress
pkgver=1.7.2
pkgrel=2
pkgdesc="Dual-screen PDF reader designed for presentations"
url="https://cimbali.github.io/pympress/"
license=('GPL-2')
arch=('any')
makedepends=('python-setuptools')
depends=('python' 'poppler' 'poppler-glib' 'python-gobject' 'python-cairo' 'gtk3' 'python-watchdog')
optdepends=('gstreamer: for media playback' 'gst-plugins-base: for media playback' 'gst-plugin-gtk: for media playback'
			'gst-plugins-good: additional media codecs' 'gst-libav: additional media codecs' 'gst-plugins-bad: additional media codecs' 'gst-plugins-ugly: additional media codecs'
			'vlc: alternative media playback option' 'python-vlc: alternative media playback option')
source=("2c5533ac61ebf23994aa821c2a8902d203435665b51146658fd788f860f272f2")
sha256sums=('1.7.2')

build() {
    cd $srcdir/pympress-$pkgver
    python setup.py build
}

package() {
    cd $srcdir/pympress-$pkgver
    python setup.py install --root="${pkgdir}" --optimize=1 --skip-build
}
