include ../../run-make-fulldeps/tools.mk

# ignore-32bit wrong/no cross compiler and sometimes we pass wrong gcc args (-m64)

all: foo
	$(call RUN,foo)

foo: foo.rs $(call NATIVE_STATICLIB,foo)
	$(RUSTC) $< -lfoo $(EXTRARSCXXFLAGS)

$(TMPDIR)/libfoo.o: foo.cpp
	$(call COMPILE_OBJ_CXX,$@,$<)
