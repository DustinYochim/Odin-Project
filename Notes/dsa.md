# Data Structures and Algorithms

## Hash Maps
A hash map is similar to a conventional array, except it uses “keys” as indices rather than meaningless sequential numbering of the values. With the data organized in this way, we get quick search speeds for keys in the structure.
A hash map takes in a key value pair, produces a hash code, and stores the pair in a bucket.

### What is a Hash Code?
Hashing involves taking an input in and generating a corresponding output. A hash function should be a pure function. Hashing the same input should always return the same hash code, and there should be no random generation component.

```js
function hash(name) {
  return name.charAt(0);
}
```

There is a key difference between hashing and ciphering (encryption): reversibility. Hashing is a one-way process. You can make a hash code from a name, but you cannot take a hash code and revert it back to a name.

In the context of hash maps, we need the hash code to be a number. This number will serve as the index to the bucket that will store the key value pair.


### Buckets
Buckets are storage that we need to store our elements. We can consider each index of an array to have a bucket. For a specific key, we decide which bucket to use for storage through our hash function. The hash function returns a number that serves as the index of the array at which we store this specific key value pair.