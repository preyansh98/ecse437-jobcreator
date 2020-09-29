# place inside the src directory, i.e. src/CMakeLists.txt

cmake_minimum_required(VERSION 3.10.2)

project(jobcreator)

# compile utils 
add_library(utils utils/input.c)
target_include_directories(utils PUBLIC include)

# compile jobs
add_library(jobs jobs/job.c)
target_include_directories(jobs PUBLIC include)

# create executable jobcreator
add_executable(jobcreator main.c)
target_link_libraries(jobcreator utils jobs)
