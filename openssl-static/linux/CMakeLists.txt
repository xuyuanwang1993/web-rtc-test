set(ENV{OPENSSL_ROOT_DIR} ${CMAKE_CURRENT_LIST_DIR})

add_library(OpenSSL::SSL STATIC IMPORTED GLOBAL)
set_target_properties(OpenSSL::SSL PROPERTIES
	INTERFACE_INCLUDE_DIRECTORIES ${CMAKE_CURRENT_LIST_DIR}/include
	IMPORTED_LOCATION ${CMAKE_CURRENT_LIST_DIR}/lib/libssl.a
	IMPORTED_LOCATION_DEBUG ${CMAKE_CURRENT_LIST_DIR}/lib/libssld.a
)
add_library(OpenSSL::Crypto STATIC IMPORTED GLOBAL)
set_target_properties(OpenSSL::Crypto PROPERTIES
	INTERFACE_INCLUDE_DIRECTORIES ${CMAKE_CURRENT_LIST_DIR}/include
	IMPORTED_LOCATION ${CMAKE_CURRENT_LIST_DIR}/lib/libcrypto.a
	IMPORTED_LOCATION_DEBUG ${CMAKE_CURRENT_LIST_DIR}/lib/libcryptod.a
)