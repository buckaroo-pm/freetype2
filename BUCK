macos_sources = glob([
])

linux_sources = glob([
])

windows_sources = glob([
  'src/winfonts/**/*.c',
])

platform_sources = macos_sources + windows_sources

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
  excludes = glob([
    'src/**/test_*.c', 
  ]) + [
    'src/autofit/aflatin2.c',
    'src/gzip/infutil.c',
    'src/base/fterrors.c', 
    'src/gxvalid/gxvfgen.c', 
    'src/gxvalid/gxfgen.c', 
  ] + platform_sources),
  platform_srcs = [
    ('macos.*', macos_sources),
    ('linux.*', linux_sources),
    ('windows.*', windows_sources),
  ],
  preprocessor_flags = [
    '-DFT2_BUILD_LIBRARY',
  ],
  visibility = [
    'PUBLIC',
  ],
)
