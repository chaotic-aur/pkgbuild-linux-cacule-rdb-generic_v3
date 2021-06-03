# Contributor: Piotr Gorski <lucjan.lucjanov@gmail.com>
# Contributor: Jan Alexander Steffens (heftig) <jan.steffens@gmail.com>
# Contributor: Tobias Powalowski <tpowa@archlinux.org>
# Contributor: Thomas Baechler <thomas@archlinux.org>
# Maintainer: ptr1337 <admin@ptr1337.dev>

### BUILD OPTIONS
# Set these variables to ANYTHING that is not null to enable them

# NUMA is optimized for multi-socket motherboards.
# A single multi-core CPU actually runs slower with NUMA enabled.
# See, https://bugs.archlinux.org/task/31187
_NUMAdisable=y
# Enable fsync
_fsync=y
#enable futex2
_futex2=y
#enable winesync
_winesync=y
### Set performance governor as default
_per_gov=y
### Disable Deadline I/O scheduler
_deadline_disable=y
### Disable Kyber I/O scheduler
_kyber_disable=y
### Running with a 2000 HZ, 1000HZ or 500HZ tick rate
_2k_HZ_ticks=
_1k_HZ_ticks=y
_500_HZ_ticks=
### Enable protect file mappings under memory pressure
_mm_protect=y
### Enable multigenerational LRU
_lru_enable=y
# Compile ONLY used modules to VASTLYreduce the number of modules built
# and the build time.
#
# To keep track of which modules are needed for your specific system/hardware,
# give module_db script a try: https://aur.archlinux.org/packages/modprobed-db
# This PKGBUILD read the database kept if it exists
#
# More at this wiki page ---> https://wiki.archlinux.org/index.php/Modprobed-db
_localmodcfg=

### Do not edit below this line unless you know what you're doing

pkgbase=linux-cacule-rdb-generic_v3
# pkgname=('linux-cacule' linux-cacule-headers)
_major=5.12.9
#_minor=1
#_minorc=$((_minor+1))
#_rcver=rc8
pkgver=${_major}
#_stable=${_major}.${_minor}
#_stablerc=${_major}-${_rcver}
_srcname=linux-${_major}
pkgrel=1
pkgdesc='Linux-CacULE Kernel by Hamad Marri and with some other patchsets'
arch=('x86_64')
url="https://github.com/hamadmarri/cacule-cpu-scheduler"
license=('GPL2')
options=('!strip')
makedepends=('kmod' 'bc' 'libelf' 'python-sphinx' 'python-sphinx_rtd_theme'
             'graphviz' 'imagemagick' 'pahole' 'cpio' 'perl' 'tar' 'xz')
_patchsource="https://raw.githubusercontent.com/ptr1337/linux-cacule-aur/master/patches/5.12"
#"_patchsource="https://raw.githubusercontent.com/ptr1337/linux-cacule-aur/master/patches/cacule-patches"
source=("https://mirrors.edge.kernel.org/pub/linux/kernel/v5.x/$_srcname.tar.xz"
        "config"
        "${_patchsource}/arch-patches-v6/0001-ZEN-Add-sysctl-and-CONFIG-to-disallow-unprivileged-C.patch"
        "${_patchsource}/cacule-patches/cacule-5.12.patch"
        "${_patchsource}/cacule-patches/rdb.patch"
        "${_patchsource}/cpu-patches-v2/0001-cpu-patches.patch"
        "${_patchsource}/futex-patches-v2/0001-futex-resync-from-gitlab.collabora.com.patch"
        "${_patchsource}/futex2-stable-patches-v5/0001-futex2-resync-from-gitlab.collabora.com.patch"
        "${_patchsource}/wine-esync-patches/0001-v5.12-winesync.patch"
        "${_patchsource}/zen-patches-v2/0001-zen-patches.patch"
        "${_patchsource}/lqx-patches-v3/0001-zen-Allow-MSR-writes-by-default.patch"
        "${_patchsource}/bfq-patches-v12/0001-bfq-patches.patch"
        "${_patchsource}/block-patches-v4/0001-block-patches.patch"
        "${_patchsource}/ll-patches/0005-Disable-CPU_FREQ_GOV_SCHEDUTIL.patch"
        "${_patchsource}/fixes-miscellaneous/0001-fixes-miscellaneous.patch"
        "${_patchsource}/bbr2-patches-v2/0001-bbr2-5.12-introduce-BBRv2.patch"
        "${_patchsource}/btrfs-patches-v9/0001-btrfs-patches.patch"
        "${_patchsource}/android-patches/0001-android-export-symbold-and-enable-building-ashmem-an.patch"
        "${_patchsource}/pf-patches-v2/0001-pf-patches.patch"
        "${_patchsource}/lru-patches-v4/0001-lru-patches.patch"
        "${_patchsource}/ntfs3-patches-v2/0001-ntfs3-patches.patch"
        "${_patchsource}/zstd-dev-patches-v3/0001-zstd-dev-patches.patch"
        "${_patchsource}/clearlinux-patches-v3/0001-clearlinux-patches.patch"
        "${_patchsource}/ksm-patches/0001-ksm-patches.patch"
        "${_patchsource}/initramfs-patches/0001-initramfs-patches.patch" )

