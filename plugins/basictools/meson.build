
basictools_moc_headers = [
  'basictoolsplugin.h'
]

if use_module
  basictools_moc_files = qt5.preprocess(moc_headers : basictools_moc_headers)
else
  moc = find_program('moc')

  gen = generator(moc,
                  output  : 'moc_@BASENAME@.cpp',
                  arguments : ['@INPUT@',
                   '-I', meson.current_source_dir()+'/../../app',
                   '-o', '@OUTPUT@'])
  basictools_moc_files = gen.process(basictools_moc_headers)
endif

basictools_sources = [
  'basictoolsplugin.cpp'
]

basictools_inc = include_directories(['../../app'])

basictools = library('pnp_basictools',
                       basictools_sources,
                       basictools_moc_files,
                       include_directories : [basictools_inc],
                       dependencies : [qt5core, qt5gui, qt5widgets]
                       )

