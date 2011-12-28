# bcm4329
DHDCFLAGS = -DLINUX -DBCMDRIVER -DBCMDONGLEHOST -DDHDTHREAD -DBCMWPA2 			\
	-DUNRELEASEDCHIP -Dlinux -DUNRELEASEDCHIP -DDHD_GPL -DDHD_SCHED -DDHD_DEBUG \
	-DSDTEST -DBDC -DTOE -DDHD_BCMEVENTS -DSHOW_EVENTS -DBCMSDIO -DPNO_SUPPORT	\
	-DSDIO_ISR_THREAD -DBCMLXSDMMC -DEMBEDDED_PLATFORM -DARP_OFFLOAD_SUPPORT 	\
	-DPKT_FILTER_SUPPORT -DBCMPLATFORM_BUS -DDHD_DEBUG_TRAP -DBCMWAPI_WPI 		\
	-DSOFTAP -DGET_CUSTOM_MAC_ENABLE -DGET_CUSTOM_MAC_ENABLE -DCSCAN 			\
	-DMMC_SDIO_ABORT -DKEEP_ALIVE -DPNO_SUPPORT -DHW_OOB -DDHD_SDALIGN=64		\
	-DMAX_HDR_READ=64 -DDHD_FIRSTREAD=64 -DCHROMIUMOS_COMPAT_WIRELESS	 		\
	-Wall -Wstrict-prototypes -Werror 											\
	-Idrivers/net/wireless/bcm4329 -Idrivers/net/wireless/bcm4329/include

DHDOFILES = dhd_linux.o linux_osl.o bcmutils.o dhd_common.o dhd_custom_gpio.o	\
	wl_iw.o siutils.o sbutils.o aiutils.o hndpmu.o bcmwifi.o dhd_sdio.o   		\
	dhd_linux_sched.o dhd_cdc.o bcmsdh_sdmmc.o bcmsdh.o bcmsdh_linux.o    		\
	bcmsdh_sdmmc_linux.o

obj-$(CONFIG_BCM4329) += dhd.o
dhd-objs += $(DHDOFILES)
EXTRA_CFLAGS = $(DHDCFLAGS)
EXTRA_LDFLAGS += --strip-debug
