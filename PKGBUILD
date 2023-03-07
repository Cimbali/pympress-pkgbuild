# Maintainer: Jose Riha < jose 1711 gmail com >
# Contributor: twiggers
# Contributor: Cimbali

pkgname=python-pympress
pkgver=1.7.2
pkgrel=2
pkgdesc="Simple yet powerful dual-screen PDF reader designed for presentations"
url="https://github.com/Cimbali/pympress"
license=('GPL-v2')
arch=('any')
makedepends=('python-setuptools')
depends=('python' 'poppler' 'poppler-glib' 'python-gobject' 'python-cairo' 'gtk3' 'python-watchdog')
optdepends=('gstreamer: for media playback' 'gst-plugins-base: for media playback' 'gst-plugin-gtk: for media playback'
			'gst-plugins-good: additional media codecs' 'gst-libav: additional media codecs' 'gst-plugins-bad: additional media codecs' 'gst-plugins-ugly: additional media codecs'
			'vlc: alternative media playback option' 'python-vlc: alternative media playback option')
source=("https://files.pythonhosted.org/packages/f6/a0/93d92200dd3febe3c83fbf491a353aed2bb8199cfc22f3b684ea77cdbecf/pympress-1.7.2.tar.gz")
sha256sums=('2c5533ac61ebf23994aa821c2a8902d203435665b51146658fd788f860f272f2')

build() {
    cd $srcdir/pympress-$pkgver
    python setup.py build
}

package() {
    cd $srcdir/pympress-$pkgver
    python setup.py install --root="${pkgdir}" --optimize=1 --skip-build
}
