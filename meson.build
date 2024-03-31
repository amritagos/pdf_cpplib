project('pdf_cpplib', 'cpp',
  version : '0.1',
  default_options : ['warning_level=3', 'cpp_std=c++20', 'optimization=3'])

add_global_arguments(['-Wno-unused-local-typedefs', '-Wno-array-bounds'], language : 'cpp')

incdir = include_directories('include')

_deps = [] # Dependencies

# Dependencies
# For clang
_deps += [declare_dependency(link_args: '-lstdc++')]

# fmt
fmt_dep = dependency('fmt', required: true)
_deps += fmt_dep

# xtensor
xtensor_dep = dependency('xtensor', required: true)
_deps += xtensor_dep

inc = include_directories('include')
pdflib = library('pdf',
  include_directories : incdir,
  dependencies: _deps,
  install : true)

pdflib_dep = declare_dependency(include_directories : inc,
  link_with : pdflib, dependencies: _deps)