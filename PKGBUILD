# Maintainer: Retro_Gamer / xaGe <https://github.com/eGax>
_pkgname=TrenchBroom
pkgname=trenchbroom-2024.1-x86_64
pkgver=2024.1
_pkgver=Linux-ubuntu-22.04-v$pkgver-Release.$CARCH
pkgrel=1
pkgdesc="A free (GPLv3), cross platform level editor for Quake-engine based games. x86_64 Ubuntu Release version repackaged for Arch."
arch=("x86_64")
url="https://trenchbroom.github.io/"
license=('GPL3')
provides=('trenchbroom')
conflicts=('trenchbroom' 'trenchbroom-git')
depends=("freeimage" "freetype2" "mesa" "libgl" "freeglut" "libxxf86vm" "glew" "glm" "tinyxml2")
source=("https://github.com/TrenchBroom/TrenchBroom/releases/download/v$pkgver/$_pkgname-$_pkgver.deb")
noextract=("$_pkgname-$_pkgver.deb")
sha256sums=('7e2b59dfcdfc94841d62a29a01581672a47935138f9b21f9faa113fbbf1ca7ce')

prepare() {
  mkdir -p "$pkgname-$pkgver"
  mkdir -p "$pkgname-$pkgver-files"
  bsdtar xvf "$srcdir/$_pkgname-$_pkgver.deb" -C "$pkgname-$pkgver"
  bsdtar xvf "$pkgname-$pkgver/data.tar.gz" -C "$pkgname-$pkgver-files"
  echo "symlinking '/usr/lib/libtinyxml2.so.10.0.0' to '/usr/lib/libtinyxml2.so.9'"
  sudo ln -s -f "/usr/lib/libtinyxml2.so.10.0.0" "/usr/lib/libtinyxml2.so.9"
}

package() {
  cd "$srcdir/$pkgname-$pkgver-files"
  install -Dm644 "usr/share/$_pkgname/trenchbroom.desktop" "$pkgdir/usr/share/applications/trenchbroom.desktop"
  install -Dm644 "usr/share/$_pkgname/icons/icon_512.png" "$pkgdir/usr/share/icons/hicolor/512x512/apps/trenchbroom.png"
  cp -rf "." "$pkgdir"
  rm -f "$pkgdir/usr/share/$_pkgname/trenchbroom.desktop"
}
