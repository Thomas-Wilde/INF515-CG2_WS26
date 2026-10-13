# Projects Settings
cmake_minimum_required (VERSION 3.5)
# The main executable
add_executable(Task05-ShaderClass
  example.cc
  shader.cc
)

set_property(TARGET Task05-ShaderClass PROPERTY CXX_STANDARD 17)
target_compile_options(Task05-ShaderClass PRIVATE -Wall)
configure_file(fragment_shader.fs fragment_shader.fs COPYONLY)
configure_file(vertex_shader.vs vertex_shader.vs COPYONLY)

target_link_libraries(
Task05-ShaderClass
  PRIVATE glfw
  PRIVATE libglew_static
)
