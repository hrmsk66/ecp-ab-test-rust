# A/B testing at the edge (with Rust SDK)

A Rust implementation of the solution on [this page](https://developer.fastly.com/solutions/tutorials/ab-testing/).

Fastly needs to know some things about the tests you want to run:

- The number of tests and the name of each one
- The number of possible buckets for each test and the relative weighting of each
- The name of each bucket

This example assumes that test items are defined in the dictionary in the format like this.

```
{
    "tests": "itemcount, buttonsize",
    "itemcount": {
        "name": "itemcount",
        "weight": "1:1",
        "bucket_params": [ "10", "15" ]
    },
    "buttonsize": {
        "name": "buttonsize",
        "weight": "7:3:2",
        "bucket_params": [ "small", "medium", "large" ]
    }
}
```

Fastly Fiddle: https://fiddle.fastlydemo.net/fiddle/c1cbbb74
