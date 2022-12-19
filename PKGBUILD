# Maintainer: bigshans <me+aur at bigshans dot com>
# Contributor: Christian Sarazin <archlinux at offlinehoster dot de>
pkgname=boxcli-git
pkgver=3.6.0
pkgrel=1
epoch=1
arch=('any')
pkgdesc="The CLI for Box.com"
url="https://box.com"
license=('Apache')
makedepends=('git' 'npm')
depends=('nodejs>=8.0.0')
provides=('box')
options=()
install=
source=("git+https://www.github.com/box/boxcli")
md5sums=('SKIP')

build() {
	cd "$srcdir"/boxcli 
    npm install
    ./node_modules/.bin/oclif-dev pack --targets=linux-x64
}

package() {
    cd "$srcdir"/boxcli/dist/box-v${pkgver}
    install -d "$pkgdir"/usr/lib
    install -d "$pkgdir"/usr/bin
    tar xvf box-v${pkgver}.tar.gz --directory "$pkgdir"/usr/lib
    ln -sf /usr/lib/box/bin/box "$pkgdir"/usr/bin/box
}
