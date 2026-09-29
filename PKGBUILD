pkgname=kubeterm-bin
pkgver=2.8.1
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
sha256sums=('c5422a610fad5725ffebac17497c3b5201dac4d131f81cb77eac057371003af4')

package() {
  bsdtar -xf data.tar.zst -C "$pkgdir"
  chmod -R go-w "$pkgdir"
  install -d "$pkgdir/usr/bin"
  local bin=$(cd "$pkgdir" && find . -type f -path "*/kubeterm/kubeterm" -print -quit)
  ln -s "${bin#.}" "$pkgdir/usr/bin/kubeterm"
}
