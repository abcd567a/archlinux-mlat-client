## Contributor: abcd567
## Maintainer: abcd567

pkgname=mlat-client
url=https://github.com/mutability/mlat-client
pkgver=latest
pkgrel=1
arch=('i686' 'amd64' 'x86_64' 'arm6' 'arm7' 'arm8' 'armhf' 'arm64' 'aarch64')

makedepends=(
  'git'
  'fakeroot'
  'python'
  'python-setuptools'
  'python-build'
  'python-installer'
  'python-wheel'
)

depends=('python')

source=('mlat-client::git+https://github.com/mutability/mlat-client.git')

md5sums=('SKIP')

pkgver (){
cd ${srcdir}/mlat-client
git describe --tags
}

build() {
  cd ${srcdir}/mlat-client
  python -m build --wheel --no-isolation
}

package() {
  cd ${srcdir}/mlat-client
  python -m installer --destdir="${pkgdir}" dist/*.whl
  install -Dm755 ${pkgdir}/usr/bin/fa-mlat-client  ${pkgdir}/usr/lib/piaware/helpers/fa-mlat-client
}

