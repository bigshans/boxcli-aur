# Maintainer: Zach Zundel <me+aur at zachzundel dot com>
# Contributor: Christian Sarazin <archlinux at offlinehoster dot de>
pkgname=boxcli-git
pkgver=2.9.0
pkgrel=1
epoch=1
arch=('any')
pkgdesc="The CLI for Box.com"
url="https://box.com"
license=('Apache')
makedepends=('git' 'nodejs>=8.0.0' 'npm')
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
    tar xvf box-v${pkgver}-linux-x64.tar.gz --directory "$pkgdir"/usr/lib
    ln -sf /usr/lib/box/bin/box "$pkgdir"/usr/bin/box
}
