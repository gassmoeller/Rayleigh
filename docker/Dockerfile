FROM rayleigh:base

LABEL maintainer <rene.gassmoeller@mailbox.org>

ENV RAYLEIGH_DIR /home/rayleigh/Rayleigh
ENV PATH="/home/rayleigh/Rayleigh/bin:${PATH}"

RUN useradd -ms /bin/bash rayleigh
USER rayleigh

# Build aspect
RUN git clone https://github.com/geodynamics/Rayleigh.git /home/rayleigh/Rayleigh && \ 
    cd ~/Rayleigh && \
    git checkout devel && \
    ./configure --with-blas=/usr --with-fftw=/usr --with-lapack=/usr && \
    make && \
    make install && \
    make clean

WORKDIR /home/rayleigh/Rayleigh
