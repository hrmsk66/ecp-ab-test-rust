# A/B testing at the edge (with Rust SDK)

A Rust implementation of the solution on [this page](https://developer.fastly.com/solutions/tutorials/ab-testing/).

Fastly needs to know some things about the tests you want to run:

- A list of tests
- A list of buckets in each tests
- Relative weighting of each bucket

This example assumes that test items are defined in the dictionary in the format like this.

```
{
    "tests": "itemcount, buttonsize",
    "itemcount": {
        "name": "itemcount",
        "weight": "1:1",
        "buckets": [ "10", "15" ]
    },
    "buttonsize": {
        "name": "buttonsize",
        "weight": "7:3:2",
        "buckets": [ "small", "medium", "large" ]
    }
}
```

Fastly Fiddle: https://fiddle.fastlydemo.net/fiddle/c1cbbb74
