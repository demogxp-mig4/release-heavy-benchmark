# Release-Heavy Benchmark (`demogxp/release-heavy-benchmark`)

Synthetic benchmark repository for stress-testing the **GHEC Consultant Suite**:
- **Scale-Adaptive Slicer (`large-releases` tier):** Exceeds the `10 GiB` (`10,737,418,240` bytes) cumulative release asset threshold so `classifyRepository()` assigns `tier: "large-releases"`, `useGei: true`, `skipReleases: true`, and `useReleaseFallback: true`.
- **Multi-Page Pagination:** Contains **42 GitHub Releases** and **42 Git tags** (`v1.0.0`–`v1.19.0`, `v2.0.0-rc.1`, `v2.0.0-rc.2`, `v2.0.0`–`v2.19.0`) across `main` and `release/v1`, ensuring multi-page REST discovery (`per_page > 30`).
- **Duplex Release Asset Streaming:** Exercises `ReleasesMigrationModule` and `transferReleaseAsset()` across multi-gigabyte binary streams (`application/octet-stream`, `application/gzip`, `application/zip`) and `.sha256` sidecars without local disk buffering.
