# Maintainer: Graham Edgecombe <graham@grahamedgecombe.com>
pkgname=linode-cli-git
epoch=1
pkgver=v1.3.2.r0.gae505f9
pkgrel=1
pkgdesc='A simple command-line interface to the Linode platform'
arch=('any')
url='https://github.com/linode/cli'
license=('GPL2' 'PerlArtistic')
depends=('perl-try-tiny' 'perl-libwww' 'perl-json' 'perl-crypt-ssleay'
         'perl-webservice-linode')
conflicts=('linode-cli')
provides=('linode-cli')
makedepends=('git')
source=("$pkgname"::'git+https://github.com/linode/cli.git')
md5sums=('SKIP')

pkgver() {
  cd "$pkgname"
  git describe --long | sed -E 's/([^-]*-g)/r\1/;s/-/./g'
}

build() {
  cd "$pkgname"
  PERL_MM_USE_DEFAULT=1 perl Makefile.PL INSTALLDIRS=vendor
  make
}

package() {
  cd "$pkgname"
  make install DESTDIR="$pkgdir"
}
