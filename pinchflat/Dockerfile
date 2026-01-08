FROM ghcr.io/kieraneglin/pinchflat:v2025.6.6

# Install Deno - required for YouTube downloads (See yt-dlp#14404)
# FFmpeg (latest build that doesn't cause an illegal instruction error for some users - see #347)
RUN  curl -fsSL https://deno.land/install.sh | DENO_INSTALL=/usr/local sh -s -- -y --no-modify-path && \
    curl -L "https://github.com/yt-dlp/FFmpeg-Builds/releases/download/autobuild-2026-01-08-14-24/ffmpeg-N-122390-gaf6a1dd0b2-linuxarm64-gpl.tar.xz" --output /tmp/ffmpeg.tar.xz && \
    tar -xf /tmp/ffmpeg.tar.xz --strip-components=2 --no-anchored -C /usr/local/bin/ "ffmpeg" && \
    tar -xf /tmp/ffmpeg.tar.xz --strip-components=2 --no-anchored -C /usr/local/bin/ "ffprobe"
