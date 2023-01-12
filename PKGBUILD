pkgname=nginx-config-grug
pkgver=0.0.1
pkgver() {
  printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}
pkgrel=1
arch=('any')
pkgdesc="nginx config for grug"
url="https://git.grug.se/admin/nginx-config-grug"
license=('MIT')
makedepends=()
provides=()
conflicts=()
install="script.install"
package() {
  depends+=(nginx)
  depends+=(nginx-mod-brotli)
  depends+=(nginx-mod-njs)
  depends+=(nginx-mod-cache_purge)
  depends+=(server-config-grug)
  mkdir -p "$pkgdir/etc/systemd/system/nginx.service.d"
  cp override.conf "$pkgdir/etc/systemd/system/nginx.service.d/"
  cp nginx-reload.path "$pkgdir/etc/systemd/system/"
  cp nginx-reload.service "$pkgdir/etc/systemd/system/"
  cp -r nginx-config-grug "$pkgdir/etc/nginx-config-grug"
}
