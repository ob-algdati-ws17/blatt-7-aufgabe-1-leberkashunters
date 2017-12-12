file(GLOB SRCS *.cpp)

if (APPLE)
    add_definitions(-DGTEST_USE_OWN_TR1_TUPLE)
    add_definitions(-D__GLIBCXX__)
endif (APPLE)

add_executable(testavltree)${SRCS})

target_link_libraries(testavltree
        avltree
        gtest
        gmock
)

include_directories("..")

install(TARGETS testavltree DESTINATION bin)
