cmake_minimum_required (VERSION 3.0)

set(SOURCES
Beat.cpp
Instrument.cpp
Note.cpp
Percussion.cpp
TrackBuffer.cpp
VoicePiece.cpp
Singer.cpp
instruments/BottleBlow.cpp
instruments/NaivePiano.cpp
instruments/PureSin.cpp
instruments/Sawtooth.cpp
instruments/Square.cpp
instruments/Triangle.cpp
percussions/TestPerc.cpp
)

set(HEADERS 
Beat.h
Deferred.h
Instrument.h
Note.h
Percussion.h
RefCounted.h
TrackBuffer.h
VoicePiece.h
Singer.h
instruments/BottleBlow.h
instruments/NaivePiano.h
instruments/PureSin.h
instruments/Sawtooth.h
instruments/Square.h
instruments/Triangle.h
percussions/TestPerc.h
)

set (INCLUDE_DIR
.
)

if (WIN32) 
set (DEFINES  ${DEFINES}
-D"_CRT_SECURE_NO_DEPRECATE"  
-D"_SCL_SECURE_NO_DEPRECATE" 
)
else()
add_definitions(-std=c++0x)
add_compile_options(-fPIC)
endif()

include_directories(${INCLUDE_DIR})
add_definitions(${DEFINES})
add_library (ScoreDraftCore ${SOURCES} ${HEADERS})





