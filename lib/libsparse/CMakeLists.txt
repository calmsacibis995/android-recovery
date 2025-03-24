add_library(sparse STATIC
	backed_block.c
	output_file.c
	sparse.c
	sparse_crc32.c
	sparse_err.c
	sparse_read.c
)

add_executable(simg2simg
	simg2simg.c
)

add_executable(img2simg
	img2simg.c
)

add_executable(simg2img
	simg2img.c
)

add_executable(append2simg
	append2simg.c
)

target_link_libraries(simg2simg sparse ZLIB::ZLIB)
target_link_libraries(img2simg sparse ZLIB::ZLIB)
target_link_libraries(simg2img sparse ZLIB::ZLIB)
target_link_libraries(append2simg sparse ZLIB::ZLIB)
