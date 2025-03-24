add_executable(recovery
	bootloader.c
	default_recovery_ui.c
	install.c
	recovery.c
	roots.c
	ui.c
	verifier.c
)

add_executable(verifier_test
	verifier.c
	verifier_test.c
)

target_link_libraries(recovery
	minelf
	minui
	pixelflinger
	minzip
	cutils
	mtdutils
	log
	mincrypt
	png
	ext4utils
	sparse
	bionic
	ZLIB::ZLIB
)

target_link_libraries(verifier_test
	mincrypt
)
