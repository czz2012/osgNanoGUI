SET(NIUBI_SETUP_TARGET_NAME example_osgNanoGUI)

SET(NIUBI_SETUP_HEADERS
)

SET(NIUBI_SETUP_SOURCES
    osgNanoGUI.cpp
)

INCLUDE_DIRECTORIES(AFTER ${PROJECT_SOURCE_DIR}/include/ )
INCLUDE_DIRECTORIES(AFTER ${OSG_INCLUDE_DIR})
# INCLUDE_DIRECTORIES(AFTER ${CEF_DIR})
INCLUDE_DIRECTORIES(AFTER ${GLEW_INCLUDE_DIR})
INCLUDE_DIRECTORIES(AFTER ${NanoVG_INCLUDE_DIR})
INCLUDE_DIRECTORIES(AFTER ${NanoGUI_INCLUDE_DIR})
INCLUDE_DIRECTORIES(AFTER ${NanoGUI_INCLUDE_DIR}/../ext/eigen)


NIUBI_SETUP_EXECUTABLE()
TARGET_LINK_LIBRARIES( ${NIUBI_SETUP_TARGET_NAME} 
    ${OPENGL_LIBRARIES}
    optimized ${OPENTHREADS_LIBRARY}    debug ${OPENTHREADS_LIBRARY_DEBUG}
    optimized ${OSG_LIBRARY}            debug ${OSG_LIBRARY_DEBUG} 
    optimized ${OSGDB_LIBRARY}          debug ${OSGDB_LIBRARY_DEBUG} 
    optimized ${OSGUTIL_LIBRARY}        debug ${OSGUTIL_LIBRARY_DEBUG}
    optimized ${OSGGA_LIBRARY}          debug ${OSGGA_LIBRARY_DEBUG} 
    optimized ${OSGVIEWER_LIBRARY}      debug ${OSGVIEWER_LIBRARY_DEBUG}

	osgNanoGUI

	optimized ${GLEW_LIBRARY_RELEASE}      debug ${GLEW_LIBRARY_DEBUG}
    )
# NIUBI_SETUP_INSTALL()
# NIUBI_SETUP_DOCUMENT()




