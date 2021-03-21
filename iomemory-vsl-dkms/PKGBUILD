# This is an example PKGBUILD file. Use this as a start to creating your own,
# and remove these comments. For more information, see 'man PKGBUILD'.
# NOTE: Please fill out the license field for your package! If it is unknown,
# then please put 'unknown'.

# The following guidelines are specific to BZR, GIT, HG and SVN packages.
# Other VCS sources are not natively supported by makepkg yet.

# Maintainer: Daniel Browne <jairuncaloth@gmail.com>
_pkgbase=iomemory-vsl
pkgname=iomemory-vsl-dkms
pkgver=5.10.0
pkgrel=1
pkgdesc="Updated FusionIO iodrive3 driver for recent kernels."
arch=('any')
url="https://github.com/snuf/iomemory-vsl"
license=('unknown')
depends=('dkms')
makedepends=('git')
conflicts=('iomemory-vsl-git')
source=('git+https://github.com/snuf/iomemory-vsl.git')
md5sums=('SKIP')

pkgver() {
  cd "${_pkgbase}"
  printf "%s" "$(git describe --long --tags | sed 's/^v//;s/\([^-]*-g\)/r\1/;s/-/./g')"
}

package() {
  cd "${_pkgbase}"
  make dkms
}
