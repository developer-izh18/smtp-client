cmake_minimum_required(VERSION 3.9)
project(client C)

set(CMAKE_C_STANDARD 99)

# add extra include directories
include_directories(/usr/local/opt/openssl/include/)

add_executable(client main.c smtp.h smtp.c str_helper.h str_helper.c network_helper.h network_helper.c files_crawler.c files_crawler.h common_structs.h converter.c converter.h common_structs.c logger.c logger.h client.c client.h)

target_link_libraries (client PRIVATE -lresolv -lssl -lcrypto -lrt -lm -pthread)