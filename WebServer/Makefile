all:webcam_server 

CC=g++
LD=ld
#CC=arm-linux-g++
#LD=arm-linux-ld
CXXFLAGS=  -c -g -O0 -fPIC -I/usr/local/include -L/usr/local/lib  

OBJS_SERVER=  capture.o vcompress.o sender.o server.o
LIBS_SERVER=  -lavcodec -lswscale -lavutil -lx264 -lpthread -lz

.cpp.o:
	$(CC) $(CXXFLAGS) $<

webcam_server: $(OBJS_SERVER)
	$(CC) -o $@ $^ -L./ffmpeg/lib $(LIBS_SERVER)

clean:
	rm -f *.o
	rm -f webcam_server
