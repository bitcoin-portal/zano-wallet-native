# zano-wallet-native

Release host for the prebuilt Zano wallet2 static libraries that `zano-wallet-sys` links. There is no source code here.

- **Built by** the `Native prebuilts` workflow of `bitcoin-portal/zano-wallet-manager`, from the Zano commit and build recipe pinned there. A release is never edited by hand.
- **One release per build:** `native-<fp16>`, where `fp16` is the first 16 hex digits of the fingerprint of `zano-wallet-sys`'s shim sources and build recipe. That rev's `build.rs` downloads exactly that release.
- **Assets:**
  - `zano-wallet-native-<rust-target>.tar.gz`, one per target: Zano's wallet libraries, Boost, OpenSSL and the compiled `wallet2_bridge` shim;
  - `SHA256SUMS`.
- **Verification:** releases are immutable, so their assets cannot be replaced after publishing. `build.rs` refuses a mutable release, checks every archive against `SHA256SUMS`, and checks the archive's `MANIFEST` target and fingerprint before linking.

## Licenses

The archives contain third-party code under its own licenses: Zano (and the CryptoNote/Monero code it derives from), Boost and OpenSSL. Each archive ships their license texts in `THIRD_PARTY_LICENSES`.
