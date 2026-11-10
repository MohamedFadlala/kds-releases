# kds-releases

## Install KDS on Linux Mint

For 64-bit Intel or AMD computers, open Terminal and run:

```bash
version=0.1.31
package="KDS-${version}-linux-amd64.deb"
curl --fail --location --output "/tmp/$package" \
  "https://github.com/MohamedFadlala/kds-releases/releases/download/linux-$version/$package" &&
  sudo apt install "/tmp/$package"
```

Open **KDS** from the application menu or run `holool-kds`. To upgrade, repeat the command with a newer version that offers a `.deb` on the [releases page](https://github.com/MohamedFadlala/kds-releases/releases).