sha512sums=('f97b025db8a469ff982d445356dac78765a4a5625fa442e0242598c807df49753eedd99517e3ca6d1713714f12b802d58e752b3b71259eb2540b86422a72e937'
            'a49537a61bd7ca80f456e0618f4c64630651efada8bcc68ee260461370e9638410b0a883e036a3e7777c841d585f91eea9a051e4c93d38b639ebebdff643cf4e'
            '1908055c446f04ef0a0a5a19579836d2f5dc60d7989677f85f084a7186a6327b240291feed8d25e320e72efa114b243a325362e2dbfbf7f4f3fb89bbdd3819be'
            '367f5ec3ec03d41c4ae5c60ca70d2aa2a1fb200245f1fd7a3409c123c0b93e36338c944864cf473b3fa236cc97d715e86de4184362837af54ff8a6ade33e7d99'
            '91a2a9173870637786cb1379ede303c5c923695069e5d3bc74d5221d45d529f9230c29e910e80eb9d8118633296f9e746fedf16ec5a3f22bd90b6d6010dd13d7'
            '60bda2070739a52af4f81816ebda8f3520a8d75ea5e00f65a903a3416ae31edba56fe151f6a9e02dc90ec3be7854e9a62e10e72120d7148fd3838806d8b9e986'
            '4b7766c590a692a008a0daca73806a1671a81b6e2ed756aae96de4c4455505b04765568ae5e04645f89bf75bd5611e3b1bf5ededff47bb0708dbca91769b5ab7'
            'a5585535a5db9b94508fe13ff6d1f796c51881ea4e7fe37bdd6ab7b62942f9775004a3ec5e4f88ef9587b87c14041210eafa6ffa6584f364eb0c4378444f830b'
            '905f97cdff3e096552159a229d069d1b1418f4142b2927134110f504bfe0883309b3f29c2aeeb94c528b63e0eec7d0d69b44c3d498211c610811969cc4d07a56'
            '1c6cdf40009ce6c62b0a35cc7c2a74818b7169d32e18fb3c2bb8761762c15c579f64cb36f9076c4f78d3f88f077f6246ee75ba93f370cc40dae450d6d71117bb'
            'd9e072c64cd413e1ba58a9924872b7a5bfed33c7b78d062a6be42f1becce450647c90066d95b8a7f1facc1cdc538d532b3d5915cd6c4f659b76ad950993af8f3'
            'a6c95262adbf0ddffd896511a9cc2c347dea0cf8cc0ec4218869ccd287a5f44c7a953b718b74db70592bc3b774bbdc1d4a39c3d6ae90acf3ff8c8cc24299773e'
            '5a865976aa40e8e3ebbf270bb3d1dbde5a737fa55c051a733a1102cb6e202a61d22020e78145d11f324d272ad6d49ee7055b4ddd20ad5ef3bc3a3f99e221b26c'
            '47f265716ebd268e4296aaba1efe5098df00736b69ec7d0413cace6dbb5cb162c1c952f7527a2a41b246ed76e6e112514c5349e8dc52f4609def30257e18d7aa'
            '5081a6a3a3db160ef0a23acd0c0db403cc4b3eb2dfd280b1b7ba2ae907d362e4d6a653d546523c870af07009c62f58eec26e7b8174a3f4fcbaa32808d965ad73'
            '28446f518e88ab934330111a01019cb164bfdd21094c69e96cc16c7931440d069ef997ae141154c97c80fcb727e8c4d940b8bf63554e3f4179652523e285c5b4'
            '9d0b86f0f36af9f00a463b9b4423241228e5d28164dadff75f2a6ab15688c6e1867bdd98217781104f0e933b1254cc409f9c38accde1000674f4a87ef02901cd'
            '1b3b48246fe70e8ca7390cacacf560696c1d98604a7716ac32df8f3d7fc7cc2ab733ab24e372fffa63016344f2e4ed078f7d597c3c1261f0ca3ff1c87a13dcb9'
            '6b574c79e6ebc866cb5ed01b2edb1187672f8cbe4ac507c811adfca859baaa89460bf66184a99c3b02a583f4b51fd15c1ef0431601dd4838a08bc031de902067'
            'd428d3f54634b91e41cac279f7c7b708a174d9cac085b7497802c5a50f77bbfcfdd8799c1db3351ba18e8316685b729d292bb45de0da443762dbd1b87cbc7dad'
            'ed0fbbafa32b05130ad61017f3d6e13fdcae7e1c59290fa2819b209de5c2368b3f9cf157ecf115fc20825599448fed7eef3b5fd3647e5889e2a66b82971b6f6f'
            'db592b1e12651ae494f1414079a3f268175776a067c69148387e05f86b6656308c810eb20cc5c1fe7804030abcb8c37ba5ab7480660c224c591f2718569c2cc9'
            'a24d649fc7f84975b8f970e921f5bf4e4046e4741e35a77b4b173275587657f6d9d30e5492052fa8df73c3177b6f54cdc4f3143c67b26f516f8ce9fc43b4bf62'
            'c8ec07f45c466b5eccef668c229b33e135e8ee8320c7f2304953860f3eb2a87f47ce4c8f122d0f4ddeca955433085194c4fc8a2e7e9034e51f35ed12a474031e'
            '21a613ef65497ecf66daf31b43e02022c71195b48082ae7628a9d2ba8619819f69a6702c4c87e39e8718074c7ebfd674694a29a962049a16d47f1e5f748c78c3')

