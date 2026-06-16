# pbPlots C++ Library Build with GCC
# Hand Written Makefile (Edit with caution)
#
# Seagate Technology
#

CXX = g++
AR = ar
TOOL_CHAIN = gcc
LIB_FILE_OUTPUT_DIR = lib
SRC_DIR = ../..

# Compiler flags matching DHM project standards
# Note: Removed -Werror=old-style-cast since pbPlots uses old-style casts and is external code
CXXFLAGS ?= -Wall -Wextra -Wshadow -Wmaybe-uninitialized -Wvla -Wfloat-equal \
    -Wlogical-op -Wdouble-promotion -Wformat-security -Wduplicated-cond -Wnull-dereference \
    -Wshift-overflow=2 -Wjump-misses-init -Wstringop-overflow -std=c++11

# Source files
SOURCES = $(SRC_DIR)/pbPlots.cpp \
          $(SRC_DIR)/supportLib.cpp

OBJECTS = $(SOURCES:.cpp=.o)
LIB_TARGET = $(LIB_FILE_OUTPUT_DIR)/libpbplots.a

# Include directories
INC_DIR = -I$(SRC_DIR) \
          -I$(SRC_DIR)/..

.PHONY: all clean

all: $(LIB_TARGET)

$(LIB_FILE_OUTPUT_DIR):
	mkdir -p $(LIB_FILE_OUTPUT_DIR)

$(LIB_TARGET): $(LIB_FILE_OUTPUT_DIR) $(OBJECTS)
	$(AR) rcs $@ $(OBJECTS)
	@echo "============================================================"
	@echo "      pbPlots library built successfully: $@"
	@echo "============================================================"

%.o: %.cpp
	$(CXX) -c $(CXXFLAGS) $(INC_DIR) $< -o $@

clean:
	rm -f $(OBJECTS)
	rm -rf $(LIB_FILE_OUTPUT_DIR)
	@echo "============================================================"
	@echo "      pbPlots has been CLEANED"
	@echo "============================================================"
