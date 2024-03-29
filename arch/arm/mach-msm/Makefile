obj-y += io.o dma.o memory.o
obj-y += clock.o clock-voter.o clock-dummy.o
obj-y += modem_notifier.o
obj-$(CONFIG_CPU_FREQ_MSM) += cpufreq.o
obj-$(CONFIG_DEBUG_FS) += nohlt.o clock-debug.o
obj-$(CONFIG_KEXEC) += msm_kexec.o

obj-$(CONFIG_MSM_PROC_COMM) += proc_comm.o
ifndef CONFIG_ARCH_MSM8X60
	obj-$(CONFIG_MSM_PROC_COMM) += clock-pcom.o internal_power_rail.o
	obj-$(CONFIG_MSM_PROC_COMM) += vreg.o mpp.o
	ifdef CONFIG_MSM_PROC_COMM
		obj-$(CONFIG_DEBUG_FS) += pmic_debugfs.o
	endif
endif

obj-$(CONFIG_ARCH_MSM_ARM11) += acpuclock.o timer.o
obj-$(CONFIG_ARCH_MSM_SCORPION) += timer.o
obj-$(CONFIG_ARCH_MSM_SCORPION) += pmu.o
obj-$(CONFIG_ARCH_MSM_SCORPIONMP) += timer.o
obj-$(CONFIG_ARCH_MSM_CORTEX_A5) += timer.o
ifndef CONFIG_ARCH_MSM8960
obj-$(CONFIG_ARCH_MSM_SCORPIONMP) += pmu.o
endif

obj-$(CONFIG_ARCH_MSM_SCORPION) += msm_fault_handlers.o

obj-$(CONFIG_MSM_VIC) += irq-vic.o

ifdef CONFIG_ARCH_QSD8X50
	obj-$(CONFIG_MSM_SOC_REV_NONE) += acpuclock-8x50.o
	obj-$(CONFIG_MSM_SOC_REV_A) += acpuclock-8x50a.o
endif

obj-$(CONFIG_SMP) += headsmp.o platsmp.o

obj-$(CONFIG_MSM_CPU_AVS) += avs.o
obj-$(CONFIG_MSM_AVS_HW) += avs_hw.o
obj-$(CONFIG_CPU_V6) += idle-v6.o
obj-$(CONFIG_CPU_V7) += idle-v7.o
obj-$(CONFIG_MSM_JTAG_V7) += jtag-v7.o

msm-etm-objs := cp14.o etm.o
obj-$(CONFIG_MSM_ETM) += msm-etm.o

quiet_cmd_mkrpcsym = MKCAP   $@
      cmd_mkrpcsym = $(PERL) $(srctree)/$(src)/mkrpcsym.pl $< $@

target += smd_rpc_sym.c
$(obj)/smd_rpc_sym.c: $(src)/smd_rpc_sym $(src)/mkrpcsym.pl
	$(call if_changed,mkrpcsym)

obj-$(CONFIG_MSM_SCM) += scm.o scm-boot.o
obj-$(CONFIG_MSM_SECURE_IO) += scm-io.o
obj-$(CONFIG_MSM_PIL) += peripheral-loader.o
obj-$(CONFIG_MSM_PIL) += peripheral-reset.o
obj-$(CONFIG_ARCH_QSD8X50) += sirc.o
obj-$(CONFIG_MSM_FIQ_SUPPORT) += fiq_glue.o
obj-$(CONFIG_MACH_TROUT) += board-trout-rfkill.o
obj-$(CONFIG_MSM_SDIO_AL) += sdio_al.o
obj-$(CONFIG_MSM_SDIO_AL) += sdio_al_test.o
obj-$(CONFIG_MSM_SDIO_AL) += sdio_al_dloader.o
obj-$(CONFIG_MSM_SDIO_DMUX) += sdio_dmux.o
obj-$(CONFIG_MSM_SMD_LOGGING) += smem_log.o
obj-$(CONFIG_MSM_SMD) += smd.o smd_debug.o remote_spinlock.o
        obj-y += socinfo.o
