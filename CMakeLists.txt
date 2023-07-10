cmake_minimum_required(VERSION 3.13)

set(PROJECT_NAME cmake_project_example)
set(CMAKE_CXX_STANDARD 17)

project(${PROJECT_NAME})    # 본격적으로 프로젝트 세팅
add_executable(${PROJECT_NAME} src/main.cpp)    #Project name 이라는 실행파일 생성할것인데, 뒤의 main.cpp 를 이용함
