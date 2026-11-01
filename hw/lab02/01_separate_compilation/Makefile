CXX = g++
CXXFLAGS = -Wall -Wextra

TARGET = calculator
OBJDIR = obj
SRCS = main.cpp calc.cpp
OBJS = $(addprefix $(OBJDIR)/, $(SRCS:.cpp=.o))

.PHONY: all clean

all: $(TARGET)

$(TARGET): $(OBJS)
	$(CXX) $(CXXFLAGS) -o $@ $^

$(OBJDIR)/%.o: %.cpp calc.h
	@mkdir -p $(OBJDIR)
	$(CXX) $(CXXFLAGS) -c $< -o $@

clean:
	rm -rf $(TARGET) $(OBJDIR)
