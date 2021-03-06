# Copyright (c) 2006, Google Inc.
# All rights reserved.
#
# Redistribution and use in source and binary forms, with or without
# modification, are permitted provided that the following conditions are
# met:
#
#     * Redistributions of source code must retain the above copyright
# notice, this list of conditions and the following disclaimer.
#     * Redistributions in binary form must reproduce the above
# copyright notice, this list of conditions and the following disclaimer
# in the documentation and/or other materials provided with the
# distribution.
#     * Neither the name of Google Inc. nor the names of its
# contributors may be used to endorse or promote products derived from
# this software without specific prior written permission.
#
# THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS
# "AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT
# LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR
# A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT
# OWNER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL,
# SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT
# LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE,
# DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY
# THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT
# (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE
# OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.


AC_PREREQ(2.57)

AC_INIT(breakpad, 0.1, opensource@google.com)
dnl Sanity check: the argument is just a file that should exist.
AC_CONFIG_SRCDIR(README)
AC_CONFIG_AUX_DIR(autotools)

AM_INIT_AUTOMAKE(subdir-objects tar-ustar)
AM_CONFIG_HEADER(src/config.h)

AC_PROG_CC
AC_PROG_CPP
AC_PROG_CXX

AC_PROG_LIBTOOL
AC_SUBST(LIBTOOL_DEPS)

AC_HEADER_STDC

AC_ARG_ENABLE(selftest,
              AS_HELP_STRING([--enable-selftest],
                             [Run extra tests with "make check" ]
                             [(may conflict with optimizations) ]
                             [(default is no)]),
              [case "${enableval}" in
                 yes)
                   selftest=true
                   ;;
                 no)
                   selftest=false
                   ;;
                 *)
                   AC_MSG_ERROR(bad value ${enableval} for --enable-selftest)
                   ;;
               esac],
              [selftest=false])
AM_CONDITIONAL(SELFTEST, test x$selftest = xtrue)

AC_CONFIG_FILES([Makefile])
AC_OUTPUT
