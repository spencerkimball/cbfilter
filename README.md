cbfilter
========

# Golang Counting Bloom Filter Implementation

A counting bloom filter implementation with arbitrary number (1-8) of
bits per slot. Uses murmur3 and Kirsch and MitzenMacher method for
determining k independent hash functions efficiently.

## Usage is simple:

```
N := <number insertions>
B := <bits-per-slot>
FP := <max-false-positive-prob>

if f, err := NewFilter(N, B, FP); err != nil {
   log.Error("error creating filter:", err)
   return
}

f.AddKey("a")
f.HasKey("a")
f.RemoveKey("a")
```