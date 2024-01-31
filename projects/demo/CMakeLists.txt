#--------------------------------------------------------------------------
# Monotreme project
#--------------------------------------------------------------------------

PROJECT(Monotreme)
FILE(GLOB project_headers code/*.hpp)
FILE(GLOB project_sources code/*.cpp)

SET(files_project ${project_headers} ${project_sources})
SOURCE_GROUP("Monotreme" FILES ${files_project})

ADD_EXECUTABLE(Monotreme ${files_project})
TARGET_LINK_LIBRARIES(Monotreme engine)
ADD_DEPENDENCIES(Monotreme engine)

IF(MSVC)
    set_property(TARGET Monotreme PROPERTY VS_DEBUGGER_WORKING_DIRECTORY "${CMAKE_SOURCE_DIR}/bin")
ENDIF()