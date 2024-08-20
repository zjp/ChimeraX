ifndef UBUNTU_DIST
.PHONY: ffmpeg/ffmpeg
all:
CLEAN_ALWAYS = ffmpeg/ffmpeg src/bin/ffmpeg

DEPS += ffmpeg/ffmpeg

ffmpeg/ffmpeg:
	$(MAKE) -C ffmpeg
endif

include ../Makefile.bundle
