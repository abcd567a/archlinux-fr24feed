#Contributor: abcd567
# Maintainer: abcd567 
# 
pkgname=fr24feed
pkgver=1.0.44
pkgrel=0

license=('GPL')
pkgdesc='Flightradar24 Feeder (fr24feed)'
arch=('amd64' 'x86_64' 'i386' 'i686' 'armhf' 'arm64' 'aarch64' 'armv6h' 'armv7h' 'armv7l' 'armv8')
url='https://www.flightradar24.com/'
depends=('bash')

install=fr24feed.install
source=('init-functions')

source_x86_64=("https://repo-feed.flightradar24.com/linux_binaries/fr24feed_1.0.44-0_amd64.deb")
source_i686=("https://repo-feed.flightradar24.com/linux_binaries/fr24feed_1.0.44-0_i386.deb")
source_armv6h=("https://repo-feed.flightradar24.com/rpi_binaries/fr24feed_1.0.44-0_armhf.deb")
source_armv7h=("https://repo-feed.flightradar24.com/rpi_binaries/fr24feed_1.0.44-0_armhf.deb")
source_aarch64=("https://repo-feed.flightradar24.com/rpi_binaries/fr24feed_1.0.44-0_arm64.deb")

sha256sums=('SKIP')
sha256sums_x86_64=('SKIP')
sha256sums_i686=('SKIP')
sha256sums_armv6h=('SKIP')
sha256sums_armv7h=('SKIP')
sha256sums_aarch64=('SKIP')

prepare() {
  tar -xf data.tar.gz
}

package() {
  install -Dm755  ${srcdir}/usr/bin/fr24feed  ${pkgdir}/usr/bin/fr24feed
  install -Dm755  ${srcdir}/usr/bin/fr24feed-status  ${pkgdir}/usr/bin/fr24feed-status
  install -Dm644  ${srcdir}/etc/fr24feed.ini ${pkgdir}/etc/fr24feed.ini
  install -Dm644  ${srcdir}/etc/systemd/system/fr24feed.service ${pkgdir}/etc/systemd/system/fr24feed.service
  sed -i '/install_dump1090.sh/d' ${pkgdir}/etc/systemd/system/fr24feed.service
  install -Dm755  ${srcdir}/usr/lib/fr24/create_missing_directories.sh ${pkgdir}/usr/lib/fr24/create_missing_directories.sh  
  install -Dm755  ${srcdir}/usr/lib/fr24/unregister_kernel_modules.sh ${pkgdir}/usr/lib/fr24/unregister_kernel_modules.sh
  install -Dm755  ${srcdir}/init-functions ${pkgdir}/usr/lib/fr24/init-functions
  sed -i 's/lib\/lsb\/init-functions/usr\/lib\/fr24\/init-functions/' ${pkgdir}/usr/bin/fr24feed-status
}

