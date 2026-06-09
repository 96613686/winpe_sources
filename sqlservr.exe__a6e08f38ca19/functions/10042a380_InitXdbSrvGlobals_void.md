# InitXdbSrvGlobals(void)

- ea: `0x10042a380`
- end: `0x100432253`
- name: `?InitXdbSrvGlobals@@YAXXZ`
- size: `32467`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `48`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x100412470`

## callees

- `0x100401aa0`
- `0x100404310`
- `0x100404340`
- `0x100404900`
- `0x100409c40`
- `0x10041d2a0`
- `0x10041e9a0`
- `0x10041e9b0`
- `0x10041ea10`
- `0x10041eaa0`
- `0x10041eb80`
- `0x10041eba0`
- `0x10041ebb0`
- `0x10041ecd0`
- `0x1004238d0`
- `0x1004238e0`
- `0x1004244f0`
- `0x100424610`
- `0x100429b50`
- `0x100429cd0`
- `0x100429d20`
- `0x100429d70`
- `0x100429dc0`
- `0x10042a380`
- `0x1004355a0`
- `0x1004355f0`
- `0x100435630`
- `0x100435640`
- `0x1004356c0`
- `0x1004356e0`
- `0x1004361a0`
- `0x100436220`
- `0x100436230`
- `0x100436240`
- `0x100436610`
- `0x10044aa20`
- `0x10044b0e0`
- `0x10044b1d0`
- `0x10044ce30`
- `0x10044ce50`
- `0x10044d370`
- `0x10044d4c0`
- `0x10044d880`
- `0x10044dbf0`
- `0x10044dd40`
- `0x10044e0b0`
- `0x10044e200`
- `0x10044e410`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x10042f64e`
- `KERNEL32!GetProcessHeap` at `0x10042f64e`
- `KERNEL32!HeapAlloc` at `0x10042f65e`
- `KERNEL32!HeapAlloc` at `0x10042f65e`
- `sqlmin!?GetDataExfiltrationAllowedFqdnList@DataExFiltrationConfigHelper@@SAJPEAVIMemObj@@AEAV?$CAutoRg@V?$CAutoRg@$$CB_W@@@@AEAH@Z` at `0x10042f8c0`
- `sqlmin!?GetDataExfiltrationAllowedFqdnList@DataExFiltrationConfigHelper@@SAJPEAVIMemObj@@AEAV?$CAutoRg@V?$CAutoRg@$$CB_W@@@@AEAH@Z` at `0x10042f8c0`
- `sqlmin!?ConfigureRgInstance@RESOURCE@@QEAAX_N@Z` at `0x10042d85f`
- `sqlmin!?ConfigureRgInstance@RESOURCE@@QEAAX_N@Z` at `0x10042d85f`
- `sqlmin!?ParseRgInstanceSettingsXml@RESOURCE@@QEAAJXZ` at `0x10042d844`
- `sqlmin!?ParseRgInstanceSettingsXml@RESOURCE@@QEAAJXZ` at `0x10042d844`
- `sqlmin!?ParseRgIsolationSettingsXml@RESOURCE@@QEAAJXZ` at `0x10042d82f`
- `sqlmin!?ParseRgIsolationSettingsXml@RESOURCE@@QEAAJXZ` at `0x10042d82f`
- `sqlmin!?GetCurrentInstance@CFeatureSwitchesMin@@SAPEBV1@XZ` at `0x10042ab0f`
- `sqlmin!?GetCurrentInstance@CFeatureSwitchesMin@@SAPEBV1@XZ` at `0x10042b93c`
- `sqlmin!?GetCurrentInstance@CFeatureSwitchesMin@@SAPEBV1@XZ` at `0x10042f5e3`
- `sqlmin!?GetCurrentInstance@CFeatureSwitchesMin@@SAPEBV1@XZ` at `0x10042ab0f`
- `sqlmin!?GetCurrentInstance@CFeatureSwitchesMin@@SAPEBV1@XZ` at `0x10042b93c`
- `sqlmin!?GetCurrentInstance@CFeatureSwitchesMin@@SAPEBV1@XZ` at `0x10042f5e3`
- `sqlmin!?ExportCurrentInstance@CFeatureSwitchesMin@@SAPEBV1@XZ` at `0x10042e07a`
- `sqlmin!?ExportCurrentInstance@CFeatureSwitchesMin@@SAPEBV1@XZ` at `0x10042fca9`
- `sqlmin!?ExportCurrentInstance@CFeatureSwitchesMin@@SAPEBV1@XZ` at `0x10042e07a`
- `sqlmin!?ExportCurrentInstance@CFeatureSwitchesMin@@SAPEBV1@XZ` at `0x10042fca9`
- `sqlmin!GetXdbServerGlobals` at `0x10042a39c`
- `sqlmin!GetXdbServerGlobals` at `0x10042ae1a`
- `sqlmin!GetXdbServerGlobals` at `0x10042ae55`
- `sqlmin!GetXdbServerGlobals` at `0x10042ae8d`
- `sqlmin!GetXdbServerGlobals` at `0x10042bc68`
- `sqlmin!GetXdbServerGlobals` at `0x10042bca3`
- `sqlmin!GetXdbServerGlobals` at `0x10042bcde`
- `sqlmin!GetXdbServerGlobals` at `0x10042bd19`
- `sqlmin!GetXdbServerGlobals` at `0x10042bd54`
- `sqlmin!GetXdbServerGlobals` at `0x10042bd8f`
- `sqlmin!GetXdbServerGlobals` at `0x10042bdca`
- `sqlmin!GetXdbServerGlobals` at `0x10042be02`
- `sqlmin!GetXdbServerGlobals` at `0x10042be12`
- `sqlmin!GetXdbServerGlobals` at `0x10042be4a`
- `sqlmin!GetXdbServerGlobals` at `0x10042be85`
- `sqlmin!GetXdbServerGlobals` at `0x10042bec1`
- `sqlmin!GetXdbServerGlobals` at `0x10042befd`
- `sqlmin!GetXdbServerGlobals` at `0x10042bf38`
- `sqlmin!GetXdbServerGlobals` at `0x10042d79d`
- `sqlmin!GetXdbServerGlobals` at `0x10042dd25`
- `sqlmin!GetXdbServerGlobals` at `0x10042f550`
- `sqlmin!GetXdbServerGlobals` at `0x10042f559`
- `sqlmin!GetXdbServerGlobals` at `0x10042f566`
- `sqlmin!GetXdbServerGlobals` at `0x10042f595`
- `sqlmin!GetXdbServerGlobals` at `0x10042f5c1`
- `sqlmin!GetXdbServerGlobals` at `0x10042f5d0`
- `sqlmin!GetXdbServerGlobals` at `0x10042f695`
- `sqlmin!GetXdbServerGlobals` at `0x10042f6b5`
- `sqlmin!GetXdbServerGlobals` at `0x10042f6cf`
- `sqlmin!GetXdbServerGlobals` at `0x10042f6f2`
- `sqlmin!GetXdbServerGlobals` at `0x10042f701`
- `sqlmin!GetXdbServerGlobals` at `0x10042f710`
- `sqlmin!GetXdbServerGlobals` at `0x10042f722`
- `sqlmin!GetXdbServerGlobals` at `0x10042f754`
- `sqlmin!GetXdbServerGlobals` at `0x10042f76b`
- `sqlmin!GetXdbServerGlobals` at `0x10042f7ba`
- `sqlmin!GetXdbServerGlobals` at `0x10042f7c7`
- `sqlmin!GetXdbServerGlobals` at `0x10042f7dd`
- `sqlmin!GetXdbServerGlobals` at `0x10042f822`
- `sqlmin!GetXdbServerGlobals` at `0x10042fb2c`
- `sqlmin!GetXdbServerGlobals` at `0x10042fb64`
- `sqlmin!GetXdbServerGlobals` at `0x10042fb9c`
- `sqlmin!GetXdbServerGlobals` at `0x10042fc8f`
- `sqlmin!GetXdbServerGlobals` at `0x100430a4c`
- `sqlmin!GetXdbServerGlobals` at `0x100430a87`
- `sqlmin!GetXdbServerGlobals` at `0x100430ac2`
- `sqlmin!GetXdbServerGlobals` at `0x100430afd`
- `sqlmin!GetXdbServerGlobals` at `0x10042a39c`
- `sqlmin!GetXdbServerGlobals` at `0x10042ae1a`
- `sqlmin!GetXdbServerGlobals` at `0x10042ae55`
- `sqlmin!GetXdbServerGlobals` at `0x10042ae8d`
- `sqlmin!GetXdbServerGlobals` at `0x10042bc68`
- `sqlmin!GetXdbServerGlobals` at `0x10042bca3`
- `sqlmin!GetXdbServerGlobals` at `0x10042bcde`
- `sqlmin!GetXdbServerGlobals` at `0x10042bd19`
- `sqlmin!GetXdbServerGlobals` at `0x10042bd54`
- `sqlmin!GetXdbServerGlobals` at `0x10042bd8f`
- `sqlmin!GetXdbServerGlobals` at `0x10042bdca`
- `sqlmin!GetXdbServerGlobals` at `0x10042be02`
- `sqlmin!GetXdbServerGlobals` at `0x10042be12`
- `sqlmin!GetXdbServerGlobals` at `0x10042be4a`
- `sqlmin!GetXdbServerGlobals` at `0x10042be85`
- `sqlmin!GetXdbServerGlobals` at `0x10042bec1`
- `sqlmin!GetXdbServerGlobals` at `0x10042befd`
- `sqlmin!GetXdbServerGlobals` at `0x10042bf38`
- `sqlmin!GetXdbServerGlobals` at `0x10042d79d`
- `sqlmin!GetXdbServerGlobals` at `0x10042dd25`
- `sqlmin!GetXdbServerGlobals` at `0x10042f550`
- `sqlmin!GetXdbServerGlobals` at `0x10042f559`
- `sqlmin!GetXdbServerGlobals` at `0x10042f566`
- `sqlmin!GetXdbServerGlobals` at `0x10042f595`
- `sqlmin!GetXdbServerGlobals` at `0x10042f5c1`
- `sqlmin!GetXdbServerGlobals` at `0x10042f5d0`
- `sqlmin!GetXdbServerGlobals` at `0x10042f695`
- `sqlmin!GetXdbServerGlobals` at `0x10042f6b5`
- `sqlmin!GetXdbServerGlobals` at `0x10042f6cf`
- `sqlmin!GetXdbServerGlobals` at `0x10042f6f2`
- `sqlmin!GetXdbServerGlobals` at `0x10042f701`
- `sqlmin!GetXdbServerGlobals` at `0x10042f710`
- `sqlmin!GetXdbServerGlobals` at `0x10042f722`
- `sqlmin!GetXdbServerGlobals` at `0x10042f754`
- `sqlmin!GetXdbServerGlobals` at `0x10042f76b`
- `sqlmin!GetXdbServerGlobals` at `0x10042f7ba`
- `sqlmin!GetXdbServerGlobals` at `0x10042f7c7`
- `sqlmin!GetXdbServerGlobals` at `0x10042f7dd`
- `sqlmin!GetXdbServerGlobals` at `0x10042f822`
- `sqlmin!GetXdbServerGlobals` at `0x10042fb2c`
- `sqlmin!GetXdbServerGlobals` at `0x10042fb64`
- `sqlmin!GetXdbServerGlobals` at `0x10042fb9c`
- `sqlmin!GetXdbServerGlobals` at `0x10042fc8f`
- `sqlmin!GetXdbServerGlobals` at `0x100430a4c`
- `sqlmin!GetXdbServerGlobals` at `0x100430a87`
- `sqlmin!GetXdbServerGlobals` at `0x100430ac2`
- `sqlmin!GetXdbServerGlobals` at `0x100430afd`
- `sqllang!?XDB_GetIsPaaSV2@@YAJAEA_N@Z` at `0x10042b872`
- `sqllang!?XDB_GetIsPaaSV2@@YAJAEA_N@Z` at `0x10042b872`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x10042a3a5`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10042f621`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100430618`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10043064b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10042f621`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100430618`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10043064b`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10042f573`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10042f7d4`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10042f819`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10042f573`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10042f7d4`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10042f819`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10042b8a1`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100430f68`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10042b8a1`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100430f68`
- `sqldk!?g_featureSwitchesDk@@3VCFeatureSwitchesDk@@A` at `0x10042e037`
- `sqldk!?g_featureSwitchesDk@@3VCFeatureSwitchesDk@@A` at `0x10042e055`
- `USER32!CharUpperW` at `0x10042f900`
- `USER32!CharUpperW` at `0x10042f900`
- `sqlfederation!GetIqGlobals` at `0x10042fce2`
- `sqlfederation!GetIqGlobals` at `0x10042fd14`
- `sqlfederation!GetIqGlobals` at `0x10042fd25`
- `sqlfederation!GetIqGlobals` at `0x10042fd57`
- `sqlfederation!GetIqGlobals` at `0x10042fd91`
- `sqlfederation!GetIqGlobals` at `0x10042fda2`
- `sqlfederation!GetIqGlobals` at `0x10042fdb6`
- `sqlfederation!GetIqGlobals` at `0x10042fde8`
- `sqlfederation!GetIqGlobals` at `0x10042fdfc`
- `sqlfederation!GetIqGlobals` at `0x10042fe2e`
- `sqlfederation!GetIqGlobals` at `0x10042fe42`
- `sqlfederation!GetIqGlobals` at `0x10042fe74`
- `sqlfederation!GetIqGlobals` at `0x10042fce2`
- `sqlfederation!GetIqGlobals` at `0x10042fd14`
- `sqlfederation!GetIqGlobals` at `0x10042fd25`
- `sqlfederation!GetIqGlobals` at `0x10042fd57`
- `sqlfederation!GetIqGlobals` at `0x10042fd91`
- `sqlfederation!GetIqGlobals` at `0x10042fda2`
- `sqlfederation!GetIqGlobals` at `0x10042fdb6`
- `sqlfederation!GetIqGlobals` at `0x10042fde8`
- `sqlfederation!GetIqGlobals` at `0x10042fdfc`
- `sqlfederation!GetIqGlobals` at `0x10042fe2e`
- `sqlfederation!GetIqGlobals` at `0x10042fe42`
- `sqlfederation!GetIqGlobals` at `0x10042fe74`
- `sqlfabric!GetPreventDataExfiltrationWinFabProperty` at `0x10042f864`
- `sqlfabric!GetPreventDataExfiltrationWinFabProperty` at `0x10042f864`
- `sqlfabric!RefreshTridentFlags` at `0x10042f5f5`
- `sqlfabric!RefreshTridentFlags` at `0x10042f5f5`

## string_xrefs

