# Contributor: Alfredo Palhares <masterkorp at masterkorp dot net>
_gemname=svn2git
pkgname=ruby-$_gemname
pkgver=2.2.2
pkgrel=2
pkgdesc="Tool written in ruby to convert svn repos to git"
arch=(any)
url="https://github.com/nirvdrum/svn2git"
# This tool has nothing to do with svn2git-git in the AUR
# But yet they share the same name
conflicts=('svn2git-git' 'svn2git')
license=('MIT')
depends=('ruby' 'git')

makedepends=(rubygems)
source=(https://github.com/nirvdrum/svn2git/tarball/v$pkgver)
md5sums=('5de8165aaeeced1da23e2cf73b860183')

build() {
  cd $srcdir/nirvdrum-svn2git-*
  gem build svn2git.gemspec
}
package() {
  cd $srcdir/nirvdrum-svn2git-*
  local _gemdir="$(ruby -rubygems -e'puts Gem.default_dir')"
  gem install --ignore-dependencies --no-user-install -i "$pkgdir$_gemdir" -n "$pkgdir/usr/bin" $_gemname-$pkgver.gem
}
