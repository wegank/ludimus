cmake_minimum_required(VERSION 3.4.1)
include_directories( curve25519 ed25519 playfair )

aux_source_directory(. play_src)
set(DIR_SRCS ${play_src})

add_library( airplay STATIC ${DIR_SRCS} )

target_link_libraries( airplay pthread curve25519 ed25519 playfair plist )

find_package(OpenSSL REQUIRED)
target_link_libraries( airplay OpenSSL::Crypto )

if(UNIX AND NOT APPLE)
    target_link_libraries( airplay dns_sd )  
endif()
