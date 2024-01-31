#--------------------------------------------------------------------------
# raytracer
#--------------------------------------------------------------------------

SET(files_raytracer
	raytracer.cpp
	raytracer.hpp)
SOURCE_GROUP("raytracer" FILES ${files_raytracer})
	
SET(files_pch ../config.h ../config.cpp)
SOURCE_GROUP("pch" FILES ${files_pch})
ADD_LIBRARY(raytracer STATIC ${files_raytracer} ${files_pch})
TARGET_PCH(raytracer ../)
ADD_DEPENDENCIES(raytracer exts glew glfw imgui glm_static)
TARGET_LINK_LIBRARIES(raytracer PUBLIC engine exts glew glfw imgui ${OPENGL_LIBS} glm_static)