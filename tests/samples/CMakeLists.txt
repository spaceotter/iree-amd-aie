# Copyright 2023 The IREE Authors
#
# Licensed under the Apache License v2.0 with LLVM Exceptions.
# See https://llvm.org/LICENSE.txt for license information.
# SPDX-License-Identifier: Apache-2.0 WITH LLVM-exception

iree_lit_test_suite(
  NAME
    lit
  SRCS
    "pack_pipeline_funcIR.mlir"
    "pad_pack_pipeline_e2e.mlir"
    "pad_pipeline_e2e.mlir"
    "simple_pack_pipeline_e2e.mlir"
    # Disabling because on Windows build: 
    #    'linalg.fill' op with consumer is being erased.
    # "pad_pipeline_conv2d.mlir"
  TOOLS
    ${IREE_LLD_TARGET}
    FileCheck
    iree-opt
    iree-compile
)
