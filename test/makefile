LIBS = \
	{Libraries}Stubs.o \
	{CLibraries}StdCLib.o \
	{Libraries}Interface.o \
	{Libraries}Runtime.o \
	{Libraries}ToolLibs.o

PPC_LIBS = {SharedLibraries}InterfaceLib \
	{SharedLibraries}StdCLib \
	{PPCLibraries}StdCRuntime.o \
	{PPCLibraries}PPCCRuntime.o

LDFLAGS = -w -c 'MPS ' -t MPST \
	-sn STDIO=Main -sn INTENV=Main -sn %A5Init=Main

SCFLAGS = -p

TARGETS = test_new_handle test_new_handle_2 test_new_pointer

all : $(TARGETS)

clean : 
	rm -f $(TARGETS) o/*

test_new_handle : o/test_new_handle.o
	mpw Link $(LDFLAGS) -o $@ $^ $(LIBS) 

test_new_handle_2 : o/test_new_handle_2.o
	mpw Link $(LDFLAGS) -o $@ $^ $(LIBS) 

test_new_pointer : o/test_new_pointer.o
	mpw Link $(LDFLAGS) -o $@ $^ $(LIBS) 


# % : o/%.o
# 	mpw Link $(LDFLAGS) -o $@ $^ $(LIBS) 

o/%.o : %.c
	mpw SC $(SCFLAGS) $< -o $@