export KBUILD_BUILD_HOST=archlinux
export KBUILD_BUILD_USER=$pkgbase
export KBUILD_BUILD_TIMESTAMP="$(date -Ru${SOURCE_DATE_EPOCH:+d @$SOURCE_DATE_EPOCH})"

prepare() {
    cd $_srcname

    ### Setting version
        echo "Setting version..."
        scripts/setlocalversion --save-scmversion
        echo "-$pkgrel" > localversion.10-pkgrel
        echo "${pkgbase#linux}" > localversion.20-pkgname

  ### Patching sources
        local src
        for src in "${source[@]}"; do
            src="${src%%::*}"
            src="${src##*/}"
            [[ $src = *.patch ]] || continue
        echo "Applying patch $src..."
        patch -Np1 < "../$src"
        done

  ### Setting config
        echo "Setting config..."
      cp "${srcdir}"/config .config
      make olddefconfig


  ### Prepared version
        make -s kernelrelease > version
        echo "Prepared $pkgbase version $(<version)"

    scripts/config --disable CONFIG_GENERIC_CPU
    scripts/config --enable CONFIG_GENERIC_CPU3

    ### Optionally set tickrate to 2000HZ
      if [ -n "$_2k_HZ_ticks" ]; then
        echo "Setting tick rate to 2k..."
        scripts/config --disable CONFIG_HZ_300
        scripts/config --enable CONFIG_HZ_2000
        scripts/config --set-val CONFIG_HZ 2000
      fi

  ### Optionally set tickrate to 1000
	   if [ -n "$_1k_HZ_ticks" ]; then
		    echo "Setting tick rate to 1k..."
        scripts/config --disable CONFIG_HZ_300
        scripts/config --enable CONFIG_HZ_1000
        scripts/config --set-val CONFIG_HZ 1000
	   fi

  ### Optionally set tickrate to 500HZ
    if [ -n "$_500_HZ_ticks" ]; then
      echo "Setting tick rate to 500HZ..."
      scripts/config --disable CONFIG_HZ_300
      scripts/config --enable CONFIG_HZ_500
      scripts/config --set-val CONFIG_HZ 500
    fi

  ### Optionally disable NUMA for 64-bit kernels only
    # (x86 kernels do not support NUMA)
    if [ -n "$_NUMAdisable" ]; then
      echo "Disabling NUMA from kernel config..."
      scripts/config --disable CONFIG_NUMA
    fi

    if [ -n "$_fsync" ]; then
      echo "Enable Fsync support"
      scripts/config --enable CONFIG_FUTEX
      scripts/config --enable CONFIG_FUTEX_PI
    fi

    if [ -n "$_futex2" ]; then
      echo "Enable Futex2 support"
      scripts/config --enable CONFIG_FUTEX2
    fi

    if [ -n "$_winesync" ]; then
          echo "Enable winesync support"
        scripts/config --module CONFIG_WINESYNC
    fi

  ### Set performance governor
    if [ -n "$_per_gov" ]; then
      echo "Setting performance governor..."
  		scripts/config --disable CONFIG_CPU_FREQ_DEFAULT_GOV_SCHEDUTIL
  		scripts/config --enable CONFIG_CPU_FREQ_DEFAULT_GOV_PERFORMANCE
  		echo "Disabling uneeded governors..."
  		scripts/config --enable CONFIG_CPU_FREQ_GOV_ONDEMAND
  		scripts/config --disable CONFIG_CPU_FREQ_GOV_CONSERVATIVE
  		scripts/config --disable CONFIG_CPU_FREQ_GOV_USERSPACE
  		scripts/config --disable CONFIG_CPU_FREQ_GOV_SCHEDUTIL
    fi

  ### Disable Deadline I/O scheduler
  	if [ -n "$_deadline_disable" ]; then
  		echo "Disabling Deadline I/O scheduler..."
  		scripts/config --disable CONFIG_MQ_IOSCHED_DEADLINE
  	fi

  ### Disable Kyber I/O scheduler
  	if [ -n "$_kyber_disable" ]; then
  		echo "Disabling Kyber I/O scheduler..."
  		scripts/config --disable CONFIG_MQ_IOSCHED_KYBER
  	fi

    ### Enable protect file mappings under memory pressure
    if [ -n "$_mm_protect" ]; then
      echo "Enabling protect file mappings under memory pressure..."
      scripts/config --enable CONFIG_UNEVICTABLE_FILE
      scripts/config --set-val CONFIG_UNEVICTABLE_FILE_KBYTES_LOW 262144
      scripts/config --set-val CONFIG_UNEVICTABLE_FILE_KBYTES_MIN 131072
    fi

            ### Enable multigenerational LRU
    if [ -n "$_lru_enable" ]; then
      echo "Enabling multigenerational LRU..."
      scripts/config --enable CONFIG_HAVE_ARCH_PARENT_PMD_YOUNG
      scripts/config --enable CONFIG_LRU_GEN
      scripts/config --set-val CONFIG_NR_LRU_GENS 7
      scripts/config --set-val CONFIG_TIERS_PER_GEN 4
      scripts/config --enable CONFIG_LRU_GEN_ENABLED
      scripts/config --disable CONFIG_LRU_GEN_STATS
    fi

      echo "Enabling standard ZSTD compression ratio..."
    	scripts/config --set-val CONFIG_KERNEL_ZSTD_LEVEL 19
    	scripts/config --disable CONFIG_KERNEL_ZSTD_LEVEL_ULTRA
  ### Enabling ZSTD COMPRESSION ##
       echo "Set module compression to ZSTD"
    scripts/config --enable CONFIG_MODULE_COMPRESS
    scripts/config --disable CONFIG_MODULE_COMPRESS_XZ
        scripts/config --enable CONFIG_MODULE_COMPRESS_ZSTD
  #      scripts/config --set-val CONFIG_MODULE_COMPRESS_ZSTD_LEVEL 19
  #      scripts/config --disable CONFIG_KERNEL_ZSTD_LEVEL_ULTRA

      echo "Enable CacULE CPU scheduler..."
      scripts/config --enable CONFIG_CACULE_SCHED
      scripts/config --enable CONFIG_CACULE_RDB
      scripts/config --set-val CONFIG_RDB_INTERVAL 19
      scripts/config --disable CONFIG_RDB_TASKS_GROUP
      scripts/config --disable CONFIG_EXPERT
      scripts/config --disable CONFIG_FAIR_GROUP_SCHED
      scripts/config --disable CONFIG_SCHED_AUTOGROUP
      scripts/config --disable CONFIG_SCHED_DEBUG
      scripts/config --disable CONFIG_SCHED_INFO
      scripts/config --disable CONFIG_SCHEDSTATS
      scripts/config --disable CONFIG_DEBUG_KERNEL
      echo "Enabling Full Tickless"
      scripts/config --disable CONFIG_HZ_PERIODIC
      scripts/config --disable CONFIG_NO_HZ_IDLE
      scripts/config --enable CONFIG_NO_HZ_FULL
      scripts/config --enable CONFIG_NO_HZ
      scripts/config --enable CONFIG_NO_HZ_COMMON
      scripts/config --enable CONFIG_CONTEXT_TRACKING
      scripts/config --disable CONFIG_CONTEXT_FORCE
      echo "Enabling KBUILD_CFLAGS -O3..."
      scripts/config --disable CONFIG_CC_OPTIMIZE_FOR_PERFORMANCE
      scripts/config --enable CONFIG_CC_OPTIMIZE_FOR_PERFORMANCE_O3
      echo "Enable PREEMPT"
      scripts/config --disable CONFIG_PREEMPT_NONE
      scripts/config --disable CONFIG_PREEMPT_VOLUNTARY
      scripts/config --enable CONFIG_PREEMPT
      scripts/config --enable CONFIG_PREEMPT_COUNT
      scripts/config --enable CONFIG_PREEMPTION
      scripts/config --enable CONFIG_PREEMPT_DYNAMIC
      echo "Enable NTFS3"
      scripts/config --module CONFIG_NTFS_FS
      scripts/config --enable CONFIG_NTFS_RW
      scripts/config --enable CONFIG_NTFS_DEBUG
      scripts/config --module CONFIG_NTFS3_FS
      scripts/config --enable CONFIG_NTFS3_64BIT_CLUSTER
      scripts/config --enable CONFIG_NTFS3_LZX_XPRESS
      scripts/config --enable CONFIG_NTFS3_FS_POSIX_ACL
      echo "Enable Anbox"
      scripts/config --module  CONFIG_ASHMEM
      scripts/config --enable  CONFIG_ANDROID_BINDER_IPC_SELFTEST
      scripts/config --enable  CONFIG_ANDROID
      scripts/config --enable  CONFIG_ANDROID_BINDER_IPC
      scripts/config --enable  CONFIG_ANDROID_BINDERFS
      scripts/config --set-str CONFIG_ANDROID_BINDER_DEVICES binder,hwbinder,vndbinder
      echo "Disabling TCP_CONG_CUBIC..."
      scripts/config --module CONFIG_TCP_CONG_CUBIC
      scripts/config --disable CONFIG_DEFAULT_CUBIC
      echo "Enabling TCP_CONG_BBR2..."
      scripts/config --enable CONFIG_TCP_CONG_BBR2
      scripts/config --enable CONFIG_DEFAULT_BBR2
      scripts/config --set-str CONFIG_DEFAULT_TCP_CONG bbr2
      echo "Enable CONFIG_VHBA"
      scripts/config --module CONFIG_VHBA
      scripts/config --disable CONFIG_GCC_PLUGINS

      ### Optionally load needed modules for the make localmodconfig
       # See https://aur.archlinux.org/packages/modprobed-db
           if [ -n "$_localmodcfg" ]; then
               if [ -f $HOME/.config/modprobed.db ]; then
               echo "Running Steven Rostedt's make localmodconfig now"
               make LSMOD=$HOME/.config/modprobed.db localmodconfig
           else
               echo "No modprobed.db data found"
               exit
               fi
           fi

  ### Save configuration for later reuse
     echo "Save config for reuse"
     cat .config > "${startdir}/config.last"

}

