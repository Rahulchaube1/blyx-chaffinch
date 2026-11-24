<img src="assets/logo.png" width="112" height="112" alt="A rose-breasted chaffinch shows a blue-grey crown and double white wing bars.">

# Chaffinch

Reconcile sorted collection snapshots without materializing their union. This Blyx workflow framework is part of the collections and storage collection.

A duplicate row should not look like a newly added key. Compare distinct sets and report repeated occurrences separately. [Python, grouping consecutive keys](https://docs.python.org/3/library/itertools.html#itertools.groupby)

## Reduce sparse worker gradients

Merge sorted sparse gradient sums from two workers, coalesce duplicate coordinates and normalize by the global example count. [Commands and worked example](https://github.com/Rahulchaube1/blyx-chaffinch/blob/v0.2.0/SCALE.md) · [Measurements and source data](https://www.blyx-lang.space/articles/training-in-factors)

## Editor extension

Install **RahulChaube.blyx-chaffinch** to run the worked example and use the framework’s function completions in a Blyx file. Open an empty `.blyx` file, enter `blyx-chaffinch-demo`, then choose **Blyx: Run File**. [Editor downloads](https://www.blyx-lang.space/packages/chaffinch#editor) · [Download the extension](https://github.com/Rahulchaube1/blyx-chaffinch/releases/download/v0.2.0/blyx-chaffinch-0.2.0.vsix) · [Starter with framework source](https://github.com/Rahulchaube1/blyx-chaffinch/releases/download/v0.2.0/blyx-chaffinch-starter-0.2.0.zip)

## Install and run

Install [Blyx 0.2.1](https://www.blyx-lang.space/download) with a Rust toolchain and host linker for native builds.

```sh
git clone --depth 1 --branch v0.2.0 https://github.com/Rahulchaube1/blyx-chaffinch.git
cd blyx-chaffinch
blyxc native-run example.blyx
blyxc native-run tests.blyx
```

[Run the editable browser example](https://www.blyx-lang.space/play?example=package-chaffinch) · [Package page](https://www.blyx-lang.space/packages/chaffinch) · [Handbook](https://doc.blyx-lang.space/guide/chaffinch)

## Import the module

Run this in the directory containing your application's entry file.

```sh
git clone --depth 1 --branch v0.2.0 https://github.com/Rahulchaube1/blyx-chaffinch.git vendor/chaffinch
```

```blyx
use vendor::chaffinch::chaffinch;

fn main() {
    let old = [1, 1, 2, 4];
    let fresh = [2, 2, 3, 4];
    let result = chaffinch_reconcile(old, fresh);
    if len(result) == 0 { println!("invalid"); return; }
    let mut i = 0;
    while i < len(result) {
        println!(at(result, i));
        i += 1;
    }
}
```

Expected output

```text
1
1
2
1
```

## API

`chaffinch_reconcile(old, fresh)`

Returns [added unique keys, removed unique keys, retained keys, duplicate occurrences in the new snapshot]. Inputs are sorted, allowing forward-only scans. Invalid arguments and nonfinite results return an empty vector. Integers carried in numeric vectors use the exact range from −(2^53−1) to 2^53−1.

| Argument | Domain |
| --- | --- |
| old | Vector of values, each a exact signed integer |
| fresh | Vector of values, each a exact signed integer |

## Run the command-line project

Run the example with your own numbers. Vector arguments accept up to 16 comma-separated entries; use `[]` for an empty vector. The imported API accepts longer vectors. Invalid arguments return a nonzero exit status.

```sh
blyxc native-run project.blyx -- "1,1,2,4" "2,2,3,4"
```

## Libraries

- [SortRuns](https://github.com/Rahulchaube1/blyx-sortruns/tree/v0.1.0) — Summarize equal-value runs in a nondecreasing integer stream.
- [MergeCounts](https://github.com/Rahulchaube1/blyx-mergecounts/tree/v0.1.0) — Count unique keys shared or exclusive to two sorted streams.

This release includes identical copies of both library modules so a tagged clone can build offline.

## Verification and contributions

The regression suite in [tests.blyx](tests.blyx) checks the example, boundary cases and invalid inputs. Include a short reproducer and your compiler version in [an issue](https://github.com/Rahulchaube1/blyx-chaffinch/issues). The source is dual-licensed under [MIT](LICENSE-MIT) or [Apache-2.0](LICENSE-APACHE). The [artwork notice](assets/NOTICE.txt) records credits for earlier editions.

## Connect with Rahul Chaube

[Portfolio](https://www.rahulchaube1.com/) · [GitHub](https://github.com/Rahulchaube1) · [LinkedIn](https://www.linkedin.com/in/rahulchaube1) · [Hugging Face](https://huggingface.co/oncody) · [X](https://x.com/RahulChaube_) · [EverestQ](https://www.everestqai.com/) · [Contact](https://www.rahulchaube1.com/contact)

[Blyx website](https://www.blyx-lang.space/) · [BlyxTorch](https://www.blyx-lang.space/packages/blyxtorch) · [Handbook](https://doc.blyx-lang.space/) · [Community](https://www.blyx-lang.space/community)

Support Rahul’s open-source work through [GitHub Sponsors](https://github.com/sponsors/Rahulchaube1) or [Buy Me a Coffee](https://buymeacoffee.com/rahulchaube).
