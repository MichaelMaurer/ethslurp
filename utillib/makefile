cflags=-std=c++11 -Wall -O2 -DLINUX

product=utillib.a

src= \
attribute.cpp \
basenode.cpp \
bigint.cpp \
biglib.cpp \
biguint.cpp \
config.cpp \
codeWriter.cpp \
curl_code.cpp \
database.cpp \
dates.cpp \
editableobject.cpp \
editableobjectbase.cpp \
exportcontext.cpp \
importcontext.cpp \
fielddata.cpp \
fieldlist.cpp \
paths.cpp \
options.cpp \
runtimeclass.cpp \
sfarchive.cpp \
sfdate.cpp \
sffile.cpp \
sffolder.cpp \
sfos.cpp \
sfstring.cpp \
sftime.cpp \
sftimeofday.cpp \
sftimespan.cpp \
sha3.cpp \
version.cpp \
visitor.cpp

#-------------------------------------------------
# probably don't have to change below this line

objects = $(patsubst %.cpp,objs/%.o,$(src))

all:
	@make $(product)
	@echo ""

$(product): $(objects)
	-@$(RM) -f $*.a
	ar qc $*.a $(objects)
#	@chown jrush.jrush $(product)

$(objects): | objs

objs:
	@mkdir -p $@

objs/%.o : %.cpp
	$(CXX) $(CXXFLAGS) $(cflags) -c $< -o $@

clean:
	-@$(RM) -f $(dest) $(product) objs/* 2> /dev/null
