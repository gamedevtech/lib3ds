FIND_PACKAGE(OpenGL)
FIND_PACKAGE(GLUT)
IF(GLUT_FOUND)
	IF(MSVC)
		ADD_DEFINITIONS(-D_CRT_SECURE_NO_WARNINGS)
	ENDIF(MSVC)
	INCLUDE_DIRECTORIES( ${lib3ds_SOURCE_DIR}/src ${OPENGL_INCLUDE_DIR} ${GLUT_INCLUDE_DIR})
	ADD_EXECUTABLE(3dsplay 3dsplay.cpp tga.c tga.h)
	TARGET_LINK_LIBRARIES(3dsplay lib3ds ${OPENGL_LIBRARIES} ${GLUT_LIBRARIES})
ENDIF(GLUT_FOUND)