- `0x10042b82b`: `MonitoringSqlMDSAgent`
- `0x10042b85e`: `MonitoringSqlMDSAgent`
- `0x10042a621`: `VersionCleanerSideListSweepTimeoutInMinutes`
- `0x10042a677`: `VersionPagesReadAheadBatchSize`
- `0x10042a8e3`: `PvsForceUpdateLowWatermarkThresholdInMB`
- `0x10042aeeb`: `SynapseLinkSasExpirationThresholdInMin`
- `0x10042af16`: `SynapseLinkOutputStreamMaxBufferSize`
- `0x10042b065`: `TemporalSystemVersioningSettings`
- `0x10042b08d`: `TemporalSystemVersioningSettings`
- `0x10042b0b7`: `TemporalSystemVersioningSettings`
- `0x10042b0e2`: `TemporalSystemVersioningSettings`
- `0x10042b10d`: `TemporalSystemVersioningSettings`
- `0x10042b138`: `TemporalSystemVersioningSettings`
- `0x10042b163`: `TemporalSystemVersioningSettings`
- `0x10042b18e`: `TemporalSystemVersioningSettings`
- `0x10042b1b9`: `TemporalSystemVersioningSettings`
- `0x10042b1e4`: `TemporalSystemVersioningSettings`
- `0x10042b20f`: `TemporalSystemVersioningSettings`
- `0x10042b23a`: `TemporalSystemVersioningSettings`
- `0x10042b265`: `TemporalSystemVersioningSettings`
- `0x10042b290`: `TemporalSystemVersioningSettings`
- `0x10042b2bb`: `TemporalSystemVersioningSettings`
- `0x10042b2e6`: `TemporalSystemVersioningSettings`
- `0x10042b311`: `TemporalSystemVersioningSettings`
- `0x10042b33c`: `TemporalSystemVersioningSettings`
- `0x10042b367`: `TemporalSystemVersioningSettings`
- `0x10042b05e`: `TemporalSystemVersioningTimeBetweenTasks`
- `0x10042b0b0`: `TemporalSystemVersioningFlushTaskPeriod`
- `0x10042b086`: `TemporalSystemVersioningFlushTaskMemoryCountRatio`
- `0x10042b106`: `TemporalSystemVersioningFlushTaskDiscoveryPeriod`
- `0x10042b0db`: `TemporalSystemVersioningFlushTaskShortPeriod`
- `0x10042b15c`: `TemporalSystemVersioningFlushTaskMaxDop`
- `0x10042b131`: `TemporalSystemVersioningFlushTaskCheckCleanupMinPeriod`
- `0x10042b1b2`: `TemporalSystemVersioningRetentionTaskPeriod`
- `0x10042b187`: `TemporalSystemVersioningFlushTaskChunkSize`
- `0x10042b208`: `TemporalSystemVersioningRetentionTaskDiscoveryPeriod`
- `0x10042b1dd`: `TemporalSystemVersioningRetentionTaskShortPeriod`
- `0x10042b25e`: `TemporalSystemVersioningRetentionTaskMaxDop`
- `0x10042b233`: `TemporalSystemVersioningRetentionTaskCheckCleanupMinPeriod`
- `0x10042b2b4`: `TemporalSystemVersioningCciRetentionTaskPeriod`
- `0x10042b289`: `TemporalSystemVersioningRetentionTaskChunkSize`
- `0x10042b30a`: `TemporalSystemVersioningCciRetentionTaskDiscoveryPeriod`
- `0x10042b2df`: `TemporalSystemVersioningCciRetentionTaskShortPeriod`
- `0x10042b360`: `TemporalSystemVersioningCciRetentionTaskMaxDop`
- `0x10042b335`: `TemporalSystemVersioningCciRetentionTaskCheckCleanupMinPeriod`
- `0x10042b392`: `TupleMoverSettings`
- `0x10042b3bd`: `TupleMoverSettings`
- `0x10042b3e8`: `TupleMoverSettings`
- `0x10042b413`: `TupleMoverSettings`
- `0x10042b38b`: `MinRowCountForAggressiveCompression`
- `0x10042b3e1`: `MinTimeInSecondsForAggressiveCompression`
- `0x10042b3b6`: `MaxRowCountForAggressiveCompression`
- `0x10042b40c`: `IterationThresholdForAggressiveCompression`
- `0x10042b564`: `MaxTempdbDbMaxSizeinMB`
- `0x10042b539`: `DefaultTempdbDbMaxSizeinMB`
- `0x10042b5ba`: `TempDbFileGrowthinMB`
- `0x10042b58f`: `InitialTempdbDbFileSizeinMB`
- `0x10042b610`: `TempDbLogFileMaxSizeinMB`
- `0x10042b5e5`: `TempDbInitialLogFileSizeinMB`
- `0x10042b666`: `ExternalFileDiskCacheCapacityMB`
- `0x10042b63b`: `TempDbLogFileGrowthinMB`
- `0x10042b691`: `ExternalFileMemoryCacheCapacityMB`
- `0x10042b79b`: `DeflationSettingsFabricURI`
- `0x10042b98b`: `InitialTempDbRemoteFileSizeinMB`
- `0x10042b960`: `TempDbRemoteFileMaxSizeInMB`
- `0x10042b9b6`: `TempDbRemoteFileGrowthinMB`
- `0x10042bac8`: `MinReadAheadQueueDepth`
- `0x10042baa1`: `MaxReadAheadSize`
- `0x10042bb16`: `MaxReadAheadSizeColumnStore`
- `0x10042baef`: `MaxReadAheadQueueDepth`
- `0x10042bd75`: `IHSTempdbSpaceUsageAnalyticsPercentile`
- `0x10042bde8`: `EstimatedRecoveryReads`
- `0x10042bf59`: `NativeShuffleAsyncReadBufferCount`
- `0x10042bf1e`: `SpaceUsageWriteStatEventIntervalMilliSec`
- `0x10042bf80`: `NativeShuffleMaxAsyncWriteBufferCount`
- `0x10042bfa7`: `NativeShuffleMinAsyncWriteBufferCount`
- `0x10042c043`: `NativeShuffleMaxThreadsPerBufferSet`
- `0x10042c17b`: `ToadMinRowCountForCompression`
- `0x10042c217`: `ToadMinStaleDeletesToRewrite`
- `0x10042c265`: `ToadRowRatioForAbortingCompression`
- `0x10042c23e`: `ToadMinUncompressedDeletesToMerge`
- `0x10042c39d`: `MaxXStoreSuggestedLogWriteKBps`
- `0x10042c460`: `DwPestoBlobXStoreReadIOSizeBytes`
- `0x10042c487`: `DwPestoBlobXStoreWriteIOSizeBytes`
- `0x10042c5e6`: `MemoryClerkStatsUpdatePeriodSeconds`
- `0x10042c65b`: `MemoryClerkStatsDumpThresholdVmCommittedKb`
- `0x10042c6f7`: `CollectCacheHashTableStatsPeriodMinutes`
- `0x10042c76c`: `CollectStoreCacheHistogramPeriodMinutes`
- `0x10042c7ba`: `StoreCacheStatsCollectionDefaultTypes`
- `0x10042c793`: `CollectCacheActivenessStatsPeriodMinutes`
- `0x10042c7de`: `ServerlessActiveCacheThresholdMinutes`
- `0x10042c7d7`: `ServerlessActiveCacheThresholdMinutesForEP`
- `0x10042c812`: `ServerlessCacheReclaimThresholdForCacheUsedPercent`
- `0x10042c80b`: `ServerlessCacheReclaimThresholdForCacheUsedPercentForEP`
- `0x10042c87b`: `ServerlessCacheReclaimThresholdForCpuUsedPercent`
- `0x10042c854`: `ServerlessCacheReclaimIntervalForCacheUsedMinutesForEP`
- `0x10042c8c9`: `ServerlessCheckFlushCachesTimePeriodMinutes`
- `0x10042c8a2`: `ServerlessCacheReclaimObjectStoresPercent`
- `0x10042c917`: `ServerlessFlushCachesResetTargetTimeoutSeconds`
- `0x10042c8f0`: `ServerlessFlushCachesCpuIdlenssThresholdMinutes`
- `0x10042ca4f`: `ServerlessTimeoutToResetInternalCacheTargetSec`
- `0x10042ca9d`: `ServerlessDirectShrinkInternalCacheMinMemoryInMB`
- `0x10042ca76`: `ServerlessTimeoutToResetExternalCacheTargetSec`
- `0x10042caeb`: `ServerlessCacheReclaimCpuTriggerPolicy`
- `0x10042cb39`: `ServerlessCpuTriggerCachePagesReclaimablePercent`
- `0x10042cb12`: `ServerlessCacheReclaimPolicy`
- `0x10042cb60`: `ProvisionedActiveCacheThresholdMinutes`
- `0x10042cbd5`: `ProvisionedCacheReclaimThresholdForCacheUsedPercent`
- `0x10042ccbf`: `PageServerCacheReclaimThresholdForCacheUsedPercent`
- `0x10042cc98`: `PageServerActiveCacheThresholdMinutes`
- `0x10042ce45`: `ServerlessLockManagerCachedObjectsMemoryLimitPercent`
- `0x10042ce1e`: `SoftCapPlanCachePercent`
- `0x10042ce6c`: `LockManagerCachedObjectsMemoryLimitPercent`
- `0x10042ceba`: `DeflationCacheMemoryLowerBoundKb`
- `0x10042cf2f`: `GlobalCacheActivenessStatsNumCoresPerPartition`
- `0x10042cf08`: `DeflationCacheMemoryOverheadPerVCoreKb`
- `0x10042cf56`: `GlobalCacheActivenessStatsIntervalPeriodSeconds`
- `0x10042d019`: `TempDbUpdateRateInMinutes`
- `0x10042d484`: `UpdateRgIsolationRetryWaitTimeInMs`
- `0x10042d45d`: `UpdateRgIsolationRetryThreshold`
- `0x10042d4ab`: `PassiveBrokerFreeMemoryGapPercent`
- `0x10042d7d3`: `AprcCompilationErrorsToSurfaceToQds`
- `0x10042dd5a`: `PFSFileWriteMBps`
- `0x10042dd85`: `PFSFileTargetReadMBps`
- `0x10042de05`: `PFSWriteBWFactor`
- `0x10042de2c`: `PFSReadBWFactor`
- `0x10042df13`: `CheckpointReadAheadEfficiency`
- `0x10042df94`: `RbpexPageReaderPoolSize`
- `0x10042e0d8`: `FirewallCacheExpirationTimeMilliSec`
- `0x10042e184`: `CacheTimeoutMs`
- `0x10042e1af`: `CacheUpdateRetryInitialBackOffMs`
- `0x10042e18b`: `XOdbcAuthenticationCacheSettings`
- `0x10042e1b6`: `XOdbcAuthenticationCacheSettings`
- `0x10042e1e1`: `XOdbcAuthenticationCacheSettings`
- `0x10042e20c`: `XOdbcAuthenticationCacheSettings`
- `0x10042e237`: `XOdbcAuthenticationCacheSettings`
- `0x10042e205`: `CacheUpdateRetryMaxNumberOfRetries`
- `0x10042e1da`: `CacheUpdateRetryMaxRetryDurationMs`
- `0x10042e25b`: `DbFwCacheTimeoutMs`
- `0x10042e286`: `DbFwCacheLockWaitTimeMs`
- `0x10042e7ef`: `AuditingNoStorageFaultServerAuditEmailNotificationTemplateVersion`
- `0x10042e857`: `AuditingNoContainerFaultServerAuditEmailNotificationTemplateVersion`
- `0x10042e823`: `AuditingNoStorageFaultDatabaseAuditEmailNotificationTemplateVersion`
- `0x10042e8bf`: `AuditingStorageNoAccessFaultServerAuditEmailNotificationTemplateVersion`
- `0x10042e88b`: `AuditingNoContainerFaultDatabaseAuditEmailNotificationTemplateVersion`
- `0x10042e8f3`: `AuditingStorageNoAccessFaultDatabaseAuditEmailNotificationTemplateVersion`
- `0x10042ebf2`: `LogFullAmountBeforeEvictingReplica`
- `0x10042ee86`: `MaxRetryOfCreateOpenBlockBlob`
- `0x10042ef71`: `LogWriterThreadCountPerCPU`
- `0x10042ef36`: `LogWriterThreadCountPerNode`
- `0x10042f05d`: `DwMaxOutstandingSbsCacheWrites`
- `0x10042f032`: `DwCatalogUpdateBatchSize`
- `0x10042f098`: `DwTargetSbsCacheWriteIoTimeInMs`
- `0x10042f10e`: `DwMaxHobtCacheStoreMemoryTarget`
- `0x10042f2aa`: `DwConsolidatedRowgroupMaxUncompressedSize`
- `0x10042f26f`: `DwThresholdSkipWriteToSbsCache`
- `0x10042f3b9`: `ParquetWriterOutputterTotalColumnChunkBufferSizeInMB`
- `0x10042f383`: `ODBCRowCacheSizeInMB`
- `0x10042f425`: `ParquetWriterOutputterMaxRowCountInRowGroup`
- `0x10042f3ef`: `ParquetWriterOutputterMaxRowGroupSizeInMB`
- `0x10042f491`: `ParquetWriterOutputterMaxLobSizeInMB`
- `0x10042f45b`: `ParquetWriterOutputterAdditionalMemoryFactorInPercent`
- `0x10042f4f9`: `ParquetWriterOutputterDataPageSizeInMB`
- `0x10042f4c3`: `ParquetWriterOutputterMaxRowCountInColumnChunkBuffer`
- `0x10042f52b`: `ParquetWriterOutputterDictionaryPageSizeLimitInMB`
- `0x10042fb19`: `DWQPTelemetryConfig`
- `0x10042fb51`: `DWQPTelemetryConfig`
- `0x10042fb89`: `DWQPTelemetryConfig`
- `0x10042fbf9`: `NumberOfOutcomesToPreserve`
- `0x10042fbbe`: `DwSbsFileTableAccessRefreshPeriod`
- `0x10042fc25`: `NumberOfOutcomeInsertsPerStatusReport`
- `0x10042fd3c`: `IqBackgroundTaskTimeout`
- `0x10042fe13`: `IqTimerBasedEvictionTaskPeriodInSeconds`
- `0x10042fe59`: `IqTimerBasedObjectVersionCleanupTaskPeriodInSeconds`
- `0x10042ffb0`: `PageServerDataReadThresholdForActivenessInRequestsPerMin`
- `0x100430008`: `PageServerPageReadTimeoutInMS`
- `0x10043043d`: `WBRecoverySkipLogReadThresholdInSec`
- `0x100430495`: `WriteBehindCheckpointStuckThresholdInSec`
- `0x100430469`: `WBRecoverySkipLogReadRateMonitorIntervalInSec`
- `0x1004304c1`: `WriteBehindRbpexLimitInGB`
- `0x100430571`: `BufferPoolExtensionOverrideSizeInMB`
- `0x100430735`: `NonCoveringRbpexWorkerThreads`
- `0x1004307ee`: `WriteBehindCheckpointMaxIOSizeInKB`
- `0x100430797`: `WriteBehindCheckpointIOSizeInKB`
- `0x10043088e`: `WriteBehindCheckpointBsnFlushRate`
- `0x1004308d3`: `WriteBehindCheckpointThrottleStatsIntervalMs`
- `0x100430b4e`: `RbIoForwarderMaxReadBufferSizeInPages`
- `0x100430b22`: `DegreeOfParallelCopyForUpdateSloSeeding`
- `0x100430c82`: `LogReadWaitTimeAtEolMs`
- `0x100430d06`: `RbIoUcsConnectionsForForwarderXlogReader`
- `0x100430d5e`: `RbIoUcsConnectionUsageForForwarderXlogReader`
- `0x100430e75`: `FidoBucketizationTempdbSpaceRatio`
- `0x100430e49`: `ColumnStoreParallelInsertSelectDopThrottleIgnoreAdditionalMemoryRatio`
- `0x100430eeb`: `FidoBucketizationMaxTempdbUsageRatio`
- `0x100430eb0`: `FidoBucketizationTempDbSizeCheckFrequencyInRows`
- `0x100430f35`: `DwCompat`
- `0x100430fa1`: `DwCompat`
- `0x100430fdc`: `DwCompat`
- `0x100431017`: `DwCompat`
- `0x100430f2e`: `DwValidCompatibilityLevels`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall InitXdbSrvGlobals(__int64 a1, __int64 a2)
{
  __int64 XdbServerGlobals; // r13
  struct IServerConfiguration *v3; // rsi
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rdi
  struct IMemObj *Pmo; // rax
  __int64 v12; // rdi
  struct IMemObj *v13; // rax
  __int64 v14; // rdi
  struct IMemObj *v15; // rax
  struct IMemObj *v16; // rax
  __int64 v17; // rbx
  struct IMemObj *v18; // rax
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // rdx
  __int64 v30; // rcx
  __int64 v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // rdx
  __int64 v34; // rcx
  __int64 v35; // rdx
  __int64 v36; // rcx
  __int64 v37; // rdx
  __int64 v38; // rcx
  __int64 v39; // rdx
  __int64 v40; // rcx
  __int64 v41; // rdx
  __int64 v42; // rcx
  __int64 v43; // rdx
  __int64 v44; // rcx
  __int64 v45; // rdx
  __int64 v46; // rcx
  int v47; // ebx
  const wchar_t *v48; // r8
  const wchar_t *v49; // r8
  __int64 v50; // rdx
  __int64 v51; // rcx
  _OWORD *v52; // rax
  RESOURCE *v53; // rax
  RESOURCE *v54; // rax
  RESOURCE *v55; // rax
  __int64 v56; // rdx
  __int64 v57; // rcx
  __int64 v58; // rax
  struct IServerConfiguration *v59; // r12
  _BOOL8 v60; // rcx
  __int64 v61; // rcx
  __int64 v62; // rcx
  __int64 v63; // rcx
  CFeatureSwitchesMin *v64; // rax
  __int64 v65; // rdi
  struct IMemObj *v66; // rax
  __int64 v67; // rdi
  struct IMemObj *v68; // rax
  __int64 v69; // rdi
  struct IMemObj *v70; // rax
  __int64 v71; // rdi
  struct IMemObj *v72; // rax
  __int64 v73; // rdi
  struct IMemObj *v74; // rax
  __int64 v75; // rdi
  struct IMemObj *v76; // rax
  __int64 v77; // rdi
  struct IMemObj *v78; // rax
  __int64 v79; // rdx
  __int64 v80; // rcx
  __int64 v81; // r15
  __int64 v82; // rdx
  __int64 v83; // rcx
  __int64 v84; // r14
  __int64 v85; // rdx
  __int64 v86; // rcx
  __int64 v87; // rsi
  struct __crt_locale_pointers *DefaultLocale; // rdi
  __int64 v89; // rdx
  const wchar_t *v90; // rbx
  __int64 v91; // rax
  __int64 v92; // rdx
  __int64 v93; // rcx
  __int64 v94; // rdx
  __int64 v95; // rcx
  __int64 v96; // rdx
  __int64 v97; // rcx
  CFeatureSwitchesMin *CurrentInstance; // rax
  unsigned int v99; // edi
  HANDLE ProcessHeap; // rax
  LPVOID v101; // rax
  unsigned __int8 *v102; // rax
  __int64 v103; // rdx
  __int64 v104; // rcx
  unsigned int v105; // esi
  const void *v106; // rbx
  unsigned int v107; // edi
  __int64 v108; // rdx
  __int64 v109; // rcx
  __int64 v110; // rax
  __int64 v111; // rdx
  __int64 v112; // rcx
  __int64 v113; // rax
  __int64 v114; // rdx
  __int64 v115; // rcx
  __int64 v116; // rdx
  __int64 v117; // rcx
  __int64 v118; // rdx
  __int64 v119; // rcx
  __int64 v120; // rax
  __int64 v121; // rdx
  __int64 v122; // rcx
  __int64 v123; // rax
  wchar_t **v124; // rbx
  struct IMemObj *v125; // rax
  __int64 v126; // r14
  __int64 v127; // rdx
  __int64 v128; // rcx
  __int64 v129; // rsi
  __int64 v130; // rdx
  __int64 v131; // rcx
  __int64 v132; // rdi
  struct __crt_locale_pointers *v133; // rbx
  __int64 v134; // rdx
  __int64 v135; // rcx
  __int64 v136; // rax
  struct __crt_locale_pointers *v137; // rbx
  __int64 v138; // rdx
  __int64 v139; // rcx
  __int64 v140; // rax
  struct IMemObj *v141; // rax
  struct IMemObj *v142; // rax
  __int64 v143; // rax
  __int64 v144; // rdx
  __int64 v145; // rcx
  __int64 v146; // rdx
  __int64 v147; // rcx
  __int64 v148; // rdx
  __int64 v149; // rcx
  __int64 v150; // rdi
  __int64 v151; // rbx
  struct IMemObj *v152; // rax
  const wchar_t *v153; // rbx
  __int64 v154; // rdx
  __int64 v155; // rcx
  __int64 v156; // rax
  CFeatureSwitchesMin *v157; // rax
  const unsigned __int8 *GlobalTraceFlagStore; // rax
  __int64 v159; // rbx
  struct IqGlobals *IqGlobals; // rax
  __int64 v161; // rbx
  struct IqGlobals *v162; // rax
  __int64 v163; // rbx
  struct IqGlobals *v164; // rax
  __int64 v165; // rbx
  struct IqGlobals *v166; // rax
  __int64 v167; // rbx
  struct IqGlobals *v168; // rax
  unsigned int v169; // ecx
  int v170; // eax
  int v171; // eax
  int v172; // eax
  int v173; // eax
  int v174; // eax
  int v175; // eax
  __int64 v176; // rdx
  __int64 v177; // rcx
  __int64 v178; // rdx
  __int64 v179; // rcx
  __int64 v180; // rdx
  __int64 v181; // rcx
  __int64 v182; // rdx
  __int64 v183; // rcx
  __int64 v184; // rbx
  struct IMemObj *v185; // rax
  struct IMemObj *v186; // rax
  wchar_t *v187; // rax
  bool v188; // zf
  int v189; // eax
  __int64 v190; // rbx
  struct IMemObj *v191; // rax
  IServerConfiguration *v192; // rbx
  int v193; // [rsp+20h] [rbp-58h]
  int v194; // [rsp+20h] [rbp-58h]
  int v195; // [rsp+20h] [rbp-58h]
  int v196; // [rsp+20h] [rbp-58h]
  int v197; // [rsp+20h] [rbp-58h]
  int v198; // [rsp+20h] [rbp-58h]
  int v199; // [rsp+20h] [rbp-58h]
  int v200; // [rsp+20h] [rbp-58h]
  int v201; // [rsp+20h] [rbp-58h]
  int v202; // [rsp+20h] [rbp-58h]
  int v203; // [rsp+20h] [rbp-58h]
  int v204; // [rsp+20h] [rbp-58h]
  int v205; // [rsp+20h] [rbp-58h]
  int v206; // [rsp+20h] [rbp-58h]
  int v207; // [rsp+20h] [rbp-58h]
  int v208; // [rsp+20h] [rbp-58h]
  int v209; // [rsp+20h] [rbp-58h]
  int v210; // [rsp+20h] [rbp-58h]
  int v211; // [rsp+20h] [rbp-58h]
  int v212; // [rsp+20h] [rbp-58h]
  int v213; // [rsp+20h] [rbp-58h]
  int v214; // [rsp+20h] [rbp-58h]
  int v215; // [rsp+20h] [rbp-58h]
  int v216; // [rsp+20h] [rbp-58h]
  int v217; // [rsp+20h] [rbp-58h]
  int v218; // [rsp+20h] [rbp-58h]
  int v219; // [rsp+20h] [rbp-58h]
  int v220; // [rsp+20h] [rbp-58h]
  int v221; // [rsp+20h] [rbp-58h]
  int v222; // [rsp+20h] [rbp-58h]
  int v223; // [rsp+20h] [rbp-58h]
  int v224; // [rsp+20h] [rbp-58h]
  int v225; // [rsp+20h] [rbp-58h]
  int v226; // [rsp+20h] [rbp-58h]
  int v227; // [rsp+20h] [rbp-58h]
  int v228; // [rsp+20h] [rbp-58h]
  int v229; // [rsp+20h] [rbp-58h]
  int v230; // [rsp+20h] [rbp-58h]
  int v231; // [rsp+20h] [rbp-58h]
  int v232; // [rsp+20h] [rbp-58h]
  int v233; // [rsp+20h] [rbp-58h]
  int v234; // [rsp+20h] [rbp-58h]
  int v235; // [rsp+20h] [rbp-58h]
  int v236; // [rsp+20h] [rbp-58h]
  int v237; // [rsp+20h] [rbp-58h]
  int v238; // [rsp+20h] [rbp-58h]
  int v239; // [rsp+20h] [rbp-58h]
  int v240; // [rsp+20h] [rbp-58h]
  int v241; // [rsp+20h] [rbp-58h]
  int v242; // [rsp+20h] [rbp-58h]
  int v243; // [rsp+20h] [rbp-58h]
  int v244; // [rsp+20h] [rbp-58h]
  int v245; // [rsp+20h] [rbp-58h]
  int v246; // [rsp+20h] [rbp-58h]
  int v247; // [rsp+20h] [rbp-58h]
  int v248; // [rsp+20h] [rbp-58h]
  int v249; // [rsp+20h] [rbp-58h]
  int v250; // [rsp+20h] [rbp-58h]
  int v251; // [rsp+20h] [rbp-58h]
  int v252; // [rsp+20h] [rbp-58h]
  int v253; // [rsp+20h] [rbp-58h]
  int v254; // [rsp+20h] [rbp-58h]
  int v255; // [rsp+20h] [rbp-58h]
  int v256; // [rsp+20h] [rbp-58h]
  int v257; // [rsp+20h] [rbp-58h]
  int v258; // [rsp+20h] [rbp-58h]
  int v259; // [rsp+20h] [rbp-58h]
  int v260; // [rsp+20h] [rbp-58h]
  int v261; // [rsp+20h] [rbp-58h]
  int v262; // [rsp+20h] [rbp-58h]
  int v263; // [rsp+20h] [rbp-58h]
  int v264; // [rsp+20h] [rbp-58h]
  int v265; // [rsp+20h] [rbp-58h]
  int v266; // [rsp+20h] [rbp-58h]
  int v267; // [rsp+20h] [rbp-58h]
  int v268; // [rsp+20h] [rbp-58h]
  int v269; // [rsp+20h] [rbp-58h]
  int v270; // [rsp+20h] [rbp-58h]
  int v271; // [rsp+20h] [rbp-58h]
  int v272; // [rsp+20h] [rbp-58h]
  int v273; // [rsp+20h] [rbp-58h]
  int v274; // [rsp+20h] [rbp-58h]
  int v275; // [rsp+20h] [rbp-58h]
  int v276; // [rsp+20h] [rbp-58h]
  int v277; // [rsp+20h] [rbp-58h]
  int v278; // [rsp+20h] [rbp-58h]
  int v279; // [rsp+20h] [rbp-58h]
  int v280; // [rsp+20h] [rbp-58h]
  int v281; // [rsp+20h] [rbp-58h]
  int v282; // [rsp+20h] [rbp-58h]
  int v283; // [rsp+20h] [rbp-58h]
  int v284; // [rsp+20h] [rbp-58h]
  int v285; // [rsp+20h] [rbp-58h]
  int v286; // [rsp+20h] [rbp-58h]
  int v287; // [rsp+20h] [rbp-58h]
  int v288; // [rsp+20h] [rbp-58h]
  int v289; // [rsp+20h] [rbp-58h]
  int v290; // [rsp+20h] [rbp-58h]
  int v291; // [rsp+20h] [rbp-58h]
  int v292; // [rsp+20h] [rbp-58h]
  int v293; // [rsp+20h] [rbp-58h]
  int v294; // [rsp+20h] [rbp-58h]
  int v295; // [rsp+20h] [rbp-58h]
  int v296; // [rsp+20h] [rbp-58h]
  int v297; // [rsp+20h] [rbp-58h]
  int v298; // [rsp+20h] [rbp-58h]
  int v299; // [rsp+20h] [rbp-58h]
  int v300; // [rsp+20h] [rbp-58h]
  int v301; // [rsp+20h] [rbp-58h]
  int v302; // [rsp+20h] [rbp-58h]
  int v303; // [rsp+20h] [rbp-58h]
  int v304; // [rsp+20h] [rbp-58h]
  int v305; // [rsp+20h] [rbp-58h]
  int v306; // [rsp+20h] [rbp-58h]
  int v307; // [rsp+20h] [rbp-58h]
  int v308; // [rsp+20h] [rbp-58h]
  int v309; // [rsp+20h] [rbp-58h]
  int v310; // [rsp+20h] [rbp-58h]
  int v311; // [rsp+20h] [rbp-58h]
  int v312; // [rsp+20h] [rbp-58h]
  int v313; // [rsp+20h] [rbp-58h]
  int v314; // [rsp+20h] [rbp-58h]
  int v315; // [rsp+20h] [rbp-58h]
  int v316; // [rsp+20h] [rbp-58h]
  int v317; // [rsp+20h] [rbp-58h]
  int v318; // [rsp+20h] [rbp-58h]
  int v319; // [rsp+20h] [rbp-58h]
  int v320; // [rsp+20h] [rbp-58h]
  int v321; // [rsp+20h] [rbp-58h]
  int v322; // [rsp+20h] [rbp-58h]
  int v323; // [rsp+20h] [rbp-58h]
  int v324; // [rsp+20h] [rbp-58h]
  int v325; // [rsp+20h] [rbp-58h]
  int v326; // [rsp+20h] [rbp-58h]
  int v327; // [rsp+20h] [rbp-58h]
  int v328; // [rsp+20h] [rbp-58h]
  int v329; // [rsp+20h] [rbp-58h]
  int v330; // [rsp+20h] [rbp-58h]
  int v331; // [rsp+20h] [rbp-58h]
  int v332; // [rsp+20h] [rbp-58h]
  int v333; // [rsp+20h] [rbp-58h]
  int v334; // [rsp+20h] [rbp-58h]
  int v335; // [rsp+20h] [rbp-58h]
  int v336; // [rsp+20h] [rbp-58h]
  int v337; // [rsp+20h] [rbp-58h]
  int v338; // [rsp+20h] [rbp-58h]
  int v339; // [rsp+20h] [rbp-58h]
  int v340; // [rsp+20h] [rbp-58h]
  int v341; // [rsp+20h] [rbp-58h]
  int v342; // [rsp+20h] [rbp-58h]
  int v343; // [rsp+20h] [rbp-58h]
  int v344; // [rsp+20h] [rbp-58h]
  int v345; // [rsp+20h] [rbp-58h]
  int v346; // [rsp+20h] [rbp-58h]
  int v347; // [rsp+20h] [rbp-58h]
  int v348; // [rsp+20h] [rbp-58h]
  int v349; // [rsp+20h] [rbp-58h]
  int v350; // [rsp+20h] [rbp-58h]
  int v351; // [rsp+20h] [rbp-58h]
  int v352; // [rsp+20h] [rbp-58h]
  int v353; // [rsp+20h] [rbp-58h]
  int v354; // [rsp+20h] [rbp-58h]
  int v355; // [rsp+20h] [rbp-58h]
  int v356; // [rsp+20h] [rbp-58h]
  int v357; // [rsp+20h] [rbp-58h]
  int v358; // [rsp+20h] [rbp-58h]
  int v359; // [rsp+20h] [rbp-58h]
  int v360; // [rsp+20h] [rbp-58h]
  int v361; // [rsp+20h] [rbp-58h]
  int v362; // [rsp+20h] [rbp-58h]
  int v363; // [rsp+20h] [rbp-58h]
  int v364; // [rsp+20h] [rbp-58h]
  int v365; // [rsp+20h] [rbp-58h]
  int v366; // [rsp+20h] [rbp-58h]
  int v367; // [rsp+20h] [rbp-58h]
  int v368; // [rsp+20h] [rbp-58h]
  int v369; // [rsp+20h] [rbp-58h]
  int v370; // [rsp+20h] [rbp-58h]
  int v371; // [rsp+20h] [rbp-58h]
  int v372; // [rsp+20h] [rbp-58h]
  int v373; // [rsp+20h] [rbp-58h]
  int v374; // [rsp+20h] [rbp-58h]
  int v375; // [rsp+20h] [rbp-58h]
  int v376; // [rsp+20h] [rbp-58h]
  int v377; // [rsp+20h] [rbp-58h]
  int v378; // [rsp+20h] [rbp-58h]
  int v379; // [rsp+20h] [rbp-58h]
  int v380; // [rsp+20h] [rbp-58h]
  int v381; // [rsp+20h] [rbp-58h]
  int v382; // [rsp+20h] [rbp-58h]
  int v383; // [rsp+20h] [rbp-58h]
  int v384; // [rsp+20h] [rbp-58h]
  int v385; // [rsp+20h] [rbp-58h]
  int v386; // [rsp+20h] [rbp-58h]
  int v387; // [rsp+20h] [rbp-58h]
  int v388; // [rsp+20h] [rbp-58h]
  int v389; // [rsp+20h] [rbp-58h]
  int v390; // [rsp+20h] [rbp-58h]
  int v391; // [rsp+20h] [rbp-58h]
  int v392; // [rsp+20h] [rbp-58h]
  int v393; // [rsp+20h] [rbp-58h]
  int v394; // [rsp+20h] [rbp-58h]
  int v395; // [rsp+20h] [rbp-58h]
  int v396; // [rsp+20h] [rbp-58h]
  int v397; // [rsp+20h] [rbp-58h]
  int v398; // [rsp+20h] [rbp-58h]
  int v399; // [rsp+20h] [rbp-58h]
  int v400; // [rsp+20h] [rbp-58h]
  int v401; // [rsp+20h] [rbp-58h]
  int v402; // [rsp+20h] [rbp-58h]
  int v403; // [rsp+20h] [rbp-58h]
  int v404; // [rsp+20h] [rbp-58h]
  int v405; // [rsp+20h] [rbp-58h]
  int v406; // [rsp+20h] [rbp-58h]
  int v407; // [rsp+20h] [rbp-58h]
  int v408; // [rsp+20h] [rbp-58h]
  int v409; // [rsp+20h] [rbp-58h]
  int v410; // [rsp+20h] [rbp-58h]
  int v411; // [rsp+20h] [rbp-58h]
  int v412; // [rsp+20h] [rbp-58h]
  int v413; // [rsp+20h] [rbp-58h]
  int v414; // [rsp+20h] [rbp-58h]
  int v415; // [rsp+20h] [rbp-58h]
  int v416; // [rsp+20h] [rbp-58h]
  int v417; // [rsp+20h] [rbp-58h]
  int v418; // [rsp+20h] [rbp-58h]
  int v419; // [rsp+20h] [rbp-58h]
  int v420; // [rsp+20h] [rbp-58h]
  int v421; // [rsp+20h] [rbp-58h]
  int v422; // [rsp+20h] [rbp-58h]
  int v423; // [rsp+20h] [rbp-58h]
  int v424; // [rsp+20h] [rbp-58h]
  int v425; // [rsp+20h] [rbp-58h]
  int v426; // [rsp+20h] [rbp-58h]
  int v427; // [rsp+20h] [rbp-58h]
  int v428; // [rsp+20h] [rbp-58h]
  int v429; // [rsp+20h] [rbp-58h]
  int v430; // [rsp+20h] [rbp-58h]
  int v431; // [rsp+20h] [rbp-58h]
  int v432; // [rsp+20h] [rbp-58h]
  int v433; // [rsp+20h] [rbp-58h]
  int v434; // [rsp+20h] [rbp-58h]
  int v435; // [rsp+20h] [rbp-58h]
  int v436; // [rsp+20h] [rbp-58h]
  int v437; // [rsp+20h] [rbp-58h]
  int v438; // [rsp+20h] [rbp-58h]
  int v439; // [rsp+20h] [rbp-58h]
  int v440; // [rsp+20h] [rbp-58h]
  int v441; // [rsp+20h] [rbp-58h]
  int v442; // [rsp+20h] [rbp-58h]
  int v443; // [rsp+20h] [rbp-58h]
  int v444; // [rsp+20h] [rbp-58h]
  int v445; // [rsp+20h] [rbp-58h]
  int v446; // [rsp+20h] [rbp-58h]
  int v447; // [rsp+20h] [rbp-58h]
  int v448; // [rsp+20h] [rbp-58h]
  int v449; // [rsp+20h] [rbp-58h]
  int v450; // [rsp+20h] [rbp-58h]
  int v451; // [rsp+20h] [rbp-58h]
  int v452; // [rsp+20h] [rbp-58h]
  int v453; // [rsp+20h] [rbp-58h]
  int v454; // [rsp+20h] [rbp-58h]
  int v455; // [rsp+20h] [rbp-58h]
  int v456; // [rsp+20h] [rbp-58h]
  int v457; // [rsp+20h] [rbp-58h]
  int v458; // [rsp+20h] [rbp-58h]
  int v459; // [rsp+20h] [rbp-58h]
  int v460; // [rsp+20h] [rbp-58h]
  int v461; // [rsp+20h] [rbp-58h]
  int v462; // [rsp+20h] [rbp-58h]
  int v463; // [rsp+20h] [rbp-58h]
  int v464; // [rsp+20h] [rbp-58h]
  int v465; // [rsp+20h] [rbp-58h]
  int v466; // [rsp+20h] [rbp-58h]
  int v467; // [rsp+20h] [rbp-58h]
  int v468; // [rsp+20h] [rbp-58h]
  int v469; // [rsp+20h] [rbp-58h]
  int v470; // [rsp+20h] [rbp-58h]
  int v471; // [rsp+20h] [rbp-58h]
  int v472; // [rsp+20h] [rbp-58h]
  int v473; // [rsp+20h] [rbp-58h]
  int v474; // [rsp+20h] [rbp-58h]
  int v475; // [rsp+20h] [rbp-58h]
  int v476; // [rsp+20h] [rbp-58h]
  int v477; // [rsp+20h] [rbp-58h]
  int v478; // [rsp+20h] [rbp-58h]
  int v479; // [rsp+20h] [rbp-58h]
  int v480; // [rsp+20h] [rbp-58h]
  int v481; // [rsp+20h] [rbp-58h]
  int v482; // [rsp+20h] [rbp-58h]
  int v483; // [rsp+20h] [rbp-58h]
  int v484; // [rsp+20h] [rbp-58h]
  int v485; // [rsp+20h] [rbp-58h]
  int v486; // [rsp+20h] [rbp-58h]
  int v487; // [rsp+20h] [rbp-58h]
  int v488; // [rsp+20h] [rbp-58h]
  int v489; // [rsp+20h] [rbp-58h]
  int v490; // [rsp+20h] [rbp-58h]
  int v491; // [rsp+20h] [rbp-58h]
  int v492; // [rsp+20h] [rbp-58h]
  int v493; // [rsp+20h] [rbp-58h]
  int v494; // [rsp+20h] [rbp-58h]
  int v495; // [rsp+20h] [rbp-58h]
  int v496; // [rsp+20h] [rbp-58h]
  int v497; // [rsp+20h] [rbp-58h]
  int v498; // [rsp+20h] [rbp-58h]
  int v499; // [rsp+20h] [rbp-58h]
  int v500; // [rsp+20h] [rbp-58h]
  int v501; // [rsp+20h] [rbp-58h]
  int v502; // [rsp+20h] [rbp-58h]
  int v503; // [rsp+20h] [rbp-58h]
  int v504; // [rsp+20h] [rbp-58h]
  int v505; // [rsp+20h] [rbp-58h]
  int v506; // [rsp+20h] [rbp-58h]
  int v507; // [rsp+20h] [rbp-58h]
  int v508; // [rsp+20h] [rbp-58h]
  int v509; // [rsp+20h] [rbp-58h]
  int v510; // [rsp+20h] [rbp-58h]
  int v511; // [rsp+20h] [rbp-58h]
  int v512; // [rsp+20h] [rbp-58h]
  int v513; // [rsp+20h] [rbp-58h]
  int v514; // [rsp+20h] [rbp-58h]
  int v515; // [rsp+20h] [rbp-58h]
  int v516; // [rsp+20h] [rbp-58h]
  int v517; // [rsp+20h] [rbp-58h]
  int v518; // [rsp+20h] [rbp-58h]
  int v519; // [rsp+20h] [rbp-58h]
  int v520; // [rsp+20h] [rbp-58h]
  int v521; // [rsp+20h] [rbp-58h]
  int v522; // [rsp+20h] [rbp-58h]
  int v523; // [rsp+20h] [rbp-58h]
  int v524; // [rsp+20h] [rbp-58h]
  int v525; // [rsp+20h] [rbp-58h]
  int v526; // [rsp+20h] [rbp-58h]
  int v527; // [rsp+20h] [rbp-58h]
  int v528; // [rsp+20h] [rbp-58h]
  int v529; // [rsp+20h] [rbp-58h]
  int v530; // [rsp+20h] [rbp-58h]
  int v531; // [rsp+20h] [rbp-58h]
  int v532; // [rsp+20h] [rbp-58h]
  int v533; // [rsp+20h] [rbp-58h]
  int v534; // [rsp+20h] [rbp-58h]
  int v535; // [rsp+20h] [rbp-58h]
  int v536; // [rsp+20h] [rbp-58h]
  int v537; // [rsp+20h] [rbp-58h]
  int v538; // [rsp+20h] [rbp-58h]
  int v539; // [rsp+20h] [rbp-58h]
  int v540; // [rsp+20h] [rbp-58h]
  int v541; // [rsp+20h] [rbp-58h]
  int v542; // [rsp+20h] [rbp-58h]
  int v543; // [rsp+20h] [rbp-58h]
  int v544; // [rsp+20h] [rbp-58h]
  int v545; // [rsp+20h] [rbp-58h]
  int v546; // [rsp+20h] [rbp-58h]
  int v547; // [rsp+20h] [rbp-58h]
  int v548; // [rsp+20h] [rbp-58h]
  int v549; // [rsp+20h] [rbp-58h]
  int v550; // [rsp+20h] [rbp-58h]
  int v551; // [rsp+20h] [rbp-58h]
  int v552; // [rsp+20h] [rbp-58h]
  int v553; // [rsp+20h] [rbp-58h]
  int v554; // [rsp+20h] [rbp-58h]
  int v555; // [rsp+20h] [rbp-58h]
  int v556; // [rsp+40h] [rbp-38h] BYREF
  int v557; // [rsp+44h] [rbp-34h] BYREF
  int v558; // [rsp+48h] [rbp-30h] BYREF
  struct IServerConfiguration *v559; // [rsp+50h] [rbp-28h]
  _BYTE v560[8]; // [rsp+58h] [rbp-20h] BYREF
  _BYTE v561[8]; // [rsp+60h] [rbp-18h] BYREF
  __int64 v562; // [rsp+68h] [rbp-10h]
  bool v563; // [rsp+C0h] [rbp+48h] BYREF
  SIZE_T dwBytes; // [rsp+C8h] [rbp+50h] BYREF
  signed int v565; // [rsp+D0h] [rbp+58h] BYREF
  int v566; // [rsp+D8h] [rbp+60h] BYREF

  v562 = -2;
  XdbServerGlobals = GetXdbServerGlobals(a1, a2);
  v559 = s_pServerConf;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, char, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"TrustServerCertificate",
    XdbServerGlobals + 8188,
    1,
    0);
  v3 = s_pServerConf;
  LOBYTE(v193) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)v559 + 520LL))(
    v559,
    L"SQL",
    L"UsesLanguageLockdown",
    XdbServerGlobals + 8308,
    v193,
    0);
  LOBYTE(v194) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)v3 + 520LL))(
    v3,
    L"SQL",
    L"UsesXStoreInfiniteLease",
    XdbServerGlobals + 15236,
    v194,
    0);
  LOBYTE(v195) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)v3 + 520LL))(
    v3,
    L"SQL",
    L"IsAbTestInstance",
    XdbServerGlobals + 0x2000,
    v195,
    0);
  LOBYTE(v196) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)v3 + 520LL))(
    v3,
    L"SQL",
    L"IsIsolatedAbTestInstance",
    XdbServerGlobals + 8196,
    v196,
    0);
  IServerConfiguration::GetDynamicBoolSetting(
    s_pServerConf,
    L"SQL",
    L"EnableHekaton",
    (bool *)(XdbServerGlobals + 16288),
    1,
    0);
  IServerConfiguration::GetDynamicBoolSetting(
    s_pServerConf,
    L"SQL",
    L"EnableApollo",
    (bool *)(XdbServerGlobals + 16289),
    1,
    0);
  LOBYTE(v197) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)v3 + 520LL))(
    v3,
    L"SQL",
    L"IsIsolatedDatabaseInstance",
    XdbServerGlobals + 16300,
    v197,
    0);
  LOBYTE(v198) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)v3 + 520LL))(
    v3,
    L"SQL",
    L"IsIsolatedDatabaseInstance",
    XdbServerGlobals + 16304,
    v198,
    0);
  LOBYTE(v199) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)v3 + 520LL))(
    v3,
    L"SQL",
    L"FilteredDumpPercentage",
    XdbServerGlobals + 24164,
    v199,
    0);
  LOBYTE(v200) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)v3 + 520LL))(
    v3,
    L"SQL",
    L"DumpUploadMode",
    XdbServerGlobals + 24168,
    v200,
    0);
  LOBYTE(v201) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)v3 + 520LL))(
    v3,
    L"SQL",
    L"VersionCleanerHobtLockTimeoutInMS",
    XdbServerGlobals + 24172,
    v201,
    0);
  LOBYTE(v202) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)v3 + 520LL))(
    v3,
    L"SQL",
    L"NonDataPagesSweptPercentThreshold",
    XdbServerGlobals + 24176,
    v202,
    0);
  LOBYTE(v203) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)v3 + 520LL))(
    v3,
    L"SQL",
    L"VersionCleanerPvsCleanupTimeInMinutes",
    XdbServerGlobals + 24180,
    v203,
    0);
  LOBYTE(v204) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)v3 + 520LL))(
    v3,
    L"SQL",
    L"VersionCleanerSideListSweepTimeoutInMinutes",
    XdbServerGlobals + 24184,
    v204,
    0);
  LOBYTE(v205) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)v3 + 520LL))(
    v3,
    L"SQL",
    L"AbortedTransactionMapNumberOfBuckets",
    XdbServerGlobals + 24192,
    v205,
    0);
  LOBYTE(v206) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)v3 + 520LL))(
    v3,
    L"SQL",
    L"VersionPagesReadAheadBatchSize",
    XdbServerGlobals + 24196,
    v206,
    0);
  LOBYTE(v207) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)v3 + 520LL))(
    v3,
    L"SQL",
    L"ShortTranLogRecCountThreshold",
    XdbServerGlobals + 24200,
    v207,
    0);
  LOBYTE(v208) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)v3 + 520LL))(
    v3,
    L"SQL",
    L"ShortTranLogUsedThresholdInMB",
    XdbServerGlobals + 24204,
    v208,
    0);
  LOBYTE(v209) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)v3 + 520LL))(
    v3,
    L"SQL",
    L"CloudServerDbVersion",
    XdbServerGlobals + 24208,
    v209,
    0);
  LOBYTE(v210) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)v3 + 520LL))(
          v3,
          L"SQL",
          L"MaxWaitTimeForAnyReplicaInRbioInitLocalPagesInSeconds",
          XdbServerGlobals + 19620,
          v210,
          0) )
    *(_DWORD *)(XdbServerGlobals + 19620) = 900;
  LOBYTE(v211) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"SQL",
          L"MaxWaitTimeForAllReplicasInRbioInitLocalPagesInSeconds",
          XdbServerGlobals + 19624,
          v211,
          0) )
    *(_DWORD *)(XdbServerGlobals + 19624) = 30;
  LOBYTE(v212) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"SQL",
          L"CTRVersionCleanupPolicyForPVSPage",
          XdbServerGlobals + 24256,
          v212,
          0) )
    *(_DWORD *)(XdbServerGlobals + 24256) = 0;
  LOBYTE(v213) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"SQL",
          L"PvsPreAllocationMaxExtentsInFreeList",
          XdbServerGlobals + 24212,
          v213,
          0) )
    *(_DWORD *)(XdbServerGlobals + 24212) = 0;
  LOBYTE(v214) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"SQL",
          L"PvsPreAllocationFactor",
          XdbServerGlobals + 24216,
          v214,
          0) )
    *(_DWORD *)(XdbServerGlobals + 24216) = 0;
  LOBYTE(v215) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"SQL",
          L"VersionCleanerDirtyPageFileSwitchThreshold",
          XdbServerGlobals + 24188,
          v215,
          0) )
    *(_DWORD *)(XdbServerGlobals + 24188) = 0;
  LOBYTE(v216) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"SQL",
          L"NonCtrTxLogRecordCountThreshold",
          XdbServerGlobals + 24664,
          v216,
          0) )
    *(_DWORD *)(XdbServerGlobals + 24664) = 10000;
  LOBYTE(v217) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"SQL",
          L"NonCtrTxLogSizeThresholdInMB",
          XdbServerGlobals + 24668,
          v217,
          0) )
    *(_DWORD *)(XdbServerGlobals + 24668) = 1000;
  LOBYTE(v218) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"SQL",
          L"PvsForceUpdateLowWatermarkThresholdInMB",
          XdbServerGlobals + 24840,
          v218,
          0) )
    *(_DWORD *)(XdbServerGlobals + 24840) = 102400;
  LOBYTE(v219) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"SQL",
          L"XdesHistoryHashTableBucketCount",
          XdbServerGlobals + 28340,
          v219,
          0) )
    *(_DWORD *)(XdbServerGlobals + 28340) = 3079;
  LOBYTE(v220) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"SQL",
          L"MTVCPfsPageSwitchThreshold",
          XdbServerGlobals + 29016,
          v220,
          0) )
    *(_DWORD *)(XdbServerGlobals + 29016) = 2;
  LOBYTE(v221) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"SQL",
          L"UserTxPageCleanupCapPerGoDormantCall",
          XdbServerGlobals + 24228,
          v221,
          0) )
    *(_DWORD *)(XdbServerGlobals + 24228) = 100;
  LOBYTE(v222) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"SQL",
          L"CleanupUnderUserXactHobtHashTableMaxPageCount",
          XdbServerGlobals + 24232,
          v222,
          0) )
    *(_DWORD *)(XdbServerGlobals + 24232) = 100000;
  LOBYTE(v223) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"SQL",
          L"CleanupUnderUserXactPageIdHashSetSize",
          XdbServerGlobals + 24236,
          v223,
          0) )
    *(_DWORD *)(XdbServerGlobals + 24236) = 0x2000;
  LOBYTE(v224) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"SQL",
          L"LockEscalationThreshold",
          XdbServerGlobals + 24240,
          v224,
          0) )
    *(_DWORD *)(XdbServerGlobals + 24240) = 5000;
  LOBYTE(v225) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"SQL",
          L"ReclaimSpaceInHoBtBatchSize",
          XdbServerGlobals + 24220,
          v225,
          0) )
    *(_DWORD *)(XdbServerGlobals + 24220) = 0;
  LOBYTE(v226) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"SQL",
          L"PrefetchRowCountThreshold",
          XdbServerGlobals + 24224,
          v226,
          0) )
    *(_DWORD *)(XdbServerGlobals + 24224) = 25;
  LOBYTE(v227) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"SQL",
          L"EmptyPageRemovalRetryCount",
          XdbServerGlobals + 29020,
          v227,
          0) )
    *(_DWORD *)(XdbServerGlobals + 29020) = 32;
  if ( *(_BYTE *)(CFeatureSwitchesMin::GetCurrentInstance() + 418) )
    CreateDefaultFeatureWorkloadEntryInXdbServerGlobals();
  IServerConfiguration::GetDynamicInt64Setting(
    s_pServerConf,
    L"SQL",
    L"MinLogFileSizeForShrinkLogInBytes",
    (__int64 *)(XdbServerGlobals + 19200),
    1,
    0);
  IServerConfiguration::GetDynamicDoubleSetting(
    s_pServerConf,
    L"SQL",
    L"MinFreeSpaceThresholdForShrinkLog",
    (double *)(XdbServerGlobals + 19208),
    1,
    0);
  IServerConfiguration::GetDynamicDoubleSetting(
    s_pServerConf,
    L"SQL",
    L"ShrinkLogTargetSizeMultiplier",
    (double *)(XdbServerGlobals + 19216),
    1,
    0);
  IServerConfiguration::GetDynamicInt64Setting(
    s_pServerConf,
    L"SQL",
    L"MaxLogRateForAutoShrinkLogGroup",
    (__int64 *)(XdbServerGlobals + 19224),
    1,
    0);
  IServerConfiguration::GetDynamicInt64Setting(
    s_pServerConf,
    L"SQL",
    L"PoolMaxLogRateForAutoShrinkLogGroup",
    (__int64 *)(XdbServerGlobals + 19232),
    1,
    0);
  LOBYTE(v228) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"SQL",
          L"SuggestedMinDbCountShrinkAdjustingForElasticPools",
          XdbServerGlobals + 19240,
          v228,
          0) )
    *(_DWORD *)(XdbServerGlobals + 19240) = 0;
  if ( !IServerConfiguration::GetDynamicDoubleSetting(
          s_pServerConf,
          L"SQL",
          L"SuggestedMaxMinutesTopLogGenerationForShrink",
          (double *)(XdbServerGlobals + 19248),
          1,
          0) )
    *(_QWORD *)(XdbServerGlobals + 19248) = 0x404E000000000000LL;
  if ( !IServerConfiguration::GetDynamicDoubleSetting(
          s_pServerConf,
          L"SQL",
          L"SuggestedMinMinutesTopLogGenerationForShrink",
          (double *)(XdbServerGlobals + 19256),
          1,
          0) )
    *(_QWORD *)(XdbServerGlobals + 19256) = 0x4014000000000000LL;
  if ( !IServerConfiguration::GetDynamicDoubleSetting(
          s_pServerConf,
          L"SQL",
          L"XstoreMaxShrinkFactorOfMinLogFileSizeForShrink",
          (double *)(XdbServerGlobals + 19264),
          1,
          0) )
    *(_QWORD *)(XdbServerGlobals + 19264) = 0x3FB999999999999ALL;
  if ( !IServerConfiguration::GetDynamicDoubleSetting(
          s_pServerConf,
          L"SQL",
          L"XioMaxShrinkFactorOfMinLogFileSizeForShrink",
          (double *)(XdbServerGlobals + 19272),
          1,
          0) )
    *(_QWORD *)(XdbServerGlobals + 19272) = 0x3FF0000000000000LL;
  if ( !IServerConfiguration::GetDynamicDoubleSetting(
          s_pServerConf,
          L"SQL",
          L"PfsMaxShrinkFactorOfMinLogFileSizeForShrink",
          (double *)(XdbServerGlobals + 19280),
          1,
          0) )
    *(_QWORD *)(XdbServerGlobals + 19280) = 0x3FE0000000000000LL;
  if ( !IServerConfiguration::GetDynamicDoubleSetting(
          s_pServerConf,
          L"SQL",
          L"SsdMaxShrinkFactorOfMinLogFileSizeForShrink",
          (double *)(XdbServerGlobals + 19288),
          1,
          0) )
    *(_QWORD *)(XdbServerGlobals + 19288) = 0x3FE0000000000000LL;
  IServerConfiguration::GetDynamicInt64Setting(
    s_pServerConf,
    L"SQL",
    L"MinLogFileSizeForShrinkLogInBytesWithForwarder",
    (__int64 *)(XdbServerGlobals + 19296),
    1,
    0);
  IServerConfiguration::GetDynamicDoubleSetting(
    s_pServerConf,
    L"SQL",
    L"MinFreeSpaceThresholdForShrinkLogWithForwarder",
    (double *)(XdbServerGlobals + 19304),
    1,
    0);
  IServerConfiguration::GetDynamicDoubleSetting(
    s_pServerConf,
    L"SQL",
    L"ShrinkLogTargetSizeMultiplierWithForwarder",
    (double *)(XdbServerGlobals + 19312),
    1,
    0);
  if ( !IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
          s_pServerConf,
          L"SQL",
          L"CDCLogConsumptionThresholdThrottlingPct",
          lambda_bac07c3abf63f930c6eddb335d9227cb_::_lambda_invoker_cdecl_,
          0,
          0) )
    *(_DWORD *)(GetXdbServerGlobals(v5, v4) + 19320) = 50;
  if ( !IServerConfiguration::SubscribeAndGetDynamicDoubleSetting(
          s_pServerConf,
          L"SQL",
          L"CDCLogThrottlingOverridePct",
          lambda_43a0c4a2653f0da49b840111c6081d6c_::_lambda_invoker_cdecl_,
          0,
          0) )
    *(_QWORD *)(GetXdbServerGlobals(v7, v6) + 19328) = 0;
  if ( !IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
          s_pServerConf,
          L"SQL",
          L"CDCLogThrottlingRecalcTime",
          lambda_30696cef0c3bc99ad1ea71bf2fcdcc56_::_lambda_invoker_cdecl_,
          0,
          0) )
    *(_DWORD *)(GetXdbServerGlobals(v9, v8) + 19336) = 15;
  LOBYTE(v229) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"SQL",
          L"ReplTxLogSizeThresholdInMB",
          XdbServerGlobals + 19340,
          v229,
          0) )
    *(_DWORD *)(XdbServerGlobals + 19340) = 16000;
  LOBYTE(v230) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"SynapseLinkSasExpirationThresholdInMin",
    XdbServerGlobals + 19344,
    v230,
    0);
  LOBYTE(v231) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"SynapseLinkOutputStreamMaxBufferSize",
    XdbServerGlobals + 19348,
    v231,
    0);
  LOBYTE(v232) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"BufferSpacePercent",
    XdbServerGlobals + 19352,
    v232,
    0);
  LOBYTE(v233) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"NumOfDataFilesAtCreationTime",
    XdbServerGlobals + 19356,
    v233,
    0);
  IServerConfiguration::GetDynamicInt64Setting(
    s_pServerConf,
    L"SQL",
    L"AllocateMoreFileSpaceThresholdGb",
    (__int64 *)(XdbServerGlobals + 19360),
    1,
    0);
  IServerConfiguration::GetDynamicInt64Setting(
    s_pServerConf,
    L"SQL",
    L"MaxFileSizeIncrementGb",
    (__int64 *)(XdbServerGlobals + 19368),
    1,
    0);
  IServerConfiguration::GetDynamicInt64Setting(
    s_pServerConf,
    L"SQL",
    L"MaxFileSizeSupportedGb",
    (__int64 *)(XdbServerGlobals + 19376),
    1,
    0);
  LOBYTE(v234) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"GracePeriodForAddFileInMinutes",
    XdbServerGlobals + 19616,
    v234,
    0);
  IServerConfiguration::GetDynamicInt64Setting(
    s_pServerConf,
    L"SQL",
    L"MinFreeDBSpaceMBToAllowAddFiles",
    (__int64 *)(XdbServerGlobals + 19384),
    1,
    0);
  LOBYTE(v235) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"TemporalSystemVersioningSettings",
    L"TemporalSystemVersioningTimeBetweenTasks",
    XdbServerGlobals + 16312,
    v235,
    0);
  IServerConfiguration::GetDynamicDoubleSetting(
    s_pServerConf,
    L"TemporalSystemVersioningSettings",
    L"TemporalSystemVersioningFlushTaskMemoryCountRatio",
    (double *)(XdbServerGlobals + 16320),
    1,
    0);
  LOBYTE(v236) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"TemporalSystemVersioningSettings",
    L"TemporalSystemVersioningFlushTaskPeriod",
    XdbServerGlobals + 16328,
    v236,
    0);
  LOBYTE(v237) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"TemporalSystemVersioningSettings",
    L"TemporalSystemVersioningFlushTaskShortPeriod",
    XdbServerGlobals + 16332,
    v237,
    0);
  LOBYTE(v238) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"TemporalSystemVersioningSettings",
    L"TemporalSystemVersioningFlushTaskDiscoveryPeriod",
    XdbServerGlobals + 16336,
    v238,
    0);
  LOBYTE(v239) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"TemporalSystemVersioningSettings",
    L"TemporalSystemVersioningFlushTaskCheckCleanupMinPeriod",
    XdbServerGlobals + 16340,
    v239,
    0);
  LOBYTE(v240) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"TemporalSystemVersioningSettings",
    L"TemporalSystemVersioningFlushTaskMaxDop",
    XdbServerGlobals + 16344,
    v240,
    0);
  LOBYTE(v241) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"TemporalSystemVersioningSettings",
    L"TemporalSystemVersioningFlushTaskChunkSize",
    XdbServerGlobals + 16348,
    v241,
    0);
  LOBYTE(v242) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"TemporalSystemVersioningSettings",
    L"TemporalSystemVersioningRetentionTaskPeriod",
    XdbServerGlobals + 16352,
    v242,
    0);
  LOBYTE(v243) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"TemporalSystemVersioningSettings",
    L"TemporalSystemVersioningRetentionTaskShortPeriod",
    XdbServerGlobals + 16356,
    v243,
    0);
  LOBYTE(v244) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"TemporalSystemVersioningSettings",
    L"TemporalSystemVersioningRetentionTaskDiscoveryPeriod",
    XdbServerGlobals + 16360,
    v244,
    0);
  LOBYTE(v245) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"TemporalSystemVersioningSettings",
    L"TemporalSystemVersioningRetentionTaskCheckCleanupMinPeriod",
    XdbServerGlobals + 16364,
    v245,
    0);
  LOBYTE(v246) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"TemporalSystemVersioningSettings",
    L"TemporalSystemVersioningRetentionTaskMaxDop",
    XdbServerGlobals + 16368,
    v246,
    0);
  LOBYTE(v247) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"TemporalSystemVersioningSettings",
    L"TemporalSystemVersioningRetentionTaskChunkSize",
    XdbServerGlobals + 16372,
    v247,
    0);
  LOBYTE(v248) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"TemporalSystemVersioningSettings",
    L"TemporalSystemVersioningCciRetentionTaskPeriod",
    XdbServerGlobals + 16376,
    v248,
    0);
  LOBYTE(v249) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"TemporalSystemVersioningSettings",
    L"TemporalSystemVersioningCciRetentionTaskShortPeriod",
    XdbServerGlobals + 16380,
    v249,
    0);
  LOBYTE(v250) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"TemporalSystemVersioningSettings",
    L"TemporalSystemVersioningCciRetentionTaskDiscoveryPeriod",
    XdbServerGlobals + 0x4000,
    v250,
    0);
  LOBYTE(v251) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"TemporalSystemVersioningSettings",
    L"TemporalSystemVersioningCciRetentionTaskCheckCleanupMinPeriod",
    XdbServerGlobals + 16388,
    v251,
    0);
  LOBYTE(v252) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"TemporalSystemVersioningSettings",
    L"TemporalSystemVersioningCciRetentionTaskMaxDop",
    XdbServerGlobals + 16392,
    v252,
    0);
  LOBYTE(v253) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"TupleMoverSettings",
    L"MinRowCountForAggressiveCompression",
    XdbServerGlobals + 16396,
    v253,
    0);
  LOBYTE(v254) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"TupleMoverSettings",
    L"MaxRowCountForAggressiveCompression",
    XdbServerGlobals + 16400,
    v254,
    0);
  LOBYTE(v255) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"TupleMoverSettings",
    L"MinTimeInSecondsForAggressiveCompression",
    XdbServerGlobals + 16404,
    v255,
    0);
  LOBYTE(v256) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"TupleMoverSettings",
    L"IterationThresholdForAggressiveCompression",
    XdbServerGlobals + 16408,
    v256,
    0);
  LOBYTE(v257) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"OpportunisticFailover",
    L"StatsEmitInterval",
    XdbServerGlobals + 16412,
    v257,
    0);
  LOBYTE(v258) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"OpportunisticFailover",
    L"WindowSecondsForStats",
    XdbServerGlobals + 16416,
    v258,
    0);
  LOBYTE(v259) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"OpportunisticFailover",
    L"LowActivityThreshold",
    XdbServerGlobals + 16420,
    v259,
    0);
  LOBYTE(v260) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"RgSettings",
    L"RecoveryIntervalMs",
    XdbServerGlobals + 19176,
    v260,
    0);
  LOBYTE(v261) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"RgSettings",
    L"CheckpointRateMBps",
    XdbServerGlobals + 19180,
    v261,
    0);
  LOBYTE(v262) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"RgSettings",
    L"CheckpointRateIO",
    XdbServerGlobals + 19184,
    v262,
    0);
  LOBYTE(v263) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"RgSettings",
    L"DefaultTempdbDbMaxSizeinMB",
    XdbServerGlobals + 16580,
    v263,
    0);
  LOBYTE(v264) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"RgSettings",
    L"MaxTempdbDbMaxSizeinMB",
    XdbServerGlobals + 16584,
    v264,
    0);
  LOBYTE(v265) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"RgSettings",
    L"InitialTempdbDbFileSizeinMB",
    XdbServerGlobals + 16588,
    v265,
    0);
  LOBYTE(v266) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"RgSettings",
    L"TempDbFileGrowthinMB",
    XdbServerGlobals + 16592,
    v266,
    0);
  LOBYTE(v267) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"RgSettings",
    L"TempDbInitialLogFileSizeinMB",
    XdbServerGlobals + 16596,
    v267,
    0);
  LOBYTE(v268) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"RgSettings",
    L"TempDbLogFileMaxSizeinMB",
    XdbServerGlobals + 16600,
    v268,
    0);
  LOBYTE(v269) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"RgSettings",
    L"TempDbLogFileGrowthinMB",
    XdbServerGlobals + 16604,
    v269,
    0);
  LOBYTE(v270) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"RgSettings",
    L"ExternalFileDiskCacheCapacityMB",
    XdbServerGlobals + 16628,
    v270,
    0);
  LOBYTE(v271) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"RgSettings",
    L"ExternalFileMemoryCacheCapacityMB",
    XdbServerGlobals + 16632,
    v271,
    0);
  LOBYTE(v272) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"RgSettings",
    L"DeflationXEventEmissionIntervalMin",
    XdbServerGlobals + 17128,
    v272,
    0);
  LOBYTE(v273) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"RgSettings",
    L"DeflationFabricPutIntervalMin",
    XdbServerGlobals + 17132,
    v273,
    0);
  LOBYTE(v274) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"RgSettings",
    L"DeflationThresholdDampenerPercent",
    XdbServerGlobals + 17136,
    v274,
    0);
  LOBYTE(v275) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"RgSettings",
    L"DeflationThresholdIntervalHr",
    XdbServerGlobals + 17120,
    v275,
    0);
  LOBYTE(v276) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"RgSettings",
    L"DeflationThresholdMaxDBSizeMB",
    XdbServerGlobals + 17140,
    v276,
    0);
  v10 = *(_QWORD *)s_pServerConf;
  Pmo = SOS_Task::GetPmo();
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, struct IMemObj *, __int64, _QWORD))(v10 + 528))(
    s_pServerConf,
    L"RgSettings",
    L"DeflationSettingsFabricURI",
    Pmo,
    XdbServerGlobals + 20760,
    0);
  LOBYTE(v277) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"RgSettings",
    L"DeflationNoopCyclesTestOverride",
    XdbServerGlobals + 17116,
    v277,
    0);
  LOBYTE(v278) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"RgSettings",
    L"DeflationThresholdIntervalMinutesTestOverride",
    XdbServerGlobals + 17124,
    v278,
    0);
  v12 = *(_QWORD *)s_pServerConf;
  v13 = SOS_Node::GetPmo();
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, struct IMemObj *, __int64, _QWORD))(v12 + 528))(
    s_pServerConf,
    L"MonitoringSqlMDSAgent",
    L"AzureDBShoeboxMetricsAccount",
    v13,
    XdbServerGlobals + 4160,
    0);
  v14 = *(_QWORD *)s_pServerConf;
  v15 = SOS_Node::GetPmo();
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, struct IMemObj *, __int64, _QWORD))(v14 + 528))(
    s_pServerConf,
    L"MonitoringSqlMDSAgent",
    L"AzureDBMetricsAccount",
    v15,
    XdbServerGlobals + 4168,
    0);
  if ( XDB_GetIsPaaSV2(&v563) || !v563 )
  {
    v17 = *(_QWORD *)s_pServerConf;
    v18 = SOS_Node::GetPmo();
    if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, struct IMemObj *, __int64, _QWORD))(v17 + 528))(
            s_pServerConf,
            L"SQL",
            L"NodeLogsRootSQL",
            v18,
            XdbServerGlobals + 24640,
            0) )
      *(_QWORD *)(XdbServerGlobals + 24640) = 0;
  }
  else
  {
    v16 = SOS_Node::GetPmo();
    *(_QWORD *)(XdbServerGlobals + 24640) = operator new[](0x208u, v16, "sql\\ntdbms\\ksource\\dbfabric.cpp", 4409, 6u);
    if ( (unsigned int)GetNodeLogsRootPathForPaaSv2(s_pServerConf, (wchar_t **)(XdbServerGlobals + 24640), 0x104u) )
      *(_QWORD *)(XdbServerGlobals + 24640) = 0;
  }
  if ( !IServerConfiguration::GetDynamicBoolSetting(
          s_pServerConf,
          L"GlobalSharedMA",
          L"IsEnabled",
          (bool *)(XdbServerGlobals + 24648),
          1,
          0) )
    *(_BYTE *)(XdbServerGlobals + 24648) = 0;
  if ( *(_BYTE *)(CFeatureSwitchesMin::GetCurrentInstance() + 75) )
  {
    LOBYTE(v279) = 1;
    (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
      s_pServerConf,
      L"RgSettings",
      L"TempDbRemoteFileMaxSizeInMB",
      XdbServerGlobals + 16616,
      v279,
      0);
    LOBYTE(v280) = 1;
    (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
      s_pServerConf,
      L"RgSettings",
      L"InitialTempDbRemoteFileSizeinMB",
      XdbServerGlobals + 16620,
      v280,
      0);
    LOBYTE(v281) = 1;
    (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
      s_pServerConf,
      L"RgSettings",
      L"TempDbRemoteFileGrowthinMB",
      XdbServerGlobals + 16624,
      v281,
      0);
  }
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"DefaultDBInactiveDurationThresholdInMinForTimers",
    lambda_b45dc00426de0c3a6a9ce39c365095a5_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::GetDynamicBoolSetting(
    s_pServerConf,
    L"RgSettings",
    L"EnableWorkloadGroupsDMV",
    (bool *)(XdbServerGlobals + 11972),
    1,
    0);
  IServerConfiguration::GetDynamicBoolSetting(
    s_pServerConf,
    L"RgSettings",
    L"EnableResourcePoolsDMV",
    (bool *)(XdbServerGlobals + 11973),
    1,
    0);
  IServerConfiguration::GetDynamicBoolSetting(
    s_pServerConf,
    L"RgSettings",
    L"IgnoreVolumeRgStatsInV2",
    (bool *)(XdbServerGlobals + 17112),
    1,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"IOQueueLimitWaitSleepTime",
    lambda_958f611a90c0b43047abd05cd2977327_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"MaxReadAheadSize",
    lambda_9bb105caeb2500a97b455ca618660463_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"MinReadAheadQueueDepth",
    lambda_aed3c9a6a635989c3e5800348bc0256b_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"MaxReadAheadQueueDepth",
    lambda_e564535fdb1a92948e4a7d84a553b24e_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"MaxReadAheadSizeColumnStore",
    lambda_7aae84a671e9eba9316ca6e8ac19dcfd_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicStringSetting(
    s_pServerConf,
    L"RgSettings",
    L"PremiumRemoteStorageIdentifier",
    lambda_b4a19cc85c67b529e68523d888ffa175_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicStringSetting(
    s_pServerConf,
    L"RgSettings",
    L"PremiumFileShareStorageIdentifier",
    lambda_e56e732f137b6d0cdaa5b6454d1ae052_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicStringSetting(
    s_pServerConf,
    L"RgSettings",
    L"PremiumFileShareZoneRedundantStorageIdentifier",
    lambda_5cea5cd096ad41f6340a54ede35f81e5_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicStringSetting(
    s_pServerConf,
    L"RgSettings",
    L"AzureManagedDiskStorageIdentifier",
    lambda_f73e1d646cb99f93f85dd2b1011b1e0a_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicStringSetting(
    s_pServerConf,
    L"RgSettings",
    L"EnableBPEInSlos",
    lambda_8e64e3eab9e7f8dd2252362e59445caf_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicStringSetting(
    s_pServerConf,
    L"RgSettings",
    L"EnableBPEOnStorageAccountTypes",
    lambda_af700f075cdf294465a4058dee1e96a0_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"L2BPoolMaxPendingIos",
    lambda_803ed2435ffa4df73c269a906de113a6_::_lambda_invoker_cdecl_,
    0,
    0);
  if ( !IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
          s_pServerConf,
          L"RgSettings",
          L"BillableIOSizeBytes",
          lambda_058795bbb955b3e2879d5d9e9fef5f0a_::_lambda_invoker_cdecl_,
          0,
          0) )
    *(_DWORD *)(GetXdbServerGlobals(v20, v19) + 17064) = 0x2000;
  if ( !IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
          s_pServerConf,
          L"Ihs",
          L"IHSMetricsCollectionIntervalMins",
          lambda_e9606bc9bd35566ebe88b7afba25d145_::_lambda_invoker_cdecl_,
          0,
          0) )
    *(_DWORD *)(GetXdbServerGlobals(v22, v21) + 22920) = 15;
  if ( !IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
          s_pServerConf,
          L"Ihs",
          L"IHSAnalyticsIntervalMinutes",
          lambda_7bbd8b37cffbf3cc63e498fcd72bf838_::_lambda_invoker_cdecl_,
          0,
          0) )
    *(_DWORD *)(GetXdbServerGlobals(v24, v23) + 22924) = 720;
  if ( !IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
          s_pServerConf,
          L"Ihs",
          L"IHSFileRetentionCheckIntervalHours",
          lambda_bd7479cbb01065edd7be11df1edad604_::_lambda_invoker_cdecl_,
          0,
          0) )
    *(_DWORD *)(GetXdbServerGlobals(v26, v25) + 22928) = 24;
  if ( !IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
          s_pServerConf,
          L"Ihs",
          L"IHSFileRetentionDays",
          lambda_64eec7c0c5d6250ff26c8f67674244e1_::_lambda_invoker_cdecl_,
          0,
          0) )
    *(_DWORD *)(GetXdbServerGlobals(v28, v27) + 22932) = 90;
  if ( !IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
          s_pServerConf,
          L"Ihs",
          L"IHSTempdbSpaceUsageAnalyticsPercentile",
          lambda_a2116ac88ff5915d1a6684c2d52f347b_::_lambda_invoker_cdecl_,
          0,
          0) )
    *(_DWORD *)(GetXdbServerGlobals(v30, v29) + 22936) = 50;
  if ( !IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
          s_pServerConf,
          L"RecoveryHelp",
          L"RecoveryHelpTriggers",
          lambda_0388363363aef809fa9879b473dc60d7_::_lambda_invoker_cdecl_,
          0,
          0) )
    *(_DWORD *)(GetXdbServerGlobals(v32, v31) + 20508) = 0;
  if ( !IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
          s_pServerConf,
          L"RecoveryHelp",
          L"EstimatedRecoveryReads",
          lambda_6cf147184d4832c04e945a22602da2e8_::_lambda_invoker_cdecl_,
          0,
          0) )
  {
    *(_DWORD *)(GetXdbServerGlobals(v34, v33) + 20504) = 0x7FFFFFFF;
    *(_DWORD *)(GetXdbServerGlobals(v36, v35) + 20508) = 0;
  }
  if ( !IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
          s_pServerConf,
          L"RecoveryHelp",
          L"DirtyPageDelayInMillis",
          lambda_29f9a52b27c81daf8ffb1e37914b1b2a_::_lambda_invoker_cdecl_,
          0,
          0) )
    *(_DWORD *)(GetXdbServerGlobals(v38, v37) + 20500) = 1;
  if ( !IServerConfiguration::SubscribeAndGetDynamicInt64Setting(
          s_pServerConf,
          L"OptimizedSpaceCalculation",
          L"SpaceCountersAutoResetMinFileSizeInMB",
          lambda_c7475dad8e996ffb8c96039171011025_::_lambda_invoker_cdecl_,
          0,
          0) )
    *(_QWORD *)(GetXdbServerGlobals(v40, v39) + 24872) = 81920;
  if ( !IServerConfiguration::SubscribeAndGetDynamicInt64Setting(
          s_pServerConf,
          L"OptimizedSpaceCalculation",
          L"SpaceCountersAutoResetMaxFileGrowthInMB",
          lambda_2bf75d22e57a0c264b084916656c4940_::_lambda_invoker_cdecl_,
          0,
          0) )
    *(_QWORD *)(GetXdbServerGlobals(v42, v41) + 24880) = 0x2000;
  if ( !IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
          s_pServerConf,
          L"OptimizedSpaceCalculation",
          L"SpaceUsageAutoResetIntervalSec",
          lambda_b4dbee34513f4228241746df6d6c3044_::_lambda_invoker_cdecl_,
          0,
          0) )
    *(_DWORD *)(GetXdbServerGlobals(v44, v43) + 24888) = 3600;
  if ( !IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
          s_pServerConf,
          L"OptimizedSpaceCalculation",
          L"SpaceUsageWriteStatEventIntervalMilliSec",
          lambda_f451cb0e4edc60193f240a68a3d1db0b_::_lambda_invoker_cdecl_,
          0,
          0) )
    *(_DWORD *)(GetXdbServerGlobals(v46, v45) + 24892) = 900000;
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"NativeShuffleSettings",
    L"NativeShuffleAsyncReadBufferCount",
    lambda_78274afa1198be897202579e1dd7c7b3_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"NativeShuffleSettings",
    L"NativeShuffleMaxAsyncWriteBufferCount",
    lambda_e24ab680849b4babf26a0855fb69cb24_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"NativeShuffleSettings",
    L"NativeShuffleMinAsyncWriteBufferCount",
    lambda_b96c410d540651fbf7aedc1662b67c4d_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"NativeShuffleSettings",
    L"NativeShuffleLocalSBSRetryCount",
    lambda_827670e49fed8c66f451db89ed4880cb_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"NativeShuffleSettings",
    L"NativeShuffleRemoteSBSRetryCount",
    lambda_8b54fcca819cd5c561f2b30ae1a364c9_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicBoolSetting(
    s_pServerConf,
    L"NativeShuffleSettings",
    L"NativeShuffleDynamicBufferSettings",
    lambda_37e1a0f46c330b37653efb919a9c807b_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"NativeShuffleSettings",
    L"NativeShuffleMaxThreadsPerBufferSet",
    lambda_deeb74ac5c6e932d420f2ec096b2e4a1_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"FidoToad",
    L"ToadBackgroundDiscoveryFrequencySeconds",
    lambda_6e2ac0c6827761bb58965863fcc0671d_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"FidoToad",
    L"ToadBackgroundActionWaitTimeoutMilliseconds",
    lambda_258561e5fe4e00412ff83d12c875d080_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"FidoToad",
    L"ToadBackgroundMaxNumberOfActionsToSchedule",
    lambda_fd47f212beb951a854903f1343a5df5d_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"FidoToad",
    L"ToadBackgroundMaxNumberOfZonesToAnalyze",
    lambda_5f2f5a7ff3250b9d746534a24de7da90_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"FidoToad",
    L"ToadOnDemandActionWaitTimeoutMilliseconds",
    lambda_1752f7f3a0678a32baa7d6a2619f95fd_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"FidoToad",
    L"ToadOnDemandMaxNumberOfActionsToSchedule",
    lambda_2a04e3741bcd8cddcabe1d1046b38b9f_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"FidoToad",
    L"ToadOnDemandMaxNumberOfZonesToAnalyze",
    lambda_8b77289c4e17e932e772306631c921b0_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"FidoToad",
    L"ToadMinRowCountForCompression",
    lambda_5dde880bbb279b65b1a2a61c89bd9c2e_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"FidoToad",
    L"ToadMaxRowGroupsToBucketize",
    lambda_41dcb1c5342b862de87761b0bae9d6a2_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"FidoToad",
    L"ToadMaxRowGroupsToMerge",
    lambda_054cff5a50e278108ff615b71c0a8651_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"FidoToad",
    L"ToadMemoryGrantMBPerWorkItem",
    lambda_f43dc5c8cd7b27c1044c49d4e2655a39_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"FidoToad",
    L"ToadMinStaleDeletesToRewrite",
    lambda_b1d14a240b4137b17b2f647fec0a1a64_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"FidoToad",
    L"ToadMinUncompressedDeletesToMerge",
    lambda_2dc605416320dd3358f0520a42c30e12_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicDoubleSetting(
    s_pServerConf,
    L"FidoToad",
    L"ToadRowRatioForAbortingCompression",
    lambda_fa923325fef8fe81e2e8ba3a8dd3a8da_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"FidoStats",
    L"DwFidoAutoStatsTimeoutInMilliseconds",
    lambda_0f3ac536ff97a205ed70b74db60fe679_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"LocalVolumeMaxOutstandingIo",
    lambda_03f04826bd4a8168feaa8f9cd8a40566_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"XStoreVolumeMaxOutstandingIo",
    lambda_00e241c68159d7eb3a3aeb05402d071c_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"XStorePremiumVolumeMaxOutstandingIo",
    lambda_4fdd31700037674bde265acae963039b_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"XStoreManagedVolumeMaxOutstandingIo",
    lambda_0bccb44816382444684ae181d87932af_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"XStoreExternalVolumeMaxOutstandingIo",
    lambda_1d3e81b4e4960d3b6ad383317dccada9_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"MaxXStoreIOPS",
    lambda_4e45512c85bca6012150d818b4f8c7ca_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"MaxXStoreSuggestedLogWriteKBps",
    lambda_9471661a7e999a75e71901d13c19b48d_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"MaxXStoreBandwidthKBps",
    lambda_1512f99e4b9dc59a4e9bd5bd0ce2acce_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"DwPestoBlobXStoreMaxOutStandingIo",
    lambda_2d11b4cf475f4d68ea7837d7936228f6_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"MaxDwPestoBlobXStoreIOPS",
    lambda_ab47dfcd7dfbbaa31faca8b2acd46a02_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"MaxDwPestoBlobXStoreBandwidthKBps",
    lambda_73cbe4d3833822991e77e7351dd3c37a_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"DwPestoBlobXStoreReadIOSizeBytes",
    lambda_e75bb7ddd5cee58d3c8d6dde05bc4372_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"DwPestoBlobXStoreWriteIOSizeBytes",
    lambda_432402b5f05d6f504b2270edd232d1eb_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"XioIORequestSizeBytes",
    lambda_5a49fac6db75fcafd118ac7004d22d75_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicStringSetting(
    s_pServerConf,
    L"RgSettings",
    L"RgSelectedReportingMetricsWithFrq",
    lambda_a5a7c60ccc50a3fd8e2ea853ce760def_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"LocalVolumeIORequestSizeBytes",
    lambda_748d74119599a4ff415a02bcbbae5090_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt64Setting(
    s_pServerConf,
    L"RgSettings",
    L"QuerySpaceToReserveWinfabPropertyPeriodInSec",
    lambda_84d43b54760fc81a58885b210f7cbf8f_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"IDSUExpiryTimeFactorSecPerGB",
    lambda_85ae604cd17b1ea201868ead4bfcbcf9_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"MaxIDSUExpiryPeriodHours",
    lambda_469065e9e165a6efe7e0ddf0ee033cde_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"ReuseSloTimeoutMinutes",
    lambda_11bc3e3276923b4c23ffeee7ccf146b7_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"MaxQPPrefetchQueueSize",
    lambda_670bd7fe2778de8922f3dccf571d2015_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"MemoryClerkStatsUpdatePeriodSeconds",
    lambda_7a3eac54af28766c1a58c00c4afceac2_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"MemoryClerkStatsDumpPeriodSeconds",
    lambda_9d0f0a5e773d652df285c1d0ff250654_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"MemoryClerkStatsDumpThresholdKb",
    lambda_f3121ddee41359d28d4da1b737111e01_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"MemoryClerkStatsDumpThresholdVmCommittedKb",
    lambda_360552c9e38c66f7afcb78baeaf97009_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicStringSetting(
    s_pServerConf,
    L"RgSettings",
    L"DefaultDumpMemoryClerkTypes",
    lambda_e945c5b2f8b042cd47bbec444d76744e_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"MultiInstanceMemRgStatsTimeoutMinutes",
    lambda_b912007995761f8410f94b95d505d454_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"Use2StatsTimeoutMinutes",
    lambda_563b303ce8e019aee504d0a22590bb79_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"CollectCacheHashTableStatsPeriodMinutes",
    lambda_33814b1056b787f903c76d7c6d066010_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"CostModelCollectionBufferPoolThresholdPages",
    lambda_6d51734a498ebb06afd4b27893b9c293_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"CostModellCollectionFreePageThresholdPages",
    lambda_9ff87f8e821d3227d64ac2d4899bacd3_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"CollectStoreCacheHistogramPeriodMinutes",
    lambda_37dc93e425604492eac6e49c1524d2e3_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"CollectCacheActivenessStatsPeriodMinutes",
    lambda_6afdc0fe07705b531c4c782f24e1e22f_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicStringSetting(
    s_pServerConf,
    L"RgSettings",
    L"StoreCacheStatsCollectionDefaultTypes",
    lambda_ff455c51df40e5bc5c6c55125ee1cc91_::_lambda_invoker_cdecl_,
    0,
    0);
  v47 = IsElasticPool();
  v48 = L"ServerlessActiveCacheThresholdMinutes";
  if ( v47 )
    v48 = L"ServerlessActiveCacheThresholdMinutesForEP";
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    v48,
    lambda_514f96f0bb334bc1c499de4e9e0b03c6_::_lambda_invoker_cdecl_,
    0,
    0);
  v49 = L"ServerlessCacheReclaimThresholdForCacheUsedPercent";
  if ( v47 )
    v49 = L"ServerlessCacheReclaimThresholdForCacheUsedPercentForEP";
  IServerConfiguration::SubscribeAndGetDynamicDoubleSetting(
    s_pServerConf,
    L"RgSettings",
    v49,
    lambda_52d481f779dfae73bd29c67fe0acd41d_::_lambda_invoker_cdecl_,
    0,
    0);
  if ( v47 )
    IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
      s_pServerConf,
      L"RgSettings",
      L"ServerlessCacheReclaimIntervalForCacheUsedMinutesForEP",
      lambda_08a09ea724517f4196e88a056bb7acae_::_lambda_invoker_cdecl_,
      0,
      0);
  IServerConfiguration::SubscribeAndGetDynamicDoubleSetting(
    s_pServerConf,
    L"RgSettings",
    L"ServerlessCacheReclaimThresholdForCpuUsedPercent",
    lambda_cc1477cb9e20673800a9f0c1e73db0fc_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicDoubleSetting(
    s_pServerConf,
    L"RgSettings",
    L"ServerlessCacheReclaimObjectStoresPercent",
    lambda_89d048c0377bf805af7408cc6490fdea_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"ServerlessCheckFlushCachesTimePeriodMinutes",
    lambda_e95d7984cb1f68e9b9c81519765676de_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"ServerlessFlushCachesCpuIdlenssThresholdMinutes",
    lambda_530203e5152f01e0e987441671899021_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"ServerlessFlushCachesResetTargetTimeoutSeconds",
    lambda_a65f512cba03e085a986ff619fdbffe7_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicDoubleSetting(
    s_pServerConf,
    L"RgSettings",
    L"ServerlessMemStepDownPercent",
    lambda_03e8ba7b89e4f1a0098a7a597d7b2117_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"ServerlessMemStepDownSizeExtraBufPercent",
    lambda_6b8ccb868fc8d39125b72313ca62cc82_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"ServerlessMemPerVcoreFactorMB",
    lambda_558c1359dae96a27fdd97b7943744554_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"ServerlessMinMemoryMB",
    lambda_acfd7eaac267e33ca05666a6549ae117_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"ServerlessMinMemoryReclaimOffsetMB",
    lambda_a45936c55a11c12c2f0d44586d8279c0_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"ServerlessRbpexMinMemoryReclaimOffsetPerVCoreMB",
    lambda_ef7bdbc379cd21a670393253a35997fd_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"ServerlessMemShrinkPolicy",
    lambda_76fd6c616df71bbc1f624b8f0f738805_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"ServerlessTimeoutToResetInternalCacheTargetSec",
    lambda_bc869b68303cc1ba0df396cbf44b3ef1_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"ServerlessTimeoutToResetExternalCacheTargetSec",
    lambda_57461e2fdb9df52574a80392f01dac58_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"ServerlessDirectShrinkInternalCacheMinMemoryInMB",
    lambda_beeb644b938da7c66f3e8c6b86d599f4_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"ServerlessFreePagesReservedForReclamation",
    lambda_ee548a9bdd8c64c319221deaca4fe9d2_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"ServerlessCacheReclaimCpuTriggerPolicy",
    lambda_199d2c9abe269d0b858d335a03354833_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"ServerlessCacheReclaimPolicy",
    lambda_91e500a685dd2ad532b42c36570bf394_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"ServerlessCpuTriggerCachePagesReclaimablePercent",
    lambda_e011d626be3abc03f3120e37125f2427_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"ProvisionedActiveCacheThresholdMinutes",
    lambda_61555382d3353fbc42e99043dc56f9db_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"ProvisionedBufferPoolShrinkageIntervalMinutes",
    lambda_78d9627067463d493578712f6ccf2254_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"ProvisionedBufferPoolSkipInitialReclamationMinutes",
    lambda_8d7f9463c97e57f3be1775d94964f60a_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicDoubleSetting(
    s_pServerConf,
    L"RgSettings",
    L"ProvisionedCacheReclaimThresholdForCacheUsedPercent",
    lambda_a4e388723f02f7c8e8b062bb03664a02_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicDoubleSetting(
    s_pServerConf,
    L"RgSettings",
    L"ProvisionedPercentFreeAndColdPagesToReclaim",
    lambda_564ec39bc73952e4f05abab930ac6f1a_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicDoubleSetting(
    s_pServerConf,
    L"RgSettings",
    L"ProvisionedPercentTargetPagesToReclaim",
    lambda_80029b10d7902d29803a86b52c2d4912_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicDoubleSetting(
    s_pServerConf,
    L"RgSettings",
    L"ProvisionedMinBufferPoolAsPercentTargetPages",
    lambda_e25e8472f15a0d6f0b90e34d5a6e6290_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"PageServerBufferPoolShrinkageIntervalSeconds",
    lambda_1b87b31b974d4131444a4f1bc24cece7_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"PageServerActiveCacheThresholdMinutes",
    lambda_19a93633705224b81b634b673cab04b1_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicDoubleSetting(
    s_pServerConf,
    L"RgSettings",
    L"PageServerCacheReclaimThresholdForCacheUsedPercent",
    lambda_77310bab7b66541a8a0fd14e6235b02c_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicDoubleSetting(
    s_pServerConf,
    L"RgSettings",
    L"PageServerPercentFreeAndColdPagesToReclaim",
    lambda_d7194ca1b90cd274a546ea86dacccf79_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicDoubleSetting(
    s_pServerConf,
    L"RgSettings",
    L"PageServerPercentTargetPagesToReclaim",
    lambda_d204a94d5847ee36876d1322c8851cb3_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicDoubleSetting(
    s_pServerConf,
    L"RgSettings",
    L"PageServerMinBufferPoolAsPercentTargetPages",
    lambda_d8c5261eefccd9da72ee3091060bde86_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"ServerlessRbpexShrinkTimeoutSec",
    lambda_cbd77689c7783da369ed9d35b9325b7e_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"ServerlessRbpexShrinkToMemRatio",
    lambda_93f133924c649d279f77206da4aa27e4_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"MemLeakDetectionLeakThresholdPercent",
    lambda_55a406ad699537a5661f25295ee1fea4_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"MemLeakDetectionMaxIntervals",
    lambda_ee8c3008cd50ecea41044d782b2e9a40_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"MemLeakDetectionMaxLeakRecords",
    lambda_7fcef0789ac33477fa5536d59f1661c2_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"SoftCapPlanCachePercent",
    lambda_0dd0f1684def6690e72f0f29d84e36eb_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"ServerlessLockManagerCachedObjectsMemoryLimitPercent",
    lambda_19fef0171b5d38b0e01fc8516c5a5569_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"LockManagerCachedObjectsMemoryLimitPercent",
    lambda_1910198486626679409d29220c45e769_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"LockManagerInitialLockBlockPercent",
    lambda_3e5e46d4bd79311fb3926bad1d558c76_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"DeflationCacheMemoryLowerBoundKb",
    lambda_16631c6496eed27f4afe7d143fa1e967_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"OomSnapshotCooldownTimeMinutes",
    lambda_9c42df3b848025dfea074d43821a9e19_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"DeflationCacheMemoryOverheadPerVCoreKb",
    lambda_323587456d2ef0de8942e2936cc20038_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"GlobalCacheActivenessStatsNumCoresPerPartition",
    lambda_dd5a77686c8a0e7e77fba4e151acd8fd_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"GlobalCacheActivenessStatsIntervalPeriodSeconds",
    lambda_2f75b79918840d35ad12c8c483a7c088_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"SnapshotSchedulerStatsDurationSecs",
    lambda_b02805158b526c72fe2dda419d91bb00_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"SendTelemetryTagsDurationMins",
    lambda_635dc0baee77980740b7ee21f229bca1_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"SnapshotDACConnectionsDurationSecs",
    lambda_b7ead38b761d5c2590c68db83b3253be_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt64Setting(
    s_pServerConf,
    L"PerfCounterTelemetry",
    L"PerfCounterEmitRateInSecond",
    lambda_687de89adfb3a52bfefb38482d54902e_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt64Setting(
    s_pServerConf,
    L"PerfCounterTelemetry",
    L"TempDbUpdateRateInMinutes",
    lambda_95329c84977276065361e570c18a21e5_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt64Setting(
    s_pServerConf,
    L"PerfCounterTelemetry",
    L"MinCorePercentForAdvancedShoeboxMetrics",
    lambda_697a364dd876a1abe2b795881b13ffbb_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt64Setting(
    s_pServerConf,
    L"PerfCounterTelemetry",
    L"HadrGeoDRMetricEmitRateInSeconds",
    lambda_53471f6b0dac64bd2ae743cfa14e7077_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicStringSetting(
    s_pServerConf,
    L"PerfCounterTelemetry",
    L"HadrGeoDRMetricNamespace",
    lambda_5321fdf447120dee2411ee77064f7635_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"CollectInstanceResourceStatsTimePeriodSeconds",
    lambda_d90755e398414ba2d2426ecfe2052c36_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"CheckForCPUUsageDiscrepancyTimePeriodSeconds",
    lambda_19a77375514250797fde2fd815ac2be8_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"TimeIntervalToLookBackForCPUDiscrepancySeconds",
    lambda_ea84e98bf4c3a0bae257478fb2b12a29_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"PercentageEntriesAboveCPUUsageDiscrepancyAlertThreshold",
    lambda_b1dc62698597a7fd3a097b001ee11272_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"CPUUsageDiscrepancyAlertThreshold",
    lambda_3016f8856823dfd4714d761c13beb8ec_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"StarvationThresholdFactor",
    lambda_bd484ee6d599d8872a031f0ad61c6325_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"DirectShrinkNoProgressTimeoutInMilliSeconds",
    lambda_566479d5a1937c37011923cf308a01f9_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicBoolSetting(
    s_pServerConf,
    L"RgSettings",
    L"EnableDirectShrinkNoProgressTelemetry",
    lambda_d1865d6bb9f346a2556421ecd739b944_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"NonYieldSchedulerErrorPeriodInMs",
    lambda_d2d5b9ec4c9607cd66eb8e95ae3fd73d_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"NonYieldSchedulerDumpPeriodInMs",
    lambda_53ff76dcac2ff7f97516a8e759a33b19_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"InstanceResourceStatsDelayStartTimePeriodSeconds",
    lambda_3ee7bfb7d67356f711c927a6b594ef51_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"AutoMemoryLeakDetectorClerkMonitors",
    lambda_ee423570cfd87c309e42ad2d8625b155_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"AutoMemoryLeakDetectorClerkMaxMonitors",
    lambda_416e0d34254eaae05a7a7f065222d64a_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"AutoMemoryLeakDetectorMinutesToStart",
    lambda_5214df236d0e6e259baee00b0d08e4c1_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"AutoMemoryLeakDetectorNonSosMinJobCapPercent",
    lambda_7343ad6a5915ff3adaefa265de8427f1_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"AutoMemoryLeakDetectorLinearPercentThreshold",
    lambda_51513d3b8318de6f589b962ac29e386e_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicDoubleSetting(
    s_pServerConf,
    L"RgSettings",
    L"AutoMemoryLeakDetectorGrowthRatePercentThreshold",
    lambda_fe719ae28aa8e6a3a3337d75f0432fa1_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicDoubleSetting(
    s_pServerConf,
    L"RgSettings",
    L"AutoMemoryLeakDetectorGrowthRatePerCoreThresholdMb",
    lambda_ecd1809e7d4914b75147946181169f43_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"MemoryClerkMonitorBufferSize",
    lambda_15a23f31f86a0617c88d42ed4e082bba_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"MemoryClerkMonitorSnapshotIntervalMinutes",
    lambda_feef235361ad59a04f696521fcfcc98f_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"MemoryClerkMonitorMonotonicCheckIntervalMinutes",
    lambda_941448d69da8c81b24f2e8976eb3fbe7_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"MemoryClerkMinPercentToMonitor",
    lambda_789d399863171e02cca3e0f25f36fa2e_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"CleanCodePackageTimeoutInMs",
    lambda_b672d2004d728f3edf86b25b1da4b676_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"ActivateCodePackageTimeoutInMs",
    lambda_e847e34a716d96b12fa65a70acd38a98_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"UpdateRgIsolationRetryThreshold",
    lambda_dd9f6c24a0714644ea74509e7ecfb96a_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"UpdateRgIsolationRetryWaitTimeInMs",
    lambda_8fbe44c159e4bb99e95ddf8d97eb93e6_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"RgSettings",
    L"PassiveBrokerFreeMemoryGapPercent",
    lambda_b53c86c51e07d7635741af87fc6210ab_::_lambda_invoker_cdecl_,
    0,
    0);
  *(_DWORD *)(XdbServerGlobals + 20312) = 16;
  *(_DWORD *)(XdbServerGlobals + 20392) = 100;
  *(_DWORD *)(XdbServerGlobals + 20396) = 1000;
  *(_DWORD *)(XdbServerGlobals + 20400) = 1000;
  LOBYTE(v282) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"LocalSeedingTcpConnectionCount",
    XdbServerGlobals + 20316,
    v282,
    0);
  LOBYTE(v283) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"GeoSeedingTcpConnectionCount",
    XdbServerGlobals + 20320,
    v283,
    0);
  LOBYTE(v284) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"ConnectionSendFailureThreshold",
    XdbServerGlobals + 20324,
    v284,
    0);
  LOBYTE(v285) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"ConnectionSendFailureBlockPeriod",
    XdbServerGlobals + 20328,
    v285,
    0);
  LOBYTE(v286) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"SeedingOutOfOrderBufferSize",
    XdbServerGlobals + 20332,
    v286,
    0);
  LOBYTE(v287) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"SeedingResendThresholdForConnectionReset",
    XdbServerGlobals + 20336,
    v287,
    0);
  LOBYTE(v288) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"GeoReplicationTcpConnectionCount",
    XdbServerGlobals + 20344,
    v288,
    0);
  LOBYTE(v289) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"GeoReplicationConnectionSendFailureThreshold",
    XdbServerGlobals + 20348,
    v289,
    0);
  LOBYTE(v290) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"GeoReplicationConnectionSendFailureBlockPeriod",
    XdbServerGlobals + 20352,
    v290,
    0);
  LOBYTE(v291) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"FlowControlCountThreshold",
    XdbServerGlobals + 20356,
    v291,
    0);
  LOBYTE(v292) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"FlowControlMonitoringPeriodInSeconds",
    XdbServerGlobals + 20360,
    v292,
    0);
  LOBYTE(v293) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"FlowControlMonitoringIntervalCap",
    XdbServerGlobals + 20364,
    v293,
    0);
  LOBYTE(v294) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"FlowControlMonitoringMinIntervalsCount",
    XdbServerGlobals + 20368,
    v294,
    0);
  LOBYTE(v295) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"MinTransferRateInKbps",
    XdbServerGlobals + 20372,
    v295,
    0);
  LOBYTE(v296) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"FlowControlMonitoringFlowControlPercentage",
    XdbServerGlobals + 20376,
    v296,
    0);
  LOBYTE(v297) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"ForwarderSeedingFullQuorumMaxWaitTimeInSeconds",
    XdbServerGlobals + 20380,
    v297,
    0);
  v52 = (_OWORD *)GetXdbServerGlobals(v51, v50);
  v52[1216] = 0;
  v52[1217] = 0;
  v52[1218] = 0;
  v52[1219] = 0;
  IServerConfiguration::SubscribeAndGetDynamicStringSetting(
    s_pServerConf,
    L"QueryStoreSettings",
    L"AprcCompilationErrorsToSurfaceToQds",
    lambda_d14f9ddedafec7f40b11d114b173444a_::_lambda_invoker_cdecl_,
    0,
    0);
  *(_DWORD *)(XdbServerGlobals + 16572) = 512;
  SOS_OS::SetMinHealthyRateOfMemReleaseKB(512);
  *(_DWORD *)(XdbServerGlobals + 17044) = 300000;
  *(_BYTE *)(XdbServerGlobals + 16925) = 0;
  SOS_OS::SetIgnoreNonYieldingScheduler(0);
  if ( (unsigned int)IsXDBInstance() )
  {
    v53 = (RESOURCE *)CAutoBase<wchar_t>::Get(&qword_10049F360);
    RESOURCE::ParseRgIsolationSettingsXml(v53);
    v54 = (RESOURCE *)CAutoBase<wchar_t>::Get(&qword_10049F360);
    if ( !RESOURCE::ParseRgInstanceSettingsXml(v54) )
    {
      v55 = (RESOURCE *)CAutoBase<wchar_t>::Get(&qword_10049F360);
      RESOURCE::ConfigureRgInstance(v55, 0);
    }
  }
  LOBYTE(v298) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"RgSettings",
    L"MaxQPPrefetchQueueSize",
    XdbServerGlobals + 8228,
    v298,
    0);
  LOBYTE(v299) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"RgSettings",
    L"MinThrottledMaxDOP",
    XdbServerGlobals + 8232,
    v299,
    0);
  LOBYTE(v300) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"RgSettings",
    L"RemainingWorkersDOPPercentageThrottling",
    XdbServerGlobals + 8236,
    v300,
    0);
  LOBYTE(v301) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"RgSettings",
    L"SqlRgHistoryRingBufferSize",
    XdbServerGlobals + 16928,
    v301,
    0);
  LOBYTE(v302) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"RgSettings",
    L"SqlRgAggregatedHistoryRingBufferSize",
    XdbServerGlobals + 16932,
    v302,
    0);
  LOBYTE(v303) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"RgSettings",
    L"ActivenessDetectionIntervalMin",
    XdbServerGlobals + 16936,
    v303,
    0);
  LOBYTE(v304) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"RgSettings",
    L"DeactivationIntervalMin",
    XdbServerGlobals + 16940,
    v304,
    0);
  LOBYTE(v305) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"RgSettings",
    L"DynamicDeactivationIntervalMin",
    XdbServerGlobals + 16944,
    v305,
    0);
  LOBYTE(v306) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"RgSettings",
    L"DynamicFileAllocationIntervalMin",
    XdbServerGlobals + 16952,
    v306,
    0);
  LOBYTE(v307) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"RgSettings",
    L"PhysicalPauseDelay",
    XdbServerGlobals + 16948,
    v307,
    0);
  LOBYTE(v308) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"RgSettings",
    L"DeactivationAdjustedIntervalCapMin",
    XdbServerGlobals + 16968,
    v308,
    0);
  LOBYTE(v309) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"RgSettings",
    L"PFSConsistencyCheckIntervalMin",
    XdbServerGlobals + 16956,
    v309,
    0);
  LOBYTE(v310) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"RgSettings",
    L"PFSDynamicScalingGetShareStatsTimerInternalMin",
    XdbServerGlobals + 16960,
    v310,
    0);
  LOBYTE(v311) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"RgSettings",
    L"PFSDynamicScalingTimerIntervalMin",
    XdbServerGlobals + 16964,
    v311,
    0);
  LOBYTE(v312) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"RgSettings",
    L"ColdDatabaseGracePeriodMin",
    XdbServerGlobals + 17000,
    v312,
    0);
  LOBYTE(v313) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"RgSettings",
    L"ExtendedDeactivationCheckPeriodMin",
    XdbServerGlobals + 17004,
    v313,
    0);
  LOBYTE(v314) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"RgSettings",
    L"PublishRgHistoryIntervalMin",
    XdbServerGlobals + 17008,
    v314,
    0);
  LOBYTE(v315) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"RgSettings",
    L"PublishSelectiveRgHistoryIntervalMin",
    XdbServerGlobals + 17012,
    v315,
    0);
  LOBYTE(v316) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"RgSettings",
    L"PublishDirtyRgHistoryIntervalMin",
    XdbServerGlobals + 17016,
    v316,
    0);
  LOBYTE(v317) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"RgSettings",
    L"RgAggregatedHistoryPublishPeriodSec",
    XdbServerGlobals + 17024,
    v317,
    0);
  LOBYTE(v318) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"RgSettings",
    L"SqlRgSnapshotPlusPeriodSeconds",
    XdbServerGlobals + 17020,
    v318,
    0);
  LOBYTE(v319) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"RgSettings",
    L"ReplicaCountGracePeriodMin",
    XdbServerGlobals + 16972,
    v319,
    0);
  IServerConfiguration::GetDynamicInt64Setting(
    s_pServerConf,
    L"RgSettings",
    L"ReplicaCountLowThresholdMB",
    (__int64 *)(XdbServerGlobals + 16976),
    1,
    0);
  IServerConfiguration::GetDynamicInt64Setting(
    s_pServerConf,
    L"RgSettings",
    L"ReplicaCountHighThresholdMB",
    (__int64 *)(XdbServerGlobals + 16984),
    1,
    0);
  LOBYTE(v320) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"RgSettings",
    L"ReplicaRestartWaitDurationSecLong",
    XdbServerGlobals + 16992,
    v320,
    0);
  LOBYTE(v321) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"RgSettings",
    L"ReplicaRestartWaitDurationSecShort",
    XdbServerGlobals + 16996,
    v321,
    0);
  *(_DWORD *)(XdbServerGlobals + 28040) = 157286400;
  *(_DWORD *)(XdbServerGlobals + 28044) = 314572800;
  *(_DWORD *)(XdbServerGlobals + 28048) = 500;
  *(_DWORD *)(XdbServerGlobals + 28052) = 3;
  *(_QWORD *)(XdbServerGlobals + 28056) = 0x3FD999999999999ALL;
  *(_QWORD *)(XdbServerGlobals + 28064) = 0x3FE3333333333333LL;
  *(_QWORD *)(XdbServerGlobals + 28072) = 0x3FB999999999999ALL;
  *(_DWORD *)(XdbServerGlobals + 28080) = 100;
  v58 = GetXdbServerGlobals(v57, v56);
  StringCchCopyW((wchar_t *)(v58 + 21864), 0x105u, &dword_10047E02C);
  LOBYTE(v322) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"RgSettings",
    L"PFSFileWriteMBps",
    XdbServerGlobals + 28040,
    v322,
    0);
  LOBYTE(v323) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"RgSettings",
    L"PFSFileTargetReadMBps",
    XdbServerGlobals + 28044,
    v323,
    0);
  LOBYTE(v324) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"RgSettings",
    L"PFSFileTargetIOps",
    XdbServerGlobals + 28048,
    v324,
    0);
  LOBYTE(v325) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"RgSettings",
    L"PFSIOpsPerGB",
    XdbServerGlobals + 28052,
    v325,
    0);
  IServerConfiguration::GetDynamicDoubleSetting(
    s_pServerConf,
    L"RgSettings",
    L"PFSWriteBWFactor",
    (double *)(XdbServerGlobals + 28056),
    1,
    0);
  v59 = s_pServerConf;
  IServerConfiguration::GetDynamicDoubleSetting(
    s_pServerConf,
    L"RgSettings",
    L"PFSReadBWFactor",
    (double *)(XdbServerGlobals + 28064),
    1,
    0);
  IServerConfiguration::GetDynamicDoubleSetting(
    s_pServerConf,
    L"RgSettings",
    L"PFSBWPerGB",
    (double *)(XdbServerGlobals + 28072),
    1,
    0);
  LOBYTE(v326) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)v59 + 520LL))(
    v59,
    L"RgSettings",
    L"PFSMinShareBWMB",
    XdbServerGlobals + 28080,
    v326,
    0);
  LOBYTE(v327) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)v59 + 520LL))(
    v59,
    L"RgSettings",
    L"FileIOPerMilleSysResourceFailureRate",
    XdbServerGlobals + 28084,
    v327,
    0);
  LOBYTE(v328) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)v59 + 520LL))(
    v59,
    L"RgSettings",
    L"FileIOPerMilleWorkingSetQuotaFailureRate",
    XdbServerGlobals + 28088,
    v328,
    0);
  *(_DWORD *)(XdbServerGlobals + 24844) = 4;
  *(_QWORD *)(XdbServerGlobals + 24848) = 100;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *))(*(_QWORD *)v59 + 520LL))(
    v59,
    L"SQL",
    L"CheckpointReadAheadEfficiency");
  LOBYTE(v329) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)v59 + 520LL))(
    v59,
    L"SQL",
    L"CheckpointRecoveryLogBytesPerMicroSec",
    XdbServerGlobals + 24848,
    v329,
    0);
  LOBYTE(v330) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)v59 + 520LL))(
    v59,
    L"SQL",
    L"CheckpointMaxLogThresholdInMB",
    XdbServerGlobals + 24852,
    v330,
    0);
  LOBYTE(v331) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)v59 + 520LL))(
    v59,
    L"SQL",
    L"RbpexPageReaderPoolSize",
    XdbServerGlobals + 24856,
    v331,
    0);
  LOBYTE(v332) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)v59 + 520LL))(
    v59,
    L"SQL",
    L"GetPageThrottlePerc",
    XdbServerGlobals + 24860,
    v332,
    0);
  LOBYTE(v333) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)v59 + 520LL))(
    v59,
    L"SQL",
    L"GetPageThrottleOnOutstandingRbioRequests",
    XdbServerGlobals + 24864,
    v333,
    0);
  v60 = (unsigned int)IsXDBInstance() != 0;
  SOSEnableIoRgV2Callback(v60, 1);
  if ( (unsigned int)IsXDBInstance() )
    LOBYTE(v61) = 1;
  else
    v61 = 0;
  SOSEnableIoRgQueueLimitCallback(v61, 1);
  if ( CFeatureSwitchesDk::FAlternateIoFactorEnabled(g_featureSwitchesDk) )
    LOBYTE(v62) = 1;
  else
    v62 = 0;
  SOSEnableAlternateIoFactorEnabledCallback(v62, 1);
  if ( CFeatureSwitchesDk::FIORGV1InlineIssueEnabled(g_featureSwitchesDk) )
    LOBYTE(v63) = 1;
  else
    v63 = 0;
  SOSEnableInlineIssueInV1EnabledCallback(v63, 1);
  *(_DWORD *)(XdbServerGlobals + 16284) = 0;
  v64 = (CFeatureSwitchesMin *)CFeatureSwitchesMin::ExportCurrentInstance();
  *(_DWORD *)(XdbServerGlobals + 16308) = CFeatureSwitchesMin::FUseInstanceLevelIORGEnabled(v64);
  *(_QWORD *)(XdbServerGlobals + 17724) = 0;
  LOBYTE(v334) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"DosGuard",
    L"DosGuardRegisterLevel",
    XdbServerGlobals + 19628,
    v334,
    0);
  LOBYTE(v335) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"DosGuard",
    L"FirewallCacheExpirationTimeMilliSec",
    XdbServerGlobals + 19632,
    v335,
    0);
  LOBYTE(v336) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"LoginSettings",
    L"LoginTimeoutAsSystemErrorMs",
    XdbServerGlobals + 19636,
    v336,
    0);
  LOBYTE(v337) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"LoginSettings",
    L"FedauthLoginTimeoutAsSystemErrorMs",
    XdbServerGlobals + 19640,
    v337,
    0);
  LOBYTE(v338) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"LoginSettings",
    L"RowVersionTransitionTimeoutMs",
    XdbServerGlobals + 19644,
    v338,
    0);
  LOBYTE(v339) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"XOdbcAuthenticationCacheSettings",
    L"CacheTimeoutMs",
    XdbServerGlobals + 19648,
    v339,
    0);
  LOBYTE(v340) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"XOdbcAuthenticationCacheSettings",
    L"CacheUpdateRetryInitialBackOffMs",
    XdbServerGlobals + 19676,
    v340,
    0);
  LOBYTE(v341) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"XOdbcAuthenticationCacheSettings",
    L"CacheUpdateRetryMaxRetryDurationMs",
    XdbServerGlobals + 19680,
    v341,
    0);
  LOBYTE(v342) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"XOdbcAuthenticationCacheSettings",
    L"CacheUpdateRetryMaxNumberOfRetries",
    XdbServerGlobals + 19684,
    v342,
    0);
  LOBYTE(v343) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"XOdbcAuthenticationCacheSettings",
    L"LockWaitTimeMs",
    XdbServerGlobals + 19688,
    v343,
    0);
  LOBYTE(v344) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SqlDbConnectivitySettings",
    L"DbFwCacheTimeoutMs",
    XdbServerGlobals + 19692,
    v344,
    0);
  LOBYTE(v345) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SqlDbConnectivitySettings",
    L"DbFwCacheLockWaitTimeMs",
    XdbServerGlobals + 19696,
    v345,
    0);
  LOBYTE(v346) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"DTAJob",
    L"DTAJobCpuRatePercent",
    XdbServerGlobals + 19392,
    v346,
    0);
  LOBYTE(v347) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"DTAJob",
    L"DTAJobMemoryLimitPercent",
    XdbServerGlobals + 19396,
    v347,
    0);
  LOBYTE(v348) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"DTAJob",
    L"DTAJobMemoryLimitMaxInMB",
    XdbServerGlobals + 19400,
    v348,
    0);
  IServerConfiguration::GetDynamicBoolSetting(
    s_pServerConf,
    L"DTAJob",
    L"DTAJobSetCpuRateLimit",
    (bool *)(XdbServerGlobals + 19404),
    1,
    0);
  LOBYTE(v349) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"LogConsumptionThresholdForXactAbortSize",
    XdbServerGlobals + 17052,
    v349,
    0);
  LOBYTE(v350) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"AppAuditingSection",
    L"AuditSessionFlags",
    XdbServerGlobals + 20520,
    v350,
    0);
  LOBYTE(v351) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"AppAuditingSection",
    L"AuditingFlushTimeout",
    XdbServerGlobals + 20524,
    v351,
    0);
  LOBYTE(v352) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"AppAuditingSection",
    L"AuditingMaxSequenceNumber",
    XdbServerGlobals + 20528,
    v352,
    0);
  LOBYTE(v353) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"AppAuditingSection",
    L"AuditingXEBufferLocality",
    XdbServerGlobals + 20532,
    v353,
    0);
  LOBYTE(v354) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"AppAuditingSection",
    L"AuditingXEBufferTimeoutInMs",
    XdbServerGlobals + 20536,
    v354,
    0);
  LOBYTE(v355) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"AppAuditingSection",
    L"AuditingXEBufferSizeInBytes",
    XdbServerGlobals + 20540,
    v355,
    0);
  LOBYTE(v356) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"AppAuditingSection",
    L"AuditingTdXEBufferSizeInBytes",
    XdbServerGlobals + 20544,
    v356,
    0);
  LOBYTE(v357) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"AppAuditingSection",
    L"AuditingTVPRowsLimitInBytes",
    XdbServerGlobals + 20548,
    v357,
    0);
  LOBYTE(v358) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"AppAuditingSection",
    L"AuditingMaxEventFieldPayloadWChar",
    XdbServerGlobals + 20556,
    v358,
    0);
  LOBYTE(v359) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"AppAuditingSection",
    L"AuditingXEBuffersCount",
    XdbServerGlobals + 20552,
    v359,
    0);
  IServerConfiguration::GetDynamicBoolSetting(
    s_pServerConf,
    L"AppAuditingSection",
    L"AuditingUseBufferManualPartition",
    (bool *)(XdbServerGlobals + 20560),
    1,
    0);
  LOBYTE(v360) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"AppAuditingSection",
    L"AuditingMaxNumberOfAuditsAllowedPerDatabase",
    XdbServerGlobals + 20564,
    v360,
    0);
  LOBYTE(v361) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"AppAuditingSection",
    L"AuditingXEBufferSizeInBytesForBC",
    XdbServerGlobals + 20568,
    v361,
    0);
  LOBYTE(v362) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"AppAuditingSection",
    L"AuditingXEBuffersCountForBC",
    XdbServerGlobals + 20572,
    v362,
    0);
  LOBYTE(v363) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"AppAuditingSection",
    L"AuditingElasticPoolTotalBufferSize",
    XdbServerGlobals + 20576,
    v363,
    0);
  LOBYTE(v364) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"AppAuditingSection",
    L"AuditingElasticPoolMaxBufferSize",
    XdbServerGlobals + 20580,
    v364,
    0);
  LOBYTE(v365) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"AppAuditingSection",
    L"AuditingElasticPoolMinBufferSize",
    XdbServerGlobals + 20584,
    v365,
    0);
  LOBYTE(v366) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"AppAuditingSection",
    L"AuditingShoeboxXEFlags",
    XdbServerGlobals + 20588,
    v366,
    0);
  LOBYTE(v367) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"AppAuditingSection",
    L"AuditingShoeboxXEFlushTimeout",
    XdbServerGlobals + 20592,
    v367,
    0);
  LOBYTE(v368) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"AppAuditingSection",
    L"AuditingShoeboxXEBufferLocality",
    XdbServerGlobals + 20596,
    v368,
    0);
  LOBYTE(v369) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"AppAuditingSection",
    L"AuditingShoeboxXEBufferTimeoutInMs",
    XdbServerGlobals + 20600,
    v369,
    0);
  LOBYTE(v370) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"AppAuditingSection",
    L"AuditingShoeboxXEBufferSizeInBytes",
    XdbServerGlobals + 20604,
    v370,
    0);
  LOBYTE(v371) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"AppAuditingSection",
    L"AuditingShoeboxXEBuffersCount",
    XdbServerGlobals + 20608,
    v371,
    0);
  LOBYTE(v372) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"AppAuditingSection",
    L"AuditingShoeboxXEBufferSizeInBytesForBC",
    XdbServerGlobals + 20612,
    v372,
    0);
  LOBYTE(v373) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"AppAuditingSection",
    L"AuditingShoeboxXEBuffersCountForBC",
    XdbServerGlobals + 20616,
    v373,
    0);
  v65 = *(_QWORD *)s_pServerConf;
  v66 = SOS_Task::GetPmo();
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, struct IMemObj *, __int64, _QWORD))(v65 + 528))(
    s_pServerConf,
    L"AppAuditingSection",
    L"AuditingInternalEmailAddresses",
    v66,
    XdbServerGlobals + 20624,
    0);
  v67 = *(_QWORD *)s_pServerConf;
  v68 = SOS_Task::GetPmo();
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, struct IMemObj *, __int64, _QWORD))(v67 + 528))(
    s_pServerConf,
    L"AppAuditingSection",
    L"AuditingNoStorageFaultServerAuditEmailNotificationTemplateVersion",
    v68,
    XdbServerGlobals + 20632,
    0);
  v69 = *(_QWORD *)s_pServerConf;
  v70 = SOS_Task::GetPmo();
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, struct IMemObj *, __int64, _QWORD))(v69 + 528))(
    s_pServerConf,
    L"AppAuditingSection",
    L"AuditingNoStorageFaultDatabaseAuditEmailNotificationTemplateVersion",
    v70,
    XdbServerGlobals + 20640,
    0);
  v71 = *(_QWORD *)s_pServerConf;
  v72 = SOS_Task::GetPmo();
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, struct IMemObj *, __int64, _QWORD))(v71 + 528))(
    s_pServerConf,
    L"AppAuditingSection",
    L"AuditingNoContainerFaultServerAuditEmailNotificationTemplateVersion",
    v72,
    XdbServerGlobals + 20648,
    0);
  v73 = *(_QWORD *)s_pServerConf;
  v74 = SOS_Task::GetPmo();
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, struct IMemObj *, __int64, _QWORD))(v73 + 528))(
    s_pServerConf,
    L"AppAuditingSection",
    L"AuditingNoContainerFaultDatabaseAuditEmailNotificationTemplateVersion",
    v74,
    XdbServerGlobals + 20656,
    0);
  v75 = *(_QWORD *)s_pServerConf;
  v76 = SOS_Task::GetPmo();
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, struct IMemObj *, __int64, _QWORD))(v75 + 528))(
    s_pServerConf,
    L"AppAuditingSection",
    L"AuditingStorageNoAccessFaultServerAuditEmailNotificationTemplateVersion",
    v76,
    XdbServerGlobals + 20664,
    0);
  v77 = *(_QWORD *)s_pServerConf;
  v78 = SOS_Task::GetPmo();
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, struct IMemObj *, __int64, _QWORD))(v77 + 528))(
    s_pServerConf,
    L"AppAuditingSection",
    L"AuditingStorageNoAccessFaultDatabaseAuditEmailNotificationTemplateVersion",
    v78,
    XdbServerGlobals + 20672,
    0);
  LOBYTE(v374) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"AppAuditingSection",
    L"XEGetCredTimeoutInMs",
    XdbServerGlobals + 20620,
    v374,
    0);
  IServerConfiguration::GetDynamicBoolSetting(
    s_pServerConf,
    L"SQL",
    L"EncryptDmkByTdeCertificate",
    (bool *)(XdbServerGlobals + 20688),
    1,
    0);
  if ( !(unsigned int)IsXDBInstance()
    || (LOBYTE(v375) = 1,
        !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
           s_pServerConf,
           L"SqlDbConnectivitySettings",
           L"UseDbTimeoutInMsForLogins",
           XdbServerGlobals + 20696,
           v375,
           0)) )
  {
    *(_DWORD *)(XdbServerGlobals + 20696) = -1;
  }
  LOBYTE(v375) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"FirewallRules",
    L"FirewallRulesMaxCount",
    XdbServerGlobals + 20700,
    v375,
    0);
  LOBYTE(v376) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"FirewallRules",
    L"IPv4ServerFirewallRulesMaxCount",
    XdbServerGlobals + 20704,
    v376,
    0);
  LOBYTE(v377) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"FirewallRules",
    L"IPv4DbFirewallRulesMaxCount",
    XdbServerGlobals + 20708,
    v377,
    0);
  LOBYTE(v378) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"FirewallRules",
    L"IPv6ServerFirewallRulesMaxCount",
    XdbServerGlobals + 20712,
    v378,
    0);
  LOBYTE(v379) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"FirewallRules",
    L"IPv6DbFirewallRulesMaxCount",
    XdbServerGlobals + 20716,
    v379,
    0);
  LOBYTE(v380) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"VnetFirewallRules",
    L"MaxRulesCount",
    XdbServerGlobals + 20720,
    v380,
    0);
  LOBYTE(v381) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"MaxBatchExecutionTimeInMs",
    XdbServerGlobals + 8220,
    v381,
    0);
  LOBYTE(v382) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"MaxSessionTimeInMs",
    XdbServerGlobals + 8224,
    v382,
    0);
  LOBYTE(v383) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"ElasticPoolPlannedFailoverIntervalInMs",
    XdbServerGlobals + 8240,
    v383,
    0);
  LOBYTE(v384) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"MaxElasticPoolPlannedFailoverBatchCount",
    XdbServerGlobals + 8244,
    v384,
    0);
  LOBYTE(v385) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"WaitTimeInMilliSecForUndoBeforeExit",
    XdbServerGlobals + 8256,
    v385,
    0);
  LOBYTE(v386) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"TimeToWaitForOpportunisticFailoverInMs",
    XdbServerGlobals + 8248,
    v386,
    0);
  LOBYTE(v387) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"TargetNumOfBatches",
    XdbServerGlobals + 8252,
    v387,
    0);
  LOBYTE(v388) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"LogFullAmountBeforeEvictingReplica",
    XdbServerGlobals + 8260,
    v388,
    0);
  LOBYTE(v389) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"WaitTimeInMinBeforeEvictingReplica",
    XdbServerGlobals + 8264,
    v389,
    0);
  LOBYTE(v390) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"CheckIfEvictingReplicaNeededIntervalInSec",
    XdbServerGlobals + 8268,
    v390,
    0);
  LOBYTE(v391) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"InstanceStorageUsagePercentBeforeEvictingReplica",
    XdbServerGlobals + 8272,
    v391,
    0);
  LOBYTE(v392) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"NumberOfCleanShutdownRetriesBeforeImmediateShutdown",
    XdbServerGlobals + 8276,
    v392,
    0);
  LOBYTE(v393) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"TimeToWaitToSynchronizeBuildReplicaOperationsOnEmptyNodeInMs",
    XdbServerGlobals + 8280,
    v393,
    0);
  LOBYTE(v394) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"SynchronizeBuildReplicaOperationCanceledPeriodCheckInMs",
    XdbServerGlobals + 8284,
    v394,
    0);
  LOBYTE(v395) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"AlterDbCrossInstancePollingPeriodInMs",
    XdbServerGlobals + 8288,
    v395,
    0);
  LOBYTE(v396) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"KillRedoBlockersWaitThresholdInSeconds",
    XdbServerGlobals + 20728,
    v396,
    0);
  LOBYTE(v397) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"KillActiveBuildsBlockingRedoOfShrinkWaitThresholdInSeconds",
    XdbServerGlobals + 20732,
    v397,
    0);
  LOBYTE(v398) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"KillRedoBlockersMinimumWaitThresholdInSeconds",
    XdbServerGlobals + 20736,
    v398,
    0);
  LOBYTE(v399) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"KillRedoBlockersRedoQueueThresholdInMB",
    XdbServerGlobals + 20740,
    v399,
    0);
  LOBYTE(v400) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"DirectConnectionEnabled",
    XdbServerGlobals + 20744,
    v400,
    0);
  LOBYTE(v401) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"WaitForTransportUpTimeoutInMs",
    XdbServerGlobals + 20748,
    v401,
    0);
  LOBYTE(v402) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"WaitForMissingLogBlockInSec",
    XdbServerGlobals + 20752,
    v402,
    0);
  LOBYTE(v403) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"MaxRetryOfCreateOpenBlockBlob",
    XdbServerGlobals + 20756,
    v403,
    0);
  LOBYTE(v404) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"PlannedFailoverMaxPrewaitTimeInSeconds",
    XdbServerGlobals + 20384,
    v404,
    0);
  LOBYTE(v405) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"PlannedFailoverMaxMustCatchupReplicaLagInSeconds",
    XdbServerGlobals + 20388,
    v405,
    0);
  LOBYTE(v406) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"LogReplicaMinVlfCount",
    XdbServerGlobals + 13064,
    v406,
    0);
  LOBYTE(v407) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"SQL",
          L"LogWriterThreadCountPerNode",
          XdbServerGlobals + 13068,
          v407,
          0) )
    *(_DWORD *)(XdbServerGlobals + 13068) = 2;
  LOBYTE(v408) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"SQL",
          L"LogWriterThreadCountPerCPU",
          XdbServerGlobals + 13072,
          v408,
          0) )
    *(_DWORD *)(XdbServerGlobals + 13072) = 1;
  LOBYTE(v409) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"SQL",
          L"DbXLockTimeoutforAssert",
          XdbServerGlobals + 20984,
          v409,
          0) )
    *(_DWORD *)(XdbServerGlobals + 20984) = 60;
  LOBYTE(v410) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"BufLatchTimeoutWaitMs",
    XdbServerGlobals + 17048,
    v410,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"Pesto",
    L"DwCatalogBatchSize",
    lambda_b1ab6bbe6afce9f3712efb78077a5f9a_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"Pesto",
    L"DwCatalogUpdateBatchSize",
    lambda_e066b718f7054e2794fad2c4fb08068b_::_lambda_invoker_cdecl_,
    0,
    0);
  LOBYTE(v411) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"Pesto",
          L"DwMaxOutstandingSbsCacheWrites",
          XdbServerGlobals + 20832,
          v411,
          0) )
    *(_DWORD *)(XdbServerGlobals + 20832) = 1024;
  LOBYTE(v412) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"Pesto",
          L"DwTargetSbsCacheWriteIoTimeInMs",
          XdbServerGlobals + 20836,
          v412,
          0) )
    *(_DWORD *)(XdbServerGlobals + 20836) = 100;
  LOBYTE(v413) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"Pesto",
          L"DwMaxMaxCSBPoolMemoryTarget",
          XdbServerGlobals + 20840,
          v413,
          0) )
    *(_DWORD *)(XdbServerGlobals + 20840) = 10;
  LOBYTE(v414) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"Pesto",
          L"DwMaxHobtCacheStoreMemoryTarget",
          XdbServerGlobals + 20872,
          v414,
          0) )
    *(_DWORD *)(XdbServerGlobals + 20872) = 100;
  LOBYTE(v415) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"Pesto",
          L"DwCatalogSequentialGuidRangeSize",
          XdbServerGlobals + 20844,
          v415,
          0) )
    *(_DWORD *)(XdbServerGlobals + 20844) = 500;
  LOBYTE(v416) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"Pesto",
          L"DwCatalogGarbageCollectorPeriod",
          XdbServerGlobals + 20848,
          v416,
          0) )
    *(_DWORD *)(XdbServerGlobals + 20848) = 1800;
  LOBYTE(v417) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"Pesto",
          L"DwCatalogTombstoneBatchSize",
          XdbServerGlobals + 20852,
          v417,
          0) )
    *(_DWORD *)(XdbServerGlobals + 20852) = 100;
  LOBYTE(v418) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"Pesto",
          L"DwCatalogLargeTransactionBatchSize",
          XdbServerGlobals + 20856,
          v418,
          0) )
    *(_DWORD *)(XdbServerGlobals + 20856) = *(_DWORD *)(XdbServerGlobals + 20844);
  LOBYTE(v419) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"Pesto",
          L"DwBackgroundScannerTransactionBatchSize",
          XdbServerGlobals + 20860,
          v419,
          0) )
    *(_DWORD *)(XdbServerGlobals + 20860) = 1;
  LOBYTE(v420) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"Pesto",
          L"DwThresholdSkipWriteToSbsCache",
          XdbServerGlobals + 20868,
          v420,
          0) )
    *(_DWORD *)(XdbServerGlobals + 20868) = 99;
  LOBYTE(v421) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"Pesto",
          L"DwConsolidatedRowgroupMaxUncompressedSize",
          XdbServerGlobals + 20876,
          v421,
          0) )
    *(_DWORD *)(XdbServerGlobals + 20876) = 0x20000000;
  if ( !IServerConfiguration::GetDynamicInt64Setting(
          s_pServerConf,
          L"Pesto",
          L"DwAdditionalMemoryBytesForBuildingConsolidatedRowgroup",
          (__int64 *)(XdbServerGlobals + 20880),
          1,
          0) )
    *(_QWORD *)(XdbServerGlobals + 20880) = 0x20000000;
  if ( !IServerConfiguration::GetDynamicInt64Setting(
          s_pServerConf,
          L"Fido",
          L"FidoAdditionalMemoryBytesForBucketizationOnPartitionedTable",
          (__int64 *)(XdbServerGlobals + 20888),
          1,
          0) )
    *(_QWORD *)(XdbServerGlobals + 20888) = 188743680;
  if ( !IServerConfiguration::GetDynamicInt64Setting(
          s_pServerConf,
          L"Fido",
          L"FidoAdditionalMemoryBytesForBucketizationOnNonPartitionedTable",
          (__int64 *)(XdbServerGlobals + 20896),
          1,
          0) )
    *(_QWORD *)(XdbServerGlobals + 20896) = 9437184;
  if ( !IServerConfiguration::GetDynamicInt64Setting(
          s_pServerConf,
          L"SQL",
          L"ODBCRowCacheSizeInMB",
          (__int64 *)(XdbServerGlobals + 24568),
          1,
          0) )
    *(_QWORD *)(XdbServerGlobals + 24568) = 16;
  if ( !IServerConfiguration::GetDynamicInt64Setting(
          s_pServerConf,
          L"SQL",
          L"ParquetWriterOutputterTotalColumnChunkBufferSizeInMB",
          (__int64 *)(XdbServerGlobals + 24576),
          1,
          0) )
    *(_QWORD *)(XdbServerGlobals + 24576) = 16;
  if ( !IServerConfiguration::GetDynamicInt64Setting(
          s_pServerConf,
          L"SQL",
          L"ParquetWriterOutputterMaxRowGroupSizeInMB",
          (__int64 *)(XdbServerGlobals + 24584),
          1,
          0) )
    *(_QWORD *)(XdbServerGlobals + 24584) = 400;
  if ( !IServerConfiguration::GetDynamicInt64Setting(
          s_pServerConf,
          L"SQL",
          L"ParquetWriterOutputterMaxRowCountInRowGroup",
          (__int64 *)(XdbServerGlobals + 24592),
          1,
          0) )
    *(_QWORD *)(XdbServerGlobals + 24592) = 0x200000;
  if ( !IServerConfiguration::GetDynamicInt64Setting(
          s_pServerConf,
          L"SQL",
          L"ParquetWriterOutputterAdditionalMemoryFactorInPercent",
          (__int64 *)(XdbServerGlobals + 24600),
          1,
          0) )
    *(_QWORD *)(XdbServerGlobals + 24600) = 10;
  if ( !IServerConfiguration::GetDynamicInt64Setting(
          s_pServerConf,
          L"SQL",
          L"ParquetWriterOutputterMaxLobSizeInMB",
          (__int64 *)(XdbServerGlobals + 24608),
          1,
          0) )
    *(_QWORD *)(XdbServerGlobals + 24608) = 1;
  if ( !IServerConfiguration::GetDynamicInt64Setting(
          s_pServerConf,
          L"SQL",
          L"ParquetWriterOutputterMaxRowCountInColumnChunkBuffer",
          (__int64 *)(XdbServerGlobals + 24616),
          1,
          0) )
    *(_QWORD *)(XdbServerGlobals + 24616) = 900;
  if ( !IServerConfiguration::GetDynamicInt64Setting(
          s_pServerConf,
          L"SQL",
          L"ParquetWriterOutputterDataPageSizeInMB",
          (__int64 *)(XdbServerGlobals + 24624),
          1,
          0) )
    *(_QWORD *)(XdbServerGlobals + 24624) = 1;
  if ( !IServerConfiguration::GetDynamicInt64Setting(
          s_pServerConf,
          L"SQL",
          L"ParquetWriterOutputterDictionaryPageSizeLimitInMB",
          (__int64 *)(XdbServerGlobals + 24632),
          1,
          0) )
    *(_QWORD *)(XdbServerGlobals + 24632) = 32;
  v81 = GetXdbServerGlobals(v80, v79);
  v84 = GetXdbServerGlobals(v83, v82) + 5578;
  v87 = GetXdbServerGlobals(v86, v85) + 5056;
  DefaultLocale = GetDefaultLocale();
  v90 = L"/subscriptions/%s/resourceGroups/%s/providers/Microsoft.Sql/servers/%s";
  if ( (unsigned int)IsCloudLifterRecollationEnabled() )
    v90 = L"/subscriptions/%s/resourceGroups/%s/providers/Microsoft.Sql/managedInstances/%s";
  v91 = GetXdbServerGlobals(L"/subscriptions/%s/resourceGroups/%s/providers/Microsoft.Sql/managedInstances/%s", v89);
  StringCchPrintf_lW((wchar_t *)(v91 + 3654), 0xFDu, v90, DefaultLocale, v87, v84, v81);
  if ( *(_BYTE *)(GetXdbServerGlobals(v93, v92) + 12009) || *(_BYTE *)(GetXdbServerGlobals(v95, v94) + 12008) )
  {
    CurrentInstance = (CFeatureSwitchesMin *)CFeatureSwitchesMin::GetCurrentInstance();
    if ( CFeatureSwitchesMin::FRefreshTridentFlagsFromFabricPropertiesEnabled(CurrentInstance)
      && (int)RefreshTridentFlags() < 0 )
    {
      utassert_fail(1u, "SUCCEEDED(hr)", "dbfabric.cpp", 7463, 0);
    }
    LODWORD(dwBytes) = 0;
    ReadWinfabProperty(L"PoolId", 0, 0, (unsigned int *)&dwBytes);
    v99 = dwBytes;
    if ( (_DWORD)dwBytes )
    {
      ProcessHeap = GetProcessHeap();
      v101 = HeapAlloc(ProcessHeap, 8u, v99);
      CAutoRg<wchar_t>::CAutoRg<wchar_t>(v560, v101);
      v102 = (unsigned __int8 *)CAutoBase<wchar_t>::Get(v560);
      ReadWinfabProperty(L"PoolId", v99, v102, (unsigned int *)&dwBytes);
      if ( (_DWORD)dwBytes && GetXdbServerGlobals(v104, v103) != -12016 )
      {
        v105 = dwBytes;
        v106 = (const void *)CAutoBase<wchar_t>::Get(v560);
        v107 = dwBytes;
        v110 = GetXdbServerGlobals(v109, v108);
        memcpy_s((void *const)(v110 + 12016), v107, v106, v105);
        v113 = GetXdbServerGlobals(v112, v111);
        *(_WORD *)(v113 + 2 * ((unsigned __int64)(unsigned int)dwBytes >> 1) + 12016) = 0;
      }
      CAutoHeapAlloc<_IP_ADAPTER_ADDRESSES_LH>::~CAutoHeapAlloc<_IP_ADAPTER_ADDRESSES_LH>(v560);
    }
  }
  if ( *(_BYTE *)(GetXdbServerGlobals(v97, v96) + 12009)
    && *(_BYTE *)(GetXdbServerGlobals(v115, v114) + 12004)
    && GetXdbServerGlobals(v117, v116) != -12538 )
  {
    LODWORD(dwBytes) = 0;
    v120 = GetXdbServerGlobals(v119, v118);
    if ( (int)ReadWinfabProperty(
                L"SynapseSqlPoolName",
                0x208u,
                (unsigned __int8 *)(v120 + 12538),
                (unsigned int *)&dwBytes) < 0
      || (unsigned int)(dwBytes - 1) > 0x103 )
    {
      *(_WORD *)(GetXdbServerGlobals(v122, v121) + 12538) = 0;
    }
    else
    {
      v123 = GetXdbServerGlobals(v122, v121);
      *(_WORD *)(v123 + 2 * ((unsigned __int64)(unsigned int)dwBytes >> 1) + 12538) = 0;
    }
  }
  if ( (unsigned int)IsVDWInstance() )
  {
    CAutoRg<wchar_t>::CAutoRg<wchar_t>(&dwBytes, 0);
    v124 = (wchar_t **)CAutoRefc<IUnknown>::operator&(&dwBytes);
    v125 = SOS_Task::GetPmo();
    PolarisCommonUtils::ReadArcadiaWorkspaceNameFromAppParameters(v125, v124);
    v126 = CAutoBase<wchar_t>::Get(&dwBytes);
    v129 = GetXdbServerGlobals(v128, v127) + 5578;
    v132 = GetXdbServerGlobals(v131, v130) + 5056;
    v133 = GetDefaultLocale();
    v136 = GetXdbServerGlobals(v135, v134);
    StringCchPrintf_lW(
      (wchar_t *)(v136 + 24912),
      0x410u,
      L"/subscriptions/%s/resourceGroups/%s/providers/Microsoft.Synapse/workspaces/%s",
      v133,
      v132,
      v129,
      v126);
    CAutoRg<void *>::~CAutoRg<void *>(&dwBytes);
  }
  else
  {
    v137 = GetDefaultLocale();
    v140 = GetXdbServerGlobals(v139, v138);
    StringCchPrintf_lW((wchar_t *)(v140 + 24912), 0x410u, &dword_10045ADE4, v137);
  }
  v141 = SOS_Task::GetPmo();
  PolarisCommonUtils::ApplyConfigOverridesFromAppProperty(v141);
  if ( (unsigned int)IsXDBInstance() )
  {
    if ( (int)GetPreventDataExfiltrationWinFabProperty(XdbServerGlobals + 24896) >= 0 )
    {
      if ( *(_BYTE *)(XdbServerGlobals + 24896) )
      {
        CAutoRg<wchar_t>::CAutoRg<wchar_t>(v560, 0);
        LODWORD(dwBytes) = 0;
        v142 = SOS_Node::GetPmo();
        if ( (int)DataExFiltrationConfigHelper::GetDataExfiltrationAllowedFqdnList(v142, v560, &dwBytes) < 0 )
        {
          *(_DWORD *)(XdbServerGlobals + 24900) = 0;
          v143 = 0;
        }
        else
        {
          v143 = CAutoBase<CAutoRg<wchar_t const>>::PvReturn(v560);
          *(_DWORD *)(XdbServerGlobals + 24900) = dwBytes;
        }
        *(_QWORD *)(XdbServerGlobals + 24904) = v143;
        CAutoRg<CAutoRg<wchar_t const>>::~CAutoRg<CAutoRg<wchar_t const>>(v560);
      }
      else
      {
        *(_QWORD *)(XdbServerGlobals + 24904) = 0;
        *(_DWORD *)(XdbServerGlobals + 24900) = 0;
      }
    }
    else
    {
      *(_BYTE *)(XdbServerGlobals + 24896) = 0;
      *(_QWORD *)(XdbServerGlobals + 24904) = 0;
      *(_DWORD *)(XdbServerGlobals + 24900) = 0;
    }
  }
  CharUpperW((LPWSTR)(XdbServerGlobals + 3654));
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"Sbs",
    L"SbsLruEvictionNumberOfFiles",
    lambda_8334b8f5e525151f5ec0b63b208001c4_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"Sbs",
    L"SbsLruEvictionNumberOfBlobs",
    lambda_f66017d849c79253e921af773c1a89a2_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"Sbs",
    L"SbsLruEvictionCutoffPercent",
    lambda_47f74c282ce5131ac2008ba40f80ad92_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"Sbs",
    L"SbsLruEvictionMaxLengthOfEvictionList",
    lambda_359ebc1ee5de847bf7aeef826f875151_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"Sbs",
    L"SbsLruEvictionThresholdGrowEvictionList",
    lambda_d022b9cddd56b17229c938a3c67d24ff_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"Sbs",
    L"SbsLruEvictionThresholdStartShrinkEvictionList",
    lambda_8e25b1f53f9794e67798baafebe883b8_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"Sbs",
    L"SbsLruEvictionThresholdStartDoubleShrinkEvictionList",
    lambda_8ea7b1bbca5a55c3c41cfa6980d7f44d_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"Sbs",
    L"SbsLruEvictionThresholdStopShrinkEvictionList",
    lambda_df7b370230d9241f48ed287c7473b2bc_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"Sbs",
    L"SbsLruEvictionThresholdRecalibrateDbUtilization",
    lambda_46eee222493cd19d7a968445ce05128e_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"Sbs",
    L"SbsLruEvictionDefaultPercentOfDbToEvict",
    lambda_22a42338844deec043a2277a647ba8a3_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"Sbs",
    L"SbsLruEvictionMaxSizeInBytesToEvict",
    lambda_3e18735f37067618ad631d95bc103bb9_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"Sbs",
    L"SbsLruEvictionGrowthFactor",
    lambda_fa7699f95f484a6087660ce41d2198e8_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    s_pServerConf,
    L"Sbs",
    L"SbsLruEvictionShrinkFactor",
    lambda_457689ec0ddc04fdfacdcab94ab4b591_::_lambda_invoker_cdecl_,
    0,
    0);
  if ( !IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
          s_pServerConf,
          L"DWQPTelemetryConfig",
          L"FrontendEventLoggingLevel",
          lambda_4b740c1c1eea634f9edbef9c7ef32030_::_lambda_invoker_cdecl_,
          0,
          0) )
    *(_DWORD *)(GetXdbServerGlobals(v145, v144) + 28216) = 0;
  if ( !IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
          s_pServerConf,
          L"DWQPTelemetryConfig",
          L"BackendEventLoggingLevel",
          lambda_b55962126b0eb311e5a2e9bebd26b91f_::_lambda_invoker_cdecl_,
          0,
          0) )
    *(_DWORD *)(GetXdbServerGlobals(v147, v146) + 28220) = 0;
  if ( !IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
          s_pServerConf,
          L"DWQPTelemetryConfig",
          L"GlmServerEventLoggingLevel",
          lambda_9d6587e3ae0d4996840169e2f234e24f_::_lambda_invoker_cdecl_,
          0,
          0) )
    *(_DWORD *)(GetXdbServerGlobals(v149, v148) + 28224) = 0;
  LOBYTE(v422) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"Pesto",
          L"DwSbsFileTableAccessRefreshPeriod",
          XdbServerGlobals + 20864,
          v422,
          0) )
    *(_DWORD *)(XdbServerGlobals + 20864) = 20;
  LOBYTE(v423) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"NumberOfOutcomesToPreserve",
    XdbServerGlobals + 20680,
    v423,
    0);
  LOBYTE(v424) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"NumberOfOutcomeInsertsPerStatusReport",
    XdbServerGlobals + 20684,
    v424,
    0);
  CAutoRg<wchar_t>::CAutoRg<wchar_t>(v561);
  v150 = *(_QWORD *)s_pServerConf;
  v151 = CAutoRefc<IUnknown>::operator&(v561);
  v152 = SOS_Task::GetPmo();
  if ( (*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, struct IMemObj *, __int64, _QWORD))(v150 + 528))(
         s_pServerConf,
         L"SQL",
         L"InstanceProfileName",
         v152,
         v151,
         0) )
  {
    v153 = (const wchar_t *)CAutoBase<wchar_t>::Get(v561);
    v156 = GetXdbServerGlobals(v155, v154);
    StringCchCopyW((wchar_t *)(v156 + 20988), 0x105u, v153);
  }
  v157 = (CFeatureSwitchesMin *)CFeatureSwitchesMin::ExportCurrentInstance();
  if ( CFeatureSwitchesMin::FDwResultSetCachingEnabled(v157) && !IsFidoInstance()
    || (GlobalTraceFlagStore = (const unsigned __int8 *)GetGlobalTraceFlagStore(),
        (unsigned int)get_bit(GlobalTraceFlagStore, 11900)) )
  {
    v159 = *(_QWORD *)s_pServerConf;
    IqGlobals = GetIqGlobals();
    LOBYTE(v425) = 1;
    if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(v159 + 520))(
            s_pServerConf,
            L"IQ",
            L"IqRetentionPeriodInDays",
            (__int64)IqGlobals + 2092,
            v425,
            0) )
      *((_DWORD *)GetIqGlobals() + 523) = 0;
    v161 = *(_QWORD *)s_pServerConf;
    v162 = GetIqGlobals();
    LOBYTE(v426) = 1;
    if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(v161 + 520))(
            s_pServerConf,
            L"IQ",
            L"IqBackgroundTaskTimeout",
            (__int64)v162 + 2096,
            v426,
            0) )
      *((_DWORD *)GetIqGlobals() + 524) = 0;
    LOBYTE(v427) = 0;
    if ( (*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, SIZE_T *, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
           s_pServerConf,
           L"IQ",
           L"IqBackgroundEvictionMaxDispactchers",
           &dwBytes,
           v427,
           0) )
    {
      *((_DWORD *)GetIqGlobals() + 525) = dwBytes;
    }
    else
    {
      *((_DWORD *)GetIqGlobals() + 525) = 32;
    }
    v163 = *(_QWORD *)s_pServerConf;
    v164 = GetIqGlobals();
    LOBYTE(v428) = 1;
    if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(v163 + 520))(
            s_pServerConf,
            L"IQ",
            L"IqMaxEvictionObjectsPerTimerEviction",
            (__int64)v164 + 2104,
            v428,
            0) )
      *((_DWORD *)GetIqGlobals() + 526) = 1000;
    v165 = *(_QWORD *)s_pServerConf;
    v166 = GetIqGlobals();
    LOBYTE(v429) = 1;
    if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(v165 + 520))(
            s_pServerConf,
            L"IQ",
            L"IqTimerBasedEvictionTaskPeriodInSeconds",
            (__int64)v166 + 2108,
            v429,
            0) )
      *((_DWORD *)GetIqGlobals() + 527) = 600;
    v167 = *(_QWORD *)s_pServerConf;
    v168 = GetIqGlobals();
    LOBYTE(v430) = 1;
    if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(v167 + 520))(
            s_pServerConf,
            L"IQ",
            L"IqTimerBasedObjectVersionCleanupTaskPeriodInSeconds",
            (__int64)v168 + 2112,
            v430,
            0) )
      *((_DWORD *)GetIqGlobals() + 528) = 600;
  }
  LOBYTE(v425) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"SQL",
          L"ForeignLogCheckpointThresholdInMB",
          XdbServerGlobals + 24260,
          v425,
          0) )
    *(_DWORD *)(XdbServerGlobals + 24260) = 512;
  LOBYTE(v431) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"RbIoWaitForQuorumCatchUpThresholdInMB",
    XdbServerGlobals + 24264,
    v431,
    0);
  LOBYTE(v432) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"RbIoWaitForQuorumCatchUpTimeoutInSecs",
    XdbServerGlobals + 24268,
    v432,
    0);
  LOBYTE(v433) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"PageServerWaitForQuorumCatchUpThresholdInMB",
    XdbServerGlobals + 24272,
    v433,
    0);
  LOBYTE(v434) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"PageServerWaitForQuorumCatchUpTimeoutInSecs",
    XdbServerGlobals + 24276,
    v434,
    0);
  LOBYTE(v435) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"RedoRingBufferSize",
    XdbServerGlobals + 24452,
    v435,
    0);
  LOBYTE(v436) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"PageServerDataReadThresholdForActivenessInRequestsPerMin",
    XdbServerGlobals + 24280,
    v436,
    0);
  LOBYTE(v437) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"PageServerLogRedoThresholdForActivenessInBSNPerMin",
    XdbServerGlobals + 24284,
    v437,
    0);
  LOBYTE(v438) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"SQL",
          L"PageServerPageReadTimeoutInMS",
          XdbServerGlobals + 24288,
          v438,
          0) )
    *(_DWORD *)(XdbServerGlobals + 24288) = 10000;
  LOBYTE(v439) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"SQL",
          L"RbIoRemoteEndpointsGoodEnoughThresholdInMicroSecs",
          XdbServerGlobals + 24292,
          v439,
          0) )
    *(_DWORD *)(XdbServerGlobals + 24292) = 10000;
  LOBYTE(v440) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"SQL",
          L"RbIoBlockPoolMinimalReserveObjects",
          XdbServerGlobals + 24296,
          v440,
          0) )
    *(_DWORD *)(XdbServerGlobals + 24296) = 0;
  LOBYTE(v441) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"HotPageMaxPagesToPrime",
    XdbServerGlobals + 24300,
    v441,
    0);
  LOBYTE(v442) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"HotPageTrackerMaxUniquePages",
    XdbServerGlobals + 24304,
    v442,
    0);
  LOBYTE(v443) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"HotPageEstimatorMaxUniquePages",
    XdbServerGlobals + 24308,
    v443,
    0);
  LOBYTE(v444) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"HotPageTrackerSnapshotBucketCount",
    XdbServerGlobals + 24312,
    v444,
    0);
  LOBYTE(v445) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"HotPageTrackerRingBufferSize",
    XdbServerGlobals + 24316,
    v445,
    0);
  LOBYTE(v446) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"HotPageEstimatorRingBufferSize",
    XdbServerGlobals + 24320,
    v446,
    0);
  LOBYTE(v447) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"HotPageTrackerSendTriggerCount",
    XdbServerGlobals + 24324,
    v447,
    0);
  LOBYTE(v448) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"HotPageTrackerSwapTriggerCount",
    XdbServerGlobals + 24328,
    v448,
    0);
  LOBYTE(v449) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"HotPageEstimatorSwapTriggerCount",
    XdbServerGlobals + 24332,
    v449,
    0);
  IServerConfiguration::GetDynamicDoubleSetting(
    s_pServerConf,
    L"SQL",
    L"HotPageEstimatorEstimateScaleFactor",
    (double *)(XdbServerGlobals + 24336),
    1,
    0);
  IServerConfiguration::GetDynamicInt64Setting(
    s_pServerConf,
    L"SQL",
    L"HotPageEstimatorDecayUnitScaleFactor",
    (__int64 *)(XdbServerGlobals + 24344),
    1,
    0);
  IServerConfiguration::GetDynamicDoubleSetting(
    s_pServerConf,
    L"SQL",
    L"HotPageEstimatorDecayFactor",
    (double *)(XdbServerGlobals + 24352),
    1,
    0);
  LOBYTE(v450) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"HotPageTrackerSnapshotBucketTimeIntervalInSeconds",
    XdbServerGlobals + 24360,
    v450,
    0);
  LOBYTE(v451) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"HotPageTrackerMaxEmitWaitTimeInSeconds",
    XdbServerGlobals + 24364,
    v451,
    0);
  LOBYTE(v452) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"HotPageTrackerMaxSwapWaitTimeInMilliseconds",
    XdbServerGlobals + 24368,
    v452,
    0);
  LOBYTE(v453) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"HotPageEstimatorMaxSwapWaitTimeInMilliseconds",
    XdbServerGlobals + 24372,
    v453,
    0);
  IServerConfiguration::GetDynamicDoubleSetting(
    s_pServerConf,
    L"SQL",
    L"HotPageTrackerPrimedPagesCounterFalsePositiveRate",
    (double *)(XdbServerGlobals + 24376),
    1,
    0);
  LOBYTE(v454) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"HotPageMaxPageServersPriming",
    XdbServerGlobals + 24384,
    v454,
    0);
  LOBYTE(v455) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"WBCheckpointIntervalInSec",
    XdbServerGlobals + 24416,
    v455,
    0);
  LOBYTE(v456) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"WBRecoverySkipThresholdInMB",
    XdbServerGlobals + 24420,
    v456,
    0);
  LOBYTE(v457) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"WBRecoverySkipLtThresholdInMB",
    XdbServerGlobals + 24424,
    v457,
    0);
  LOBYTE(v458) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"WBRecoverySkipLogReadThresholdInSec",
    XdbServerGlobals + 24428,
    v458,
    0);
  LOBYTE(v459) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"WBRecoverySkipLogReadRateMonitorIntervalInSec",
    XdbServerGlobals + 24432,
    v459,
    0);
  LOBYTE(v460) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"WriteBehindCheckpointStuckThresholdInSec",
    XdbServerGlobals + 24444,
    v460,
    0);
  LOBYTE(v461) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"WriteBehindRbpexLimitInGB",
    XdbServerGlobals + 24448,
    v461,
    0);
  LOBYTE(v462) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"HotSegmentTrackerMaxEmitWaitTimeInMilliseconds",
    XdbServerGlobals + 24388,
    v462,
    0);
  LOBYTE(v463) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"HotSegmentTrackerHeartbeatWaitTimeInMinutes",
    XdbServerGlobals + 24392,
    v463,
    0);
  LOBYTE(v464) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"HotSegmentTrackerSimulatedSegmentSizeKB",
    XdbServerGlobals + 24396,
    v464,
    0);
  LOBYTE(v465) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"BufferPoolExtensionOverrideSizeInMB",
    XdbServerGlobals + 20456,
    v465,
    0);
  LOBYTE(v466) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"NonCoveringRbpexTargetPrimingPercentage",
    XdbServerGlobals + 20484,
    v466,
    0);
  v565 = 0;
  LOBYTE(v467) = 0;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, signed int *, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"NonCoveringRbpexSegmentSizeInKB",
    &v565,
    v467,
    0);
  v169 = v565;
  if ( v565 % 8 )
  {
    utassert_fail(1u, "nonCoveringRbpexSegmentSizeInKB % 8 == 0", "dbfabric.cpp", 8016, 0);
    v169 = v565;
  }
  if ( v169 > 0xFFFFF )
  {
    utassert_fail(
      1u,
      "nonCoveringRbpexSegmentSizeInKB >= 0 && nonCoveringRbpexSegmentSizeInKB < 1024 * 1024",
      "dbfabric.cpp",
      8017,
      0);
    v169 = v565;
  }
  if ( !v169 )
    v169 = 1024;
  v565 = v169;
  *(_DWORD *)(XdbServerGlobals + 20468) = v169;
  v566 = 0;
  LOBYTE(v468) = 0;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, int *, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"NonCoveringRbpexNumberOfFiles",
    &v566,
    v468,
    0);
  v170 = v566;
  if ( !v566 )
    v170 = 1;
  v566 = v170;
  *(_DWORD *)(XdbServerGlobals + 20472) = v170;
  v556 = 0;
  LOBYTE(v469) = 0;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, int *, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"NonCoveringRbpexFileStrideSizeInMB",
    &v556,
    v469,
    0);
  v171 = v556;
  if ( !v556 )
    v171 = 1;
  v556 = v171;
  *(_DWORD *)(XdbServerGlobals + 20476) = v171;
  v557 = 0;
  LOBYTE(v470) = 0;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, int *, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"CoveringRbpexSegmentSizeInMBForCAS",
    &v557,
    v470,
    0);
  *(_DWORD *)(XdbServerGlobals + 20464) = v557;
  v558 = 0;
  LOBYTE(v471) = 0;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, int *, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"NonCoveringRbpexWorkerThreads",
    &v558,
    v471,
    0);
  *(_DWORD *)(XdbServerGlobals + 20480) = v558;
  LOBYTE(v472) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"RbioDatabaseShutdownTimeoutInSec",
    XdbServerGlobals + 24400,
    v472,
    0);
  LOBYTE(v473) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"SQL",
          L"WriteBehindCheckpointIOSizeInKB",
          XdbServerGlobals + 24408,
          v473,
          0)
    || (v172 = RoundDown<int>(*(unsigned int *)(XdbServerGlobals + 24408), 8),
        (*(_DWORD *)(XdbServerGlobals + 24408) = v172) == 0) )
  {
    *(_DWORD *)(XdbServerGlobals + 24408) = 64;
  }
  LOBYTE(v474) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"SQL",
          L"WriteBehindCheckpointMaxIOSizeInKB",
          XdbServerGlobals + 24412,
          v474,
          0)
    || (v173 = RoundDown<int>(*(unsigned int *)(XdbServerGlobals + 24412), 8),
        (*(_DWORD *)(XdbServerGlobals + 24412) = v173) == 0) )
  {
    *(_DWORD *)(XdbServerGlobals + 24412) = 1024;
  }
  LOBYTE(v475) = 1;
  if ( (*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
         s_pServerConf,
         L"SQL",
         L"CoveringRbpexSeedingIOSizeInKB",
         XdbServerGlobals + 28332,
         v475,
         0) )
  {
    v174 = RoundDown<int>(*(unsigned int *)(XdbServerGlobals + 28332), 8);
  }
  else
  {
    v174 = 1024;
  }
  *(_DWORD *)(XdbServerGlobals + 28332) = v174;
  LOBYTE(v476) = 1;
  if ( (*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
         s_pServerConf,
         L"SQL",
         L"WriteBehindCheckpointBsnFlushRate",
         XdbServerGlobals + 24440,
         v476,
         0)
    || *(int *)(XdbServerGlobals + 24440) < 0 )
  {
    *(_DWORD *)(XdbServerGlobals + 24440) = 40;
  }
  LOBYTE(v477) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"SQL",
          L"WriteBehindCheckpointThrottleStatsIntervalMs",
          XdbServerGlobals + 24436,
          v477,
          0)
    || *(int *)(XdbServerGlobals + 24436) < 0 )
  {
    *(_DWORD *)(XdbServerGlobals + 24436) = 10;
  }
  LOBYTE(v478) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"HyperScaleServerless",
          L"RbpexZoneSizeMB",
          XdbServerGlobals + 24456,
          v478,
          0)
    || *(int *)(XdbServerGlobals + 24456) <= 0 )
  {
    *(_DWORD *)(XdbServerGlobals + 24456) = 1024;
  }
  LOBYTE(v479) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"HyperScaleServerless",
          L"RbpexIncrementalGrowSizeInMB",
          XdbServerGlobals + 24460,
          v479,
          0)
    || *(int *)(XdbServerGlobals + 24460) <= 0 )
  {
    *(_DWORD *)(XdbServerGlobals + 24460) = 1024;
  }
  LOBYTE(v480) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"HyperScaleServerless",
          L"RbpexInitialGraceSizeInMB",
          XdbServerGlobals + 24464,
          v480,
          0)
    || *(int *)(XdbServerGlobals + 24464) <= 0 )
  {
    *(_DWORD *)(XdbServerGlobals + 24464) = 0x2000;
  }
  LOBYTE(v481) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"HyperScaleServerless",
          L"EmitZoneHotnessTimeIntervalInSec",
          XdbServerGlobals + 24468,
          v481,
          0)
    || (v175 = RoundDown<int>(*(unsigned int *)(XdbServerGlobals + 24468), 60),
        *(_DWORD *)(XdbServerGlobals + 24468) = v175,
        v175 <= 0) )
  {
    *(_DWORD *)(XdbServerGlobals + 24468) = 60;
  }
  if ( !IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
          s_pServerConf,
          L"HyperScaleServerless",
          L"RbpexAdditionalBufferReportingMB",
          lambda_7fa5d9a969c554d66fa1eaad7a0a65d5_::_lambda_invoker_cdecl_,
          0,
          0) )
    *(_DWORD *)(GetXdbServerGlobals(v177, v176) + 24472) = 20480;
  if ( !IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
          s_pServerConf,
          L"HyperScaleServerless",
          L"RbpexGrowFailCountThresholdForEviction",
          lambda_3a9fbde99450dce4622a24dec6b215d2_::_lambda_invoker_cdecl_,
          0,
          0) )
    *(_DWORD *)(GetXdbServerGlobals(v179, v178) + 24484) = 10;
  if ( !IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
          s_pServerConf,
          L"HyperScaleServerless",
          L"RbpexGrowFailTimeThresholdForMaxSizeReportingSec",
          lambda_1708e47e9231ab16f9964e68318a215e_::_lambda_invoker_cdecl_,
          0,
          0) )
    *(_DWORD *)(GetXdbServerGlobals(v181, v180) + 24488) = 600;
  if ( !IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
          s_pServerConf,
          L"HyperScaleServerless",
          L"RbpexSegmentFragPercentToSkipGrow",
          lambda_340c773027155168cb3197cb5ac5627a_::_lambda_invoker_cdecl_,
          0,
          0) )
    *(_DWORD *)(GetXdbServerGlobals(v183, v182) + 24492) = 50;
  LOBYTE(v482) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"DegreeOfParallelCopyForUpdateSloSeeding",
    XdbServerGlobals + 28184,
    v482,
    0);
  LOBYTE(v483) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"RbIoForwarderMaxReadBufferSizeInPages",
    XdbServerGlobals + 24496,
    v483,
    0);
  LOBYTE(v484) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"RbIoForwarderIteratorRequestSizeInBsn",
    XdbServerGlobals + 24500,
    v484,
    0);
  LOBYTE(v485) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"RbIoForwarderIteratorMaxRequests",
    XdbServerGlobals + 24504,
    v485,
    0);
  LOBYTE(v486) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"RbIoForwarderIteratorMaxBuffers",
    XdbServerGlobals + 24508,
    v486,
    0);
  LOBYTE(v487) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"RbIoForwarderIteratorMaxBytesPerIteration",
    XdbServerGlobals + 24512,
    v487,
    0);
  LOBYTE(v488) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"RbioForwarderIteratorMaxIterationTimeInMs",
    XdbServerGlobals + 24516,
    v488,
    0);
  LOBYTE(v489) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"RbioForwarderIteratorClientIdCount",
    XdbServerGlobals + 24520,
    v489,
    0);
  LOBYTE(v490) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"LogReadWaitTimeAtEolMs",
    XdbServerGlobals + 24524,
    v490,
    0);
  LOBYTE(v491) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"LogReplicaLogPoolTruncationIntervalInMs",
    XdbServerGlobals + 24528,
    v491,
    0);
  LOBYTE(v492) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"RbIoUcsConnectionsPerEndpoint",
    XdbServerGlobals + 24532,
    v492,
    0);
  LOBYTE(v493) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"RbIoUcsConnectionsForForwarderXlogReader",
    XdbServerGlobals + 24536,
    v493,
    0);
  LOBYTE(v494) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"RbIoUcsConnectionUsage",
    XdbServerGlobals + 24540,
    v494,
    0);
  LOBYTE(v495) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"RbIoUcsConnectionUsageForForwarderXlogReader",
    XdbServerGlobals + 24544,
    v495,
    0);
  LOBYTE(v496) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"FailoverMaxWaitTimeOutForLogOrPageServerInSeconds",
    XdbServerGlobals + 24404,
    v496,
    0);
  LOBYTE(v497) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"MaxQueryMemoryRetainRatioForColumnStoreBulkInsert",
    XdbServerGlobals + 24548,
    v497,
    0);
  LOBYTE(v498) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"MaxQueryMemoryRetainRatioForColumnStoreReorganize",
    XdbServerGlobals + 24560,
    v498,
    0);
  LOBYTE(v499) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"Fido",
          L"FidoGarbageCollectionPeriod",
          XdbServerGlobals + 20904,
          v499,
          0) )
    *(_DWORD *)(XdbServerGlobals + 20904) = 600;
  LOBYTE(v500) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"SQL",
    L"ColumnStoreParallelInsertSelectDopThrottleIgnoreAdditionalMemoryRatio",
    XdbServerGlobals + 24552,
    v500,
    0);
  LOBYTE(v501) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"Fido",
          L"FidoBucketizationTempdbSpaceRatio",
          XdbServerGlobals + 20908,
          v501,
          0) )
    *(_DWORD *)(XdbServerGlobals + 20908) = 20;
  LOBYTE(v502) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"Fido",
          L"FidoBucketizationTempDbSizeCheckFrequencyInRows",
          XdbServerGlobals + 20912,
          v502,
          0) )
    *(_DWORD *)(XdbServerGlobals + 20912) = 10000;
  LOBYTE(v503) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"Fido",
          L"FidoBucketizationMaxTempdbUsageRatio",
          XdbServerGlobals + 20916,
          v503,
          0) )
    *(_DWORD *)(XdbServerGlobals + 20916) = 99;
  v184 = *(_QWORD *)s_pServerConf;
  v185 = SOS_Task::GetPmo();
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, struct IMemObj *, __int64, _QWORD))(v184 + 528))(
          s_pServerConf,
          L"DwCompat",
          L"DwValidCompatibilityLevels",
          v185,
          XdbServerGlobals + 20920,
          0) )
  {
    v186 = SOS_Node::GetPmo();
    v187 = (wchar_t *)operator new[](0x208u, v186, "sql\\ntdbms\\ksource\\dbfabric.cpp", 8374, 6u);
    *(_QWORD *)(XdbServerGlobals + 20920) = v187;
    StringCchCopyW(v187, 0x104u, L"10,20,30,40,9000");
  }
  LOBYTE(v504) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"DwCompat",
          L"DwMaxCompatibilityLevel",
          XdbServerGlobals + 20928,
          v504,
          0) )
    *(_DWORD *)(XdbServerGlobals + 20928) = 40;
  LOBYTE(v505) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"DwCompat",
          L"DwMinCompatibilityLevel",
          XdbServerGlobals + 20932,
          v505,
          0) )
    *(_DWORD *)(XdbServerGlobals + 20932) = 10;
  LOBYTE(v506) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"DwCompat",
          L"DwDefaultCompatibilityLevel",
          XdbServerGlobals + 20936,
          v506,
          0) )
    *(_DWORD *)(XdbServerGlobals + 20936) = 30;
  if ( !IServerConfiguration::GetDynamicInt64Setting(
          s_pServerConf,
          L"DwUqo",
          L"ComputeNodeDiskCapacityInBytes",
          (__int64 *)(XdbServerGlobals + 20944),
          1,
          0) )
    *(_QWORD *)(XdbServerGlobals + 20944) = 0x10000000000LL;
  LOBYTE(v507) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"DwUqo",
          L"ComputeNodeCores",
          XdbServerGlobals + 20952,
          v507,
          0) )
    *(_DWORD *)(XdbServerGlobals + 20952) = 12;
  if ( !IServerConfiguration::GetDynamicDoubleSetting(
          s_pServerConf,
          L"DwUqo",
          L"DwUQOForcedBulkloadMemoryEstimationFactor",
          (double *)(XdbServerGlobals + 20960),
          1,
          0) )
    *(_QWORD *)(XdbServerGlobals + 20960) = 0x3FF8000000000000LL;
  LOBYTE(v508) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"Fido",
          L"FidoBucketizationFireReceivedRowsXeventFrequencyDuringTempdbSizeCheck",
          XdbServerGlobals + 20968,
          v508,
          0) )
    *(_DWORD *)(XdbServerGlobals + 20968) = 100;
  LOBYTE(v509) = 0;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"Fido",
          L"FcsColumnAttributeCacheBucketCount",
          XdbServerGlobals + 20972,
          v509,
          0)
    || *(int *)(XdbServerGlobals + 20972) <= 0 )
  {
    if ( (unsigned int)IsVDWFrontendInstance() || (v188 = (unsigned int)IsXCopyInstance() == 0, v189 = 200003, !v188) )
      v189 = 10007;
    *(_DWORD *)(XdbServerGlobals + 20972) = v189;
  }
  if ( !IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
          s_pServerConf,
          L"Fido",
          L"FcsColumnAttributeCacheReadAheadSize",
          lambda_302df1edd28c80fc0febbdc994fee0aa_::_lambda_invoker_cdecl_,
          0,
          0) )
    *(_DWORD *)(XdbServerGlobals + 20976) = 128;
  if ( !IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
          s_pServerConf,
          L"Fido",
          L"FcsColumnAttributeCacheReadAheadMode",
          lambda_51f4edb24d11119aefef4487f2527d57_::_lambda_invoker_cdecl_,
          0,
          0) )
    *(_WORD *)(XdbServerGlobals + 19532) = 1;
  if ( !IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
          s_pServerConf,
          L"Fido",
          L"FidoPhysicalCatalogSyncMode",
          lambda_41004aea63185c4685060e3e4ad01872_::_lambda_invoker_cdecl_,
          0,
          0) )
    *(_WORD *)(XdbServerGlobals + 19534) = 0;
  LOBYTE(v510) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"Fido",
          L"FidoIndexStoreMinCacheMissForStableState",
          XdbServerGlobals + 20980,
          v510,
          0) )
    *(_DWORD *)(XdbServerGlobals + 20980) = 1000;
  if ( !IServerConfiguration::GetDynamicDoubleSetting(
          s_pServerConf,
          L"SocratesQpPushdownTelemetryConfig",
          L"SqpTelemetryScanSizeThreshold",
          (double *)(XdbServerGlobals + 28104),
          1,
          0) )
    *(_QWORD *)(XdbServerGlobals + 28104) = 0x3F50624DD2F1A9FCLL;
  if ( !IServerConfiguration::GetDynamicDoubleSetting(
          s_pServerConf,
          L"SocratesQpPushdownTelemetryConfig",
          L"SqpTelemetryDataReductionThreshold",
          (double *)(XdbServerGlobals + 28096),
          1,
          0) )
    *(_QWORD *)(XdbServerGlobals + 28096) = 0x3FE0000000000000LL;
  if ( !IServerConfiguration::GetDynamicDoubleSetting(
          s_pServerConf,
          L"SocratesQpPushdownSettings",
          L"SqpScanSizeThreshold",
          (double *)(XdbServerGlobals + 28120),
          1,
          0) )
    *(_QWORD *)(XdbServerGlobals + 28120) = 0x3FB999999999999ALL;
  if ( !IServerConfiguration::GetDynamicDoubleSetting(
          s_pServerConf,
          L"SocratesQpPushdownSettings",
          L"SqpDataReductionThreshold",
          (double *)(XdbServerGlobals + 28112),
          1,
          0) )
    *(_QWORD *)(XdbServerGlobals + 28112) = 0x3F847AE147AE147BLL;
  LOBYTE(v511) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"SocratesQpPushdownSettings",
          L"SqpPageIdCountPerRequest",
          XdbServerGlobals + 28160,
          v511,
          0) )
    *(_DWORD *)(XdbServerGlobals + 28160) = 2048;
  LOBYTE(v512) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"SocratesQpPushdownSettings",
          L"SqpComputeReadaheadRequestCount",
          XdbServerGlobals + 28164,
          v512,
          0) )
    *(_DWORD *)(XdbServerGlobals + 28164) = 64;
  LOBYTE(v513) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"SocratesQpPushdownSettings",
          L"SqpPageServerReadaheadPageCount",
          XdbServerGlobals + 28168,
          v513,
          0) )
    *(_DWORD *)(XdbServerGlobals + 28168) = 128;
  if ( !IServerConfiguration::GetDynamicInt64Setting(
          s_pServerConf,
          L"SocratesQpPushdownSettings",
          L"SqpRbioQueueUsedPagesCap",
          (__int64 *)(XdbServerGlobals + 28128),
          1,
          0)
    || *(__int64 *)(XdbServerGlobals + 28128) <= 0 )
  {
    *(_QWORD *)(XdbServerGlobals + 28128) = 0x10000;
  }
  if ( !IServerConfiguration::GetDynamicDoubleSetting(
          s_pServerConf,
          L"SocratesQpPushdownSettings",
          L"SqpPageIdsPerPageReducer",
          (double *)(XdbServerGlobals + 28136),
          1,
          0)
    || *(double *)(XdbServerGlobals + 28136) <= 0.0 )
  {
    *(_QWORD *)(XdbServerGlobals + 28136) = 0x3FF4CCCCCCCCCCCDLL;
  }
  LOBYTE(v514) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"SocratesQpPushdownSettings",
          L"SqpPageIdsPerPageUpSteps",
          XdbServerGlobals + 28144,
          v514,
          0)
    || *(int *)(XdbServerGlobals + 28144) <= 0 )
  {
    *(_DWORD *)(XdbServerGlobals + 28144) = 32;
  }
  LOBYTE(v515) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"SocratesQpPushdownSettings",
          L"SqpPageIdsPerPageDownSteps",
          XdbServerGlobals + 28148,
          v515,
          0)
    || *(int *)(XdbServerGlobals + 28148) <= 0 )
  {
    *(_DWORD *)(XdbServerGlobals + 28148) = 8;
  }
  LOBYTE(v516) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"SocratesQpPushdownSettings",
          L"SqpMinPagesPerHeapRange",
          XdbServerGlobals + 28152,
          v516,
          0)
    || *(int *)(XdbServerGlobals + 28152) <= 0 )
  {
    *(_DWORD *)(XdbServerGlobals + 28152) = 1024;
  }
  LOBYTE(v517) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"SocratesQpPushdownSettings",
          L"SqpMinPagesPerBtreeRange",
          XdbServerGlobals + 28156,
          v517,
          0)
    || *(int *)(XdbServerGlobals + 28156) <= 0 )
  {
    *(_DWORD *)(XdbServerGlobals + 28156) = 8;
  }
  LOBYTE(v518) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"SQL",
          L"BufferPoolEventThresholdInSeconds",
          XdbServerGlobals + 28172,
          v518,
          0) )
    *(_DWORD *)(XdbServerGlobals + 28172) = 1;
  LOBYTE(v519) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"SQL",
          L"VldbPlannedFailoverThrottlingRetryInMs",
          XdbServerGlobals + 28188,
          v519,
          0) )
    *(_DWORD *)(XdbServerGlobals + 28188) = 5000;
  LOBYTE(v520) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"SQL",
          L"VldbPlannedFailoverMinThresholdThrottlingRate",
          XdbServerGlobals + 28192,
          v520,
          0) )
    *(_DWORD *)(XdbServerGlobals + 28192) = 1024;
  LOBYTE(v521) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"SQL",
          L"VldbPlannedFailoverReadOnlyWindowInSec",
          XdbServerGlobals + 28196,
          v521,
          0) )
    *(_DWORD *)(XdbServerGlobals + 28196) = 1;
  LOBYTE(v522) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"SQL",
          L"VldbPlannedFailoverThrottlingLockTimeoutInSec",
          XdbServerGlobals + 28200,
          v522,
          0) )
    *(_DWORD *)(XdbServerGlobals + 28200) = 30;
  LOBYTE(v523) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"SQL",
          L"VldbPlannedFailoverRbRglogRefreshTimeoutInMs",
          XdbServerGlobals + 28204,
          v523,
          0) )
    *(_DWORD *)(XdbServerGlobals + 28204) = 5000;
  LOBYTE(v524) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"SQL",
          L"VldbPlannedFailoverTimeoutDurationInSec",
          XdbServerGlobals + 28228,
          v524,
          0) )
    *(_DWORD *)(XdbServerGlobals + 28228) = 300;
  LOBYTE(v525) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"SQL",
          L"DeadlockAcquireLockThresholdInMs",
          XdbServerGlobals + 28232,
          v525,
          0) )
    *(_DWORD *)(XdbServerGlobals + 28232) = 900000;
  if ( !IServerConfiguration::GetDynamicInt64Setting(
          s_pServerConf,
          L"SQL",
          L"ShrinkWaitLowPriorityTimeout",
          (__int64 *)(XdbServerGlobals + 28208),
          1,
          0) )
    *(_QWORD *)(XdbServerGlobals + 28208) = 0;
  LOBYTE(v526) = 0;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"SQL",
          L"SecurityCacheTokenAndPermUserStoreBuckets",
          XdbServerGlobals + 28236,
          v526,
          0) )
    *(_DWORD *)(XdbServerGlobals + 28236) = 0;
  LOBYTE(v527) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"SQL",
          L"VolumeTrafficPolicerTimerFrequencyMs",
          XdbServerGlobals + 28240,
          v527,
          0) )
    *(_DWORD *)(XdbServerGlobals + 28240) = 300000;
  LOBYTE(v528) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"SQL",
          L"VolumeTrafficPolicerTokenBucketFillIntervalMs",
          XdbServerGlobals + 28244,
          v528,
          0) )
    *(_DWORD *)(XdbServerGlobals + 28244) = 500;
  LOBYTE(v529) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"SQL",
          L"VolumeTrafficPolicerMaxRetriesForIOViolation",
          XdbServerGlobals + 28248,
          v529,
          0) )
    *(_DWORD *)(XdbServerGlobals + 28248) = 1000;
  LOBYTE(v530) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"SQL",
          L"GrowthInMBForLargeLogFile",
          XdbServerGlobals + 28312,
          v530,
          0) )
    *(_DWORD *)(XdbServerGlobals + 28312) = 0;
  LOBYTE(v531) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"SQL",
          L"GrowthInMBForLargeDataFile",
          XdbServerGlobals + 28316,
          v531,
          0) )
    *(_DWORD *)(XdbServerGlobals + 28316) = 0;
  LOBYTE(v532) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"SQL",
          L"MaxOutstandingReadsInPageServerRBPEXSeeding",
          XdbServerGlobals + 28320,
          v532,
          0) )
    *(_DWORD *)(XdbServerGlobals + 28320) = 32;
  LOBYTE(v533) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"SQL",
          L"RbpexAdditionalBufferReportingDcrsMB",
          XdbServerGlobals + 24476,
          v533,
          0) )
    *(_DWORD *)(XdbServerGlobals + 24476) = 10240;
  LOBYTE(v534) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)v559 + 520LL))(
          v559,
          L"SQL",
          L"RbpexDcrsFailpointBitmap",
          XdbServerGlobals + 24480,
          v534,
          0) )
    *(_DWORD *)(XdbServerGlobals + 24480) = 0;
  LOBYTE(v535) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)v559 + 520LL))(
          v559,
          L"SQL",
          L"MaxCoveringRbpexSeedingSnapshotRetryIntervalInSeconds",
          XdbServerGlobals + 28324,
          v535,
          0) )
    *(_DWORD *)(XdbServerGlobals + 28324) = 0;
  v190 = *(_QWORD *)v559;
  v191 = SOS_Task::GetPmo();
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, struct IMemObj *, __int64, _QWORD))(v190 + 528))(
          v559,
          L"ManagementServiceControlPlane",
          L"CmsOnTrDacFxDeploymentAppName",
          v191,
          XdbServerGlobals + 28360,
          0) )
    *(_QWORD *)(XdbServerGlobals + 28360) = L"DacFx Deploy";
  LOBYTE(v536) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)v559 + 520LL))(
          v559,
          L"SQL",
          L"MaxRBPEXSeedingConcurrency",
          XdbServerGlobals + 28328,
          v536,
          0) )
    *(_DWORD *)(XdbServerGlobals + 28328) = 2;
  LOBYTE(v537) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)v559 + 520LL))(
          v559,
          L"SQL",
          L"PercentageOfWritesSkippedToRBPEX",
          XdbServerGlobals + 28336,
          v537,
          0) )
    *(_DWORD *)(XdbServerGlobals + 28336) = 0;
  if ( !IServerConfiguration::GetDynamicInt64Setting(
          v559,
          L"SQL",
          L"HkLogBytesForCkpt",
          (__int64 *)(XdbServerGlobals + 29072),
          1,
          0) )
    *(_QWORD *)(XdbServerGlobals + 29072) = 0x20000000;
  LOBYTE(v538) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)v559 + 520LL))(
          v559,
          L"Polaris",
          L"AADRefreshTokenExpirationTime",
          XdbServerGlobals + 28900,
          v538,
          0) )
    *(_DWORD *)(XdbServerGlobals + 28900) = 6912000;
  LOBYTE(v539) = 1;
  v192 = v559;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)v559 + 520LL))(
    v559,
    L"ExternalRestEndpoints",
    L"ExternalRestEndpointMaxPayloadSizeBytes",
    XdbServerGlobals + 28904,
    v539,
    0);
  LOBYTE(v540) = 1;
  (*(void (__fastcall **)(IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)v192 + 520LL))(
    v192,
    L"ExternalRestEndpoints",
    L"ExternalRestEndpointMaxQueryStringLength",
    XdbServerGlobals + 28908,
    v540,
    0);
  LOBYTE(v541) = 1;
  (*(void (__fastcall **)(IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)v192 + 520LL))(
    v192,
    L"ExternalRestEndpoints",
    L"ExternalRestEndpointMaxUrlLength",
    XdbServerGlobals + 28912,
    v541,
    0);
  LOBYTE(v542) = 1;
  (*(void (__fastcall **)(IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)v192 + 520LL))(
    v192,
    L"ExternalRestEndpoints",
    L"ExternalRestEndpointResolveTimeout",
    XdbServerGlobals + 28916,
    v542,
    0);
  LOBYTE(v543) = 1;
  (*(void (__fastcall **)(IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)v192 + 520LL))(
    v192,
    L"ExternalRestEndpoints",
    L"ExternalRestEndpointConnectTimeout",
    XdbServerGlobals + 28920,
    v543,
    0);
  LOBYTE(v544) = 1;
  (*(void (__fastcall **)(IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)v192 + 520LL))(
    v192,
    L"ExternalRestEndpoints",
    L"ExternalRestEndpointSendTimeout",
    XdbServerGlobals + 28924,
    v544,
    0);
  LOBYTE(v545) = 1;
  (*(void (__fastcall **)(IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)v192 + 520LL))(
    v192,
    L"ExternalRestEndpoints",
    L"ExternalRestEndpointReceiveTimeout",
    XdbServerGlobals + 28928,
    v545,
    0);
  LOBYTE(v546) = 1;
  (*(void (__fastcall **)(IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)v192 + 520LL))(
    v192,
    L"ExternalRestEndpoints",
    L"ExternalRestEndpointMaxRequestHeaderSizeBytes",
    XdbServerGlobals + 28932,
    v546,
    0);
  IServerConfiguration::SubscribeAndGetDynamicStringSetting(
    v192,
    L"InMemSatelliteAppOOMMonitor",
    L"AppName",
    lambda_f89cb5160f06c52e8fb30f1342e2acac_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    v192,
    L"InMemSatelliteAppOOMMonitor",
    L"IntervalInSeconds",
    lambda_b536c24414b6a9dcb939f35840677cef_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    v192,
    L"InMemSatelliteAppOOMMonitor",
    L"MitigationMemPercent",
    lambda_159d4a3b16058d0edff6da28a6b57aa8_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    v192,
    L"Fido",
    L"DwFidoGlmControllerBackgroundTaskIntervalMs",
    lambda_07505010a303feef9318091d707f5f07_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    v192,
    L"Fido",
    L"DwFidoGlmBackupIntervalMin",
    lambda_4632f0272b96cc4a2619ead0f6f1f64b_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    v192,
    L"Fido",
    L"DwFidoGLogRetentionMin",
    lambda_a46645fa60809694b45b2a663f71eafc_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    v192,
    L"Fido",
    L"DwFidoGlmStoreDbTargetVersion",
    lambda_9350f5116970f0a822fa3d8bcc220c90_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    v192,
    L"Fido",
    L"DwFidoGlmCacheDbTargetVersion",
    lambda_13e42c0e4426213482899d5e9a156e5b_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    v192,
    L"Fido",
    L"DwFidoDbTargetVersion",
    lambda_6cc7f28838f404166de5d82d6960dd05_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    v192,
    L"Fido",
    L"DwFidoGlmMaxAsyncWorkerCount",
    lambda_e420220d767db3b9692d202258982c76_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    v192,
    L"Fido",
    L"DwFidoGlmIdleAsyncWorkerCount",
    lambda_21ee830be8ef16e2e86bde58c7402b13_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    v192,
    L"Fido",
    L"DwFidoTransportNumberOfRetriesToCloseUcsConnection",
    lambda_a9ff288b6d138582083250b172ff990e_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    v192,
    L"Fido",
    L"DwFidoTransportServerWaitTimeoutMs",
    lambda_da317907de017f9a75bac6bd246e18da_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    v192,
    L"Fido",
    L"DwFidoTransportRetryBackoffSec",
    lambda_8fcec558fe7c21f6f29370e32fcc4a33_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    v192,
    L"DwLakeCheckpointing",
    L"DwLakeCheckpointMaxDelayMinutes",
    lambda_1974279d86d5f7065680afc1f8a3e8d7_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    v192,
    L"DwLakeCheckpointing",
    L"DwLakeCheckpointMinDelayMinutes",
    lambda_08619d20bf7fb6925d0749b2a41163b4_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    v192,
    L"DwLakeCheckpointing",
    L"DwLakeCheckpointPeriodicTriggerIntervalSeconds",
    lambda_2f34dd677baeaf5defc28f448a808567_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    v192,
    L"DwLakeCheckpointing",
    L"DwLakeCheckpointDeltaLogCheckpointFileInterval",
    lambda_7a6d596f1ff9c1d7b21fe349d34443f1_::_lambda_invoker_cdecl_,
    0,
    0);
  LOBYTE(v547) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)v192 + 520LL))(
          v192,
          L"PolarisFrontend",
          L"SynapseMetastoreCreateDbValidationTimeoutMS",
          XdbServerGlobals + 28036,
          v547,
          0) )
    *(_DWORD *)(XdbServerGlobals + 28036) = 10000;
  if ( !IServerConfiguration::GetDynamicInt64Setting(
          v192,
          L"SQL",
          L"ShrinkFileIdForegroundLockTimeout",
          (__int64 *)(XdbServerGlobals + 28936),
          1,
          0) )
    *(_QWORD *)(XdbServerGlobals + 28936) = 0;
  LOBYTE(v548) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)v192 + 520LL))(
          v192,
          L"SQL",
          L"ShrinkFileIdMaxRetryCount",
          XdbServerGlobals + 28944,
          v548,
          0) )
    *(_DWORD *)(XdbServerGlobals + 28944) = 5;
  LOBYTE(v549) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)v192 + 520LL))(
          v192,
          L"SQL",
          L"ShrinkFileIdMaxWaitTimeBeforeRetry",
          XdbServerGlobals + 28948,
          v549,
          0) )
    *(_DWORD *)(XdbServerGlobals + 28948) = 60;
  LOBYTE(v550) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)v192 + 520LL))(
          v192,
          L"SQL",
          L"ShrinkFileIdWaitOnLowwatermarkWaitInterval",
          XdbServerGlobals + 28952,
          v550,
          0) )
    *(_DWORD *)(XdbServerGlobals + 28952) = 10;
  LOBYTE(v551) = 1;
  if ( !(*(unsigned __int8 (__fastcall **)(IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)v192 + 520LL))(
          v192,
          L"SQL",
          L"ShrinkFileIdWaitOnLowwatermarkWaitCount",
          XdbServerGlobals + 28956,
          v551,
          0) )
    *(_DWORD *)(XdbServerGlobals + 28956) = 6;
  LOBYTE(v552) = 1;
  (*(void (__fastcall **)(IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)v192 + 520LL))(
    v192,
    L"ExternalRuntimeConfig",
    L"ExternalRuntimeMaxPayloadSizeRows",
    XdbServerGlobals + 28960,
    v552,
    0);
  IServerConfiguration::GetDynamicInt64Setting(
    v192,
    L"ExternalRuntimeConfig",
    L"ExternalRuntimeMaxPayloadSizeBytes",
    (__int64 *)(XdbServerGlobals + 28968),
    1,
    0);
  LOBYTE(v553) = 1;
  (*(void (__fastcall **)(IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)v192 + 520LL))(
    v192,
    L"ExternalRuntimeConfig",
    L"ExternalRuntimeProtocolMaxRetryAttempts",
    XdbServerGlobals + 28976,
    v553,
    0);
  LOBYTE(v554) = 1;
  (*(void (__fastcall **)(IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)v192 + 520LL))(
    v192,
    L"ExternalRuntimeConfig",
    L"ExternalRuntimeProtocolMaxDelayInterval",
    XdbServerGlobals + 28980,
    v554,
    0);
  LOBYTE(v555) = 1;
  (*(void (__fastcall **)(IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, int, _QWORD))(*(_QWORD *)v192 + 520LL))(
    v192,
    L"ExternalRuntimeConfig",
    L"ExternalRuntimeProtocolDelayInterval",
    XdbServerGlobals + 28984,
    v555,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    v192,
    L"MultiPlan",
    L"MaxMultiPlanExpressions",
    lambda_a4d83efa798846b859e1385a7a4db1f2_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicDoubleSetting(
    v192,
    L"MultiPlan",
    L"MaxMinCardinalityRatio",
    lambda_d08a8797a63647b2868242eb06abc9e8_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicDoubleSetting(
    v192,
    L"MultiPlan",
    L"PredicateRangeLowBoundary",
    lambda_e32b171309396e8d973d52c6cb61c3c9_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicDoubleSetting(
    v192,
    L"MultiPlan",
    L"PredicateRangeHighBoundary",
    lambda_c26f67fc862684ea34932e395e28c720_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicDoubleSetting(
    v192,
    L"MultiPlan",
    L"StatsFrequencyPercentile",
    lambda_e646fab00436dfcd05f31682e7e01e2f_::_lambda_invoker_cdecl_,
    0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
    v192,
    L"MultiPlan",
    L"CompileCpuTimeThreshold",
    lambda_a1b8e51cfe09933bf0cdeec212c6e0cc_::_lambda_invoker_cdecl_,
    0,
    0);
  CAutoRg<void *>::~CAutoRg<void *>(v561);
}

```

## disassembly

```asm
0x10042a380  push    rbp
0x10042a382  push    rbx
0x10042a383  push    rsi
0x10042a384  push    rdi
0x10042a385  push    r12
0x10042a387  push    r13
0x10042a389  push    r14
0x10042a38b  push    r15
0x10042a38d  mov     rbp, rsp
0x10042a390  sub     rsp, 78h
0x10042a394  mov     [rbp+var_10], 0FFFFFFFFFFFFFFFEh
0x10042a39c  call    cs:__imp_GetXdbServerGlobals
0x10042a3a2  mov     r13, rax
0x10042a3a5  mov     rcx, cs:__imp_?s_pServerConf@@3PEAVIServerConfiguration@@EA; IServerConfiguration * s_pServerConf
0x10042a3ac  mov     rax, [rcx]
0x10042a3af  mov     [rbp+var_28], rax
0x10042a3b3  mov     r10, [rax]
0x10042a3b6  lea     r9, [r13+1FFCh]
0x10042a3bd  xor     r14d, r14d
0x10042a3c0  mov     [rsp+78h+var_50], r14
0x10042a3c5  mov     byte ptr [rsp+78h+var_58], 1
0x10042a3ca  lea     r8, aTrustservercer; "TrustServerCertificate"
0x10042a3d1  lea     rdx, aSql; "SQL"
0x10042a3d8  mov     rcx, rax
0x10042a3db  call    qword ptr [r10+208h]
0x10042a3e2  mov     rsi, [rbp+var_28]
0x10042a3e6  mov     rax, [rsi]
0x10042a3e9  lea     r9, [r13+2074h]
0x10042a3f0  mov     [rsp+78h+var_50], r14
0x10042a3f5  mov     byte ptr [rsp+78h+var_58], 1
0x10042a3fa  lea     r8, aUseslanguagelo; "UsesLanguageLockdown"
0x10042a401  lea     rdx, aSql; "SQL"
0x10042a408  mov     rcx, rsi
0x10042a40b  call    qword ptr [rax+208h]
0x10042a411  mov     rax, [rsi]
0x10042a414  lea     r9, [r13+3B84h]
0x10042a41b  mov     [rsp+78h+var_50], r14
0x10042a420  mov     byte ptr [rsp+78h+var_58], 1
0x10042a425  lea     r8, aUsesxstoreinfi; "UsesXStoreInfiniteLease"
0x10042a42c  lea     rdx, aSql; "SQL"
0x10042a433  mov     rcx, rsi
0x10042a436  call    qword ptr [rax+208h]
0x10042a43c  mov     rax, [rsi]
0x10042a43f  lea     r9, [r13+2000h]
0x10042a446  mov     [rsp+78h+var_50], r14
0x10042a44b  mov     byte ptr [rsp+78h+var_58], 1
0x10042a450  lea     r8, aIsabtestinstan; "IsAbTestInstance"
0x10042a457  lea     rdx, aSql; "SQL"
0x10042a45e  mov     rcx, rsi
0x10042a461  call    qword ptr [rax+208h]
0x10042a467  mov     rax, [rsi]
0x10042a46a  lea     r9, [r13+2004h]
0x10042a471  mov     [rsp+78h+var_50], r14
0x10042a476  mov     byte ptr [rsp+78h+var_58], 1
0x10042a47b  lea     r8, aIsisolatedabte; "IsIsolatedAbTestInstance"
0x10042a482  lea     rdx, aSql; "SQL"
0x10042a489  mov     rcx, rsi
0x10042a48c  call    qword ptr [rax+208h]
0x10042a492  lea     r9, [r13+3FA0h]; bool *
0x10042a499  mov     [rsp+78h+var_50], r14; wchar_t *
0x10042a49e  mov     byte ptr [rsp+78h+var_58], 1; bool
0x10042a4a3  lea     r8, aEnablehekaton; "EnableHekaton"
0x10042a4aa  lea     rdx, aSql; "SQL"
0x10042a4b1  mov     rcx, rsi; this
0x10042a4b4  call    ?GetDynamicBoolSetting@IServerConfiguration@@QEAA_NPEB_W0PEA_N_N0@Z; IServerConfiguration::GetDynamicBoolSetting(wchar_t const *,wchar_t const *,bool *,bool,wchar_t const *)
0x10042a4b9  lea     r9, [r13+3FA1h]; bool *
0x10042a4c0  mov     [rsp+78h+var_50], r14; wchar_t *
0x10042a4c5  mov     byte ptr [rsp+78h+var_58], 1; bool
0x10042a4ca  lea     r8, aEnableapollo; "EnableApollo"
0x10042a4d1  lea     rdx, aSql; "SQL"
0x10042a4d8  mov     rcx, rsi; this
0x10042a4db  call    ?GetDynamicBoolSetting@IServerConfiguration@@QEAA_NPEB_W0PEA_N_N0@Z; IServerConfiguration::GetDynamicBoolSetting(wchar_t const *,wchar_t const *,bool *,bool,wchar_t const *)
0x10042a4e0  mov     rax, [rsi]
0x10042a4e3  lea     r9, [r13+3FACh]
0x10042a4ea  mov     [rsp+78h+var_50], r14
0x10042a4ef  mov     byte ptr [rsp+78h+var_58], 1
0x10042a4f4  lea     r8, aIsisolateddata; "IsIsolatedDatabaseInstance"
0x10042a4fb  lea     rdx, aSql; "SQL"
0x10042a502  mov     rcx, rsi
0x10042a505  call    qword ptr [rax+208h]
0x10042a50b  mov     rax, [rsi]
0x10042a50e  lea     r9, [r13+3FB0h]
0x10042a515  mov     [rsp+78h+var_50], r14
0x10042a51a  mov     byte ptr [rsp+78h+var_58], 1
0x10042a51f  lea     r8, aIsisolateddata; "IsIsolatedDatabaseInstance"
0x10042a526  lea     rdx, aSql; "SQL"
0x10042a52d  mov     rcx, rsi
0x10042a530  call    qword ptr [rax+208h]
0x10042a536  mov     rax, [rsi]
0x10042a539  lea     r9, [r13+5E64h]
0x10042a540  mov     [rsp+78h+var_50], r14
0x10042a545  mov     byte ptr [rsp+78h+var_58], 1
0x10042a54a  lea     r8, aFiltereddumppe; "FilteredDumpPercentage"
0x10042a551  lea     rdx, aSql; "SQL"
0x10042a558  mov     rcx, rsi
0x10042a55b  call    qword ptr [rax+208h]
0x10042a561  mov     rax, [rsi]
0x10042a564  lea     r9, [r13+5E68h]
0x10042a56b  mov     [rsp+78h+var_50], r14
0x10042a570  mov     byte ptr [rsp+78h+var_58], 1
0x10042a575  lea     r8, aDumpuploadmode; "DumpUploadMode"
0x10042a57c  lea     rdx, aSql; "SQL"
0x10042a583  mov     rcx, rsi
0x10042a586  call    qword ptr [rax+208h]
0x10042a58c  mov     rax, [rsi]
0x10042a58f  lea     r9, [r13+5E6Ch]
0x10042a596  mov     [rsp+78h+var_50], r14
0x10042a59b  mov     byte ptr [rsp+78h+var_58], 1
0x10042a5a0  lea     r8, aVersioncleaner; "VersionCleanerHobtLockTimeoutInMS"
0x10042a5a7  lea     rdx, aSql; "SQL"
0x10042a5ae  mov     rcx, rsi
0x10042a5b1  call    qword ptr [rax+208h]
0x10042a5b7  mov     rax, [rsi]
0x10042a5ba  lea     r9, [r13+5E70h]
0x10042a5c1  mov     [rsp+78h+var_50], r14
0x10042a5c6  mov     byte ptr [rsp+78h+var_58], 1
0x10042a5cb  lea     r8, aNondatapagessw; "NonDataPagesSweptPercentThreshold"
0x10042a5d2  lea     rdx, aSql; "SQL"
0x10042a5d9  mov     rcx, rsi
0x10042a5dc  call    qword ptr [rax+208h]
0x10042a5e2  mov     rax, [rsi]
0x10042a5e5  lea     r9, [r13+5E74h]
0x10042a5ec  mov     [rsp+78h+var_50], r14
0x10042a5f1  mov     byte ptr [rsp+78h+var_58], 1
0x10042a5f6  lea     r8, aVersioncleaner_2; "VersionCleanerPvsCleanupTimeInMinutes"
0x10042a5fd  lea     rdx, aSql; "SQL"
0x10042a604  mov     rcx, rsi
0x10042a607  call    qword ptr [rax+208h]
0x10042a60d  mov     rax, [rsi]
0x10042a610  lea     r9, [r13+5E78h]
0x10042a617  mov     [rsp+78h+var_50], r14
0x10042a61c  mov     byte ptr [rsp+78h+var_58], 1
0x10042a621  lea     r8, aVersioncleaner_0; "VersionCleanerSideListSweepTimeoutInMin"...
0x10042a628  lea     rdx, aSql; "SQL"
0x10042a62f  mov     rcx, rsi
0x10042a632  call    qword ptr [rax+208h]
0x10042a638  mov     rax, [rsi]
0x10042a63b  lea     r9, [r13+5E80h]
0x10042a642  mov     [rsp+78h+var_50], r14
0x10042a647  mov     byte ptr [rsp+78h+var_58], 1
0x10042a64c  lea     r8, aAbortedtransac; "AbortedTransactionMapNumberOfBuckets"
0x10042a653  lea     rdx, aSql; "SQL"
0x10042a65a  mov     rcx, rsi
0x10042a65d  call    qword ptr [rax+208h]
0x10042a663  mov     rax, [rsi]
0x10042a666  lea     r9, [r13+5E84h]
0x10042a66d  mov     [rsp+78h+var_50], r14
0x10042a672  mov     byte ptr [rsp+78h+var_58], 1
0x10042a677  lea     r8, aVersionpagesre; "VersionPagesReadAheadBatchSize"
0x10042a67e  lea     rdx, aSql; "SQL"
0x10042a685  mov     rcx, rsi
0x10042a688  call    qword ptr [rax+208h]
0x10042a68e  mov     rax, [rsi]
0x10042a691  lea     r9, [r13+5E88h]
0x10042a698  mov     [rsp+78h+var_50], r14
0x10042a69d  mov     byte ptr [rsp+78h+var_58], 1
0x10042a6a2  lea     r8, aShorttranlogre; "ShortTranLogRecCountThreshold"
0x10042a6a9  lea     rdx, aSql; "SQL"
0x10042a6b0  mov     rcx, rsi
0x10042a6b3  call    qword ptr [rax+208h]
0x10042a6b9  mov     rax, [rsi]
0x10042a6bc  lea     r9, [r13+5E8Ch]
0x10042a6c3  mov     [rsp+78h+var_50], r14
0x10042a6c8  mov     byte ptr [rsp+78h+var_58], 1
0x10042a6cd  lea     r8, aShorttranlogus; "ShortTranLogUsedThresholdInMB"
0x10042a6d4  lea     rdx, aSql; "SQL"
0x10042a6db  mov     rcx, rsi
0x10042a6de  call    qword ptr [rax+208h]
0x10042a6e4  mov     rax, [rsi]
0x10042a6e7  lea     r9, [r13+5E90h]
0x10042a6ee  mov     [rsp+78h+var_50], r14
0x10042a6f3  mov     byte ptr [rsp+78h+var_58], 1
0x10042a6f8  lea     r8, aCloudserverdbv; "CloudServerDbVersion"
0x10042a6ff  lea     rdx, aSql; "SQL"
0x10042a706  mov     rcx, rsi
0x10042a709  call    qword ptr [rax+208h]
0x10042a70f  mov     rax, [rsi]
0x10042a712  mov     [rsp+78h+var_50], r14
0x10042a717  mov     byte ptr [rsp+78h+var_58], 1
0x10042a71c  lea     r9, [r13+4CA4h]
0x10042a723  lea     r8, aMaxwaittimefor_0; "MaxWaitTimeForAnyReplicaInRbioInitLocal"...
0x10042a72a  lea     rdx, aSql; "SQL"
0x10042a731  mov     rcx, rsi
0x10042a734  call    qword ptr [rax+208h]
0x10042a73a  test    al, al
0x10042a73c  jnz     short loc_10042A749
0x10042a73e  mov     dword ptr [r13+4CA4h], 384h
0x10042a749  mov     rax, [rsi]
0x10042a74c  mov     [rsp+78h+var_50], r14
0x10042a751  mov     byte ptr [rsp+78h+var_58], 1
0x10042a756  lea     r9, [r13+4CA8h]
0x10042a75d  lea     r8, aMaxwaittimefor; "MaxWaitTimeForAllReplicasInRbioInitLoca"...
0x10042a764  lea     rdx, aSql; "SQL"
0x10042a76b  mov     rcx, rsi
0x10042a76e  call    qword ptr [rax+208h]
0x10042a774  test    al, al
0x10042a776  jnz     short loc_10042A783
0x10042a778  mov     dword ptr [r13+4CA8h], 1Eh
0x10042a783  mov     rax, [rsi]
0x10042a786  mov     [rsp+78h+var_50], r14
0x10042a78b  mov     byte ptr [rsp+78h+var_58], 1
0x10042a790  lea     r9, [r13+5EC0h]
0x10042a797  lea     r8, aCtrversionclea; "CTRVersionCleanupPolicyForPVSPage"
0x10042a79e  lea     rdx, aSql; "SQL"
0x10042a7a5  mov     rcx, rsi
0x10042a7a8  call    qword ptr [rax+208h]
0x10042a7ae  test    al, al
0x10042a7b0  jnz     short loc_10042A7B9
0x10042a7b2  mov     [r13+5EC0h], r14d
0x10042a7b9  mov     rax, [rsi]
0x10042a7bc  mov     [rsp+78h+var_50], r14
0x10042a7c1  mov     byte ptr [rsp+78h+var_58], 1
0x10042a7c6  lea     r9, [r13+5E94h]
0x10042a7cd  lea     r8, aPvspreallocati_0; "PvsPreAllocationMaxExtentsInFreeList"
0x10042a7d4  lea     rdx, aSql; "SQL"
0x10042a7db  mov     rcx, rsi
0x10042a7de  call    qword ptr [rax+208h]
0x10042a7e4  test    al, al
0x10042a7e6  jnz     short loc_10042A7EF
0x10042a7e8  mov     [r13+5E94h], r14d
0x10042a7ef  mov     rax, [rsi]
0x10042a7f2  mov     [rsp+78h+var_50], r14
0x10042a7f7  mov     byte ptr [rsp+78h+var_58], 1
0x10042a7fc  lea     r9, [r13+5E98h]
0x10042a803  lea     r8, aPvspreallocati; "PvsPreAllocationFactor"
0x10042a80a  lea     rdx, aSql; "SQL"
0x10042a811  mov     rcx, rsi
0x10042a814  call    qword ptr [rax+208h]
0x10042a81a  test    al, al
0x10042a81c  jnz     short loc_10042A825
0x10042a81e  mov     [r13+5E98h], r14d
0x10042a825  mov     rax, [rsi]
0x10042a828  mov     [rsp+78h+var_50], r14
0x10042a82d  mov     byte ptr [rsp+78h+var_58], 1
0x10042a832  lea     r9, [r13+5E7Ch]
0x10042a839  lea     r8, aVersioncleaner_1; "VersionCleanerDirtyPageFileSwitchThresh"...
0x10042a840  lea     rdx, aSql; "SQL"
0x10042a847  mov     rcx, rsi
0x10042a84a  call    qword ptr [rax+208h]
0x10042a850  test    al, al
0x10042a852  jnz     short loc_10042A85B
0x10042a854  mov     [r13+5E7Ch], r14d
0x10042a85b  mov     rax, [rsi]
0x10042a85e  mov     [rsp+78h+var_50], r14
0x10042a863  mov     byte ptr [rsp+78h+var_58], 1
0x10042a868  lea     r9, [r13+6058h]
0x10042a86f  lea     r8, aNonctrtxlogrec; "NonCtrTxLogRecordCountThreshold"
0x10042a876  lea     rdx, aSql; "SQL"
0x10042a87d  mov     rcx, rsi
0x10042a880  call    qword ptr [rax+208h]
0x10042a886  test    al, al
0x10042a888  jnz     short loc_10042A895
0x10042a88a  mov     dword ptr [r13+6058h], 2710h
0x10042a895  mov     rax, [rsi]
0x10042a898  mov     [rsp+78h+var_50], r14
0x10042a89d  mov     byte ptr [rsp+78h+var_58], 1
0x10042a8a2  lea     r9, [r13+605Ch]
0x10042a8a9  lea     r8, aNonctrtxlogsiz; "NonCtrTxLogSizeThresholdInMB"
0x10042a8b0  lea     rdx, aSql; "SQL"
0x10042a8b7  mov     rcx, rsi
0x10042a8ba  call    qword ptr [rax+208h]
0x10042a8c0  test    al, al
0x10042a8c2  jnz     short loc_10042A8CF
0x10042a8c4  mov     dword ptr [r13+605Ch], 3E8h
0x10042a8cf  mov     rax, [rsi]
0x10042a8d2  mov     [rsp+78h+var_50], r14
0x10042a8d7  mov     byte ptr [rsp+78h+var_58], 1
0x10042a8dc  lea     r9, [r13+6108h]
0x10042a8e3  lea     r8, aPvsforceupdate; "PvsForceUpdateLowWatermarkThresholdInMB"
0x10042a8ea  lea     rdx, aSql; "SQL"
0x10042a8f1  mov     rcx, rsi
0x10042a8f4  call    qword ptr [rax+208h]
0x10042a8fa  test    al, al
0x10042a8fc  jnz     short loc_10042A909
0x10042a8fe  mov     dword ptr [r13+6108h], 19000h
0x10042a909  mov     rax, [rsi]
0x10042a90c  mov     [rsp+78h+var_50], r14
0x10042a911  mov     byte ptr [rsp+78h+var_58], 1
0x10042a916  lea     r9, [r13+6EB4h]
0x10042a91d  lea     r8, aXdeshistoryhas; "XdesHistoryHashTableBucketCount"
0x10042a924  lea     rdx, aSql; "SQL"
0x10042a92b  mov     rcx, rsi
0x10042a92e  call    qword ptr [rax+208h]
0x10042a934  test    al, al
0x10042a936  jnz     short loc_10042A943
0x10042a938  mov     dword ptr [r13+6EB4h], 0C07h
0x10042a943  mov     rax, [rsi]
0x10042a946  mov     [rsp+78h+var_50], r14
0x10042a94b  mov     byte ptr [rsp+78h+var_58], 1
0x10042a950  lea     r9, [r13+7158h]
0x10042a957  lea     r8, aMtvcpfspageswi; "MTVCPfsPageSwitchThreshold"
0x10042a95e  lea     rdx, aSql; "SQL"
0x10042a965  mov     rcx, rsi
0x10042a968  call    qword ptr [rax+208h]
0x10042a96e  test    al, al
0x10042a970  jnz     short loc_10042A97D
0x10042a972  mov     dword ptr [r13+7158h], 2
0x10042a97d  mov     rax, [rsi]
0x10042a980  mov     [rsp+78h+var_50], r14
0x10042a985  mov     byte ptr [rsp+78h+var_58], 1
  ... truncated ...
```
