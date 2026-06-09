# CSECDEK::DecryptCurrDEKWithAKV(IMetadataAccess *,IMEDAsymmetricKey *,_GUID,bool)

- ea: `0x1014da610`
- end: `0x1014db7de`
- name: `?DecryptCurrDEKWithAKV@CSECDEK@@AEAAXPEAVIMetadataAccess@@PEAVIMEDAsymmetricKey@@U_GUID@@_N@Z`
- size: `4558`
- prototype: `void __fastcall(CSECDEK *__hidden this, struct IMetadataAccess *, struct IMEDAsymmetricKey *, struct _GUID *, bool)`
- caller_count: `1`
- callee_count: `19`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1014d9170`

## callees

- `0x100401070`
- `0x100401090`
- `0x100403080`
- `0x10041154d`
- `0x100754350`
- `0x100755b10`
- `0x10121d760`
- `0x10121d890`
- `0x10149cf70`
- `0x10149e850`
- `0x1014c5210`
- `0x1014d7610`
- `0x1014da610`
- `0x1014dc130`
- `0x1014dfa60`
- `0x1014e03b0`
- `0x1014e72b0`
- `0x101e4fcd0`
- `0x101e88fe0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1014da9cf`
- `KERNEL32!GetLastError` at `0x1014dab20`
- `KERNEL32!GetLastError` at `0x1014dabd6`
- `KERNEL32!GetLastError` at `0x1014daf25`
- `KERNEL32!GetLastError` at `0x1014db01a`
- `KERNEL32!GetLastError` at `0x1014db426`
- `KERNEL32!GetLastError` at `0x1014da9cf`
- `KERNEL32!GetLastError` at `0x1014dab20`
- `KERNEL32!GetLastError` at `0x1014dabd6`
- `KERNEL32!GetLastError` at `0x1014daf25`
- `KERNEL32!GetLastError` at `0x1014db01a`
- `KERNEL32!GetLastError` at `0x1014db426`
- `ole32!StringFromGUID2` at `0x1014daeba`
- `ole32!StringFromGUID2` at `0x1014dafb1`
- `ole32!StringFromGUID2` at `0x1014db100`
- `ole32!StringFromGUID2` at `0x1014db212`
- `ole32!StringFromGUID2` at `0x1014db298`
- `ole32!StringFromGUID2` at `0x1014db38e`
- `ole32!StringFromGUID2` at `0x1014daeba`
- `ole32!StringFromGUID2` at `0x1014dafb1`
- `ole32!StringFromGUID2` at `0x1014db100`
- `ole32!StringFromGUID2` at `0x1014db212`
- `ole32!StringFromGUID2` at `0x1014db298`
- `ole32!StringFromGUID2` at `0x1014db38e`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1014da7e5`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1014db74a`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1014da7e5`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1014db74a`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x1014da98f`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x1014daabf`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x1014dae7d`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x1014db3eb`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x1014da98f`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x1014daabf`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x1014dae7d`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x1014db3eb`
- `sqldk!SystemThread_TlsIndex` at `0x1014da678`
- `sqldk!SystemThread_TlsIndex` at `0x1014daa69`
- `sqldk!SystemThread_TlsIndex` at `0x1014dae27`
- `sqldk!SystemThread_TlsOffset` at `0x1014da681`
- `sqldk!SystemThread_TlsOffset` at `0x1014daa72`
- `sqldk!SystemThread_TlsOffset` at `0x1014dae30`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1014daa8d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1014dae4b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1014daa8d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1014dae4b`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014da705`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014da789`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014da8db`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014db07d`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014db09c`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014db0ce`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014db249`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014db25c`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014db267`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014db2c7`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014db319`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014db49b`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014db4ae`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014db4b9`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014db4da`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014db786`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014db796`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014da705`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014da789`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014da8db`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014db07d`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014db09c`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014db0ce`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014db249`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014db25c`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014db267`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014db2c7`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014db319`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014db49b`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014db4ae`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014db4b9`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014db4da`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014db786`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014db796`
- `sqlfabric!GetPerDatabaseAkvUris` at `0x1014dacde`
- `sqlfabric!GetPerDatabaseAkvUris` at `0x1014dacde`
- `sqlfabric!?FDatabaseLevelKeys@CFabricReplicaController@@QEAA_NXZ` at `0x1014dac9c`
- `sqlfabric!?FDatabaseLevelKeys@CFabricReplicaController@@QEAA_NXZ` at `0x1014db136`
- `sqlfabric!?FDatabaseLevelKeys@CFabricReplicaController@@QEAA_NXZ` at `0x1014db5f8`
- `sqlfabric!?FDatabaseLevelKeys@CFabricReplicaController@@QEAA_NXZ` at `0x1014dac9c`
- `sqlfabric!?FDatabaseLevelKeys@CFabricReplicaController@@QEAA_NXZ` at `0x1014db136`
- `sqlfabric!?FDatabaseLevelKeys@CFabricReplicaController@@QEAA_NXZ` at `0x1014db5f8`
- `sqlfabric!?FPerDatabaseCMK@CFabricReplicaController@@QEAA_NXZ` at `0x1014dac83`
- `sqlfabric!?FPerDatabaseCMK@CFabricReplicaController@@QEAA_NXZ` at `0x1014db5e4`
- `sqlfabric!?FPerDatabaseCMK@CFabricReplicaController@@QEAA_NXZ` at `0x1014dac83`
- `sqlfabric!?FPerDatabaseCMK@CFabricReplicaController@@QEAA_NXZ` at `0x1014db5e4`
- `sqlfabric!?GetFabricReplicaControllerByPhysicalDbIdWithRef@CFabricReplicaManager@@QEAAPEAVCFabricReplicaController@@U_GUID@@@Z` at `0x1014db5c8`
- `sqlfabric!?GetFabricReplicaControllerByPhysicalDbIdWithRef@CFabricReplicaManager@@QEAAPEAVCFabricReplicaController@@U_GUID@@@Z` at `0x1014db5c8`
- `sqlfabric!?GetFabricReplicaControllerByDbIdWithRef@CFabricReplicaManager@@QEAAPEAVCFabricReplicaController@@AEBK@Z` at `0x1014dac67`
- `sqlfabric!?GetFabricReplicaControllerByDbIdWithRef@CFabricReplicaManager@@QEAAPEAVCFabricReplicaController@@AEBK@Z` at `0x1014db5ae`
- `sqlfabric!?GetFabricReplicaControllerByDbIdWithRef@CFabricReplicaManager@@QEAAPEAVCFabricReplicaController@@AEBK@Z` at `0x1014dac67`
- `sqlfabric!?GetFabricReplicaControllerByDbIdWithRef@CFabricReplicaManager@@QEAAPEAVCFabricReplicaController@@AEBK@Z` at `0x1014db5ae`
- `sqlfabric!?GetReplicaManagerWithRef@FabricStatefulServiceFactory@@SAPEAVCFabricReplicaManager@@XZ` at `0x1014daa43`
- `sqlfabric!?GetReplicaManagerWithRef@FabricStatefulServiceFactory@@SAPEAVCFabricReplicaManager@@XZ` at `0x1014db587`
- `sqlfabric!?GetReplicaManagerWithRef@FabricStatefulServiceFactory@@SAPEAVCFabricReplicaManager@@XZ` at `0x1014daa43`
- `sqlfabric!?GetReplicaManagerWithRef@FabricStatefulServiceFactory@@SAPEAVCFabricReplicaManager@@XZ` at `0x1014db587`
- `hostregdll!HostReg_FreeElementData` at `0x1014db0bd`
- `hostregdll!HostReg_FreeElementData` at `0x1014db0bd`
- `hostregdll!HostReg_GetPlainTextElements` at `0x1014dadd1`
- `hostregdll!HostReg_GetPlainTextElements` at `0x1014dadd1`

## string_xrefs

- `0x1014da7d2`: `sql\ntdbms\msql\security\src\seccryptmd.cpp`
- `0x1014da974`: `sql\ntdbms\msql\security\src\seccryptmd.cpp`
- `0x1014daaa7`: `sql\ntdbms\msql\security\src\seccryptmd.cpp`
- `0x1014dae65`: `sql\ntdbms\msql\security\src\seccryptmd.cpp`
- `0x1014db3d0`: `sql\ntdbms\msql\security\src\seccryptmd.cpp`
- `0x1014db737`: `sql\ntdbms\msql\security\src\seccryptmd.cpp`
- `0x1014dad0a`: `AzureKeyVaultUri`
- `0x1014dadc3`: `/ArrayOfAzureKeyVaultUriInfo/AzureKeyVaultUriInfo`
- `0x1014db2b6`: `[%hs] Could not retrieve AKV URI while trying to initialize dek for restore headeronly with Per DB CMK. Physical Database ID = '[%s]'`

## pseudocode

```c

```
