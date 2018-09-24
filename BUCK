genrule(
  name = 'headers-a', 
  out = 'headers-a', 
  srcs = glob([
    'include/a/**/*.hpp', 
  ]), 
  cmd = 'cp -r $SRCDIR/include/a $OUT', 
)

genrule(
  name = 'headers-b', 
  out = 'headers-b', 
  srcs = glob([
    'include/b/**/*.hpp', 
  ]), 
  cmd = 'cp -r $SRCDIR/include/b $OUT', 
)

export_file(
  name = 'header-dirs', 
  src = 'header-dirs.txt', 
  out = 'header-dirs.txt', 
)

prebuilt_cxx_library(
  name = 'x', 
  header_namespace = '', 
  header_only = True, 
  header_dirs = [
    ':header-dirs'
  ], 
  # header_dirs = [
  #   ':headers-a', 
  #   ':headers-b', 
  # ], 
)

cxx_binary(
  name = 'main', 
  srcs = [
    'src/main.cpp'
  ], 
  deps = [
    ':x', 
  ], 
)
