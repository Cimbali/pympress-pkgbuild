# Maintainer: Jose Riha < jose 1711 gmail com >
# Contributor: twiggers
# Contributor: Cimbali

pkgname=pympress
pkgver=1.8.6
pkgrel=1
pkgdesc="Simple yet powerful dual-screen PDF reader designed for presentations"
url="https://github.com/Cimbali/pympress"
license=('GPL-v2')
arch=('any')

source=("https://files.pythonhosted.org/packages/87/66/fb9f8f2975740ea8880de293eb16b543965387881c71ca323a00a5d77d8a/pympress-1.8.6.tar.gz")
sha256sums=('243dc5dd225acd13fb6bae680e2de1816d521203b98a9cff588b66f141fffd9a')

# build using wheel, sphinx/myst-parser for docs building
makedepends=('python' 'python-setuptools' 'python-pip' 'python-wheel' 'python-sphinx' 'python-myst-parser')
depends=('python' 'poppler' 'poppler-glib' 'python-gobject' 'python-cairo' 'gtk3' 'python-watchdog')
# 3 different optdepends: base media playback, extended codecs for same media playback, alternative option using vlc
optdepends=(
	'gstreamer: for media playback' 'gst-plugins-base: for media playback' 'gst-plugin-gtk: for media playback'
	'gst-plugins-good: additional media codecs' 'gst-libav: additional media codecs' 'gst-plugins-bad: additional media codecs' 'gst-plugins-ugly: additional media codecs'
	'vlc: alternative media playback option' 'python-vlc: alternative media playback option'
)

build() {
	cd "$srcdir/pympress-$pkgver/"
    python -m pip wheel --verbose --progress-bar off --disable-pip-version-check --use-pep517 --no-build-isolation --no-deps --wheel-dir build/ .
    python -m pip sphinx -a -d build/doctrees/ -D skip_api_doc=1 -D packaged_docs=1 -b html docs/ build/html/
    python -m pip sphinx -a -d build/doctrees/ -D skip_api_doc=1 -D packaged_docs=1 -b man docs/ build/man/
}

package() {
	cd "$srcdir/pympress-$pkgver/"

	python -m pip install --verbose --progress-bar off --disable-pip-version-check --root="${pkgdir}" --no-compile --ignore-installed --no-deps --no-index --find-links build/

	install -Dm644 build/man/pympress.1 "$pkgdir/usr/share/man/man1/$pkgbase.1"
	cd build/html
	find * -type f -exec install -Dm644 "$pkgdir/usr/share/doc/$pkgbase/{}" ';'
}
