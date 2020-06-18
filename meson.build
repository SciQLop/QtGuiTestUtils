project(
  'QtGuiTestUtils',
  'cpp',
  default_options : ['cpp_std=c++17']
)


qt5 = import('qt5')
qt5core = dependency('qt5', modules : 'Core')
qt5widgets = dependency('qt5', modules : 'Widgets')
qt5gui = dependency('qt5', modules : 'Gui')
qt5test = dependency('qt5', modules : 'Test')

QtGuiTestUtils_inc = include_directories(['.'])

QtGuiTestUtils_lib = library('QtGuiTestUtils', 'QtGuiTestUtils/GUITestUtils.cpp',include_directories: QtGuiTestUtils_inc,
                       dependencies: [qt5test, qt5gui, qt5widgets, qt5core])

QtGuiTestUtils_dep = declare_dependency(
	include_directories : QtGuiTestUtils_inc,
	link_with: QtGuiTestUtils_lib
)

