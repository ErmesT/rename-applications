pkgname=rename-applications
pkgver=1.0.0
pkgrel=1
pkgdesc='Rename applications shown in the desktop launcher'
arch=('any')
url='https://github.com/ErmesT/rename-applications'
license=('MIT')
depends=('bash' 'zenity' 'desktop-file-utils')
optdepends=('omarchy: refresh the Omarchy launcher menu')
source=("$pkgname-$pkgver.tar.gz::$url/releases/download/v$pkgver/$pkgname-$pkgver.tar.gz")
sha256sums=('SKIP')

package() {
    install -Dm755 rename-applications \
        "$pkgdir/usr/bin/rename-applications"
    install -Dm644 rename-applications.desktop \
        "$pkgdir/usr/share/applications/rename-applications.desktop"
}
