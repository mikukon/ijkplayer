cmake_minimum_required(VERSION 3.4.1)

set(CMAKE_VERBOSE_MAKEFILE on)

# set binary output folder to Android assets folder
#set(EXECUTABLE_OUTPUT_PATH      "${CMAKE_CURRENT_SOURCE_DIR}/src/main/assets/${ANDROID_ABI}")
# android 特定变量。。。使用LIBRARY_OUTPUT_PATH无效
#set(CMAKE_LIBRARY_OUTPUT_DIRECTORY     "${CMAKE_CURRENT_SOURCE_DIR}/src/main/assets/${ANDROID_ABI}")

set(ijkffmpeg_base_dir ${CMAKE_CURRENT_SOURCE_DIR}/../../../android/contrib/build)

if(${ANDROID_ABI} STREQUAL armeabi)
    set(ijkffmpeg_target_dir ${ijkffmpeg_base_dir}/ffmpeg-armv5/output)
elseif(${ANDROID_ABI} STREQUAL armeabi-v7a)
    set(ijkffmpeg_target_dir ${ijkffmpeg_base_dir}/ffmpeg-armv7a/output)
elseif(${ANDROID_ABI} STREQUAL arm64-v8a)
    set(ijkffmpeg_target_dir ${ijkffmpeg_base_dir}/ffmpeg-arm64/output)
elseif(${ANDROID_ABI} STREQUAL x86)
    set(ijkffmpeg_target_dir ${ijkffmpeg_base_dir}/ffmpeg-x86/output)
elseif(${ANDROID_ABI} STREQUAL x86_64)
    set(ijkffmpeg_target_dir ${ijkffmpeg_base_dir}/ffmpeg-x86_64/output)
endif()

set(ijkffmpeg_target_inc_dir ${ijkffmpeg_target_dir}/include)

set(ijkffmpeg_target_lib_path ${CMAKE_SOURCE_DIR}/libs/${ANDROID_ABI})

add_subdirectory(src/main/cpp/android-ndk-prof)
add_subdirectory(src/main/cpp/ijkmedia)