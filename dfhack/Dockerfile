FROM fullbl/dwarffortress:0.47.04

ENV DFHACK_VERSION=0.47.04-r1 \
    DFHACK_ARCHIVE_NAME=dfhack-0.47.04-r1-Linux-64bit-gcc-7.tar.bz2 \
    DFHACK_ARCHIVE_SHA1=9091fc7fda6cbf7a1e8dfb5e0fa20aeeb9bff2b1 \
    TERM=linux \
    DFHACK_HEADLESS=1 \
    DFHACK_DISABLE_CONSOLE=0

RUN curl -LSo dfhack.tar.bz2 https://github.com/DFHack/dfhack/releases/download/${DFHACK_VERSION}/${DFHACK_ARCHIVE_NAME} \
 && echo "${DFHACK_ARCHIVE_SHA1} *dfhack.tar.bz2" | sha1sum -c \
 && tar -xjvf dfhack.tar.bz2 \
 && rm -rf dfhack.tar.bz2 stonesense hack/plugins/stonesense.plug.so \
 && mv dfhack.init-example dfhack.init \
 && echo "if ! setarch x86_64 -R grep -q 00040000 /proc/self/personality; then echo 'Access to the ADDR_NO_RANDOMIZE personality is required for DFHack to run.'; echo 'See https://github.com/BenLubar/df-docker#readme for details.'; exit 2; fi" > distro_fixes.sh

CMD ["./dfhack"]
