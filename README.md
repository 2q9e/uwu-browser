# Uwu Browser

An independent browser fork with an original soft-pink design, based on the
Chromium open-source project. The source tree is kept in [`src/`](src/).

## Authors and credits

- **Fork maintainer:** [@2q9e](https://github.com/2q9e). Fork-specific changes
  are recorded in this repository's commit history.
- **Upstream project:** Chromium contributors are listed in
  [`src/AUTHORS`](src/AUTHORS); source copyright and attribution notices are
  retained. That file is the upstream contributor roster, not a complete list
  of contributors to this fork.
- **Project artwork:** the Uwu Browser icon and wordmark are original artwork
  for this fork.

This project is independent and is not affiliated with or endorsed by Google
LLC or the Chromium project.

## Upstream project

- [Chromium project](https://www.chromium.org/)
- [Chromium source repository](https://github.com/chromium/chromium)

## Licenses and third-party credits

The Chromium source license is in [`src/LICENSE`](src/LICENSE). The ChromiumOS
license is in [`src/LICENSE.chromium_os`](src/LICENSE.chromium_os). Components
in [`src/third_party/`](src/third_party/) may have their own licenses and
notices; check the applicable files before reusing or distributing them. Keep
the required copyright and license notices with redistributed source and
binary builds. A built browser lists shipped dependency credits at
`chrome://credits`.

## Names and trademarks

The product uses a distinct name and original icon. “Chromium” is used here to
identify the upstream source project and its contributors. Google lists
Chromium as a trademark and advises against using its marks in product names
or imitating its visual identity. Attribution and open-source licensing do not
grant trademark permission. Review [Google's trademark list](https://about.google/brand-resource-center/trademark-list/)
and [brand guidance](https://about.google/brand-resource-center/guidance/)
before distributing a build. No README wording can guarantee protection from a
legal claim.

## Source documentation

See the upstream [`src/README.md`](src/README.md) and
[`src/docs/README.md`](src/docs/README.md) for source and developer
documentation.

## Platform support and builds

The fork retains Chromium's native desktop build paths:

| Platform | Build notes |
| --- | --- |
| Linux (including Fedora and Arch) | Use the [Linux build guide](src/docs/linux/build_instructions.md), including its [Fedora](src/docs/linux/build_instructions.md#fedora) and [Arch](src/docs/linux/build_instructions.md#arch-linux) dependency notes. Chromium says non-Ubuntu distributions are mostly unsupported upstream, so package names and builds can vary by release. |
| Windows | Use the [Windows build guide](src/docs/windows_build_instructions.md). It documents the browser and `mini_installer` targets. |
| macOS (Intel or Apple silicon) | Use the [macOS build guide](src/docs/mac_build_instructions.md). A Mac with Xcode and the macOS SDK is required; the native build produces an `.app` bundle. |

These are native source-build paths; this fork has not been independently
verified on every listed operating system. The Windows guide includes a
self-contained installer target, and Linux packaging uses Chromium's upstream
tools. This repository does not set up Fedora or Arch package repositories.
The macOS build creates an app bundle; distributing it publicly requires a
separate signing and notarization flow. See [Apple's distribution guidance](https://developer.apple.com/macos/distribution/).

### Build this fork

Install Chromium's `depot_tools`, then clone this repository. From the checkout
root, sync Chromium's pinned dependencies without replacing the fork's source
tree:

```shell
git clone https://github.com/2q9e/uwu-browser.git uwu-browser
cd uwu-browser
gclient config --name=src --unmanaged https://github.com/2q9e/uwu-browser.git
gclient sync --nohooks
```

Install the prerequisites for your host using the platform guide above. Then
from the `src/` directory, run the hooks and build the browser:

```shell
cd src
gclient runhooks
gn gen out/Default
autoninja -C out/Default chrome
```

Run each build on its target operating system; the macOS instructions require
a Mac, and the Windows instructions require Windows and Visual Studio. The
Windows guide explains how to build its installer target; macOS packaging and
signing are separate from building the `.app` bundle.
