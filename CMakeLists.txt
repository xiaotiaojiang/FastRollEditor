
cmake_minimum_required(VERSION 3.15)
project(MyProject LANGUAGES CXX)

# 设置C++标准
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# 可执行文件配置
add_executable(${PROJECT_NAME}
    src/main.cpp
    src/utility.cpp
)

# 包含目录
target_include_directories(${PROJECT_NAME} PUBLIC
    include/
)

# 依赖查找示例
find_package(Boost 1.70 REQUIRED COMPONENTS filesystem system)
target_link_libraries(${PROJECT_NAME} PRIVATE
    Boost::filesystem
    Boost::system
)
