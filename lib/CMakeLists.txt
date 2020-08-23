cmake_minimum_required(VERSION 3.4.1)
include_directories( curve25519 ed25519 playfair )

set(CMAKE_C_STANDARD 11)

aux_source_directory(. play_src)
set(DIR_SRCS ${play_src})

add_library( airplay STATIC ${DIR_SRCS} )
if(UNIX AND NOT APPLE)
    find_library(libplist plist REQUIRED)
else()
    find_library(libplist libplist-2.0.a REQUIRED)
endif()
target_link_libraries( airplay pthread curve25519 ed25519 playfair ${libplist} )

if(WIN32)
    set(OPENSSL_USE_STATIC_LIBS TRUE)
endif()
find_package(OpenSSL REQUIRED)
target_link_libraries( airplay OpenSSL::Crypto )

if(UNIX AND NOT APPLE)
    target_link_libraries( airplay dns_sd ) 
endif()

if(WIN32)
    target_link_libraries( airplay ws2_32 )  
endif()