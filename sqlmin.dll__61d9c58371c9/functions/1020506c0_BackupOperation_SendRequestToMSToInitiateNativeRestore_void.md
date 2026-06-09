# BackupOperation::SendRequestToMSToInitiateNativeRestore(void)

- ea: `0x1020506c0`
- end: `0x10205190a`
- name: `?SendRequestToMSToInitiateNativeRestore@BackupOperation@@AEAAXXZ`
- size: `4682`
- prototype: `void __fastcall(BackupOperation *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x10204ba10`

## callees

- `0x100401490`
- `0x100401fcf`
- `0x100402920`
- `0x100415e90`
- `0x1005c06d0`
- `0x100626050`
- `0x10078c7c0`
- `0x100799940`
- `0x101807bf0`
- `0x101fc9d70`
- `0x10204f520`
- `0x1020506c0`
- `0x1023af450`

## import_xrefs

- `KERNEL32!MultiByteToWideChar` at `0x10205117e`
- `KERNEL32!MultiByteToWideChar` at `0x1020511e3`
- `KERNEL32!MultiByteToWideChar` at `0x102051352`
- `KERNEL32!MultiByteToWideChar` at `0x1020513af`
- `KERNEL32!MultiByteToWideChar` at `0x10205117e`
- `KERNEL32!MultiByteToWideChar` at `0x1020511e3`
- `KERNEL32!MultiByteToWideChar` at `0x102051352`
- `KERNEL32!MultiByteToWideChar` at `0x1020513af`
- `sqlTsEs!?WszFromWsz@@YAPEA_WPEAVIMemObj@@PEB_WPEAH@Z` at `0x102050785`
- `sqlTsEs!?WszFromWsz@@YAPEA_WPEAVIMemObj@@PEB_WPEAH@Z` at `0x102050fbd`
- `sqlTsEs!?WszFromWsz@@YAPEA_WPEAVIMemObj@@PEB_WPEAH@Z` at `0x102051042`
- `sqlTsEs!?WszFromWsz@@YAPEA_WPEAVIMemObj@@PEB_WPEAH@Z` at `0x102050785`
- `sqlTsEs!?WszFromWsz@@YAPEA_WPEAVIMemObj@@PEB_WPEAH@Z` at `0x102050fbd`
- `sqlTsEs!?WszFromWsz@@YAPEA_WPEAVIMemObj@@PEB_WPEAH@Z` at `0x102051042`
- `sqlTsEs!?WszFromWsLen@@YAPEA_WPEAVIMemObj@@PEB_WH@Z` at `0x1020507bf`
- `sqlTsEs!?WszFromWsLen@@YAPEA_WPEAVIMemObj@@PEB_WH@Z` at `0x102050fab`
- `sqlTsEs!?WszFromWsLen@@YAPEA_WPEAVIMemObj@@PEB_WH@Z` at `0x102051030`
- `sqlTsEs!?WszFromWsLen@@YAPEA_WPEAVIMemObj@@PEB_WH@Z` at `0x1020507bf`
- `sqlTsEs!?WszFromWsLen@@YAPEA_WPEAVIMemObj@@PEB_WH@Z` at `0x102050fab`
- `sqlTsEs!?WszFromWsLen@@YAPEA_WPEAVIMemObj@@PEB_WH@Z` at `0x102051030`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x102050b4e`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x102050897`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x102050968`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x102050b14`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x102050e2c`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x102050f27`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1020510b0`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1020511af`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10205127a`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10205137f`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1020515e4`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10205164b`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x102050897`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x102050968`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x102050b14`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x102050e2c`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x102050f27`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1020510b0`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1020511af`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10205127a`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10205137f`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1020515e4`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10205164b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10205076a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x102050c35`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x102050c7b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x102050ca1`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10205076a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x102050c35`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x102050c7b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x102050ca1`
- `sqldk!SystemThread_TlsIndex` at `0x102050f5b`
- `sqldk!SystemThread_TlsIndex` at `0x102050ff0`
- `sqldk!SystemThread_TlsOffset` at `0x102050f64`
- `sqldk!SystemThread_TlsOffset` at `0x102050ff9`
- `sqldk!??_V@YAXPEAX@Z` at `0x10205097c`
- `sqldk!??_V@YAXPEAX@Z` at `0x1020509d1`
- `sqldk!??_V@YAXPEAX@Z` at `0x102050a1e`
- `sqldk!??_V@YAXPEAX@Z` at `0x102050b24`
- `sqldk!??_V@YAXPEAX@Z` at `0x102050e3c`
- `sqldk!??_V@YAXPEAX@Z` at `0x1020510ce`
- `sqldk!??_V@YAXPEAX@Z` at `0x1020511c3`
- `sqldk!??_V@YAXPEAX@Z` at `0x102051206`
- `sqldk!??_V@YAXPEAX@Z` at `0x102051292`
- `sqldk!??_V@YAXPEAX@Z` at `0x10205138f`
- `sqldk!??_V@YAXPEAX@Z` at `0x1020513cd`
- `sqldk!??_V@YAXPEAX@Z` at `0x102051480`
- `sqldk!??_V@YAXPEAX@Z` at `0x1020515f6`
- `sqldk!??_V@YAXPEAX@Z` at `0x10205165b`
- `sqldk!??_V@YAXPEAX@Z` at `0x1020517ef`
- `sqldk!??_V@YAXPEAX@Z` at `0x1020517f9`
- `sqldk!??_V@YAXPEAX@Z` at `0x102051804`
- `sqldk!??_V@YAXPEAX@Z` at `0x102051810`
- `sqldk!??_V@YAXPEAX@Z` at `0x10205181b`
- `sqldk!??_V@YAXPEAX@Z` at `0x102051825`
- `sqldk!??_V@YAXPEAX@Z` at `0x10205182f`
- `sqldk!??_V@YAXPEAX@Z` at `0x102051839`
- `sqldk!??_V@YAXPEAX@Z` at `0x102051844`
- `sqldk!??_V@YAXPEAX@Z` at `0x10205184f`
- `sqldk!??_V@YAXPEAX@Z` at `0x10205185a`
- `sqldk!??_V@YAXPEAX@Z` at `0x102051865`
- `sqldk!??_V@YAXPEAX@Z` at `0x10205189d`
- `sqldk!??_V@YAXPEAX@Z` at `0x1020518a8`
- `sqldk!??_V@YAXPEAX@Z` at `0x1020518b3`
- `sqldk!??_V@YAXPEAX@Z` at `0x1020518be`
- `sqldk!??_V@YAXPEAX@Z` at `0x1020518c9`
- `sqldk!??_V@YAXPEAX@Z` at `0x1020518d4`
- `sqldk!??_V@YAXPEAX@Z` at `0x10205097c`
- `sqldk!??_V@YAXPEAX@Z` at `0x1020509d1`
- `sqldk!??_V@YAXPEAX@Z` at `0x102050a1e`
- `sqldk!??_V@YAXPEAX@Z` at `0x102050b24`
- `sqldk!??_V@YAXPEAX@Z` at `0x102050e3c`
- `sqldk!??_V@YAXPEAX@Z` at `0x1020510ce`
- `sqldk!??_V@YAXPEAX@Z` at `0x1020511c3`
- `sqldk!??_V@YAXPEAX@Z` at `0x102051206`
- `sqldk!??_V@YAXPEAX@Z` at `0x102051292`
- `sqldk!??_V@YAXPEAX@Z` at `0x10205138f`
- `sqldk!??_V@YAXPEAX@Z` at `0x1020513cd`
- `sqldk!??_V@YAXPEAX@Z` at `0x102051480`
- `sqldk!??_V@YAXPEAX@Z` at `0x1020515f6`
- `sqldk!??_V@YAXPEAX@Z` at `0x10205165b`
- `sqldk!??_V@YAXPEAX@Z` at `0x1020517ef`
- `sqldk!??_V@YAXPEAX@Z` at `0x1020517f9`
- `sqldk!??_V@YAXPEAX@Z` at `0x102051804`
- `sqldk!??_V@YAXPEAX@Z` at `0x102051810`
- `sqldk!??_V@YAXPEAX@Z` at `0x10205181b`
- `sqldk!??_V@YAXPEAX@Z` at `0x102051825`
- `sqldk!??_V@YAXPEAX@Z` at `0x10205182f`
- `sqldk!??_V@YAXPEAX@Z` at `0x102051839`
- `sqldk!??_V@YAXPEAX@Z` at `0x102051844`
- `sqldk!??_V@YAXPEAX@Z` at `0x10205184f`
- `sqldk!??_V@YAXPEAX@Z` at `0x10205185a`
- `sqldk!??_V@YAXPEAX@Z` at `0x102051865`
- `sqldk!??_V@YAXPEAX@Z` at `0x10205189d`
- `sqldk!??_V@YAXPEAX@Z` at `0x1020518a8`
- `sqldk!??_V@YAXPEAX@Z` at `0x1020518b3`
- `sqldk!??_V@YAXPEAX@Z` at `0x1020518be`
- `sqldk!??_V@YAXPEAX@Z` at `0x1020518c9`
- `sqldk!??_V@YAXPEAX@Z` at `0x1020518d4`
- `sqllang!?SendAsyncGlobalClusterInternalServerActionRequest@@YAXPEAVIMemObj@@W4DBSQLStmtType@XeCloudPkg@@_NPEA_WPEB_W33333422@Z` at `0x1020517e5`
- `sqllang!?SendAsyncGlobalClusterInternalServerActionRequest@@YAXPEAVIMemObj@@W4DBSQLStmtType@XeCloudPkg@@_NPEA_WPEB_W33333422@Z` at `0x1020517e5`
- `sqllang!?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ` at `0x10205121e`
- `sqllang!?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ` at `0x102051665`
- `sqllang!?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ` at `0x10205121e`
- `sqllang!?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ` at `0x102051665`

