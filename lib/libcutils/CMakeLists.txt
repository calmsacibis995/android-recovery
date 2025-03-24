add_library(cutils STATIC
	android_reboot.c
	partition_utils.c
	properties.c
	android_memset16.S
	android_memset32.S
)

set_property(SOURCE android_memset16.S APPEND PROPERTY COMPILE_OPTIONS "-x" "assembler-with-cpp")
set_property(SOURCE android_memset32.S APPEND PROPERTY COMPILE_OPTIONS "-x" "assembler-with-cpp")
