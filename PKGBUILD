# Maintainer: Johannes Schindelin/Matthew J Cheetham

_realname="git-credential-manager"
pkgname=("${_realname}")
conflicts=("git-credential-manager-core")
replaces=("git-credential-manager-core")
pkgver=2.1.2
pkgrel=1
_realver=$pkgver
_realtag=v${pkgver}
pkgdesc="Credential Manager for Git"
install=git-credential-manager.install
arch=('any')
project_url="https://github.com/git-ecosystem/git-credential-manager"
zip_url="${project_url}/releases/download/${_realtag}/gcm-win-x86-${_realver}.zip"
src_zip_url="${project_url}/archive/${_realtag}.zip"
license=('MIT')
groups=('VCS')
options=('!strip')

source=("${zip_url}" "$src_zip_url")

sha256sums=('14e0fae94c14ef100544dbb77aad0d59238d58afc6edfae4160f6ae6cb2588e2'
            '57506f80e741dc7b98e03c78bca42c5db4014a52a2c985499ea02c17ced3af12')

package() {
  prefix="$pkgdir/${MSYSTEM_PREFIX}"
  srcdir2="${srcdir}/"
  install -d -m755 "${prefix}"/bin
  install -m755 "$srcdir2"/*.{dll,exe,config} "${prefix}"/bin
  install -d -m755 "${prefix}"/doc/git-credential-manager
  install -m644 "$srcdir2"/git-credential-manager-${_realtag#v}/{README.md,LICENSE,NOTICE} "${prefix}"/doc/git-credential-manager
}
