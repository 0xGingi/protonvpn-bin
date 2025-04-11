# Maintainer: Zylquinal <contact@zylquinal.com>

pkgname=protonvpn-bin
pkgver=4.9.5~b0
pkgrel=1
pkgdesc="ProtonVPN for Linux"
url="https://github.com/Zylquinal/protonvpn-bin"
arch=('any')

depends=('gnome-keyring'
         'dbus-python'
         'python-gobject'
         'python-packaging'
         'python-distro'
         'python'
         'python-aiohttp'
         'python-gnupg'
         'python-bcrypt'
         'python-importlib-metadata'
         'python-pyopenssl'
         'python-requests'
         'python-pynacl'
         'python-setuptools'
         'python-keyring'
         'python-jinja'
         'python-importlib-metadata'
         'gobject-introspection'
         'networkmanager'
         'networkmanager-openvpn'
         'librsvg'
         'python-sentry_sdk'
)

optdepends=('libayatana-appindicator'
            'gnome-shell-extension-appindicator'
            'gnome-shell-extensions'
)

conflicts=('protonvpn'
           'protonvpn-cli'
           'protonvpn-gui'
)

source=("https://repo.protonvpn.com/fedora-41-unstable/proton-vpn-gtk-app/proton-vpn-gtk-app-4.9.5~b0-1.fc41.noarch.rpm"
        "https://repo.protonvpn.com/fedora-41-unstable/python3-proton-keyring-linux/python3-proton-keyring-linux-0.2.0-1.fc41.noarch.rpm"
        "https://repo.protonvpn.com/fedora-41-unstable/python3-proton-vpn-api-core/python3-proton-vpn-api-core-0.42.4-1.fc41.noarch.rpm"
        "https://repo.protonvpn.com/fedora-41-unstable/python3-proton-vpn-network-manager/python3-proton-vpn-network-manager-0.12.13-1.fc41.noarch.rpm"
        "https://repo.protonvpn.com/fedora-41-unstable/python3-proton-core/python3-proton-core-0.4.0-1.fc41.noarch.rpm"
)

sha256sums=('28a0e4b516fbe577cce9ab14bd9f904ba560aa246a03ec664ddb86f36037ea6f'
            '222d44e91f35dd7d736edd84d59e799ad4cdcf6fb87b5649fcc7e7af45e708ee'
            '9e23288bff4dc835fd313764ca06b2dd19d9afc88a7abf44cf775a62eb207d5e'
            '508fadb171a1aee3d4f1a3ebfe20a33ba0f18c6c00606dd8a14b65c29d9f2698'
            '6304599e58ccae15384f03dbd1b27f8b70414709f021ae8b559a54ceb7b54bc1')

if [[ "$CARCH" == "x86_64" ]]; then
  source+=("https://repo.protonvpn.com/fedora-41-unstable/python3-proton-vpn-local-agent/python3-proton-vpn-local-agent-1.4.5-1.fc41.x86_64.rpm")
  sha256sums+=("e90c4bb306dfb1252c524e062c559040d9df215df1457473d4c7a5795f316f71")
elif [[ "$CARCH" == "aarch64" ]]; then
  source+=("https://repo.protonvpn.com/fedora-41-unstable/python3-proton-vpn-local-agent/python3-proton-vpn-local-agent-1.4.5-1.fc41.aarch64.rpm")
  sha256sums+=("aadeb57f804907826707a9067075b0d38fae357c29a5a1cb3e5d488034a74701")
fi

package() {
    find $srcdir/ -mindepth 1 -maxdepth 1 -type d | xargs cp -r -t "$pkgdir"
    cp -a $pkgdir/usr/lib64/* $pkgdir/usr/lib
    rm -rf $pkgdir/usr/lib64
}
