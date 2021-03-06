cmake_minimum_required(VERSION 3.1)
project(nxsedit)

include_directories(../../../vcglib ../../../vcglib/eigenlib)


SET(HEADERS
	../../../vcglib/wrap/system/qgetopt.h
	../common/virtualarray.h
	../common/nexusdata.h
	../common/traversal.h
	../common/signature.h
	../nxszip/zpoint.h
	../nxszip/model.h
	../nxszip/range.h
	../nxszip/fpu_precision.h
	../nxszip/bytestream.h
	../nxszip/math_class.h
	../nxszip/bitstream.h
	../nxszip/tunstall.h
	../nxszip/cstream.h
	../nxszip/meshcoder.h
	../nxszip/meshdecoder.h
	extractor.h

)

SET(SOURCES
	 ../../../vcglib/wrap/system/qgetopt.cpp
	../../../vcglib/wrap/ply/plylib.cpp
	../common/virtualarray.cpp
	../common/nexusdata.cpp
	../common/traversal.cpp
	../common/cone.cpp
	../nxszip/bitstream.cpp
	../nxszip/tunstall.cpp
	../nxszip/meshcoder.cpp
	../nxszip/meshdecoder.cpp
	main.cpp
	extractor.cpp

)

cmake_minimum_required(VERSION 3.1)

project(nxsedit)

set(CMAKE_INCLUDE_CURRENT_DIR ON)
set(CMAKE_AUTOMOC ON)

find_package(Qt5Widgets)

add_executable(nxsedit ${SOURCES} ${HEADERS})

target_link_libraries(nxsedit Qt5::Widgets)

