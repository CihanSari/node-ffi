# node-ffi

Rick Branson rick [at] diodeware [dot] com
http://github.com/rbranson/node-ffi

# DESCRIPTION

node-ffi is a Node.js addon for loading and calling dynamic libraries using pure JavaScript. It can be used to create bindings to native libraries without writing any C++ code.

WARNING: node-ffi assumes you know what you're doing. You can pretty easily create situations where you will segfault the interpreter and unless you've got C debugger skills, you probably won't know what's going on.

# EXAMPLE

    var FFI = require("node-ffi");

    var libm = new FFI.Library("libm", { "ceil": [ "double", [ "double" ] ] });
    libm.ceil(1.5); // 2

    // You can also access just functions in the current process by passing a null
    var current = new FFI.Library(null, { "atoi": [ "int32", [ "string" ] ] });
    current.atoi("1234"); // 1234

# REQUIREMENTS

* Linux, OS X, or Solaris.
* You will need node.js 0.2.3+

# NPM INSTALL
  
    $ npm install node-ffi

# SOURCE INSTALL

    $ git clone git://github.com/rbranson/node-ffi.git
    $ cd node-ffi
    $ node-waf configure build
    $ node test.js
    $ node-waf install

# TYPES

    int8        Signed 8-bit Integer
    uint8       Unsigned 8-bit Integer
    int16       Signed 16-bit Integer
    uint16      Unsigned 16-bit Integer
    int32       Signed 32-bit Integer
    uint32      Unsigned 32-bit Integer
    int64       Signed 64-bit Integer 
    uint64      Unsigned 64-bit Integer 
    float       Single Precision Floating Point Number (float)
    double      Double Precision Floating Point Number (double)
    pointer     Pointer Type
    string      Null-Terminated String (char *)

In addition to the basic types, there are type aliases for common C types.

    byte        unsigned char
    char        char
    uchar       unsigned char
    short       short
    ushort		unsigned short
    int			int
    uint		unsigned int
    long		long
    ulong		unsigned long
    longlong	long long
    ulonglong	unsigned long long
    size_t      unsigned int (size is platform-dependent)

# LICENSE

See LICENSE file.