ifndef CONFIG_ARCH_MSM8960
ifndef CONFIG_ARCH_MSM8X60
	obj-$(CONFIG_MSM_SMD) += pmic.o
	obj-$(CONFIG_MSM_SMD) += nand_partitions.o
	obj-$(CONFIG_MSM_ONCRPCROUTER) += rpc_hsusb.o rpc_pmapp.o rpc_fsusb.o
endif
endif
obj-$(CONFIG_MSM_SDIO_TTY) += sdio_tty.o sdio_tty_ciq.o
obj-$(CONFIG_MSM_SMD_TTY) += smd_tty.o
obj-$(CONFIG_MSM_SMD_QMI) += smd_qmi.o
obj-$(CONFIG_MSM_SMD_PKT) += smd_pkt.o
obj-$(CONFIG_MSM_SDIO_CMUX) += sdio_cmux.o
obj-$(CONFIG_MSM_DSPS) += msm_dsps.o
obj-$(CONFIG_MSM_SDIO_CTL) += sdio_ctl.o
obj-$(CONFIG_MSM_SMD_NMEA) += smd_nmea.o
obj-$(CONFIG_MSM_RESET_MODEM) += reset_modem.o
obj-$(CONFIG_MSM_IPC_ROUTER_SMD_XPRT) += ipc_router_smd_xprt.o
obj-$(CONFIG_MSM_ONCRPCROUTER) += smd_rpcrouter.o
obj-$(CONFIG_MSM_ONCRPCROUTER) += smd_rpcrouter_device.o
obj-$(CONFIG_MSM_IPC_ROUTER) += ipc_router.o
obj-$(CONFIG_MSM_IPC_ROUTER)+= ipc_socket.o
obj-$(CONFIG_DEBUG_FS) += smd_rpc_sym.o
obj-$(CONFIG_MSM_ONCRPCROUTER) += smd_rpcrouter_servers.o
obj-$(CONFIG_MSM_ONCRPCROUTER) += smd_rpcrouter_clients.o
obj-$(CONFIG_MSM_ONCRPCROUTER) += smd_rpcrouter_xdr.o
obj-$(CONFIG_MSM_ONCRPCROUTER) += rpcrouter_smd_xprt.o
obj-$(CONFIG_MSM_RPC_SDIO_XPRT) += rpcrouter_sdio_xprt.o
obj-$(CONFIG_MSM_RPC_PING) += ping_mdm_rpc_client.o
obj-$(CONFIG_MSM_RPC_PROC_COMM_TEST) += proc_comm_test.o
obj-$(CONFIG_MSM_RPC_PING) += ping_mdm_rpc_client.o ping_apps_server.o
obj-$(CONFIG_MSM_RPC_OEM_RAPI) += oem_rapi_client.o
obj-$(CONFIG_MSM_RPC_WATCHDOG) += rpc_dog_keepalive.o
obj-$(CONFIG_MSM_RPCSERVER_WATCHDOG) += rpc_server_dog_keepalive.o
obj-$(CONFIG_MSM_RPCSERVER_TIME_REMOTE) += rpc_server_time_remote.o
obj-$(CONFIG_MSM_DALRPC) += dal.o
obj-$(CONFIG_MSM_DALRPC_TEST) += dal_remotetest.o
obj-$(CONFIG_ARCH_MSM7X30) += dal_axi.o
obj-$(CONFIG_MSM_ADSP) += qdsp5/
obj-$(CONFIG_MSM7KV2_AUDIO) += qdsp5v2/
obj-$(CONFIG_MSM_RPCSERVER_HANDSET) += rpc_server_handset.o
obj-$(CONFIG_MSM_QDSP6) += qdsp6/
obj-$(CONFIG_MSM8X60_AUDIO) += qdsp6v2/
obj-$(CONFIG_MSM_HW3D) += hw3d.o
ifdef CONFIG_PM
	obj-$(CONFIG_ARCH_MSM8X60) += pm-8x60.o
	obj-$(CONFIG_ARCH_QSD8X50) += pm2.o
	obj-$(CONFIG_ARCH_MSM7X30) += pm2.o
	obj-$(CONFIG_ARCH_MSM7X27) += pm2.o
	obj-$(CONFIG_ARCH_MSM7X25) += pm.o
	obj-$(CONFIG_ARCH_MSM7X01A) += pm.o
