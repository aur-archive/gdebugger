# Maintainer: Lukas Jirkovsky <l.jirkovsky@gmail.com>
pkgname=gdebugger
pkgver=6.2.438
pkgrel=4
pkgdesc="An advanced OpenGL and OpenCL debugger, profiler and memory analyzer"
arch=('i686' 'x86_64')
url="http://developer.amd.com/tools/heterogeneous-computing/amd-gdebugger/"
license=('custom')
depends=('libpng12' 'libgl' 'libcl')
options=(!strip)

# the sources must be manually downloaded from:
#   http://developer.amd.com/tools/heterogeneous-computing/amd-gdebugger/

if [ "$CARCH" = "i686" ]; then
  _arch=x86
  source=(gDEBugger_LNX_6.2_32.tar.gz \
          gDEBugger.sh gdebugger.png gdebugger.desktop)
  md5sums=('61542aa500d93f4389ab1eaaeb0cb3de'
           '278d60ac5d8f04003488e2e871f2b2b0'
           '7236dccfd1dc47aec9812fb449b243d2'
           'e0f9de6f04a29be8ff8b5deae6bb964f')
else
  _arch=x86_64
  source=(gDEBugger_LNX6.2_64.tar.gz \
          gDEBugger.sh gdebugger.png gdebugger.desktop)
  md5sums=('9c2e9f7ee425cc9279b7f99d19e80be6'
           '278d60ac5d8f04003488e2e871f2b2b0'
           '7236dccfd1dc47aec9812fb449b243d2'
           'e0f9de6f04a29be8ff8b5deae6bb964f')
fi

package() {
  install -d -m755 "$pkgdir/opt"
  cp -a gDEBugger$pkgver-$_arch  "$pkgdir/opt/gDEBugger"

  install -D -m755 "gDEBugger.sh" "$pkgdir/usr/bin/gDEBugger"
  install -D -m755 "gdebugger.png" "$pkgdir/usr/share/pixmaps/gdebugger.png"
  install -D -m755 "gdebugger.desktop" "$pkgdir/usr/share/applications/gdebugger.desktop"
  install -D -m644 "gDEBugger$pkgver-$_arch/Legal/EndUserLicenseAgreement.htm" "$pkgdir/usr/share/licenses/$pkgname/EULA.htm"
}

# vim:set ts=2 sw=2 et:
