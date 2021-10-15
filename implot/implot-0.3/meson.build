project(
  'ImGui Plotting Library',
  'cpp',
  license : 'MIT',
  version : '0.3',
)

dearimgui_sp = subproject('imgui', default_options: [
  'default_library=static',
  # use 'auto_features=disabled' once available: https://github.com/mesonbuild/meson/issues/5320
  'dx9=disabled',
  'dx10=disabled',
  'dx11=disabled',
  'dx12=disabled',
  'metal=disabled',
  'opengl=disabled',
  'vulkan=disabled',
  'glfw=disabled',
  'sdl2=disabled',
  'osx=disabled',
  'win=disabled',
  'marmalade=disabled',
  'allegro5=disabled',
])

dearimgui_dep = dearimgui_sp.get_variable('imgui_dep')

implot_inc = include_directories(['.'])
implot_src = files(
  'implot.cpp',
)

implot_lib = static_library(
  'implot',
  implot_src,
  include_directories : implot_inc,
  dependencies: [dearimgui_dep]
)

implot_dep = declare_dependency(
  link_with : implot_lib,
  include_directories : implot_inc
)
