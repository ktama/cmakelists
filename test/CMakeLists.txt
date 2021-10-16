# 実行ファイル a.out をソースコード main.cpp hello.cpp から作成
add_executable(a.out main.cpp)

# a.out を作成する際に libgreetings.a をリンク
target_link_libraries(a.out greetings)
