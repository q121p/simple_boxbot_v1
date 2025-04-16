cmake_minimum_required(VERSION 3.8)
project(simple_boxbot)

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

# find dependencies
find_package(ament_cmake REQUIRED)

# --- ここに依存パッケージ追加するなら後で追記 ---

if(BUILD_TESTING)
  find_package(ament_lint_auto REQUIRED)
  set(ament_cmake_copyright_FOUND TRUE)
  set(ament_cmake_cpplint_FOUND TRUE)
  ament_lint_auto_find_test_dependencies()
endif()

# 🔽 URDFやlaunchフォルダをインストールする設定
install(DIRECTORY launch urdf
  DESTINATION share/${PROJECT_NAME}/
)

ament_package()
