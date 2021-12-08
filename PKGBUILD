# Maintainer: Jose Riha < jose 1711 gmail com >
# Contributor: twiggers
# Contributor: Cimbali

pkgname=python-pympress
pkgver=1.7.1
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
source=("bfdc228cb14862dba943abf9ece92d9e966c433e566ba514985739966f838ee3")
sha256sums=('1.7.1')

build() {
    cd $srcdir/pympress-$pkgver
    python setup.py build
}

package() {
    cd $srcdir/pympress-$pkgver
    python setup.py install --root="${pkgdir}" --optimize=1 --skip-build
}
