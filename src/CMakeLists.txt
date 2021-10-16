# cmake -DGREETINGS_BUILD_SHARED_LIBS=ON .. で指定
option(GREETINGS_BUILD_SHARED_LIBS "build greetings as a shared library" OFF)

if (GREETINGS_BUILD_SHARED_LIBS)
    # hello.cpp good_morning.cpp から静的ライブラリ libgreetings.a を作成
    add_library(greetings
    STATIC
        hello.cpp
        good_morning.cpp
    )
else()
    # hello.cpp good_morning.cpp から共有ライブラリ libgreetings.a を作成
    add_library(greetings
    SHARED
        hello.cpp
        good_morning.cpp
    )
endif()

target_include_directories(greetings
    PUBLIC ${PROJECT_SOURCE_DIR}/include
    )
