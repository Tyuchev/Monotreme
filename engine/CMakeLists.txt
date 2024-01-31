#--------------------------------------------------------------------------
# engine
#--------------------------------------------------------------------------

ADD_LIBRARY(engine INTERFACE)
TARGET_INCLUDE_DIRECTORIES(engine INTERFACE ${CMAKE_CURRENT_SOURCE_DIR})
TARGET_LINK_LIBRARIES(engine INTERFACE ${OPENGL_LIBS})
ADD_SUBDIRECTORY(raytracer)
TARGET_LINK_LIBRARIES(engine INTERFACE raytracer)

SET_TARGET_PROPERTIES(raytracer PROPERTIES FOLDER "engine")