add_library(mtdutils STATIC
	mounts.c
	mtdutils.c
)

add_executable(flash_image flash_image.c)
target_link_libraries(flash_image mtdutils log)
