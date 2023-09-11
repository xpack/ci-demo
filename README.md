# ci-demo

This project demonstrates how to use xPack binary dependencies in a
simple Hello World C++ project, running on GitHub Actions.

The toolchain is `clang`, and the build is managed by `cmake` and `ninja`.

All these tools are defined with specific versions as `xpack/devDependencies`,
installed in the project via `xpm install`.

The test is performed via `xpm run test`.
