project('wxwidgets test', 'cpp', default_options : ['cpp_std=c++11'])

# tracking sources
main_sources   = []
header_sources = []
interfaces     = []
# add folder to build tree
inc = include_directories('include')
subdir('src')
subdir('include')
subdir('resources')
# dependencies
wxd = dependency('wxwidgets', version : '>=3.3.0', required : false)

## target ##

if wxd.found()
 # wp = executable('wxprog', 'wxprog.cpp', dependencies : wxd)

  #test('wxtest', wp)

  # WxWidgets framework is available, we can use required here
  wx_stc  = dependency('wxwidgets', version : '>=3.3.0', modules : ['std', 'stc'])
  stc_exe = executable('wxstc', 
  	        main_sources,
  	        include_directories:inc, 
  	        dependencies : wx_stc)
  test('wxstctest', stc_exe)

  # Check we can apply a version constraint
  dependency('wxwidgets', version: '>=@0@'.format(wxd.version()))

endif