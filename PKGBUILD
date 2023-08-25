# Mali userspace driver for HiKey960, Wayland
# Maintainer: Hyeseon Oh <okw1003@gmail.com>

buildarch=12
pkgname=mali-hikey960-wayland
pkgver=r16p0_01rel0
pkgrel=1
arch=('aarch64' 'armv7h')
options=('!strip')
url="https://developer.arm.com/downloads/-/mali-drivers/user-space"
license=('custom')
source=('mali_G71_r16p0-01rel0_linux_wayland_1.tar.gz::https://developer.arm.com/-/media/Files/downloads/mali-drivers/user-space/HiKey%20960/mali_G71_r16p0-01rel0_linux_wayland_1.tar.gz?rev=97b69ac1ddbd45948999da2613920d94&revision=97b69ac1-ddbd-4594-8999-da2613920d94')
md5sums=('5df76735014ff8152a462f5710167350')

package() {
	install -Dm644 "$srcdir/END_USER_LICENCE_AGREEMENT.txt" "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
	mkdir -p "$pkgdir/usr/lib"
	case $CARCH in
		aarch64)
			# lib64 contains AArch64 binaries
			cp -d --preserve=mode "$srcdir/wayland-drm/lib64/"* "$pkgdir/usr/lib/"
			;;
		armv7h)
			# lib contains ARMv7 binaries
			cp -d --preserve=mode "$srcdir/wayland-drm/lib/"* "$pkgdir/usr/lib/"
			;;
	esac
}
