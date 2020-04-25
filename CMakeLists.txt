project (NearestSearch CXX C)
cmake_minimum_required(VERSION 2.6)

find_package(LAPACK)

SET(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -O2 -std=c++0x -m64")
SET(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -O2 -std=c++0x -m64")

SET(YAEL_DIR /home/manstein/workplace/cv/yael_install_all/yael_v438)
SET(YAEL_LIB /home/manstein/workplace/cv/yael_install_all/yael_v438/yael)

SET(BLAS_DIR /home/manstein/workplace/cv/OpenBLAS/lib/include)
SET(BLAS_LIB /home/manstein/workplace/cv/OpenBLAS/lib/lib)

#########################################################################################
INCLUDE_DIRECTORIES(${BLAS_DIR})
INCLUDE_DIRECTORIES(${YAEL_DIR})
LINK_DIRECTORIES(${YAEL_LIB})
LINK_DIRECTORIES(${BLAS_LIB})
ADD_EXECUTABLE (learnGNOIMI learn_GNOIMI.cpp)
TARGET_LINK_LIBRARIES (learnGNOIMI yael lapack cblas blas pthread ${LAPACK_LIBRARIES})

#########################################################################################
INCLUDE_DIRECTORIES(${BLAS_DIR})
INCLUDE_DIRECTORIES(${YAEL_DIR})
LINK_DIRECTORIES(${YAEL_LIB})
LINK_DIRECTORIES(${BLAS_LIB})
ADD_EXECUTABLE (searchGNOIMI search_GNOIMI.cpp)
TARGET_LINK_LIBRARIES (searchGNOIMI yael lapack cblas blas pthread ${LAPACK_LIBRARIES})
