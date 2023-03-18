# Maintainer: Johannes Schindelin/Matthew J Cheetham

_realname="git-credential-manager"
pkgname=("${_realname}")
conflicts=("git-credential-manager-core")
replaces=("git-credential-manager-core")
pkgver=2.0.935
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

sha256sums=('3ce520927a4f048da19c4b9d3b449045a20a646ee941b16850be22f406f76047'
            '83c3612e34a5759c97331430f300741b0bfdae7af8ee6189452032fc16b77b80')

package() {
  prefix="$pkgdir/${MSYSTEM_PREFIX}"
  srcdir2="${srcdir}/"
  install -d -m755 "${prefix}"/bin
  install -m755 "$srcdir2"/*.{dll,exe,config} "${prefix}"/bin
  install -d -m755 "${prefix}"/doc/git-credential-manager
  install -m644 "$srcdir2"/git-credential-manager-${_realtag#v}/{README.md,LICENSE,NOTICE} "${prefix}"/doc/git-credential-manager
}