## string_xrefs

- `0x10205095a`: `sql\ntdbms\include\Xhttpcommon.h`
- `0x102051737`: `d:CreateManagedDatabaseNativeRestoreRequestV2`
- `0x102051730`: `CreateManagedDatabaseNativeRestoreRequestV2`
- `0x102051786`: `Calls Management Service to create a managed database %s on a managed server: %s. Action: %s. Payload: %s\n`
- `0x102051763`: `{ "managedServerName": "%s", "managedDatabaseName": "%s", "files": [ %s ], "ownerSid": "%s", "expectedSizeBytes": "%s" }`
- `0x102051716`: `{ "managedServerName": "%s", "managedDatabaseName": "%s", "restoreDevices": [ %s ], "files": [ %s ], "ownerSid": "%s", "expectedSizeBytes": "%s" }`
- `0x1020516df`: `d:CreateManagedDatabaseNativeRestoreRequestV3`
- `0x1020516d8`: `CreateManagedDatabaseNativeRestoreRequestV3`
- `0x1020516be`: `{ "managedServerName": "%s", "managedDatabaseName": "%s", "restoreDevices": [ %s ], "files": [ %s ], "ownerSid": "%s", "expectedSizeBytes": "%s", "tdeCertificateThumbprint": "%s" }`
- `0x102050b71`: `RestoreService`
- `0x102050bac`: `RestoreService`

## pseudocode

```c

```
