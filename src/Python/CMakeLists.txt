if(PYTHON_PREFIX)
	if(${CMAKE_VERSION} VERSION_LESS "3.12.0")
		install(CODE "execute_process(COMMAND ${PYTHON_EXECUTABLE} setup.py install --prefix=${CMAKE_INSTALL_PREFIX} --force WORKING_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR})")
	else()
		install(CODE "execute_process(COMMAND ${Python_EXECUTABLE} setup.py install --prefix=${CMAKE_INSTALL_PREFIX} --force WORKING_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR})")
	endif()
endif()

if(${CMAKE_VERSION} VERSION_LESS "3.12.0")
	install(CODE "execute_process(COMMAND ${PYTHON_EXECUTABLE} setup.py install --force WORKING_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR})")
else()
	install(CODE "execute_process(COMMAND ${Python_EXECUTABLE} setup.py install --force WORKING_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR})")
endif()
