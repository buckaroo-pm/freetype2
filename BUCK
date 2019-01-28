load('//:subdir_glob.bzl', 'subdir_glob')
load('//:buckaroo_macros.bzl', 'buckaroo_deps')

macos_srcs = [
]

linux_srcs = [
]

windows_srcs = [
]

platform_srcs = macos_srcs + windows_srcs

cxx_library(
  name = 'freetype',
  header_namespace = '',
  exported_headers = subdir_glob([
    ('include', '**/*.h'),
  ]),
  headers = subdir_glob([
    ('src', '**/*.h'),
    ('', 'src/**/*.c'),
  ]),
  srcs = glob([
    'src/**/*.c',
  ],
  exclude = glob([
    'src/**/test_*.c', 
  ]) + [
    'src/autofit/aflatin2.c',
    'src/gzip/infutil.c',
    'src/base/fterrors.c', 
    'src/gxvalid/gxvfgen.c', 
    'src/gxvalid/gxfgen.c', 
  ] + platform_srcs),
  platform_srcs = [
    ('macos.*', macos_srcs),
    ('linux.*', linux_srcs),
    ('windows.*', windows_srcs),
  ],
  preprocessor_flags = [
    '-DFT2_BUILD_LIBRARY',
  ],
  deps = buckaroo_deps(),
  visibility = [
    'PUBLIC',
  ],
)
