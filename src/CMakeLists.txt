#add_definitions(-DLUABIND_BUILDING)
include_directories(${Boost_INCLUDE_DIRS} ${LUA_INCLUDE_DIR} ${CMAKE_SOURCE_DIR})

add_definitions(-fsanitize=address -fno-omit-frame-pointer)

add_library(luabind class.cpp class_registry.cpp error.cpp function.cpp link_compatibility.cpp open.cpp scope.cpp weak_ref.cpp
                    class_info.cpp class_rep.cpp create_class.cpp exception_handler.cpp inheritance.cpp object_rep.cpp
                    pcall.cpp stack_content_by_name.cpp wrapper_base.cpp)

target_link_libraries(luabind ${LUA_LIBRARIES})

INSTALL(
    TARGETS luabind
#    DESTINATION lib
    PERMISSIONS OWNER_READ OWNER_WRITE GROUP_READ WORLD_READ
)
