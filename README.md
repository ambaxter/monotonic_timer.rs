# Monotonic Timer

Simple implementation of a Monotonic Timer in and for Rust.

# Example
```rust
extern crate monotonic_timer;
use std::sync::mpsc::channel;

let timer = monotonic_timer::Timer::new();
let (tx, rx) = channel();

let _guard = timer.schedule_with_delay(Duration::from_sec(3), move || {
  tx.send(()).unwrap();
});

rx.recv().unwrap();
println!("This code has been executed after 3 seconds");
```

# Attribution
This project is a slightly modified version of https://github.com/Yoric/timer.rs.  

