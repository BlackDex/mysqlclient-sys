mysqlclient-sys
======

Autogenerated Rust bindings for libmysql-client (`#include <mysql.h>`)

Building
--------

For this crate to build, `libmysqlclient` must be installed on your system
(`brew install mysql` on macOS, `apt-get install libmysqlclient-dev` on Ubuntu,
included with the server distribution on Windows). Additionally, either
`pkg-config` or `mysql_config` must be present and able to successfully locate
`libmysqlclient`.

The build script of the crate will attempt to find the lib path of
libmysql-client using the following methods:

- First, it will attempt to use pkg-config to locate it. All the config options,
  such as `PKG_CONFIG_ALLOW_CROSS`, `PKG_CONFIG_ALL_STATIC` etc., of the crate
  [pkg-config](http://alexcrichton.com/pkg-config-rs/pkg_config/index.html)
  apply.
- MSVC ABI builds will then check for a [Vcpkg](https://github.com/Microsoft/vcpkg)
  installation using the [vcpkg cargo build helper](https://github.com/mcgoo/vcpkg-rs).
  Set the `VCPKG_ROOT` environment variable to point to your Vcpkg installation and
  run `vcpkg install libmysql:x64-windows` to install the required libraries.
- If the library cannot be found by using the steps above the build script will 
  check the `MYSQLCLIENT_LIB_DIR` and `MYSQLCLIENT_VERSION` environment variables
- If the library cannot be found using `pkg-config`, it will invoke the command
  `mysql_config --variable=pkglibdir`

The crate will try to use pregenerated bindings for a variety of libmysqlclient versions and supported operating systems.

## License

Licensed under either of

 * Apache License, Version 2.0, ([LICENSE-APACHE](LICENSE-APACHE) or
   http://www.apache.org/licenses/LICENSE-2.0)
 * MIT license ([LICENSE-MIT](LICENSE-MIT) or
   http://opensource.org/licenses/MIT)

at your option.

The `mysqlclient-src` crate is licensed under [GPL-2.0](https://www.gnu.org/licenses/old-licenses/gpl-2.0.html)
to match the license of the packed mysql source code.

### Contribution

Unless you explicitly state otherwise, any contribution intentionally submitted
for inclusion in the work by you, as defined in the Apache-2.0 license, shall be
dual licensed as above, without any additional terms or conditions.