build() {
  cd $_srcname

  make all
}

_package() {
    pkgdesc="The $pkgdesc kernel and modules"
    depends=('coreutils' 'kmod' 'initramfs')
    optdepends=('crda: to set the correct wireless channels of your country'
                'linux-firmware: firmware images needed for some devices'
                'modprobed-db: Keeps track of EVERY kernel module that has ever been probed - useful for those of us who make localmodconfig')
    provides=(VIRTUALBOX-GUEST-MODULES WIREGUARD-MODULE linux-cacule-rdb-generic_v3)


  cd $_srcname
  local kernver="$(<version)"
  local modulesdir="$pkgdir/usr/lib/modules/$kernver"

  echo "Installing boot image..."
  # systemd expects to find the kernel here to allow hibernation
  # https://github.com/systemd/systemd/commit/edda44605f06a41fb86b7ab8128dcf99161d2344
  install -Dm644 "$(make -s image_name)" "$modulesdir/vmlinuz"

  # Used by mkinitcpio to name the kernel
  echo "$pkgbase" | install -Dm644 /dev/stdin "$modulesdir/pkgbase"

  echo "Installing modules..."
  make INSTALL_MOD_PATH="$pkgdir/usr" INSTALL_MOD_STRIP=1 modules_install

  # remove build and source links
  rm "$modulesdir"/{source,build}
}

