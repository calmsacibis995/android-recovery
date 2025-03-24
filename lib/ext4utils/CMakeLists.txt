add_library(ext4utils STATIC
	allocate.c
	contents.c
	ext4fixup.c
	ext4_utils.c
	extent.c
	indirect.c
	make_ext4fs.c
	sha1.c
	uuid.c
	wipe.c
)

add_executable(setup_fs
	setup_fs.c
)

add_executable(make_ext4fs
	make_ext4fs_main.c
)

add_executable(ext2simg
	ext2simg.c
)

add_executable(ext4fixup
	ext4fixup_main.c
)

target_link_libraries(setup_fs ext4utils cutils)
target_link_libraries(make_ext4fs ext4utils sparse ZLIB::ZLIB)
target_link_libraries(ext2simg ext4utils sparse ZLIB::ZLIB)
target_link_libraries(ext4fixup ext4utils sparse ZLIB::ZLIB)
