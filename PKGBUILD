pkgname=nginx-config-grug
pkgver() {
  # Use number of revisions and hash as version
  cd "$pkgname"
  printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}
pkgrel=1
arch=('any')
pkgdesc="nginx config for grug"
url="https://git.grug.se/admin/nginx-config-grug"
license=('MIT')
depends=('nginx' 'nginx-mod-brotli' 'nginx-mod-njs' 'nginx-mod-cache_purge' 'server-config-grug')
makedepends=()
provides=()
conflicts=()
install="script.install"
package() {
  mkdir -p "$pkgdir/etc/systemd/system/nginx.service.d"
  cp override.conf "$pkgdir/etc/systemd/system/nginx.service.d/"
  cp nginx-reload.path "$pkgdir/etc/systemd/system/"
  cp nginx-reload.service "$pkgdir/etc/systemd/system/"
  cp -r nginx-config-grug "$pkgdir/etc/nginx-config-grug"
}