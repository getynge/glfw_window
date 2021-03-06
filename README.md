# glfw_window [![Build Status](https://travis-ci.org/PistonDevelopers/glfw_window.svg?branch=master)](https://travis-ci.org/PistonDevelopers/glfw_window)

A GLFW window back-end for the Piston game engine.

Maintainers: @TyOverby, @bvssvni, @Coeuvre

[How to contribute](https://github.com/PistonDevelopers/piston/blob/master/CONTRIBUTING.md)

### How to create a window

```Rust
let mut window: GlfwWindow = WindowSettings::new("GLFW Window", (640, 480))
    .fullscreen(false)
    .vsync(true)
    .build()
    .unwrap();
```

See the examples for more ways to create a window.

### How to set up Gfx

After you have created a window, do the following:

```Rust
let mut device = gfx::GlDevice::new(|s|
    self.window.get_proc_address(s)
);
let (w, h) = window.get_size();
let frame = gfx::Frame::new(w as u16, h as u16);
```

### Troubleshooting

* OSX: https://github.com/PistonDevelopers/rust-empty/issues/48

## Dependencies

![dependencies](./Cargo.png)

