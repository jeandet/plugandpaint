
extrafilters_moc_headers = [
  'extrafiltersplugin.h'
]

if use_module
  extrafilters_moc_files = qt5.preprocess(moc_headers : extrafilters_moc_headers)
else
  moc = find_program('moc')

  gen = generator(moc,
                  output  : 'moc_@BASENAME@.cpp',
                  arguments : ['@INPUT@',
                   '-I', meson.current_source_dir()+'/../../app',
                   '-o', '@OUTPUT@'])
  extrafilters_moc_files = gen.process(extrafilters_moc_headers)
endif

extrafilters_sources = [
  'extrafiltersplugin.cpp'
]

extrafilters_inc = include_directories(['../../app'])

extrafilters = library('pnp_extrafilters',
                       extrafilters_sources,
                       extrafilters_moc_files,
                       include_directories : [extrafilters_inc],
                       dependencies : [qt5core, qt5gui, qt5widgets]
                       )

