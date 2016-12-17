include $(srcdir)/../manpages

mandir = @mandir@/zh_CN

if APPEND_COLOPHON
APPEND_COLOPHON = ${top_srcdir}/utils/append-colophon
else !APPEND_COLOPHON
APPEND_COLOPHON = tee
endif

man_MANS = $(MANPAGES)

if UTF8
%.4: $(srcdir)/../%.4
	$(APPEND_COLOPHON) < $< > $@
else !UTF8
%.4: $(srcdir)/../%.4
	$(APPEND_COLOPHON) < $< | iconv -f utf8 -t gbk -o $@
endif

clean-local:
	rm -f $(man_MANS)
