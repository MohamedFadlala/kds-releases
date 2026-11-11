# kds-releases

## Install KDS on Linux Mint

For 64-bit Intel or AMD computers, open Terminal and run:

```bash
version=0.1.32
package="KDS-${version}-linux-amd64.deb"
curl --fail --location --output "/tmp/$package" \
  "https://github.com/MohamedFadlala/kds-releases/releases/download/linux-$version/$package" &&
  sudo apt install "/tmp/$package"
```

Open **KDS** from the application menu or run `holool-kds`. To upgrade, repeat the command with a newer version that offers a `.deb` on the [releases page](https://github.com/MohamedFadlala/kds-releases/releases).

Launch KDS as your normal desktop user. Only installation needs `sudo`. Version 0.1.32 fixes Linux machine identification used by activation and trials.

If launching reports that the SUID sandbox helper is configured incorrectly, restore its installed permissions and launch again:

```bash
sudo chown root:root /opt/KDS/chrome-sandbox
sudo chmod 4755 /opt/KDS/chrome-sandbox
holool-kds
```
