# kds-releases

## Install KDS on Linux Mint

For 64-bit Intel or AMD computers, open Terminal and run:

```bash
version=0.1.33
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

## Printing on Linux Mint

For Xprinter USB receipt printers, install the Linux receipt driver matching your model from [Xprinter's official downloads](https://www.xprintertech.com/download/receipt-printer-series). Add the printer in Mint's **Printers** settings and print a system test page. Then select that queue in KDS under **System / USB printer setup**. The current thermal layout uses 80 mm paper. A raw CUPS queue needs a suitable driver for system printing.

For ESC/POS Ethernet printers, assign the printer's address directly in KDS, for example `tcp://192.168.1.50:9100`. Configure the cashier and each kitchen station, then send a test ticket. KDS renders Arabic text before sending raster commands to the printer.

Version 0.1.33 fixes Linux receipt page sizing, communication icons, and printer setup wording. Linux automatic updates are disabled. Upgrade using the terminal installation command above.

The full regression suite passed on Ubuntu 22.04. The installed package also passed startup, trial storage, owner login, CUPS customer receipts and kitchen tickets, long receipts, network ESC/POS output, communication window and tray, LAN endpoint, and clean shutdown checks on Ubuntu 22.04 and 24.04. [GitHub Actions verification](https://github.com/MohamedFadlala/Holool-KDS/actions/runs/43109398779)

CUPS was tested with a virtual printer and network printing with a local receiver. Physical Xprinter USB drivers, paper feed, print quality, and cutting still require a test on your printer.
