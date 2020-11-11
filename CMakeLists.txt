cmake_minimum_required(VERSION 2.8)
project(corehttp C)

add_library(corehttp STATIC source/core_http_client.c
                            source/dependency/3rdparty/http_parser/http_parser.c)

target_include_directories(corehttp PUBLIC source/include)
target_include_directories(corehttp PUBLIC source/interface)
target_include_directories(corehttp PUBLIC source/dependency/3rdparty/http_parser)

install(TARGETS corehttp
        DESTINATION ${LIB_INSTALL_DIR}
	PERMISSIONS OWNER_READ OWNER_WRITE OWNER_EXECUTE GROUP_READ GROUP_EXECUTE WORLD_READ WORLD_EXECUTE)
