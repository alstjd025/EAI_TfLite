CC := g++
CFLAGS := -std=c++11 -I/usr/include
INCLUDEPATHS := -I/home/pi/tensorflow -I/home/pi/tensorflow/tensorflow/lite/tools/make/downloads/absl\
	        -I/home/pi/tensorflow/tensorflow/lite/tools/make/downloads/flatbuffers/build
LDFLAGS := -pthread -ltensorflow-lite -lflatbuffers -ldl
LDPATH := -L/home/pi/tensorflow/tensorflow/lite/tools/make/gen/bbb_armv7l/lib\
	  -L/home/pi/tensorflow/tensorflow/lite/tools/make/downloads/absl\
	  -L/home/pi/tensorflow/tensorflow/lite/tools/make/downloads/flatbuffers/build

SRCS := minimal.cc
OBJS := $(SRCS:.cc=.o)
EXEC := minimal

.PHONY: all clean

all: $(EXEC)

$(EXEC): $(OBJS)
	$(CC) $(CFLAGS) $(INCLUDEPATHS) -o $@ $^ $(LDPATH) $(LDFLAGS)  

%.o: %.cc
	$(CC) $(CFLAGS) $(INCLUDEPATHS) -c $< -o $@ $(LDPATH) $(LDFLAGS)  

clean : 
	rm -f $(OBJS) $(EXEC)
