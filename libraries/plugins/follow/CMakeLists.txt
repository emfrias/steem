file(GLOB HEADERS "include/steemit/follow/*.hpp")

add_library( steemit_follow
             follow_plugin.cpp
           )

target_link_libraries( steemit_follow steemit_chain steemit_app graphene_time )
target_include_directories( steemit_follow
                            PUBLIC "${CMAKE_CURRENT_SOURCE_DIR}/include" )

install( TARGETS
   steemit_follow

   RUNTIME DESTINATION bin
   LIBRARY DESTINATION lib
   ARCHIVE DESTINATION lib
)
