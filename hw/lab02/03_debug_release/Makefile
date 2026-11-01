CXX = g++
CXXFLAGS = -Wall -Wextra -MMD -MP

MODE ?= release


ifeq ($(MODE), debug)
	CXXFLAGS += -g -O0
else
	CXXFLAGS += -O3
endif

TARGET = calculator
OBJDIR = obj
SRCS = $(wildcard *.cpp)
OBJS = $(patsubst %.cpp, $(OBJDIR)/%.o, $(SRCS))
DEPS = $(OBJS:.o=.d)

.PHONY: all clean

all: $(TARGET)

$(TARGET): $(OBJS)
	$(CXX) $(CXXFLAGS) -o $@ $^

$(OBJDIR)/%.o: %.cpp
	@mkdir -p $(OBJDIR)
	$(CXX) $(CXXFLAGS) -c $< -o $@

-include $(DEPS)

clean:
	rm -rf $(TARGET) $(OBJDIR)