else
	obj-y += no-pm.o
endif
obj-$(CONFIG_MSM_DMA_TEST) += dma_test.o
obj-$(CONFIG_SURF_FFA_GPIO_KEYPAD) += keypad-surf-ffa.o

obj-$(CONFIG_ARCH_MSM7X01A) += board-halibut.o devices-msm7x01a.o
obj-$(CONFIG_MACH_TROUT) += board-trout.o board-trout-gpio.o
obj-$(CONFIG_MACH_TROUT) += board-trout-keypad.o board-trout-panel.o
obj-$(CONFIG_MACH_TROUT) += htc_akm_cal.o htc_wifi_nvs.o htc_acoustic.o
obj-$(CONFIG_MACH_TROUT) += board-trout-mmc.o board-trout-wifi.o
obj-$(CONFIG_ARCH_QSD8X50) += devices-qsd8x50.o
obj-$(CONFIG_MACH_QSD8X50_SURF) += board-qsd8x50.o
obj-$(CONFIG_MACH_QSD8X50_FFA) += board-qsd8x50.o
#obj-$(CONFIG_MACH_QSD8X50_COMET) += board-comet.o
obj-$(CONFIG_MACH_QSD8X50A_SURF) += board-qsd8x50.o
obj-$(CONFIG_MACH_QSD8X50A_FFA) += board-qsd8x50.o
obj-$(CONFIG_MACH_QSD8X50A_ST1_5) += board-qsd8x50a-st1x.o
obj-$(CONFIG_ARCH_MSM8X60) += devices-msm8x60.o clock-local.o clock-8x60.o acpuclock-8x60.o
obj-$(CONFIG_ARCH_MSM8X60) += clock-rpm.o spm.o restart.o
obj-$(CONFIG_ARCH_MSM8X60) += saw-regulator.o
obj-$(CONFIG_ARCH_MSM8X60) += rpm-regulator.o
obj-$(CONFIG_ARCH_MSM8X60) += footswitch-8x60.o

ifdef CONFIG_MSM_SUBSYSTEM_RESTART
	obj-y += subsystem_notif.o
	obj-y += subsystem_restart.o
	obj-y += ramdump.o
	obj-$(CONFIG_ARCH_MSM8X60) += subsystem-fatal-8x60.o
endif

ifdef CONFIG_ARCH_MSM8X60
	obj-$(CONFIG_CPU_IDLE) += cpuidle.o
	obj-$(CONFIG_MSM_WATCHDOG) += msm_watchdog.o
endif

obj-$(CONFIG_MACH_MSM8X60_RUMI3) += board-msm8x60.o
obj-$(CONFIG_MACH_MSM8X60_SIM) += board-msm8x60.o
obj-$(CONFIG_MACH_MSM8X60_SURF) += board-msm8x60.o
obj-$(CONFIG_MACH_MSM8X60_FFA) += board-msm8x60.o
obj-$(CONFIG_MACH_MSM8X60_FLUID) += board-msm8x60.o
obj-$(CONFIG_MACH_MSM8X60_CHARM_SURF) += board-msm8x60.o mdm.o
obj-$(CONFIG_MACH_MSM8X60_CHARM_FFA) += board-msm8x60.o mdm.o
obj-$(CONFIG_MACH_MSM8X60_QRDC) += board-qrdc.o
obj-$(CONFIG_MACH_MSM8X60_QT) += board-qt8660.o
obj-$(CONFIG_TROUT_H2W) += board-trout-h2w.o
obj-$(CONFIG_TROUT_BATTCHG) += htc_battery.o
obj-$(CONFIG_TROUT_PWRSINK) += htc_pwrsink.o
obj-$(CONFIG_MACH_MSM7X27_SURF) += board-msm7x27.o devices-msm7x27.o
ifeq ($(CONFIG_BOARD_PW28),y)
obj-$(CONFIG_MACH_MSM7X27_FFA) += board-pw28.o devices-msm7x27.o
else
obj-$(CONFIG_MACH_MSM7X27_FFA) += board-msm7x27.o devices-msm7x27.o
endif
obj-$(CONFIG_MACH_MSM7X27A_RUMI3) += board-msm7x27a.o devices-msm7x27a.o
obj-$(CONFIG_MACH_MSM7X27A_SURF) += board-msm7x27a.o devices-msm7x27a.o
obj-$(CONFIG_MACH_MSM7X27A_FFA) += board-msm7x27a.o devices-msm7x27a.o
obj-$(CONFIG_ARCH_MSM7X30) += board-msm7x30.o devices-msm7x30.o memory_topology.o
obj-$(CONFIG_ARCH_MSM7X30) += clock-local.o clock-7x30.o acpuclock-7x30.o
obj-$(CONFIG_MACH_MSM7X25_SURF) += board-msm7x27.o devices-msm7x25.o
obj-$(CONFIG_MACH_MSM7X25_FFA) += board-msm7x27.o devices-msm7x25.o
obj-$(CONFIG_ARCH_MSM8960) += board-msm8960.o devices-8960.o footswitch-8x60.o
obj-$(CONFIG_ARCH_MSM8960) += board-msm8960-regulator.o

