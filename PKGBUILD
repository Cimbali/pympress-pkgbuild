# Maintainer: Jose Riha < jose 1711 gmail com >
# Contributor: twiggers
# Contributor: Cimbali

pkgname=python-pympress
pkgver=1.8.0
pkgrel=1
pkgdesc="Simple yet powerful dual-screen PDF reader designed for presentations"
url="https://github.com/Cimbali/pympress"
license=('GPL-v2')
arch=('any')
makedepends=('python-setuptools')
depends=('python' 'poppler' 'poppler-glib' 'python-gobject' 'python-cairo' 'gtk3' 'python-watchdog')
optdepends=('gstreamer: for media playback' 'gst-plugins-base: for media playback' 'gst-plugin-gtk: for media playback'
			'gst-plugins-good: additional media codecs' 'gst-libav: additional media codecs' 'gst-plugins-bad: additional media codecs' 'gst-plugins-ugly: additional media codecs'
			'vlc: alternative media playback option' 'python-vlc: alternative media playback option')
source=("https://files.pythonhosted.org/packages/70/a0/08ead2b665bea74f291466fca2996fb784110777ec441347e10555534135/pympress-1.8.0.tar.gz")
sha256sums=('160255c6dcfa5fa6bc69b40b1bde3c4ba7c10f750aeee2d6bc1877d343f743ec')

build() {
    cd $srcdir/pympress-$pkgver
    python setup.py build
}

package() {
    cd $srcdir/pympress-$pkgver
    python setup.py install --root="${pkgdir}" --optimize=1 --skip-build
}
