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
    'src/autofit/aflatin2.c',
    'src/gzip/infutil.c',
    'src/base/fterrors.c', 
  ]) + platform_sources),
  platform_srcs = [
    ('macos.*', macos_sources),
    ('linux.*', linux_sources),
    ('windows.*', windows_sources),
  ],
  preprocessor_flags = [
    '-DFT2_BUILD_LIBRARY',
    '-DFT_ADVANCES_H=<freetype/ftadvanc.h>',
    '-DFT_INTERNAL_DEBUG_H=<freetype/internal/ftdebug.h>',
    '-DFT_INTERNAL_MEMORY_H=<freetype/internal/ftmemory.h>',
    '-DFT_INTERNAL_OBJECTS_H=<freetype/internal/ftobjs.h>',
    '-DFT_INTERNAL_POSTSCRIPT_AUX_H=<freetype/internal/psaux.h>',
    '-DFT_INTERNAL_STREAM_H=<freetype/internal/ftstream.h>',
    '-DFT_SERVICE_POSTSCRIPT_CMAPS_H=<freetype/internal/services/svpscmap.h>',
  ],
  visibility = [
    'PUBLIC',
  ],
)
