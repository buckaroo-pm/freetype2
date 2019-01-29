load('//:subdir_glob.bzl', 'subdir_glob')
load('//:buckaroo_macros.bzl', 'buckaroo_deps')

base_srcs = [
  'src/autofit/autofit.c',
  'src/base/ftbase.c',
  'src/base/ftbbox.c',
  'src/base/ftbdf.c',
  'src/base/ftbitmap.c',
  'src/base/ftcid.c',
  'src/base/ftfstype.c',
  'src/base/ftgasp.c',
  'src/base/ftglyph.c',
  'src/base/ftgxval.c',
  'src/base/ftinit.c',
  'src/base/ftmm.c',
  'src/base/ftotval.c',
  'src/base/ftpatent.c',
  'src/base/ftpfr.c',
  'src/base/ftstroke.c',
  'src/base/ftsynth.c',
  'src/base/ftsystem.c',
  'src/base/fttype1.c',
  'src/base/ftwinfnt.c',
  'src/bdf/bdf.c',
  'src/bzip2/ftbzip2.c',
  'src/cache/ftcache.c',
  'src/cff/cff.c',
  'src/cid/type1cid.c',
  'src/gzip/ftgzip.c',
  'src/lzw/ftlzw.c',
  'src/pcf/pcf.c',
  'src/pfr/pfr.c',
  'src/psaux/psaux.c',
  'src/pshinter/pshinter.c',
  'src/psnames/psnames.c',
  'src/raster/raster.c',
  'src/sfnt/sfnt.c',
  'src/smooth/smooth.c',
  'src/truetype/truetype.c',
  'src/type1/type1.c',
  'src/type42/type42.c',
  'src/winfonts/winfnt.c',
]

macos_srcs = [
  'src/base/ftdebug.c',
]

linux_srcs = [
  'src/base/ftdebug.c',
]

windows_srcs = [
]

platform_srcs = linux_srcs + macos_srcs + windows_srcs

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
  srcs = base_srcs,
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
