## Reconcile two sorted snapshots with repeated keys

Returns [added unique keys, removed unique keys, retained keys, duplicate occurrences in the new snapshot]. Inputs are sorted, allowing forward-only scans. Invalid arguments and nonfinite results return an empty vector.

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

[Work through the example in the browser](https://www.blyx-lang.space/play?example=package-chaffinch)
