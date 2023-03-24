# Maintainer: Jose Riha < jose 1711 gmail com >
# Contributor: twiggers
# Contributor: Cimbali

pkgname=python-pympress
pkgver=1.8.1
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
source=("https://files.pythonhosted.org/packages/8c/1f/6d081d546bd57fd2b6537bd6dcb204a96f5490150b0f1ed8e152fe0e484a/pympress-1.8.1.tar.gz")
sha256sums=('448c6abc9c74373311be5fff5e09d5dc32e7a18459290180eb34f3373d9ba4ce')

build() {
    cd $srcdir/pympress-$pkgver
    python setup.py build
}

package() {
    cd $srcdir/pympress-$pkgver
    python setup.py install --root="${pkgdir}" --optimize=1 --skip-build
}
