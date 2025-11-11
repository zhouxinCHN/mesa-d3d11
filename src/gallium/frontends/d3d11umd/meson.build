inc_d3d11umd = include_directories('.')
_c_args_d3d11umd = []

if cc.get_argument_syntax() == 'gcc'
  _c_args_d3d11umd += '-Wno-unknown-pragmas'
endif

libd3d11umd = static_library(
  'd3d11umd',
  files(
    'Adapter.cpp',
    'Debug.cpp',
    'Device.cpp',
    'Draw.cpp',
    'DxgiFns.cpp',
    'Format.cpp',
    'InputAssembly.cpp',
    'OutputMerger.cpp',
    'Query.cpp',
    'Rasterizer.cpp',
    'Resource.cpp',
    'Shader.cpp',
    'ShaderDump.cpp',
    'ShaderParse.c',
    'ShaderTGSI.c',
    'D3DKMT.cpp',
    'Video.cpp',
    'D3d11Add.cpp',
  ),
  c_args : _c_args_d3d11umd,
  cpp_args : _c_args_d3d11umd,
  include_directories : [
    inc_include, inc_src, inc_gallium, inc_gallium_aux, inc_winddk,
  ],
)
