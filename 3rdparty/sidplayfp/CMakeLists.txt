project(libsidplayfp)

add_definitions(-DHAVE_CONFIG_H -DSID_EXTERN=)
include_directories(".")
include_directories("src")

file(GLOB SRCS_CXX "src/sidplayfp/*.cpp" "src/c64/*.cpp" "src/c64/CIA/*.cpp" "src/c64/CPU/*.cpp" "src/c64/VIC_II/*.cpp" "src/sidtune/*.cpp"
	"utils/MD5/*.cpp"
	"builders/resid-builder/*.cpp"
	"builders/resid-builder/resid/*.cc")

file(GLOB SRCS_H "src/*.h" "src/c64/*.h" "src/c64/CIA/*.h" "src/c64/CPU/*.h" "src/c64/VIC_II/*.h" "src/sidtune/*.h"
	"utils/MD5/*.h"
	"builders/resid-builder/*.h"
	"builders/resid-builder/resid/*.h")

add_library(sidplayfp ${SRCS_CXX} ${SRCS_H})
set_property(TARGET sidplayfp PROPERTY FOLDER "3rdparty")
