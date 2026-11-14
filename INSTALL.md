# Install AxonPix Manager 0.51.2

Download the package for your operating system from the [release page](https://github.com/UnikAgent/axonpix-manager-downloads/releases/tag/v0.51.2). Downloads are public; access to the private development repository is not required.

All packages include Qwen3.5:0.8b and a local inference engine. Windows and Linux packages use the CPU. You can configure supported remote model APIs in **Skills & Tools** instead. Allow at least 8 GB RAM and 6 GB free disk space.

| Platform | Package | Requirements |
| --- | --- | --- |
| macOS | `.dmg` | Apple Silicon, macOS 26 or later; Intel Macs are not supported by this build |
| Windows | `Setup.exe` | Windows 10 22H2 or Windows 11, x64 |
| Linux | `.deb` | Ubuntu 22.04 x64 tested; compatible Ubuntu/Debian systems require the listed package dependencies and working bubblewrap user namespaces |

## macOS

Open the DMG and drag **AxonPix Manager** to **Applications**. Close the previous Manager before replacing it. Launch it from Applications.

This build is ad-hoc signed, not Apple-notarized. macOS may require an explicit approval in Privacy & Security. Only approve a package you intentionally downloaded from this repository; do not disable system protection globally.

## Windows

Close the previous Manager, run the installer and follow its steps. It installs for the current Windows user and preserves the existing identity and conversations. No separate Python or Ollama installation is needed.

The installer is not signed with a commercial Windows certificate; Windows may show an unknown-publisher warning. Verify the release and checksum before deciding whether to proceed.

## Linux

Install the downloaded package using the software installer, or run from its download directory:

```sh
sudo apt install ./AxonPix-Manager-0.51.2-Linux-amd64.deb
```

Open **AxonPix Manager** from the applications menu. The program is installed in `/opt/axonpix-manager`. Dependencies are installed through the system package manager; Python, Qwen and its engine are bundled.

Local inference requires bubblewrap and permitted user namespaces. If local security policy blocks them, consult your administrator rather than disabling the model's isolation. This package has no maintainer scripts and does not automatically stop, start or remove your existing installation.

## Upgrades and identities

Existing user data directories are intentionally preserved for compatibility. Never delete them just to upgrade. Back up your identity before changing computers. Packages contain no personal identity keys, credentials or conversations.

## Verify a download

Each installer has a matching `.sha256` file. Compare it with `shasum -a 256` on macOS, `sha256sum` on Linux, or `Get-FileHash -Algorithm SHA256` in Windows PowerShell. Checksums detect corruption; they do not replace trust in the publishing account.

## Validation scope

Mac and Linux package checks cover the native interface, real local Qwen inference, identity backup/restore, and blocked access to the identity key from the isolated model. Linux is also tested after extracting the final Debian package. Windows CI checks protocol tests, the packaged application and a silent installation followed by another application self-test.

These checks do not certify every hardware configuration. Start with non-sensitive test tasks.

## Interrupted tasks

After an interruption, the task stays paused. In **Messages**, choose **Review interrupted task…** and approve one recovery attempt. Choosing No leaves it paused. Enabling automatic processing does not approve recovery.
