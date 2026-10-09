pkgname=kubeterm-bin
pkgver=2.8.2
pkgrel=1
pkgdesc="Kubernetes monitoring and management desktop client"
arch=('x86_64')
url="https://github.com/kbterm/kubeterm"
license=('LicenseRef-kubeterm')
depends=('gtk3' 'libsecret' 'libepoxy' 'xdg-utils')
provides=('kubeterm')
conflicts=('kubeterm')
options=('!strip' '!debug')
source=("https://github.com/kbterm/kubeterm/releases/download/v$pkgver/kubeterm-$pkgver-x86_64.deb")
sha256sums=('b11c84c7e4b9bc8f2bebff7282fe81ef1b893475f0ef3e679f2c76a9759fe87d')

package() {
  bsdtar -xf data.tar.zst -C "$pkgdir"
  chmod -R go-w "$pkgdir"
  install -d "$pkgdir/usr/bin"
  local bin=$(cd "$pkgdir" && find . -type f -path "*/kubeterm/kubeterm" -print -quit)
  ln -s "${bin#.}" "$pkgdir/usr/bin/kubeterm"
}
