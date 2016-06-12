RESOLUTIONS := 800x600 640x480 320x240 160x120
RAW_IMGS := $(wildcard raw/*)
RAW_BASE_IMGS := $(notdir ${RAW_IMGS})

all: ${RESOLUTIONS}

.PHONY: ${RESOLUTIONS}
${RESOLUTIONS}: %: ${RAW_IMGS}
	@command -v convert > /dev/null 2> /dev/null || { echo "Need ImageMagick for that." ; exit 1 ; }
	@mkdir -p gen_$@
	@for img in ${RAW_BASE_IMGS} ; do \
		echo convert raw/$$img -resize $@ gen_$@/$$img.png ; \
		     convert raw/$$img -resize $@ gen_$@/$$img.png || exit 1 ; \
	done
