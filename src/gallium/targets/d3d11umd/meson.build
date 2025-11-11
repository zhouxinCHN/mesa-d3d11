# Copyright © 2021 VMware, Inc
# Copyright © 2018 Intel Corporation
# SPDX-License-Identifier: MIT

libgallium_d3d11_def = custom_target(
  'd3d11.def',
  input: 'd3d11.def.in',
  output : 'd3d11.def',
  command : gen_vs_module_defs_normal_command,
)

gallium_d3d11_name = get_option('gallium-d3d11-dll-name')
libgallium_d3d11 = shared_library(
  gallium_d3d11_name,
  ['d3d11_gdi.c'],
  vs_module_defs : libgallium_d3d11_def,
  include_directories : [
    inc_include, inc_src, inc_gallium, inc_gallium_aux, inc_d3d11umd, inc_gallium_winsys, inc_gallium_winsys_sw, inc_gallium_drivers, inc_winddk
  ],
  link_whole : [libd3d11umd],
  link_with : [
    libgallium, libwsgdi
  ],
  dependencies : [
    dep_ws2_32, idep_nir, driver_swrast, idep_mesautil
  ],
  name_prefix: '',
  install : true,
)

if with_tests
  test(
    'd3d11',
    executable(
      'test_d3d11',
      files('tests/tri.cpp'),
      cpp_args : [cpp_msvc_compat_args],
      dependencies : [cpp.find_library('d3d11')],
      link_with : [libgallium_d3d11],
    ),
    suite : ['d3d11'],
  )
endif
