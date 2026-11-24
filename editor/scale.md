# Merge sparse gradients

Each worker writes numeric pairs, one coordinate and one summed gradient per CSV row, in ascending coordinate order. Duplicates are allowed. Merge two runs in linear time, compensate for floating-point cancellation, then divide by the number of training examples across the two workers. Missing coordinates contribute zero.

In the shipped fixture, one worker contributes 10¹⁶ and 1 at coordinate 7, and another contributes −10¹⁶. The mean over four examples is 0.25. Across 52 additional rows the implementation matched the independently accumulated reference on all four checked coordinates.

[Native commands and compiler installation](https://github.com/Rahulchaube1/blyx-chaffinch/blob/v0.2.0/SCALE.md)
