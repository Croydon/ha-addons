FROM ghcr.io/kieraneglin/pinchflat:v2025.6.6

# Install Deno - required for YouTube downloads (See yt-dlp#14404)
RUN  curl -fsSL https://deno.land/install.sh | DENO_INSTALL=/usr/local sh -s -- -y --no-modify-path
