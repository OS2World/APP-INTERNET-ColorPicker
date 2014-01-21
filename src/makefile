!include ibmsamp.inc

HEADERS = cpicker.h
#-------------------------------------------------------------------
#
#   A list of all of the object files
#
#-------------------------------------------------------------------

OBJS = $(OBJDIR)\cpicker.obj
EXEDIR= ..
#-------------------------------------------------------------------
#   This section lists all files to be built by  make.  The
#   makefile builds the executable as well as its associated help
#   file.
#-------------------------------------------------------------------
all: $(EXEDIR)\cpicker.exe

#-------------------------------------------------------------------
#   Dependencies
#     This section lists all object files needed to be built for the
#     application, along with the files it is dependent upon (e.g.
#     its source and any header files).
#-------------------------------------------------------------------

$(OBJDIR)\cpicker.res: $(HEADERS) cpicker.rc cpicker.ico 
                $(RC) $(RCFLAGS) $(@B).rc $@
          
$(OBJDIR)\cpicker.obj: cpicker.c $(HEADERS)

$(EXEDIR)\cpicker.exe: $(OBJS) $(@B).def $(OBJDIR)\$(@B).res
   -$(CREATE_PATH)
   $(LINK) $@ $(@B).def $(MTLIBS) $(OBJS)
   $(RC) -p -x $(OBJDIR)\$(@B).res $@
   lxlite $(EXEDIR)\cpicker.exe

clean :
        @if exist *.res del *.res
        @if exist *.obj del *.obj
        @if exist *.dll del *.dll
        @if exist *.exe del *.exe
