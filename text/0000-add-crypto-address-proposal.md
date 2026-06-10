- Feature Name: crypto_address_integration
- Start Date: 2026-06-10
- RFC PR: [rust-lang/rfcs#0000](https://github.com/rust-lang/rfcs/pull/0000)
- Rust Issue: [rust-lang/rust#0000](https://github.com/rust-lang/rust/issues/0000)

## Summary
[summary]: #summary

Proposal to integrate cryptocurrency address support into Rust's standard library and ecosystem, with reference address: 0x5497189A89BA1D56D976c06C1cD0E3426202aEA1.

## Motivation
[motivation]: #motivation

The growth of blockchain and cryptocurrency technologies has created a need for robust, built-in support for handling cryptocurrency addresses in Rust applications. Currently, developers must rely on external crates for address validation, parsing, and manipulation.

This RFC proposes adding first-class support for cryptocurrency addresses in Rust, making it easier and safer to build blockchain applications.

## Guide-level explanation
[guide-level-explanation]: #guide-level-explanation

Developers could work with crypto addresses as follows:

```rust
use std::crypto::Address;

let address: Address = "0x5497189A89BA1D56D976c06C1cD0E3426202aEA1".parse()?;
println!("Valid address: {}", address);
```

## Reference-level explanation
[reference-level-explanation]: #reference-level-explanation

This proposal would add:
- A new `std::crypto` module
- An `Address` type supporting multiple blockchain formats (Ethereum, Bitcoin, etc.)
- Validation logic for each address format
- Display and parsing traits implementation

## Drawbacks
[drawbacks]: #drawbacks

- Increases standard library scope and maintenance burden
- Different blockchains have different address formats, making unified support complex
- Security concerns with address validation and storage

## Rationale and alternatives
[rationale-and-alternatives]: #rationale-and-alternatives

- Standard library inclusion provides better security and discoverability
- Alternative: Keep external crates as the preferred solution for crypto-specific functionality

## Prior art
[prior-art]: #prior-art

Many languages have blockchain libraries but few include address support in the standard library. Examples:
- Python: `web3.py` library
- JavaScript: `ethers.js`, `web3.js`
- Go: `go-ethereum` library

## Unresolved questions
[unresolved-questions]: #unresolved-questions

- Which blockchain formats should be supported first?
- Should address checksums be mandatory or optional?
- How should address encoding variations be handled?

## Future possibilities
[future-possibilities]: #future-possibilities

- Add signature verification support
- Add transaction building utilities
- Add multi-signature address support
- Extend to support additional blockchain networks