obj-$(CONFIG_MACH_SAPPHIRE) += board-sapphire.o board-sapphire-gpio.o
obj-$(CONFIG_MACH_SAPPHIRE) += board-sapphire-keypad.o board-sapphire-panel.o
obj-$(CONFIG_MACH_SAPPHIRE) += board-sapphire-mmc.o board-sapphire-wifi.o
obj-$(CONFIG_MACH_SAPPHIRE) += board-sapphire-rfkill.o msm_vibrator.o

obj-$(CONFIG_TROUT_BATTCHG) += htc_battery.o

obj-$(CONFIG_HTC_PWRSINK) += htc_pwrsink.o
obj-$(CONFIG_HTC_HEADSET) += htc_headset.o
obj-$(CONFIG_MSM_RMT_STORAGE_CLIENT) += rmt_storage_client.o
obj-$(CONFIG_MSM_SDIO_SMEM) += sdio_smem.o
obj-$(CONFIG_PMIC8058) += pmic8058-gpio.o pmic8058-mpp.o
obj-$(CONFIG_ARCH_MSM7X30) += spm.o
obj-$(CONFIG_MSM_RPM) += rpm.o rpm_resources.o
obj-$(CONFIG_MSM_MPM) += mpm.o
obj-$(CONFIG_MSM_RPM_STATS_LOG) += rpm_stats.o
obj-$(CONFIG_MSM_RPM_LOG) += rpm_log.o
obj-$(CONFIG_MSM_XO) += msm_xo.o
obj-$(CONFIG_MSM_BUS_SCALING) += msm_bus/

obj-$(CONFIG_MSM_IOMMU)		+= iommu.o iommu_dev.o devices-iommu.o

ifdef CONFIG_VCM
obj-$(CONFIG_ARCH_MSM8X60) += board-msm8x60-vcm.o
endif

obj-$(CONFIG_ARCH_MSM7X27) += gpiomux-7x27.o gpiomux-v1.o gpiomux.o
obj-$(CONFIG_ARCH_MSM7X30) += gpiomux-7x30.o gpiomux-v1.o gpiomux.o
obj-$(CONFIG_ARCH_QSD8X50) += gpiomux-8x50.o gpiomux-v1.o gpiomux.o
obj-$(CONFIG_ARCH_MSM8X60) += gpiomux-8x60.o gpiomux-v2.o gpiomux.o
obj-$(CONFIG_ARCH_MSM8960) += gpiomux-v2.o gpiomux.o
ifdef CONFIG_MSM_V2_TLMM
obj-y	+= gpio-v2.o
else
obj-y	+= gpio.o
endif
obj-$(CONFIG_MSM_SLEEP_STATS) += msm_rq_stats.o idle_stats.o
obj-$(CONFIG_MSM_SHOW_RESUME_IRQ) += msm_show_resume_irq.o
obj-$(CONFIG_BT_MSM_PINTEST)  += btpintest.o
obj-$(CONFIG_ENABLE_ROMLITE)  += romlite_sec.o
romlite_sec-objs := msm_romlite_sec.o msm_romlite_pa.o
