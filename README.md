# wayrs

A simple Rust implementation of Wayland client library.

## Design decisions

- Single event queue
- No interior mutability
- No `libwayland` compatibility
- Support blocking, non-blocking and async IO

## Project structure

The project is split into multiple crates:

- `wayrs-client`: The main crate with implements Wayland wire protocol. Provides `Connection` type which represents open Wayland socket.
- `wayrs-scanner`: Provides `generate!` macro that generates glue code from `.xml` files. Generated code for the core protocol is already included in `wayrs-client`. Reexported as `wayrs_client::scanner`.
- `wayrs-protocols`: A collection of Wayland protocols to use with `wayrs-client`.
- `wayrs-utils`: A collection of utils and abstractions for `wayrs-client`. Includes a shared memory allocator and more.

## MSRV

1.65
