cmake_minimum_required(VERSION 3.4.1)

file(GLOB_RECURSE protobuf_SRC
        "*.h"
        "*.cc"
        )

#add_library(
#        protobuf
#        ${protobuf_SRC}
#)

add_library(
        protobuf
        SHARED
        io/coded_stream.cc
        extension_set.cc
        wire_format_lite.cc
        descriptor.cc
        generated_message_reflection.cc
        reflection_ops.cc
        wire_format.cc
        port_def.inc
        parse_context.cc
        io/zero_copy_stream.cc
        arena.cc
        implicit_weak_message.cc
        repeated_field.cc
        stubs/strutil.cc
        stubs/common.cc
        stubs/stringpiece.cc
        stubs/status.cc
        stubs/int128.cc
        message_lite.cc
        stubs/stringprintf.cc
        parse_context.cc
        io/zero_copy_stream_impl.cc
        io/zero_copy_stream_impl_lite.cc
        generated_message_table_driven.cc
        generated_message_util.cc
        port_undef.inc
        message.cc
        map_field.cc
        generated_message_table_driven_lite.cc
)

target_link_libraries(protobuf
        log)

target_compile_options(protobuf PRIVATE
        -frtti)