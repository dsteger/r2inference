# Copyright (C) 2018-2020 RidgeRun, LLC (http://www.ridgerun.com)
# All Rights Reserved.
#
# The contents of this software are proprietary and confidential to RidgeRun,
# LLC.  No part of this program may be photocopied, reproduced or translated
# into another programming language without prior written consent of
# RidgeRun, LLC.  The user is free to modify the source code after obtaining
# a software license from RidgeRun.  All source code changes must be provided
# back to RidgeRun without any encumbrance.

AM_DEFAULT_SOURCE_EXT = .cc

if ENABLE_TESTS
if HAVE_TENSORFLOW

TESTS =                 \
        model           \
        loader          \
        engine          \
        prediction      \
        frame           \
        parameters      \
        frameworkfactory

check_PROGRAMS=$(TESTS)

endif # HAVE_TENSORFLOW
endif # ENABLE_TESTS

if ENABLE_CODE_COVERAGE
SINGLE_PROCESS=--single-process yes
else
SINGLE_PROCESS=
endif

LOG_DRIVER=$(top_builddir)/common/rr-test-driver.py $(SINGLE_PROCESS)

AM_CXXFLAGS =                       \
        $(RR_CXXFLAGS)              \
        $(TESTS_CFLAGS)             \
        $(TENSORFLOW_CFLAGS)        \
        $(CODE_COVERAGE_CXXFLAGS)

AM_CFLAGS =                         \
        $(RR_CFLAGS)                \
        $(TESTS_CFLAGS)             \
        $(TENSORFLOW_CFLAGS)        \
        $(CODE_COVERAGE_CFLAGS)

AM_CPPFLAGS =                       \
        $(RR_CPPFLAGS)              \
        $(CODE_COVERAGE_CPPFLAGS)

AM_LDFLAGS =                        \
        $(RR_LIBS)                  \
        $(TENSORFLOW_LIBS)          \
        $(TESTS_LIBS)               \
        $(CODE_COVERAGE_LIBS)       \
        $(top_builddir)/r2i/libr2inference-@RR_PACKAGE_VERSION@.la

CLEANFILES = cpputest_*.xml
