# Install Edge CLI

All releases of CLI for mainnet and testnet are available on [Edge Network Files](https://files.edge.network/cli/). You can browse it to find the suitable release for your system, or find the latest version in the table below:

| Network | OS | Arch | Binary | Checksum |
|:--------|:---|:-----|:-------|:---------|
| Mainnet | Linux | x64 | [Download](https://files.edge.network/cli/mainnet/linux/x64/latest/edge) | [View](https://files.edge.network/cli/mainnet/linux/x64/latest/checksum) |
| Mainnet | Linux | arm64 | [Download](https://files.edge.network/cli/mainnet/linux/arm64/latest/edge) | [View](https://files.edge.network/cli/mainnet/linux/arm64/latest/checksum) |
| Mainnet | Mac OS | x64 | [Download](https://files.edge.network/cli/mainnet/macos/x64/latest/edge) | [View](https://files.edge.network/cli/mainnet/macos/x64/latest/checksum) |
| Mainnet | Mac OS | arm64 | [Download](https://files.edge.network/cli/mainnet/macos/arm64/latest/edge) | [View](https://files.edge.network/cli/mainnet/macos/arm64/latest/checksum) |
| Mainnet | Windows | x64 | [Download](https://files.edge.network/cli/mainnet/windows/x64/latest/edge) | [View](https://files.edge.network/cli/mainnet/windows/x64/latest/checksum) |
| Mainnet | Windows | arm64 | [Download](https://files.edge.network/cli/mainnet/windows/x64/latest/edge) | [View](https://files.edge.network/cli/mainnet/windows/x64/latest/checksum) |

You can install Edge CLI manually by downloading the binary through the browser, or by using curl/wget. After downloading the CLI binary, move it to an executable and writable path and ensure the binary itself is also executable.

For example, to download the mainnet CLI on an Ubuntu x64 host:

```bash
curl \
  -s https://files.edge.network/cli/mainnet/linux/x64/latest/edge \
  -o /usr/local/bin/edge && \
chmod +x /usr/local/bin/edge
```

You can verify your download by comparing its checksum with the one in Edge Network Files:

- On Linux, `sha256 $(which edge)`
- On Mac OS, `shasum -a 256 $(which edge)`
<!-- On Windows TBC -->

Once Edge CLI is installed, run `edge --version` to check it is usable. If the Edge CLI version is displayed without error, it's ready to use:

```
% edge --version
Edge CLI v1.5.3 (Mainnet)
```

{% hint style="info" %}
**When you download an Edge CLI binary, it's recommended to keep the original filename i.e.** `edge` **for mainnet and** `edgetest` **for testnet. This naming helps to distinguish them on your device.**
{% endhint %}

{% hint style="warning" %}
**On Mac OS, downloading the Edge CLI through a browser may cause difficulty running it due to Mac OS' security model, resulting in the message, _"edge" _is damaged and can't be opened._ If you encounter this problem, delete the downloaded binary and use** `curl` **to redownload Edge CLI, and it should work then.**
{% endhint %}

## Updating Edge CLI

After Edge CLI is installed, you can run `edge update` (or `edgetest update`) to update it in-place when a new version becomes available. This method also validates the checksum automatically, ensuring the update is successful and secure.

In order to ensure stability on your device, Edge CLI does not self-update in the background. It's recommended to check for updates periodically to ensure your CLI is up to date. You can check for a new version without updating Edge CLI by running `edge update check`. Edge CLI will also automatically check for updates in normal use.

If for whatever reason you are unable to self-update Edge CLI, or you need to change to a specific version, you can download it again from Edge Network Files following the same steps you used for the original installation.

## Next Steps

Now that Edge CLI is installed on your device, you can contribute to the network by [setting up a Host](set-up-a-host.md). For more information about CLI usage, have a look at the [Commands Overview](overview.md).
