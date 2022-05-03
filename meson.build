project(
  'QtGuiTestUtils',
  'cpp',
  default_options : ['cpp_std=c++17']
)

qt_sdk=get_option('qt_version')

qt_sdk=get_option('qt_version')
if qt_sdk=='auto'
    qt_version=run_command(find_program('qmake'), '-query', 'QT_VERSION').stdout()
    if qt_version.startswith('5.')
        qt_sdk='qt5'
    elif qt_version.startswith('6.')
        qt_sdk='qt6'
    endif
endif

qt = import(qt_sdk)
qt_core = dependency(qt_sdk, modules : 'Core')
qt_widgets = dependency(qt_sdk, modules : 'Widgets')
qt_gui = dependency(qt_sdk, modules : 'Gui')
qt_test = dependency(qt_sdk, modules : 'Test')

QtGuiTestUtils_inc = include_directories(['.'])

QtGuiTestUtils_lib = library('QtGuiTestUtils', 'QtGuiTestUtils/GUITestUtils.cpp',include_directories: QtGuiTestUtils_inc,
                       dependencies: [qt_test, qt_gui, qt_widgets, qt_core])

QtGuiTestUtils_dep = declare_dependency(
	include_directories : QtGuiTestUtils_inc,
	link_with: QtGuiTestUtils_lib
)