_package-headers() {
    pkgdesc="Headers and scripts for building modules for the $pkgdesc kernel"
    depends=('linux-cacule-rdb' 'pahole')

  cd $_srcname
  local builddir="$pkgdir/usr/lib/modules/$(<version)/build"

  echo "Installing build files..."
  install -Dt "$builddir" -m644 .config Makefile Module.symvers System.map \
    localversion.* version vmlinux
  install -Dt "$builddir/kernel" -m644 kernel/Makefile
  install -Dt "$builddir/arch/x86" -m644 arch/x86/Makefile
  cp -t "$builddir" -a scripts

  # add objtool for external module building and enabled VALIDATION_STACK option
  install -Dt "$builddir/tools/objtool" tools/objtool/objtool

  # add xfs and shmem for aufs building
  mkdir -p "$builddir"/{fs/xfs,mm}

  echo "Installing headers..."
  cp -t "$builddir" -a include
  cp -t "$builddir/arch/x86" -a arch/x86/include
  install -Dt "$builddir/arch/x86/kernel" -m644 arch/x86/kernel/asm-offsets.s

  install -Dt "$builddir/drivers/md" -m644 drivers/md/*.h
  install -Dt "$builddir/net/mac80211" -m644 net/mac80211/*.h

  # http://bugs.archlinux.org/task/13146
  install -Dt "$builddir/drivers/media/i2c" -m644 drivers/media/i2c/msp3400-driver.h

  # http://bugs.archlinux.org/task/20402
  install -Dt "$builddir/drivers/media/usb/dvb-usb" -m644 drivers/media/usb/dvb-usb/*.h
  install -Dt "$builddir/drivers/media/dvb-frontends" -m644 drivers/media/dvb-frontends/*.h
  install -Dt "$builddir/drivers/media/tuners" -m644 drivers/media/tuners/*.h

  echo "Installing KConfig files..."
  find . -name 'Kconfig*' -exec install -Dm644 {} "$builddir/{}" \;

  echo "Removing unneeded architectures..."
  local arch
  for arch in "$builddir"/arch/*/; do
    [[ $arch = */x86/ ]] && continue
    echo "Removing $(basename "$arch")"
    rm -r "$arch"
  done

  echo "Removing documentation..."
  rm -r "$builddir/Documentation"

  echo "Removing broken symlinks..."
  find -L "$builddir" -type l -printf 'Removing %P\n' -delete

  echo "Removing loose objects..."
  find "$builddir" -type f -name '*.o' -printf 'Removing %P\n' -delete

  echo "Stripping build tools..."
  local file
  while read -rd '' file; do
    case "$(file -bi "$file")" in
      application/x-sharedlib\;*)      # Libraries (.so)
        strip -v $STRIP_SHARED "$file" ;;
      application/x-archive\;*)        # Libraries (.a)
        strip -v $STRIP_STATIC "$file" ;;
      application/x-executable\;*)     # Binaries
        strip -v $STRIP_BINARIES "$file" ;;
      application/x-pie-executable\;*) # Relocatable binaries
        strip -v $STRIP_SHARED "$file" ;;
    esac
  done < <(find "$builddir" -type f -perm -u+x ! -name vmlinux -print0)

  echo "Stripping vmlinux..."
  strip -v $STRIP_STATIC "$builddir/vmlinux"

  echo "Adding symlink..."
  mkdir -p "$pkgdir/usr/src"
  ln -sr "$builddir" "$pkgdir/usr/src/$pkgbase"
}

pkgname=("$pkgbase" "$pkgbase-headers")
for _p in "${pkgname[@]}"; do
  eval "package_$_p() {
    $(declare -f "_package${_p#$pkgbase}")
    _package${_p#$pkgbase}
  }"
done