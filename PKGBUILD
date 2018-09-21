# Maintainer: Jan Boelsche <jan@lagomorph.de>

pkgname=ssb-electroparty-chromium-keypair-git
pkgver=1.0.0.r2.99f9854
pkgrel=1
pkgdesc="Provides ep-set-keypair to set a keypair in Chromium's localStorage"
arch=('any')
url=""
license=('GPL')
groups=()
depends=('')
makedepends=('git' 'npm')
provides=("${pkgname%-git}")
conflicts=("${pkgname%-git}")
replaces=()
backup=()
options=()

source=("git+ssh://git@github.com/regular/${pkgname%-git}.git")
sha256sums=('SKIP')

pkgver() {
	cd "$srcdir/${pkgname%-git}"
  printf "%s.r%s.%s" "$(node -e 'console.log(require("./package.json").version)')" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

package () {
	cd "$srcdir/${pkgname%-git}"
  source "$HOME/.nvm/nvm.sh"
  nvm use 10.8.0
  local _npmdir="${pkgdir}/usr/lib/node_modules/"
  mkdir -p $_npmdir
  npm install -g --prefix "${pkgdir}/usr" "regular/${pkgname%-git}"
}
