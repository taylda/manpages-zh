include $(srcdir)/../manpages

mandir = @mandir@/zh_TW

if APPEND_COLOPHON
APPEND_COLOPHON = ${top_srcdir}/utils/append-colophon
else !APPEND_COLOPHON
APPEND_COLOPHON = tee
endif

man_MANS = $(MANPAGES)

if UTF8
%.3: $(srcdir)/../%.3
	$(APPEND_COLOPHON) < $< | iconv -f utf8 -t gbk | autob5 | $(top_srcdir)/utils/totw.pl | iconv -f big5 -t utf8 > $@
else
%.3: $(srcdir)/../%.3
	$(APPEND_COLOPHON) < $< | iconv -f utf8 -t gbk $< | autob5 | $(top_srcdir)/utils/totw.pl > $@
endif

clean-local:
	rm -f $(man_MANS)
