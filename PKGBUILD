# Maintainer: jsteel <jsteel at aur.archlinux.org>

pkgname='perl-excel-template-plus'
_pkgname='Excel-Template-Plus'
pkgver='0.05'
pkgrel='2'
pkgdesc="An extension to the Excel::Template module"
arch=('any')
license=('PerlArtistic' 'GPL')
options=('!emptydirs')
depends=('perl-spreadsheet-parseexcel' 'perl-excel-template'
  'perl-moosex-param' 'perl-io-string')
url="http://search.cpan.org/dist/$_pkgname"
source=(http://search.cpan.org/CPAN/authors/id/S/ST/STEVAN/$_pkgname-$pkgver.tar.gz)
md5sums=('1d6c1c9ed09249c8433250fa6a2c1368')

build() {
  ( export PERL_MM_USE_DEFAULT=1 PERL5LIB=""                 \
      PERL_AUTOINSTALL=--skipdeps                            \
      PERL_MM_OPT="INSTALLDIRS=vendor DESTDIR='$pkgdir'"     \
      PERL_MB_OPT="--installdirs vendor --destdir '$pkgdir'" \
      MODULEBUILDRC=/dev/null

    cd "$srcdir"/$_pkgname-$pkgver

    /usr/bin/perl Makefile.PL

    make
  )
}

check() {
  cd "$srcdir"/$_pkgname-$pkgver

  ( export PERL_MM_USE_DEFAULT=1 PERL5LIB=""
    make test
  )
}

package() {
  cd "$srcdir"/$_pkgname-$pkgver

  make install
}
