include $(srcdir)/../manpages

mandir = @mandir@/zh_TW

if APPEND_COLOPHON
APPEND_COLOPHON = ${top_srcdir}/utils/append-colophon
else !APPEND_COLOPHON
APPEND_COLOPHON = tee
endif

man_MANS = $(MANPAGES)

%.2: $(srcdir)/../%.2
	$(APPEND_COLOPHON) < $< | iconv -f utf8 -t gbk | autob5 | $(top_srcdir)/utils/totw.pl | iconv -f big5 -t utf8 > $@

clean-local:
	rm -f $(man_MANS)
