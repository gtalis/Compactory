cmake_minimum_required(VERSION 3.10)

project(Compactory)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED True)

# sources
file(GLOB sources
	BitmapText.cpp
	Box.cpp
	Conveyor.cpp
	EntryPoint.cpp
	FactoryState.cpp
	Main.cpp
	State.cpp
	Bouncer.cpp
	Cell.cpp
	Directions.cpp
	ExitPoint.cpp
	Game.cpp
	Splitter.cpp
)


#-------------------------------------------------------------------------------
# Dependencies
#-------------------------------------------------------------------------------
include(FindPkgConfig)
# SFML
PKG_SEARCH_MODULE(SFML REQUIRED sfml-all)

include_directories(${SFML_INCLUDE_DIRS})

include_directories("${PROJECT_SOURCE_DIR}")

add_executable(Compactory ${sources})
target_link_libraries(Compactory ${SFML_LIBRARIES})

#-------------------------------------------------------------------------------
# Install commands
#-------------------------------------------------------------------------------
install(TARGETS   Compactory RUNTIME DESTINATION bin)
install(DIRECTORY Resource/ DESTINATION share/Compactory/Resource)
