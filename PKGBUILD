
pkgname=qarma-git
_gitname=qarma
pkgver=1.0.1
pkgrel=1
pkgdesc="A drop-in replacement clone for zenity, for easy user interfaces scripting, written in Qt4/5"
arch=('x86_64')
url="https://github.com/luebking/qarma"
license=('GPL')
depends=('qt5-base' 'qt5-x11extras')
makedepends=('git')
#provides=('qarma' 'zenity')
#conflicts=('zenity' 'qarma')
source=("git://github.com/luebking/qarma.git")
sha256sums=('SKIP')

pkgver() {
    cd ${_gitname}
    git rev-list --count HEAD
    }

build()
{
    cd $srcdir/$_gitname
    qmake-qt5
    make
    }

package() {
    cd $srcdir/$_gitname
    strip qarma
    mkdir -p $pkgdir/usr/bin
    cp qarma $pkgdir/usr/bin
    ln -s /usr/bin/qarma $pkgdir/usr/bin/zenity
    }
