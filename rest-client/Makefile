##########################################################
program_NAME = client
CXXFLAGS+= -std=c++11

##########################################################
### all .c, .cc and .cpp
program_SRC_DIRS += ./src/ ./rest-client/source/
program_SRCS +=  $(foreach dir,$(program_SRC_DIRS),$(wildcard $(dir)*.c))
program_SRCS +=  $(foreach dir,$(program_SRC_DIRS),$(wildcard $(dir)*.cc))
program_SRCS +=  $(foreach dir,$(program_SRC_DIRS),$(wildcard $(dir)*.cpp))

##########################################################
### -I ./include
###  directory with .h, .hpp
###  include<>
program_INCLUDE_DIRS = ./rest-client/include ./curl/include
###  -L ./lib
###  directory with .a .so .lib .dll
program_LIBRARY_DIRS = ./curl/lib
###  linux:   lib***.a = -l***
###  windows: lib***.lib = -lib***.lib
program_LIBRARIES = curl

#  include
CPPFLAGS += $(foreach includedir,$(program_INCLUDE_DIRS),-I$(includedir))
#  link
LDFLAGS += $(foreach librarydir,$(program_LIBRARY_DIRS),-L$(librarydir))
LDFLAGS += $(foreach library,$(program_LIBRARIES),-l$(library))

##########################################################
all:
	$(CXX) $(CXXFLAGS) $(program_SRCS) $(LDFLAGS) $(CPPFLAGS) -o $(program_NAME)
