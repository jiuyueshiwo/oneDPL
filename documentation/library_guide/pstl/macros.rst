Macros
#######

Version Macros
===============
Use these macros to get the current version of the oneAPI DPC++ Library (oneDPL).

================================= ==============================
Macro                             Description
================================= ==============================
``ONEDPL_VERSION_MAJOR``          A decimal number for the major version of the library.
--------------------------------- ------------------------------
``ONEDPL_VERSION_MINOR``          A decimal number for the minor version.
--------------------------------- ------------------------------
``ONEDPL_VERSION_PATCH``          A decimal number for the patch.
--------------------------------- ------------------------------
``_PSTL_VERSION``                 The version of LLVM PSTL code used in oneDPL.

                                  The value is a decimal numeral of the form ``xxyyz``
                                  where ``xx`` is the major version number, ``yy`` is the
                                  minor version number and ``z`` is the patch number.
--------------------------------- ------------------------------
``_PSTL_VERSION_MAJOR``           ``_PSTL_VERSION/1000``: The major version number.
--------------------------------- ------------------------------
``_PSTL_VERSION_MINOR``           ``(_PSTL_VERSION % 1000) / 10``: The minor version number.
--------------------------------- ------------------------------
``_PSTL_VERSION_PATCH``           ``_PSTL_VERSION % 10``: The patch number.
================================= ==============================

Additional Macros
==================
Use these macros to control aspects of oneDPL usage. You can set them in your program code
before including oneDPL headers.

================================= ==============================
Macro                             Description
================================= ==============================
``PSTL_USE_NONTEMPORAL_STORES``   This macro enables the use of ``#pragma vector nontemporal``
                                  for write-only data when algorithms such as ``std::copy``, ``std::fill``, etc.,
                                  are executed with unsequenced policies.
                                  For further details about the pragma,
                                  see the `Developer Guide and Reference <https://software.intel.com/
                                  content/www/us/en/develop/documentation/
                                  oneapi-dpcpp-cpp-compiler-dev-guide-and-reference/top/
                                  compiler-reference/pragmas/
                                  intel-specific-pragma-reference/vector.html>`_.
                                  If the macro evaluates to a non-zero value,
                                  the use of ``#pragma vector nontemporal`` is enabled.
                                  By default the macro is not defined.

                                  Using this macro may have the same effect on the implementation of parallel
                                  algorithms in the C++ standard libraries of GCC and LLVM.
--------------------------------- ------------------------------
``PSTL_USAGE_WARNINGS``           This macro enables Parallel STL to
                                  emit compile-time messages, such as warnings
                                  about an algorithm not supporting a certain execution policy.
                                  When set to 1, the macro allows the implementation to emit
                                  usage warnings. When the macro is not defined (by default)
                                  or evaluates to zero, usage warnings are disabled.

                                  Using this macro may have the same effect on the implementation of parallel
                                  algorithms in the C++ standard libraries of GCC and LLVM.
--------------------------------- ------------------------------
``ONEDPL_USE_TBB_BACKEND``        This macro controls the use of oneAPI Threading Building Blocks (oneTBB) or
                                  Threading Building Blocks (TBB) for parallel policies.
                                  When the macro is set to 0, algorithms with the ``par`` and ``par_unseq`` policies are only
                                  executed by the calling thread. This is recommended for code that should not depend on the
                                  presence of the oneTBB or TBB library. When the macro is not defined (by default)
                                  or evaluates to a non-zero value,
                                  parallel policies are executed using the oneTBB or TBB library.
--------------------------------- ------------------------------
``ONEDPL_USE_DPCPP_BACKEND``      This macro enables the use of the DPC++ policies.
                                  When the macro is not defined (by default)
                                  or evaluates to non-zero, DPC++ policies are enabled.
                                  When the macro is set to 0 there is no dependency on
                                  the oneAPI DPC++/C++ Compiler and runtime libraries.
                                  Trying to use DPC++ policies will lead to compilation errors.
--------------------------------- ------------------------------
``ONEDPL_ALLOW_DEFERRED_WAITING`` This macro allows waiting for completion of certain algorithms executed with 
                                  DPC++ policies to be deferred. (Disabled by default.)
--------------------------------- ------------------------------
``ONEDPL_FPGA_DEVICE``            Use this macro to build your code containing oneDPL parallel
                                  algorithms for FPGA devices. (Disabled by default.)
--------------------------------- ------------------------------
``ONEDPL_FPGA_EMULATOR``          Use this macro to build your code containing Parallel STL
                                  algorithms for FPGA emulation device. (Disabled by default.)

                                  Note: Define ``ONEDPL_FPGA_DEVICE`` and ``ONEDPL_FPGA_EMULATOR`` macros in the same
                                  application to run on a FPGA emulation device.
                                  Define only the ``ONEDPL_FPGA_DEVICE`` macro to run on a FPGA hardware device.
================================= ==============================

