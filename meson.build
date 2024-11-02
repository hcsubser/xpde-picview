project(
	'xpde-picview',
	'c',
	version: '0.1.0',
	license: 'MIT',
	meson_version: '>=0.55.0',
	default_options: [
		'c_std=c11',
		'warning_level=3',
		'werror=true',
	],
)

cc = meson.get_compiler('c')
installdir='"'+join_paths(get_option('prefix'),'share/xpde/xpde-picview')+'"'
add_project_arguments(cc.get_supported_arguments([
	'-Wno-sign-compare',
	'-Wno-implicit-fallthrough',
	'-Wno-deprecated-declarations',
	'-Wno-format-extra-args',
	'-Wno-cast-function-type',
	'-Wno-unused-parameter',
	'-Wno-empty-body',
	'-Wno-misleading-indentation',
	'-Wno-switch',
	'-Wno-error',
	'-DPACKAGE_ICONS_DIR='+installdir,
]), language: 'c')

gtk3        = dependency('gtk+-3.0')
m_dep 		= cc.find_library('m', required : true)
jpeg		= dependency('libjpeg')

install_data('xpde-picview.desktop', install_dir: join_paths(get_option('prefix'),'share','applications'))
subdir('src')
subdir('icons')
