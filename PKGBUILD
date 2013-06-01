pkgname=packer-guildencrantz-git
pkgver=0.280.71d98de
pkgrel=1
pkgdesc="Bash wrapper for pacman and the AUR"
url="https://github.com/guildencrantz/packer"
license="GPL"
arch=('any')
makedepends=('git')
depends=('grep' 'sed' 'bash' 'curl' 'pacman' 'jshon' 'sudo')
conflicts=('packer')
optdepends=('customizepkg: apply customizepkg modifications')
source=("${pkgname}::git+${url}.git#branch=master")
md5sums=('SKIP')

pkgver () {
  cd "${srcdir}/${pkgname}"
  echo "0.$(git rev-list --count HEAD).$(git describe --always | sed 's|-|.|g')"
}

package() {
  cd "${srcdir}/${pkgname}"
  mkdir -p ${pkgdir}/usr/bin
  mkdir -p ${pkgdir}/usr/share/man/man8
  install -m 755 packer ${pkgdir}/usr/bin/packer
  install -m 644 packer.8 ${pkgdir}/usr/share/man/man8/packer.8
}
