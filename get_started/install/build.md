## Build from source

#### Daemon and CLI client:

Clone hyper in GoPath

    > cd ${GOPATH}/src
    > mkdir -p github.com/hyperhq
    > cd github.com/hyperhq
    > git clone https://github.com/hyperhq/hyper.git hyper
    > git clone https://github.com/hyperhq/runv.git runv

And make sure you have `go` (>= 1.4) and `autotools`, develop files of
`libdevmapper`, `libsqlite3`, then

    > cd hyper
    > ./autogen.sh
    > ./configure
    > make

(If you want to build without Xen support, use configure option `--without-xen`.)

Then you can get the binaries `hyperd` daemon and `hyper` CLI tool.

#### Build Xen from source

Download Xen 4.5.0 or later version, and configure with the following option

    > ./configure --with-extra-qemuu-configure-args="--enable-virtfs"

#### Guest Kernel and Initrd

Clone hyperstart

    > git clone https://github.com/hyperhq/hyperstart.git hyperstart

And build with autotools

    > ./autogen.sh
    > ./configure
    > make

Then you can find `hyper-initrd.img` in build directory, together with a pre-build `kernel`. You can also find the `kernel_config` in the repo.

#### Build Your Own Kernel

You can reference the [Hyper kernel configuration](https://github.com/hyperhq/hyperstart/blob/master/build/kernel_config),
and for Qemu/KVM driver, you'd better build new CBFS ROMs with `make cbfs`, which will add the kernel in `build/` and initramfs into a CBFS ROM.

You can find related configuration items in [the config file](../reference/configuration.html).
