# Kate legacy offline compatibility trial

Unofficial repack of Debian Buster Kate 18.08.0 binaries for amd64 / glibc >= 2.28. Not an official KDE, Debian or UnionTech release. **Actual UOS desktop compatibility has not been verified.**

Download the complete `.deb` from this repository's Releases, alongside its checksum and installation guide. No split-volume reconstruction is required.

## Run without root

```sh
mkdir -p "$HOME/apps/kate-offline"
dpkg-deb -x kate-offline-legacy_18.08.0-1uoscompat1_amd64.deb "$HOME/apps/kate-offline"
"$HOME/apps/kate-offline/opt/kate-offline/start-kate.sh"
```

Before extraction verify SHA256:
`674fe204a68e6c084ac709c4cd8656d92d480a595713d11dc3ff2504771acd14`

The package contains private runtime libraries, resources and a launcher under `/opt/kate-offline`. No maintainer scripts, system library overwrites, services or apt source changes. Configuration and cache use separate `kate-offline-18` subdirectories.

## Checks and limitations

- Debian 10 glibc 2.28 extracted userland: version/startup smoke tests passed.
- Cloud Xvfb GUI: SQL highlighting and Chinese text rendering inspected.
- Not tested on a real UOS 20 desktop, its signature enforcement, input method, printer or all plugins.
- Old, end-of-life software: not recommended for untrusted documents or network-facing use. Follow your organization's software policy. No warranty.

## Sources and licenses

Original component copyright notices and license texts are retained inside the binary bundle. The accompanying source archive in Releases contains exact-version Debian source packages (upstream archives, Debian patches and build/install scripts), plus the custom launcher and control file. It covers the acquisition/test environment superset, not only the smaller installed runtime. No upstream sources were changed. Components retain their own licenses; the custom launcher and control file have an MIT permission notice in the source archive.

Official upstream: https://invent.kde.org/utilities/kate

Debian archive: https://archive.debian.org/debian/
