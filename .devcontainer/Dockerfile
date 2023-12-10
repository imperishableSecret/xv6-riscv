FROM "mcr.microsoft.com/devcontainers/base:bullseye"

ENV PATH /home/vscode/riscv_tools/bin:${PATH}

USER vscode
RUN sudo apt update && sudo apt upgrade -y && \
    sudo apt install -y autoconf automake autotools-dev curl python3 python3-pip libmpc-dev libmpfr-dev libgmp-dev gawk build-essential bison flex texinfo gperf libtool patchutils bc zlib1g-dev libexpat-dev ninja-build git cmake libglib2.0-dev qemu qemu-system-riscv64

RUN git clone https://github.com/riscv/riscv-gnu-toolchain ~/riscv
RUN cd ~/riscv/ && ./configure --prefix=/home/vscode/riscv_tools && make linux -j$(nproc)
RUN rm -rf ~/riscv
