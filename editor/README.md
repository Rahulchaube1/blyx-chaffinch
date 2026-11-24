# Blyx Chaffinch

Reconcile sorted collection snapshots without materializing their union.

This extension includes the Blyx Chaffinch 0.2.0 source, a runnable example and completions for its public functions. It uses the Blyx Language extension for syntax highlighting and execution.

## Reduce sparse worker gradients

Merge sorted sparse gradient sums from two workers, coalesce duplicate coordinates and normalize by the global example count. [Commands and worked example](https://github.com/Rahulchaube1/blyx-chaffinch/blob/v0.2.0/SCALE.md) · [Measurements and source data](https://www.blyx-lang.space/articles/training-in-factors)

## Run in the editor

1. Open an empty file named `chaffinch-demo.blyx`.
2. Type `blyx-chaffinch-demo` and select **Chaffinch — runnable example**. You can also use **Snippets: Fill File with Snippet**.
3. Choose **Blyx: Run File** from the command palette. Change an argument near the end of `fn main()` to try another input.

Expected output

```text
1
1
2
1
```

## Use Chaffinch in a project

Extract the starter into a new folder. It contains `main.blyx`, the licensed framework source in `vendor/chaffinch`, and a VS Code task. With the Blyx 0.2.1 compiler and host toolchain installed, run `blyxc native-run main.blyx` from that folder. Type `blyx-chaffinch-` in a Blyx file to see the framework completions. [Download the starter ZIP](https://github.com/Rahulchaube1/blyx-chaffinch/releases/download/v0.2.0/blyx-chaffinch-starter-0.2.0.zip)

[API and input requirements](https://www.blyx-lang.space/packages/chaffinch) · [Framework source](https://github.com/Rahulchaube1/blyx-chaffinch/tree/v0.2.0) · [Report an issue](https://github.com/Rahulchaube1/blyx-chaffinch/issues)

[GitHub Sponsors](https://github.com/sponsors/Rahulchaube1) · [Buy Me a Coffee](https://buymeacoffee.com/rahulchaube)
