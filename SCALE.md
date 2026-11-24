# Reduce sparse worker gradients

Each worker writes numeric pairs, one coordinate and one summed gradient per CSV row, in ascending coordinate order. Duplicates are allowed. Merge two runs in linear time, compensate for floating-point cancellation, then divide by the number of training examples across the two workers. Missing coordinates contribute zero.

## Try the native command

Extract the archive for your platform from the [Chaffinch 0.2.0 release](https://github.com/Rahulchaube1/blyx-chaffinch/releases/tag/v0.2.0). Add its directory to PATH or use the executable’s full path. Run the fixture commands from the extracted directory.

~~~sh
chaffinch reduce 4 fixtures/worker-a.csv fixtures/worker-b.csv
~~~

## Scope and input contract

The denominator is the global example count, including examples with a zero gradient. The CLI accepts finite gradients and exact integer coordinates from 0 to 9,007,199,254,740,991. Input and output are in memory. A merge processes two worker files and does not provide a network collective.

## Import in Blyx

The executable includes its runtime. To compile the source example, install the tested compiler revision and a host linker, then run these commands from the tagged source tree.

~~~sh
cargo install --locked --git https://github.com/Rahulchaube1/blyxxxx --rev 120d6b6ec6df09ff018d7c18752fb3297b5e629d blyxc
blyxc native-run scale_example.blyx
~~~

~~~blyx
use gradients;

fn main() {
    let a = [7,1.0e16,7,1,2000000000000,8];
    let b = [7,-1.0e16,31,4];
    let means = chaffinch_gradient_mean(a,b,4);
    println!(at(means,1));
    println!(at(means,3));
    println!(at(means,5));
}
~~~

## Verification

In the shipped fixture, one worker contributes 10¹⁶ and 1 at coordinate 7, and another contributes −10¹⁶. The mean over four examples is 0.25. Across 52 additional rows the implementation matched the independently accumulated reference on all four checked coordinates. [Study, raw timings and reproduction instructions](https://www.blyx-lang.space/articles/training-in-factors)
