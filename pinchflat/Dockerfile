FROM ghcr.io/kieraneglin/pinchflat:v2025.6.6

# Install Deno - required for YouTube downloads (See yt-dlp#14404)
RUN curl -fsSL https://deno.land/install.sh | DENO_INSTALL=/usr/local sh -s -- -y --no-modify-path

# FFmpeg (latest build that doesn't cause an illegal instruction error for some users - see #347)
RUN apt-get update && apt-get install -y xz-utils
RUN curl -L "https://github.com/yt-dlp/FFmpeg-Builds/releases/download/autobuild-2026-02-12-14-57/ffmpeg-N-122730-g57fe259773-linuxarm64-gpl.tar.xz" --output /tmp/ffmpeg.tar.xz
RUN tar -xf /tmp/ffmpeg.tar.xz --strip-components=2 --no-anchored -C /usr/local/bin/ "ffmpeg"
RUN tar -xf /tmp/ffmpeg.tar.xz --strip-components=2 --no-anchored -C /usr/local/bin/ "ffprobe"
