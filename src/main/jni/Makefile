# Define a variable for classpath
CLASS_PATH = ../../../classes/target/alg/deeplearn/

# Define a virtual path for .class in the bin directory
vpath %.class $(CLASS_PATH)

# $* matches the target filename without the extension
header :
	javah -jni -classpath ../../../target/classes utils.CPrint

all : libcfloat.so

utils_CPrint.o : utils_CPrint.c utils_CPrint.h
	gcc -fPIC -I/System/Library/Frameworks/JavaVM.framework/Headers -c utils_CPrint.c
	#gcc -I/Library/Java/JavaVirtualMachines/jdk1.7.0_79.jdk/Contents/Home/include/ -I/Library/Java/JavaVirtualMachines/jdk1.7.0_79.jdk/Contents/Home/include/darwin/ -c $< -o $@

#	gcc -Wl -shared -o $@ $<
libcfloat.so : utils_CPrint.o
	gcc -shared -o libcfloat.so utils_CPrint.o

clean :
	rm libcfloat.so utils_CPrint.o