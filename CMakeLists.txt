cmake_minimum_required(VERSION 3.13)

set(PROJECT_NAME cmake_project_example)
set(CMAKE_CXX_STANDARD 17)

project(${PROJECT_NAME})    # 본격적으로 프로젝트 세팅
add_executable(${PROJECT_NAME} src/main.cpp)    #Project name 이라는 실행파일 생성할것인데, 뒤의 main.cpp 를 이용함

include(dependency.cmake)

# 우리 프로젝트에 include / lib 관련 옵션 추가
target_include_directories(${PROJECT_NAME} PUBLIC ${DEP_INCLUDE_DIR})
target_link_directories(${PROJECT_NAME} PUBLIC ${DEP_LIB_DIR})
target_link_libraries(${PROJECT_NAME} PUBLIC ${DEP_LIBS})

# Dependency들이 먼저 build 될 수 있게 관계 설정
add_dependencies(${PROJECT_NAME} ${DEP_LIST})   #List 안에 있는것들 먼저 컴파일 한 뒤, 우리 프로젝트 컴파일 가능