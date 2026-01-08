FROM ghcr.io/kieraneglin/pinchflat:v2025.6.6

# Install Deno - required for YouTube downloads (See yt-dlp#14404)
RUN  curl -fsSL https://deno.land/install.sh | DENO_INSTALL=/usr/local sh -s -- -y --no-modify-path && \
    # FFmpeg (latest build that doesn't cause an illegal instruction error for some users - see #347)
    export FFMPEG_DOWNLOAD=$(case ${TARGETPLATFORM:-linux/amd64} in \
    "linux/amd64")   echo "https://github.com/yt-dlp/FFmpeg-Builds/releases/download/autobuild-2025-09-25-18-11/ffmpeg-N-121208-g2c8835dd72-linux64-gpl.tar.xz"   ;; \
    "linux/arm64")   echo "https://github.com/yt-dlp/FFmpeg-Builds/releases/download/autobuild-2025-09-25-18-11/ffmpeg-N-121208-g2c8835dd72-linuxarm64-gpl.tar.xz" ;; \
    *)               echo ""        ;; esac) && \
    curl -L ${FFMPEG_DOWNLOAD} --output /tmp/ffmpeg.tar.xz && \
    tar -xf /tmp/ffmpeg.tar.xz --strip-components=2 --no-anchored -C /usr/local/bin/ "ffmpeg" && \
    tar -xf /tmp/ffmpeg.tar.xz --strip-components=2 --no-anchored -C /usr/local/bin/ "ffprobe"
