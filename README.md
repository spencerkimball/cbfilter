cbfilter
========

# Golang Counting Bloom Filter Implementation

A counting bloom filter implementation with arbitrary number (1-8) of
bits per slot. Uses murmur3 and Kirsch and MitzenMacher method for
determining k independent hash functions efficiently.

## Usage is simple:

```
const (
      N = <number insertions>
      B = <bits-per-slot>
      FP = <max-false-positive-prob>
)

f, err := NewFilter(N, B, FP)
if err != nil {
   log.Error("error creating filter:", err)
   return
}

f.AddKey("a")
f.HasKey("a")
f.RemoveKey("a")
```