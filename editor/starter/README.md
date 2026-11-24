# Chaffinch starter

Reconcile sorted collection snapshots without materializing their union.

Open the extracted folder in VS Code. With Blyx 0.2.1 and its host toolchain installed, choose **Terminal → Run Task → Run Chaffinch** or run the following command in this directory.

```sh
blyxc native-run main.blyx
```

Expected output

```text
1
1
2
1
```

The vendor directory contains the framework source for 0.1.0 and its license texts. [Read the API guide](https://www.blyx-lang.space/packages/chaffinch) · [View the release](https://github.com/Rahulchaube1/blyx-chaffinch/releases/tag/v0.2.0)

## Scale example

Merge sorted sparse gradient sums from two workers, coalesce duplicate coordinates and normalize by the global example count. Install this compiler and run the editable example from the starter directory.

~~~sh
cargo install --locked --git https://github.com/Rahulchaube1/blyxxxx --rev 120d6b6ec6df09ff018d7c18752fb3297b5e629d blyxc
blyxc native-run scale_example.blyx
~~~
