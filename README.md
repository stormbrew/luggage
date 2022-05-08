# Luggage: A smaller and more constrained build system for Rust

This repository is for a small build system built more or less
off the pieces of cargo, but designed specifically with the 
following non-cargo-ish goals in mind:

- Simplified and more strict dependency resolution: Only one version
of everything, only one set of feature flags for everything.
- No default features: Unlike cargo, you have to opt in to every
feature, even if the dependency is several levels deep.
- Global feature flags: Disable `std` on all crates that have that
feature. Enable `no_std` on everything that has it too. Disable
`serde` everywhere possible.
- Interacts nicely as a sub-build system with, for example, cmake.

All of these together mean that you only include what you want, and
you can make it work with other build systems more easily.
