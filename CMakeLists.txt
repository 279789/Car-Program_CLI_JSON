cmake_minimum_required(VERSION 3.20)
project(Car_Bike-Program_CLI_JSON)

set(CMAKE_CXX_STANDARD 23)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

include(FetchContent)

FetchContent_Declare(
	CLI11
	GIT_REPOSITORY https://github.com/CLIUtils/CLI11.git
	GIT_TAG main
)

FetchContent_MakeAvailable(CLI11)

FetchContent_Declare(
	json
	GIT_REPOSITORY https://github.com/nlohmann/json.git
	GIT_TAG v3.12.0
)
FetchContent_MakeAvailable(json)



add_executable(${PROJECT_NAME} src/main.cpp)
target_link_libraries(${PROJECT_NAME} PRIVATE CLI11::CLI11 nlohmann_json::nlohmann_json)
