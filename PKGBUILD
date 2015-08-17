# Maintainer: Felix Yan <felixonmars@gmail.com>

_pkgname=jieba
pkgname=python2-$_pkgname-git
pkgver=20121001
pkgrel=1
pkgdesc="JieBa Chinese Words Segment Library based on HMM model for Python"
arch=('any')
url=('https://github.com/fxsjy/jieba')
license=("MIT")
depends=('python2')

_gitroot="git://github.com/fxsjy/jieba.git"
_gitname=$_pkgname

build() {
  cd "$srcdir"
  msg "Connecting to github.com GIT server...."

  if [ -d "$srcdir"/$_gitname ] ; then
    cd $_gitname && git pull origin
    msg "The local files are updated."
  else
    git clone $_gitroot
  fi

  msg "GIT checkout done or server timeout"
}

package() {
  cd "$srcdir"/$_gitname
  python2 setup.py install --root="$pkgdir"
}
