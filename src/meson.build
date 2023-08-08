main = files('main.cc')
mainWindow = files('mainWindow.cc')
main_sources += main
wx_stc_static  = dependency('wxwidgets', version : '>=3.2.0', modules : ['std', 'stc'])
mainWindowStatic = static_library('mainWindow',
	mainWindow,
	include_directories:inc,
	dependencies:wx_stc_static)

subdir('interface')