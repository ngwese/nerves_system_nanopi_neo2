[ ] Copy over the fwup, post build, post create image bits from rpi3

For nerves_defconfig....
=================================
BR2_GENERATE_LOCALE="en_US.UTF-8"
BR2_ROOTFS_OVERLAY="${BR2_EXTERNAL_NERVES_PATH}/board/nerves-common/rootfs_overlay ${NERVES_DEFCONFIG_DIR}/rootfs_overlay"
BR2_ROOTFS_POST_BUILD_SCRIPT="${NERVES_DEFCONFIG_DIR}/post-build.sh ${BR2_EXTERNAL_NERVES_PATH}/board/nerves-common/post-build.sh"
BR2_ROOTFS_POST_IMAGE_SCRIPT="${NERVES_DEFCONFIG_DIR}/post-createfs.sh"

...but base it off the setup which is commented out:
#BR2_ROOTFS_POST_IMAGE_SCRIPT="support/scripts/genimage.sh"
#BR2_ROOTFS_POST_SCRIPT_ARGS="-c board/friendlyarm/nanopi-neo2/genimage.cfg"

...the details of which can be found here:
mix nerves.system.shell
cd deps/nerves_system_br/
more buildroot/support/scripts/genimage.sh
more buildroot/board/friendlyarm/nanopi-neo2/genimage.cfg


[ ] Add packages for alsa, jack2, avahi

[ ] Find and remove whatever is bringing in `host-python` and `host-swig` (pydtc ? in u-boot config?)

