resource_files = files('baobab.gresource.xml')
resources = gnome.compile_resources('org.gnome.baobab', resource_files, c_name: 'resources')

vapi_sources = [
  'config.vapi',
]

baobab_vala_sources = [
  'baobab-application.vala',
  'baobab-cellrenderers.vala',
  'baobab-chart.vala',
  'baobab-location-list.vala',
  'baobab-location.vala',
  'baobab-ringschart.vala',
  'baobab-scanner.vala',
  'baobab-treemap.vala',
  'baobab-window.vala',
  'main.vala'
]

baobab_sources = [
  vapi_sources,
  baobab_vala_sources,
  resources
]

baobab_vala_args = [
  '--target-glib', '2.44',
  '--vapidir', meson.current_source_dir(),
  '--gresources', resource_files,
]

baobab_c_args = [
  '-include', 'config.h'
]

baobab_link_args = [
  '-rdynamic'
]

baobab_dependencies = [
  glib,
  gio,
  gio_unix,
  gobject,
  gtk,
  math
]

executable('baobab', baobab_sources,
  include_directories: config_h_dir,
  vala_args: baobab_vala_args,
  c_args: baobab_c_args,
  dependencies: baobab_dependencies,
  link_args: baobab_link_args,
  install: true
)
