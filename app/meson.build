
app_moc_headers = [
  'mainwindow.h',
  'paintarea.h',
  'plugindialog.h'
]

app_ui_files = [
]

app_qresources = []

app_moc_files = qt5.preprocess(moc_headers : app_moc_headers,
                               ui_files : app_ui_files,
                               qresources : app_qresources)

app_sources = [
  'main.cpp',
  'mainwindow.cpp',
  'paintarea.cpp',
  'plugindialog.cpp'
]

app_inc = include_directories([])

app = executable('plugandpaint',
                       app_sources,
                       app_moc_files,
                       include_directories : [app_inc],
                       link_with : [basictools],
                       dependencies : [qt5core, qt5widgets, qt5gui]
                       )

