#Place this at the same level of the src/ dir
cmake_minimum_required(VERSION 3.10)

# set the project name
project(jobcreator)
# add the headers
include_directories(src/include/)
# create libraries
add_library(jobs src/jobs/job.c)
add_library(utils src/utils/input.c)
target_include_directories(jobs PRIVATE src/include/)
target_include_directories(utils PRIVATE src/include/)
# add all src files to the executable
add_executable(jobcreator src/main.c src/jobs/job.c src/utils/input.c)
target_link_libraries(jobcreator jobs utils)

