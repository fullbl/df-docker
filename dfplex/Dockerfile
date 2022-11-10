FROM fullbl/dfhack:0.47.04

ENV DFPLEX_VERSION=0.2.1 \
    DFPLEX_ARCHIVE_NAME=dfplex-v0.2.1-Linux64 \
    DFPLEX_ARCHIVE_SHA1=14b6d737162d43a3f266724299b40ef2315ae8b1 \
    DFHACK_HEADLESS=1 \
    DFHACK_DISABLE_CONSOLE=0

RUN curl -LSo dfplex.zip https://github.com/white-rabbit-dfplex/dfplex/releases/download/v${DFPLEX_VERSION}-dfplex/${DFPLEX_ARCHIVE_NAME}.zip \
 && (echo "${DFPLEX_ARCHIVE_SHA1} *dfplex.zip";) | sha1sum -c \
 && unzip dfplex.zip \
 && cp -r ${DFPLEX_ARCHIVE_NAME}/* . \
 && rm -rf ${DFPLEX_ARCHIVE_NAME} dfplex.zip

RUN echo "\n[PRINT_MODE:TEXT]\n[INTRO:NO]\n[TRUETYPE:NO]\n[SOUND:NO]" >> /df_linux/data/init/init.txt
RUN echo "\n[BIRTH_CITIZEN:A_D:D_D]\n[MOOD_BUILDING_CLAIMED:A_D:D_D]\n[ARTIFACT_BEGUN:A_D:D_D]" >> /df_linux/data/init/announcements.txt
EXPOSE 8000
EXPOSE 5000
EXPOSE 1234
