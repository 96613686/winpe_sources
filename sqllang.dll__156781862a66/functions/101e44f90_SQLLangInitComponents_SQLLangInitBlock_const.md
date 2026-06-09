# SQLLangInitComponents(SQLLangInitBlock const *)

- ea: `0x101e44f90`
- end: `0x101e464a5`
- name: `?SQLLangInitComponents@@YAXPEBUSQLLangInitBlock@@@Z`
- size: `5397`
- prototype: `void __fastcall(const struct SQLLangInitBlock *)`
- caller_count: `0`
- callee_count: `37`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x100401070`
- `0x100440350`
- `0x100567ff0`
- `0x1007978b0`
- `0x1007a1d00`
- `0x1007a2e00`
- `0x1007a70d0`
- `0x1007a72f0`
- `0x1007d4560`
- `0x1007e01f0`
- `0x1007e0c00`
- `0x1007e0e70`
- `0x1007e4480`
- `0x10082f5d0`
- `0x100860500`
- `0x100861470`
- `0x1008bc030`
- `0x1008cde20`
- `0x1008d3270`
- `0x100dc85b0`
- `0x100f07fc0`
- `0x100f4e090`
- `0x1010fd3e0`
- `0x101149490`
- `0x1014380a0`
- `0x1016e8590`
- `0x101709570`
- `0x101730bf0`
- `0x101895b70`
- `0x101d44780`
- `0x101e44680`
- `0x101e44f90`
- `0x101e88ac0`
- `0x101ee9990`
- `0x101ef5cb0`
- `0x101eff7b0`
- `0x101f00b40`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x101e45f52`
- `KERNEL32!QueryPerformanceCounter` at `0x101e45fa5`
- `KERNEL32!QueryPerformanceCounter` at `0x101e46125`
- `KERNEL32!QueryPerformanceCounter` at `0x101e46179`
- `KERNEL32!QueryPerformanceCounter` at `0x101e45f52`
- `KERNEL32!QueryPerformanceCounter` at `0x101e45fa5`
- `KERNEL32!QueryPerformanceCounter` at `0x101e46125`
- `KERNEL32!QueryPerformanceCounter` at `0x101e46179`
- `KERNEL32!VirtualProtect` at `0x101e4620f`
- `KERNEL32!VirtualProtect` at `0x101e4620f`
- `KERNEL32!VirtualFree` at `0x101e46350`
- `KERNEL32!VirtualFree` at `0x101e46350`
- `sqldk!?s_pfnCreateAutoSetXLvlIntCtxt@@3P6APEAVIAutoSetXLvlIntCtxt@@PEAVIMemObj@@PEAVCSession@@PEAVCBatch@@@ZEA` at `0x101e45067`
- `sqldk!?g_pfnAutoSetupContextForInternalTasksFactory@@3P6APEAVIAutoSetupExecContextsForInternalTasksImpl@@W4thread_type@@FPEB_W@ZEA` at `0x101e45056`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x101e454e9`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x101e45a96`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x101e45b0c`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x101e46373`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x101e45f66`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x101e4613a`
- `sqldk!?SOS_Tracing_osTrace@@3KA` at `0x101e46339`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x101e45ef4`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x101e460c4`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x101e462bd`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x101e462f6`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101e45f42`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101e45f95`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101e46114`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101e46168`
- `sqldk!?g_pmoGlobal@@3PEAVIMemObj@@EA` at `0x101e4518c`
- `sqldk!?g_pmoGlobal@@3PEAVIMemObj@@EA` at `0x101e4521a`
- `sqldk!?g_pmoGlobal@@3PEAVIMemObj@@EA` at `0x101e457c0`
- `sqldk!?x_pDefAllocMemObj@@3PEAVIMemObj@@EA` at `0x101e452a7`
- `sqldk!?EnqueueTask@SOS_OS@@SA?AW4SOS_RESULT@@P6APEAXPEAX@Z0KPEAPEAVSOS_Task@@_K@Z` at `0x101e45e6b`
- `sqldk!?EnqueueTask@SOS_OS@@SA?AW4SOS_RESULT@@P6APEAXPEAX@Z0KPEAPEAVSOS_Task@@_K@Z` at `0x101e45e6b`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@@Z` at `0x101e457f0`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@@Z` at `0x101e458b6`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@@Z` at `0x101e45921`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@@Z` at `0x101e457f0`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@@Z` at `0x101e458b6`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@@Z` at `0x101e45921`
- `sqldk!?CreateMemoryClerk@SOS_Node@@SAPEAVMemoryClerk@@PEB_WW4SOSHOST_MEMORYCLERK_TYPE@@W4SOS_CallerType@@@Z` at `0x101e4538f`
- `sqldk!?CreateMemoryClerk@SOS_Node@@SAPEAVMemoryClerk@@PEB_WW4SOSHOST_MEMORYCLERK_TYPE@@W4SOS_CallerType@@@Z` at `0x101e45403`
- `sqldk!?CreateMemoryClerk@SOS_Node@@SAPEAVMemoryClerk@@PEB_WW4SOSHOST_MEMORYCLERK_TYPE@@W4SOS_CallerType@@@Z` at `0x101e4538f`
- `sqldk!?CreateMemoryClerk@SOS_Node@@SAPEAVMemoryClerk@@PEB_WW4SOSHOST_MEMORYCLERK_TYPE@@W4SOS_CallerType@@@Z` at `0x101e45403`
- `sqldk!?Create@SOS_RingBuffer@@CAPEAV1@W4RINGBUFFER_TYPE@@KKKP6AXPEAVSOS_RingBufferRecord@@PEA_W_KPEAPEA_WPEA_K@ZPEAVIMemObj@@@Z` at `0x101e459e9`
- `sqldk!?Create@SOS_RingBuffer@@CAPEAV1@W4RINGBUFFER_TYPE@@KKKP6AXPEAVSOS_RingBufferRecord@@PEA_W_KPEAPEA_WPEA_K@ZPEAVIMemObj@@@Z` at `0x101e459e9`
- `sqldk!?IsTaskStoreDisabled@SOS_Node@@QEAA_NXZ` at `0x101e46070`
- `sqldk!?IsTaskStoreDisabled@SOS_Node@@QEAA_NXZ` at `0x101e46070`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x101e458e5`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x101e458e5`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101e451bb`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101e45247`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101e451bb`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101e45247`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x101e450ab`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x101e450c1`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x101e455cf`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x101e455e8`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x101e4571f`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x101e45738`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x101e45848`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x101e45861`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x101e45d8d`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x101e45da6`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x101e450ab`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x101e450c1`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x101e455cf`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x101e455e8`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x101e4571f`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x101e45738`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x101e45848`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x101e45861`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x101e45d8d`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x101e45da6`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101e4517a`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101e4537a`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101e453ee`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101e4545d`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101e45489`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101e4563e`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101e4566e`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101e45699`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101e456c4`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101e45790`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101e45c0f`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101e4517a`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101e4537a`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101e453ee`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101e4545d`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101e45489`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101e4563e`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101e4566e`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101e45699`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101e456c4`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101e45790`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101e45c0f`
- `sqldk!?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z` at `0x101e450eb`
- `sqldk!?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z` at `0x101e453c0`
- `sqldk!?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z` at `0x101e4542d`
- `sqldk!?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z` at `0x101e45610`
- `sqldk!?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z` at `0x101e45764`
- `sqldk!?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z` at `0x101e4588d`
- `sqldk!?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z` at `0x101e45dcf`
- `sqldk!?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z` at `0x101e450eb`
- `sqldk!?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z` at `0x101e453c0`
- `sqldk!?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z` at `0x101e4542d`
- `sqldk!?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z` at `0x101e45610`
- `sqldk!?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z` at `0x101e45764`
- `sqldk!?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z` at `0x101e4588d`
- `sqldk!?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z` at `0x101e45dcf`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x101e452f4`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x101e45540`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x101e457cf`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x101e452f4`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x101e45540`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x101e457cf`
- `sqldk!SystemThread_TlsIndex` at `0x101e454a6`
- `sqldk!SystemThread_TlsIndex` at `0x101e45597`
- `sqldk!SystemThread_TlsIndex` at `0x101e456e7`
- `sqldk!SystemThread_TlsIndex` at `0x101e45810`
- `sqldk!SystemThread_TlsIndex` at `0x101e4594a`
- `sqldk!SystemThread_TlsIndex` at `0x101e4598b`
- `sqldk!SystemThread_TlsIndex` at `0x101e45d55`
- `sqldk!SystemThread_TlsIndex` at `0x101e45e13`
- `sqldk!SystemThread_TlsIndex` at `0x101e45f14`
- `sqldk!SystemThread_TlsIndex` at `0x101e46003`
- `sqldk!SystemThread_TlsIndex` at `0x101e460e6`
- `sqldk!SystemThread_TlsOffset` at `0x101e454af`
- `sqldk!SystemThread_TlsOffset` at `0x101e455a0`
- `sqldk!SystemThread_TlsOffset` at `0x101e456f0`
- `sqldk!SystemThread_TlsOffset` at `0x101e45819`
- `sqldk!SystemThread_TlsOffset` at `0x101e45953`
- `sqldk!SystemThread_TlsOffset` at `0x101e45994`
- `sqldk!SystemThread_TlsOffset` at `0x101e45d5e`
- `sqldk!SystemThread_TlsOffset` at `0x101e45e1c`
- `sqldk!SystemThread_TlsOffset` at `0x101e45f1d`
- `sqldk!SystemThread_TlsOffset` at `0x101e4600c`
- `sqldk!SystemThread_TlsOffset` at `0x101e460ef`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101e45bd0`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101e45bd0`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101e454ca`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101e455bb`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101e4570b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101e45834`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101e4596e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101e459af`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101e45d79`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101e454ca`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101e455bb`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101e4570b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101e45834`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101e4596e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101e459af`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101e45d79`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101e45e42`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101e45e42`
- `sqldk!?GetDefaultMemoryClerksForNode@PerProcessGlobals@@QEAAPEAPEAVMemoryClerk@@G@Z` at `0x101e450b8`
- `sqldk!?GetDefaultMemoryClerksForNode@PerProcessGlobals@@QEAAPEAPEAVMemoryClerk@@G@Z` at `0x101e455df`
- `sqldk!?GetDefaultMemoryClerksForNode@PerProcessGlobals@@QEAAPEAPEAVMemoryClerk@@G@Z` at `0x101e4572f`
- `sqldk!?GetDefaultMemoryClerksForNode@PerProcessGlobals@@QEAAPEAPEAVMemoryClerk@@G@Z` at `0x101e45858`
- `sqldk!?GetDefaultMemoryClerksForNode@PerProcessGlobals@@QEAAPEAPEAVMemoryClerk@@G@Z` at `0x101e45d9d`
- `sqldk!?GetDefaultMemoryClerksForNode@PerProcessGlobals@@QEAAPEAPEAVMemoryClerk@@G@Z` at `0x101e450b8`
- `sqldk!?GetDefaultMemoryClerksForNode@PerProcessGlobals@@QEAAPEAPEAVMemoryClerk@@G@Z` at `0x101e455df`
- `sqldk!?GetDefaultMemoryClerksForNode@PerProcessGlobals@@QEAAPEAPEAVMemoryClerk@@G@Z` at `0x101e4572f`
- `sqldk!?GetDefaultMemoryClerksForNode@PerProcessGlobals@@QEAAPEAPEAVMemoryClerk@@G@Z` at `0x101e45858`
- `sqldk!?GetDefaultMemoryClerksForNode@PerProcessGlobals@@QEAAPEAPEAVMemoryClerk@@G@Z` at `0x101e45d9d`
- `sqldk!?SetCreateExecSql@@YAXP6APEAVIExecSql@@PEAVIMemObj@@PEAVICallerParse@@@Z@Z` at `0x101e45c3f`
- `sqldk!?SetCreateExecSql@@YAXP6APEAVIExecSql@@PEAVIMemObj@@PEAVICallerParse@@@Z@Z` at `0x101e45c3f`
- `sqldk!?Create@SOS_PartitionedHeap@@SAPEAV1@W4SOS_PARTITIONEDHEAP@@W4PARTITIONING_TYPE@@_KW4SOSHOST_MEMOBJ_ID@@I@Z` at `0x101e45118`
- `sqldk!?Create@SOS_PartitionedHeap@@SAPEAV1@W4SOS_PARTITIONEDHEAP@@W4PARTITIONING_TYPE@@_KW4SOSHOST_MEMOBJ_ID@@I@Z` at `0x101e45118`
- `sqlTsEs!?SetExtenderInterface@CSqlTypeSystemHost@@SAXPEAUISqlTypeSystemExtender_IJsonTypeProvider@@@Z` at `0x101e45049`
- `sqlTsEs!?SetExtenderInterface@CSqlTypeSystemHost@@SAXPEAUISqlTypeSystemExtender_IJsonTypeProvider@@@Z` at `0x101e45049`
- `sqlTsEs!?SetExtenderInterface@CSqlTypeSystemHost@@SAXPEAUISqlTypeSystemExtender_ContextProvider@@@Z` at `0x101e4503c`
- `sqlTsEs!?SetExtenderInterface@CSqlTypeSystemHost@@SAXPEAUISqlTypeSystemExtender_ContextProvider@@@Z` at `0x101e4503c`
- `sqlTsEs!?SetExtenderInterface@CSqlTypeSystemHost@@SAXPEAUISqlTypeSystemExtender_IUdtProvider@@@Z` at `0x101e4502f`
- `sqlTsEs!?SetExtenderInterface@CSqlTypeSystemHost@@SAXPEAUISqlTypeSystemExtender_IUdtProvider@@@Z` at `0x101e4502f`
- `sqlTsEs!?SetExtenderInterface@CSqlTypeSystemHost@@SAXPEAUISqlTypeSystemExtender_IOLEDB@@@Z` at `0x101e45022`
- `sqlTsEs!?SetExtenderInterface@CSqlTypeSystemHost@@SAXPEAUISqlTypeSystemExtender_IOLEDB@@@Z` at `0x101e45022`
- `sqlTsEs!?SetExtenderInterface@CSqlTypeSystemHost@@SAXPEAUISqlTypeSystemExtender_ITDSFormatter@@@Z` at `0x101e45015`
- `sqlTsEs!?SetExtenderInterface@CSqlTypeSystemHost@@SAXPEAUISqlTypeSystemExtender_ITDSFormatter@@@Z` at `0x101e45015`
- `sqlTsEs!?SetExtenderInterface@CSqlTypeSystemHost@@SAXPEAUISqlTypeSystemExtender_IExecControl@@@Z` at `0x101e45008`
- `sqlTsEs!?SetExtenderInterface@CSqlTypeSystemHost@@SAXPEAUISqlTypeSystemExtender_IExecControl@@@Z` at `0x101e45008`
- `sqlTsEs!?SetExtenderInterface@CSqlTypeSystemHost@@SAXPEAUISqlTypeSystemExtender_IXMLTypeProvider@@@Z` at `0x101e44ffb`
- `sqlTsEs!?SetExtenderInterface@CSqlTypeSystemHost@@SAXPEAUISqlTypeSystemExtender_IXMLTypeProvider@@@Z` at `0x101e44ffb`
- `sqlTsEs!?SetExtenderInterface@CSqlTypeSystemHost@@SAXPEAUISqlTypeSystemExtender_IDbAndSetOptsProvider@@@Z` at `0x101e44fee`
- `sqlTsEs!?SetExtenderInterface@CSqlTypeSystemHost@@SAXPEAUISqlTypeSystemExtender_IDbAndSetOptsProvider@@@Z` at `0x101e44fee`
- `sqlTsEs!?FastUnicodeToDBCS@@YAHIPEB_WHPEADH@Z` at `0x101e45abd`
- `sqlTsEs!?FastUnicodeToDBCS@@YAHIPEB_WHPEADH@Z` at `0x101e45abd`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x101e462c9`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x101e46302`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x101e462c9`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x101e46302`
- `sqlmin!?RegisterSqlMinSTVF@@YAXHPEAVCSTVFDefine@@@Z` at `0x101e45c32`
- `sqlmin!?RegisterSqlMinSTVF@@YAXHPEAVCSTVFDefine@@@Z` at `0x101e45c32`
- `sqlmin!?InitManager@IQDSPerfManager@@SAPEAV1@XZ` at `0x101e45a4a`
- `sqlmin!?InitManager@IQDSPerfManager@@SAPEAV1@XZ` at `0x101e45a4a`
- `sqlmin!?SetFFtSql@@YAXPEAVIFFtSql@@@Z` at `0x101e45a1e`
- `sqlmin!?SetFFtSql@@YAXPEAVIFFtSql@@@Z` at `0x101e45a1e`
- `sqlmin!?HkHostGetGlobalThreadInfo@@YAPEAUHkHostThreadInfo@@XZ` at `0x101e450a5`

## string_xrefs

- `0x101e452e1`: `Sql\DkTemp\base\include\sehash.inl`
- `0x101e457b6`: `sql\common\dk\ucs\src\ucsmgr.cpp`
- `0x101e458d3`: `sql\ntdbms\broker\src\ssbroker.cpp`
- `0x101e453fc`: `MemoryClerk Security`
- `0x101e4523c`: `sql\ntdbms\msql\utils\dbccdll.cpp`
- `0x101e4515e`: `HkProcCache::Init`
- `0x101e4564d`: `FInitProcCacheStores`
- `0x101e4567d`: `Remote Session Cache`
- `0x101e46399`: `CompileCpuTimeShallowScanInViewThresholdMillisec`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
// Hidden C++ exception states: #wind=12
void __fastcall SQLLangInitComponents(const struct SQLLangInitBlock *a1)
{
  struct ICurrentSqlToTextConverter *v2; // rdx
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // r8
  PerProcessGlobals *ClientProcessGlobals; // rax
  struct MemoryClerk **DefaultMemoryClerksForNode; // rbx
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  struct MemoryClerk *v11; // rax
  char *v12; // r8
  _WORD *v13; // rax
  __int64 v14; // rbx
  _DWORD *v15; // rax
  LpeEvents *v16; // rcx
  _DWORD *v17; // rdi
  int i; // esi
  __int64 v19; // r14
  unsigned __int64 v20; // rax
  _QWORD *v21; // rax
  __int64 MemoryClerk; // rax
  struct MemoryClerk *v23; // rax
  __int64 v24; // rbx
  __int64 v25; // rax
  struct IMemObj *v26; // r10
  unsigned int v27; // eax
  __int64 v28; // rbx
  unsigned __int64 v29; // rax
  unsigned __int64 v30; // kr00_8
  struct CDiagManager::tagDiagBucket *v31; // rax
  __int64 v32; // r8
  char *v33; // rcx
  _QWORD *ThreadLocalStoragePointer; // rdx
  __int64 v35; // rcx
  __int64 v36; // rbx
  __int64 v37; // rax
  __int64 v38; // rbx
  PerProcessGlobals *v39; // rax
  struct MemoryClerk **v40; // rbx
  __int64 v41; // rdx
  __int64 v42; // rcx
  __int64 v43; // r8
  __int64 v44; // r8
  __int64 v45; // r8
  _QWORD *v46; // rdx
  __int64 v47; // rcx
  __int64 v48; // rbx
  __int64 v49; // rax
  __int64 v50; // rbx
  PerProcessGlobals *v51; // rax
  struct MemoryClerk **v52; // rbx
  __int64 v53; // rdx
  __int64 v54; // rcx
  __int64 v55; // r8
  struct MemoryClerk *v56; // rax
  char *v57; // r8
  struct IMemObj *MemObject; // rbx
  CUcsManager *v59; // rax
  __int64 v60; // r8
  _QWORD *v61; // rdx
  __int64 v62; // rcx
  __int64 v63; // rbx
  __int64 v64; // rax
  __int64 v65; // rbx
  PerProcessGlobals *v66; // rax
  struct MemoryClerk **v67; // rbx
  __int64 v68; // rdx
  __int64 v69; // rcx
  __int64 v70; // r8
  struct MemoryClerk *v71; // rax
  char *v72; // r8
  struct IMemObj *v73; // rax
  struct IMemObj *v74; // rbx
  CServiceBrokerMgr *v75; // rax
  CServiceBrokerMgr *v76; // rcx
  __int64 v77; // rbx
  __int64 v78; // rax
  __int64 v79; // rdi
  __int64 v80; // rbx
  __int64 v81; // rax
  struct SOS_RingBuffer *v82; // rax
  struct SOS_RingBuffer *v83; // rbx
  QPEvent *v84; // rcx
  struct IQDSPerfManager *inited; // rax
  const wchar_t *v86; // rax
  bool v87; // bl
  __m128i *p_si128; // r14
  unsigned int v89; // r15d
  int v90; // edx
  const wchar_t *v91; // r12
  int v92; // esi
  unsigned int v93; // ebx
  CNLRegNodeS *v94; // rdi
  unsigned int v95; // ebx
  const wchar_t **v96; // rdi
  unsigned int v97; // ebx
  const wchar_t **v98; // rdi
  unsigned int v99; // ebx
  CacheStoreWrapper **v100; // rdi
  const wchar_t *v101; // rax
  __int64 v102; // r8
  signed int v103; // edi
  const wchar_t **v104; // rbx
  _QWORD *v105; // rdx
  __int64 v106; // rcx
  __int64 v107; // rbx
  __int64 v108; // rax
  __int64 v109; // rbx
  PerProcessGlobals *v110; // rax
  struct MemoryClerk **v111; // rbx
  __int64 v112; // rdx
  __int64 v113; // rcx
  __int64 v114; // r8
  struct MemoryClerk *v115; // rax
  char *v116; // r8
  __int64 v117; // rcx
  __int64 v118; // rbx
  __int64 v119; // rax
  struct CSessionTraceFlags *v120; // rcx
  unsigned int v121; // eax
  __int64 *v122; // rdi
  CSbTransportMgr *QuadPart; // rbx
  signed __int64 UniqueThread_low; // r14
  __int64 v125; // rsi
  __int64 v126; // r8
  CSbTransportMgr *v127; // rcx
  signed __int64 v128; // rax
  _QWORD *v129; // rcx
  __int64 v130; // rax
  __int64 v131; // r8
  __int64 v132; // rax
  ISOSHost_TaskImpl *v133; // rcx
  SOS_Node *v134; // rcx
  __int64 v135; // rbx
  __int64 *v136; // rsi
  __int64 v137; // rdi
  CSbTransportMgr *v138; // rbx
  signed __int64 v139; // r12
  __int64 v140; // r14
  __int64 v141; // r8
  __int64 v142; // rcx
  CSbTransportMgr *v143; // rcx
  signed __int64 v144; // rax
  __int64 *v145; // rcx
  unsigned __int64 v146; // rax
  SOS_ObjectStore *v147; // rcx
  __int64 PoolIdForObject; // r10
  __int64 v149; // rax
  _QWORD *v150; // r8
  __int64 v151; // rcx
  int v152; // r8d
  int v153; // r8d
  __int64 *v154; // rcx
  bool v155; // zf
  int v156; // [rsp+28h] [rbp-E0h]
  int v157; // [rsp+28h] [rbp-E0h]
  int v158; // [rsp+28h] [rbp-E0h]
  int v159; // [rsp+28h] [rbp-E0h]
  int v160; // [rsp+28h] [rbp-E0h]
  int v161; // [rsp+28h] [rbp-E0h]
  int v162; // [rsp+28h] [rbp-E0h]
  int v163[2]; // [rsp+38h] [rbp-D0h] BYREF
  _QWORD *v164; // [rsp+40h] [rbp-C8h]
  LARGE_INTEGER v165; // [rsp+48h] [rbp-C0h] BYREF
  LARGE_INTEGER v166; // [rsp+50h] [rbp-B8h] BYREF
  struct CDiagManager::tagDiagBucket *v167; // [rsp+58h] [rbp-B0h]
  volatile signed __int64 *v168; // [rsp+60h] [rbp-A8h] BYREF
  int v169; // [rsp+68h] [rbp-A0h]
  __int64 v170; // [rsp+70h] [rbp-98h] BYREF
  CNLRegNodeS *v171; // [rsp+78h] [rbp-90h] BYREF
  volatile signed __int32 *v172; // [rsp+80h] [rbp-88h] BYREF
  LARGE_INTEGER v173; // [rsp+88h] [rbp-80h] BYREF
  DWORD flOldProtect; // [rsp+90h] [rbp-78h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+98h] [rbp-70h] BYREF
  struct IMemObj *v176; // [rsp+A0h] [rbp-68h]
  __int64 v177; // [rsp+A8h] [rbp-60h]
  struct IMemObj *v178; // [rsp+B0h] [rbp-58h]
  __m128i si128; // [rsp+B8h] [rbp-50h] BYREF
  char v180[272]; // [rsp+C8h] [rbp-40h] BYREF
  char v181[256]; // [rsp+1D8h] [rbp+D0h] BYREF

  v177 = -2;
  if ( (*((_DWORD *)a1 + 6) & 0x8000) == 0 )
  {
    InitSharedResource(*((_DWORD *)a1 + 1));
    CSqlTypeSystemHost::SetExtenderInterface((struct ISqlTypeSystemExtender_IDbAndSetOptsProvider *)&off_102FEF4E8);
    CSqlTypeSystemHost::SetExtenderInterface((struct ISqlTypeSystemExtender_IXMLTypeProvider *)&off_102FDFDA8);
    CSqlTypeSystemHost::SetExtenderInterface((struct ISqlTypeSystemExtender_IExecControl *)&off_102FD94E0);
    CSqlTypeSystemHost::SetExtenderInterface((struct ISqlTypeSystemExtender_ITDSFormatter *)&off_102FD63B8);
    CSqlTypeSystemHost::SetExtenderInterface((struct ISqlTypeSystemExtender_IOLEDB *)&off_102FDE070);
    CSqlTypeSystemHost::SetExtenderInterface((struct ISqlTypeSystemExtender_IUdtProvider *)&off_102FD9810);
    CSqlTypeSystemHost::SetExtenderInterface((struct ISqlTypeSystemExtender_ContextProvider *)&CContextProviderForTypeSystem::x_tsContextProvider);
    CSqlTypeSystemHost::SetExtenderInterface((struct ISqlTypeSystemExtender_IJsonTypeProvider *)&off_102FD6C00);
    g_pfnAutoSetupContextForInternalTasksFactory = (struct IAutoSetupExecContextsForInternalTasksImpl *(__high *)(enum thread_type, __int16, const wchar_t *))&CreateSQLAutoSetupContextForInternalTasks;
    s_pfnCreateAutoSetXLvlIntCtxt = CreateAutoSetXLvlIntCtxtImpl;
    EngineCommonComponentInitializers::SetSqlHandleModuleConverter(
      (EngineCommonComponentInitializers *)&off_102FDDA48,
      v2);
    SqlDumpInit(*((void (**)(const struct _EXCEPTION_POINTERS *))a1 + 4), *((void (**)(void))a1 + 5));
    if ( IsHekatonEnabled() )
    {
      HkHostGetGlobalThreadInfo();
      ClientProcessGlobals = (PerProcessGlobals *)SOS_OS::GetClientProcessGlobals(v4, v3, v5);
      DefaultMemoryClerksForNode = PerProcessGlobals::GetDefaultMemoryClerksForNode(ClientProcessGlobals, 0);
      SOS_OS::GetClientProcessGlobals(v9, v8, v10);
      v11 = DefaultMemoryClerksForNode[32];
      v12 = (char *)v11 + 64;
      if ( !v11 )
        v12 = 0;
      qword_102F11700 = MemoryObjectFactory::CreateMemObject(273, 2, v12, 8, 128);
      if ( qword_102F11700
        && (HkProcCache::sm_ParHeap = (struct SOS_PartitionedHeap *)SOS_PartitionedHeap::Create(
                                                                      5,
                                                                      1,
                                                                      TDelayedPartitionedStack<CMsqlExecContext,40>::sm_PartitionedObjectSize,
                                                                      280,
                                                                      256)) != 0 )
      {
        if ( *(_DWORD *)(qword_102ECFB00 + 14504) )
        {
          HkProcCache::sm_isStmtStatsEnabled = 1;
          HkProcCache::sm_isProcStatsEnabled = 1;
        }
        else
        {
          HkProcCache::sm_isStmtStatsEnabled = 0;
          HkProcCache::sm_isProcStatsEnabled = 0;
        }
      }
      else
      {
        scierrlog(0x42F2u, L"HkProcCache::Init");
        SQLExit(106, 0, 2147942414LL);
      }
      v166.QuadPart = (LONGLONG)&g_sqlHostIntrinsics;
      qword_102FD96C0 = (__int64)g_pmoGlobal;
      v163[0] = 81;
      v13 = operator new(0x28u, g_pmoGlobal, "sql\\ntdbms\\Hekaton\\sqlhost\\sqllang\\SqlHostIntrinsics.cpp", 81, 3u);
      v14 = (__int64)v13;
      v165.QuadPart = (LONGLONG)v13;
      if ( v13 )
      {
        v173.QuadPart = (LONGLONG)v13;
        *(_QWORD *)v13 = qword_102FD96C0;
        v13[4] = v163[0];
        *((_DWORD *)v13 + 3) = 0;
        *((_QWORD *)v13 + 2) = 0;
        *((_QWORD *)v13 + 3) = 0;
        *((_DWORD *)v13 + 8) = 0;
        CTHashTable<Pair<CValRef *,CTSingleColumnPredicateCombiner<CIntervalForCE> *>,CTMap<CValRef *,CTSingleColumnPredicateCombiner<CIntervalForCE> *,CFnH_Pointer,CFnC_Default<CValRef *>,CFnI_Default<CTSingleColumnPredicateCombiner<CIntervalForCE> *>,CFnD_Noop<CValRef *>,CFnD_Ptr<CTSingleColumnPredicateCombiner<CIntervalForCE>>,CMemObjAlloc<0>>::CEntryHashFn,CTMap<CValRef *,CTSingleColumnPredicateCombiner<CIntervalForCE> *,CFnH_Pointer,CFnC_Default<CValRef *>,CFnI_Default<CTSingleColumnPredicateCombiner<CIntervalForCE> *>,CFnD_Noop<CValRef *>,CFnD_Ptr<CTSingleColumnPredicateCombiner<CIntervalForCE>>,CMemObjAlloc<0>>::CEntryCmpFn,CTMap<CValRef *,CTSingleColumnPredicateCombiner<CIntervalForCE> *,CFnH_Pointer,CFnC_Default<CValRef *>,CFnI_Default<CTSingleColumnPredicateCombiner<CIntervalForCE> *>,CFnD_Noop<CValRef *>,CFnD_Ptr<CTSingleColumnPredicateCombiner<CIntervalForCE>>,CMemObjAlloc<0>>::CEntryInvalidFn,CTMap<CValRef *,CTSingleColumnPredicateCombiner<CIntervalForCE> *,CFnH_Pointer,CFnC_Default<CValRef *>,CFnI_Default<CTSingleColumnPredicateCombiner<CIntervalForCE> *>,CFnD_Noop<CValRef *>,CFnD_Ptr<CTSingleColumnPredicateCombiner<CIntervalForCE>>,CMemObjAlloc<0>>::CEntryDestroyFn,CMemObjAlloc<0>>::Resize(
          v13,
          40);
      }
      else
      {
        v14 = 0;
      }
      qword_102FD96C8 = v14;
    }
    SetupSessions(*(_DWORD *)a1);
    v166.QuadPart = (LONGLONG)g_pmoGlobal;
    v163[0] = 40;
    v15 = operator new(0x70u, g_pmoGlobal, "sql\\ntdbms\\msql\\utils\\dbccdll.cpp", 40, 3u);
    v17 = v15;
    v165.QuadPart = (LONGLONG)v15;
    if ( v15 )
    {
      v15[6] = 44;
      *((_QWORD *)v15 + 1) = 0;
      *((_QWORD *)v15 + 2) = 0;
      *(_QWORD *)v15 = 0;
      *((_QWORD *)v15 + 4) = 0;
      v15[10] = 0;
      v15[12] = 0;
      *((_QWORD *)v15 + 7) = 0;
      *((_QWORD *)v15 + 8) = 0;
      v15[18] = v15[22];
      *((_QWORD *)v15 + 10) = 0;
      v15[22] = -1;
      *((_QWORD *)v15 + 13) = v15 + 24;
      *((_QWORD *)v15 + 12) = v15 + 24;
      v178 = x_pDefAllocMemObj;
      for ( i = 1; i < 31; i *= 2 )
        ;
      v15[11] = i - 1;
      v19 = i;
      v20 = 16LL * i;
      if ( !is_mul_ok(i, 0x10u) )
        v20 = -1;
      v21 = operator new[](v20, x_pDefAllocMemObj, 1, "Sql\\DkTemp\\base\\include\\sehash.inl", 127, 3u);
      v164 = v21;
      if ( v21 )
      {
        v16 = (LpeEvents *)v21;
        do
        {
          *((_QWORD *)v16 + 1) = v16;
          *(_QWORD *)v16 = v16;
          v16 = (LpeEvents *)((char *)v16 + 16);
          --v19;
        }
        while ( v19 );
      }
      else
      {
        v21 = 0;
      }
      *((_QWORD *)v17 + 4) = v21;
      if ( v21 )
      {
        v17[10] = i;
        *((_QWORD *)v17 + 7) = x_pDefAllocMemObj;
      }
      else
      {
        LOBYTE(v16) = -31;
        ex_raise_oom(v16);
      }
    }
    else
    {
      v17 = 0;
    }
    g_pDLLHashTable = (HashDLL *)v17;
    if ( !(unsigned int)LpeEvents::FInitLpeEventsSubSystem(v16) )
    {
      scierrlog(0x42F2u, L"Server events subsystem");
      SQLExit(107, 0, 2147942414LL);
    }
    MemoryClerk = SOS_Node::CreateMemoryClerk(L"MemoryClerk DEK", 89, 1);
    CSECDEK::s_memoryClerkDEK = (struct MemoryClerk *)MemoryClerk;
    if ( !MemoryClerk
      || (*(_DWORD *)(MemoryClerk + 1572) |= 0x10u,
          LOWORD(v156) = 128,
          (CSECDEK::s_pmoDEK = (struct IMemObj *)MemoryObjectFactory::CreateMemObject(416, 6, MemoryClerk + 64, 8, v156)) == 0) )
    {
      scierrlog(0x42F2u, L"DEK memory object");
      SQLExit(108, 0, 2147942414LL);
    }
    v23 = (struct MemoryClerk *)SOS_Node::CreateMemoryClerk(L"MemoryClerk Security", 93, 1);
    SecThreadSafePmo::s_memoryClerkSec = v23;
    if ( !v23
      || (LOWORD(v156) = 128,
          (SecThreadSafePmo::s_pmoSec = (struct IMemObj *)MemoryObjectFactory::CreateMemObject(
                                                            428,
                                                            6,
                                                            (char *)v23 + 64,
                                                            8,
                                                            v156)) == 0) )
    {
      scierrlog(0x42F2u, L"Sec memory object");
      SQLExit(327, 0, 2147942414LL);
    }
    if ( !InitXPMO() )
    {
      scierrlog(0x42F2u, L"XP memory object");
      SQLExit(109, 0, 2147942414LL);
    }
    CDiagnosticsBase::m_sdServerStartTime = **((_QWORD **)a1 + 2);
    v24 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v25 = *(_QWORD *)(v24 + 256);
    if ( !v25 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v25 = *(_QWORD *)(v24 + 256);
    }
    v26 = *(struct IMemObj **)(*(_QWORD *)(v25 + 992) + 320LL);
    v176 = v26;
    v27 = CDiagManager::m_cBuckets;
    if ( !*((_DWORD *)s_pServerConf + 2) )
      v27 = 100;
    CDiagManager::m_cBuckets = v27;
    v28 = v27;
    LODWORD(v164) = 3693;
    v30 = v27;
    v29 = 32LL * v27;
    if ( !is_mul_ok(v30, 0x20u) )
      v29 = -1;
    v31 = (struct CDiagManager::tagDiagBucket *)operator new[](
                                                  v29,
                                                  v26,
                                                  1,
                                                  "sql\\ntdbms\\msql\\utils\\diag.cpp",
                                                  3693,
                                                  3u);
    v167 = v31;
    if ( v31 )
    {
      if ( v28 )
      {
        v33 = (char *)v31 + 8;
        do
        {
          *((_QWORD *)v33 - 1) = 0;
          *((_QWORD *)v33 + 1) = v33;
          *(_QWORD *)v33 = v33;
          *((_DWORD *)v33 + 4) = 0;
          v33 += 32;
          --v28;
        }
        while ( v28 );
      }
    }
    else
    {
      v31 = 0;
    }
    CDiagManager::m_rgBuckets = v31;
    if ( !v31 )
      goto LABEL_57;
    ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
    v35 = SystemThread_TlsIndex;
    v36 = ThreadLocalStoragePointer[SystemThread_TlsIndex] + SystemThread_TlsOffset;
    v37 = *(_QWORD *)(v36 + 256);
    if ( !v37 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v37 = *(_QWORD *)(v36 + 256);
    }
    v38 = *(_QWORD *)(v37 + 992);
    v39 = (PerProcessGlobals *)SOS_OS::GetClientProcessGlobals(v35, ThreadLocalStoragePointer, v32);
    v40 = PerProcessGlobals::GetDefaultMemoryClerksForNode(v39, *(_WORD *)(v38 + 160));
    SOS_OS::GetClientProcessGlobals(v42, v41, v43);
    v44 = (__int64)*v40 + 64;
    if ( !*v40 )
      v44 = 0;
    LOWORD(v157) = 1568;
    CDiagnostics::m_pmo = (struct IMemObj *)MemoryObjectFactory::CreateMemObject(32, 10, v44, 1568, v157);
    if ( !CDiagnostics::m_pmo )
    {
LABEL_57:
      scierrlog(0x42F2u, L"Diagnostics");
      SQLExit(110, 0, 2147942414LL);
    }
    if ( !CCache::FInitProcCacheStores() )
    {
      scierrlog(0x42F2u, L"FInitProcCacheStores");
      SQLExit(111, 17138, 2147942414LL);
    }
    if ( !CRemSessCache::FInitSessionCache() )
    {
      scierrlog(0x42F2u, L"Remote Session Cache");
      SQLExit(112, 0, 2147942414LL);
    }
    if ( !(unsigned int)CXmldbCache::FInit() )
    {
      scierrlog(0x42F2u, L"FInit");
      SQLExit(113, 0, 2147942414LL);
    }
    if ( !FInitRGPerfCtrsManager() )
      scierrlog(0x42D3u);
    v46 = NtCurrentTeb()->ThreadLocalStoragePointer;
    v47 = SystemThread_TlsIndex;
    v48 = v46[SystemThread_TlsIndex] + SystemThread_TlsOffset;
    v49 = *(_QWORD *)(v48 + 256);
    if ( !v49 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v49 = *(_QWORD *)(v48 + 256);
    }
    v50 = *(_QWORD *)(v49 + 992);
    v51 = (PerProcessGlobals *)SOS_OS::GetClientProcessGlobals(v47, v46, v45);
    v52 = PerProcessGlobals::GetDefaultMemoryClerksForNode(v51, *(_WORD *)(v50 + 160));
    SOS_OS::GetClientProcessGlobals(v54, v53, v55);
    v56 = v52[31];
    v57 = (char *)v56 + 64;
    if ( !v56 )
      v57 = 0;
    LOWORD(v157) = 32;
    MemObject = (struct IMemObj *)MemoryObjectFactory::CreateMemObject(60, 4194310, v57, 4, v157);
    if ( !MemObject )
    {
      scierrlog(0x42F2u, L"SQLTrace memory object");
      SQLExit(173, 0, 2147942414LL);
    }
    CTraceController::Init((CTraceController *)(qword_102ECFB00 + 56), MemObject);
    v59 = (CUcsManager *)operator new[](0x51B0u, g_pmoGlobal, 1, "sql\\common\\dk\\ucs\\src\\ucsmgr.cpp", 49, 6u);
    if ( v59 )
    {
      qword_102F3EEE8 = v59;
      CUcsManager::CUcsManager(v59);
    }
    else
    {
      SsbLogError(9694, 16, 33);
      SQLExit(358);
    }
    v61 = NtCurrentTeb()->ThreadLocalStoragePointer;
    v62 = SystemThread_TlsIndex;
    v63 = v61[SystemThread_TlsIndex] + SystemThread_TlsOffset;
    v64 = *(_QWORD *)(v63 + 256);
    if ( !v64 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v64 = *(_QWORD *)(v63 + 256);
    }
    v65 = *(_QWORD *)(v64 + 992);
    v66 = (PerProcessGlobals *)SOS_OS::GetClientProcessGlobals(v62, v61, v60);
    v67 = PerProcessGlobals::GetDefaultMemoryClerksForNode(v66, *(_WORD *)(v65 + 160));
    SOS_OS::GetClientProcessGlobals(v69, v68, v70);
    v71 = v67[21];
    v72 = (char *)v71 + 64;
    if ( !v71 )
      v72 = 0;
    LOWORD(v158) = 128;
    v73 = (struct IMemObj *)MemoryObjectFactory::CreateMemObject(47, 4194306, v72, 8, v158);
    v74 = v73;
    v167 = v73;
    if ( v73 )
    {
      LODWORD(v164) = 3071;
      v75 = (CServiceBrokerMgr *)operator new(0x94B0u, v73, 1, "sql\\ntdbms\\broker\\src\\ssbroker.cpp", 3071, 8u);
      v176 = v75;
      if ( v75 )
        v76 = CServiceBrokerMgr::CServiceBrokerMgr(v75, v74);
      else
        v76 = 0;
      if ( v76 )
      {
        *(_QWORD *)(qword_102ECFB00 + 43248) = v76;
        CServiceBrokerMgr::Init(v76);
      }
      else
      {
        SsbLogError(9694, 16, 32);
        SQLExit(360);
      }
    }
    else
    {
      SsbLogError(9694, 16, 6);
      SQLExit(359);
    }
    InitializeSecurityOnStartup();
    v77 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v78 = *(_QWORD *)(v77 + 256);
    if ( !v78 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v78 = *(_QWORD *)(v77 + 256);
    }
    v79 = *(_QWORD *)(v78 + 992);
    v80 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v81 = *(_QWORD *)(v80 + 256);
    if ( !v81 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v81 = *(_QWORD *)(v80 + 256);
    }
    v82 = (struct SOS_RingBuffer *)SOS_RingBuffer::Create(
                                     83,
                                     48,
                                     128,
                                     1,
                                     BdcControllerClientRingBufferRecord::SerializeRecord,
                                     *(_QWORD *)(*(_QWORD *)(v81 + 992) + 320LL),
                                     v163[0],
                                     v164);
    v83 = v82;
    if ( v82 )
    {
      *(_QWORD *)v82 = 0;
      *((_QWORD *)v82 + 1) = 0;
      TList<SOS_Node,SOS_RingBuffer,0,TListSLock>::AppendElem(v79 + 96, v82);
    }
    CBdcControllerClient::sm_pRingBuffer = v83;
    InitFileStreamState();
    SetFFtSql((struct IFFtSql *)&off_10304F018);
    if ( (*((_BYTE *)a1 + 24) & 4) != 0 )
      CCLRHostBase::CreateCLRHost(&off_103029DA8, 0);
    InitSQLLangIntrinsics();
    QPEvent::Startup(v84);
    if ( *((_BYTE *)a1 + 28) )
    {
      inited = (struct IQDSPerfManager *)IQDSPerfManager::InitManager();
      InitializeQDSManager((struct IQDSHost *)&off_1030499C0, inited);
      qword_102F28880 = (__int64)FeedbackDataJson;
    }
    if ( !*(_DWORD *)(qword_102ECFB00 + 14544) )
      SetOSYieldCallback(OSYieldCallback);
    if ( (*((_BYTE *)a1 + 24) & 2) != 0 )
    {
      v86 = (const wchar_t *)(*(__int64 (__fastcall **)(struct IServerConfiguration *))(*(_QWORD *)s_pServerConf + 224LL))(s_pServerConf);
      FastUnicodeToDBCS(0, v86, -1, v180, 261);
      v180[260] = 0;
      v87 = !*(_DWORD *)(qword_102ECFB00 + 14544) && !*(_DWORD *)(qword_102ECFB00 + 14548);
      p_si128 = 0;
      v89 = 0;
      v170 = 0x500000001LL;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      if ( *(_DWORD *)(qword_102ECFB00 + 14544)
        || (v90 = *((_DWORD *)s_pServerConf + 3), v90 == 1) && (*((_BYTE *)qword_102ECFB10 + 975) & 0x40) == 0 )
      {
        v89 = 2;
        p_si128 = (__m128i *)&v170;
      }
      else if ( *(_DWORD *)(qword_102ECFB00 + 14548) || v90 == 1 && (*((_BYTE *)qword_102ECFB10 + 975) & 0x40) != 0 )
      {
        v89 = 4;
        p_si128 = &si128;
      }
      v91 = (const wchar_t *)(*(__int64 (__fastcall **)(struct IServerConfiguration *))(*(_QWORD *)s_pServerConf + 224LL))(s_pServerConf);
      v92 = 0;
      v163[0] = 0;
      if ( v87 )
      {
        v171 = 0;
        v93 = CNLRegNodeS::SSgetRootHandle(v91, (void **)&v171, 0, 0);
        v94 = v171;
        if ( !v93 )
        {
          v93 = CNLRegNodeS::SSgetClusterSettings(v171, v163, v181, 0x100u);
          v92 = v163[0];
        }
        if ( v94 )
          operator delete(v94, 0x418u);
        if ( v93 )
          goto LABEL_119;
      }
      v93 = SNIInitializeEx(0, p_si128, v89, 0, v92, v91);
      if ( v93 )
      {
LABEL_119:
        scierrlog(0x4314u, v93);
        SQLExit(328, 0, v93);
      }
    }
    RegisterSqlMinSTVF(531, (struct CSTVFDefine *)&x_rgSTVFs);
    SetCreateExecSql((struct IExecSql *(*)(struct IMemObj *, struct ICallerParse *))CreateCExecSqlImp);
    v95 = 0;
    v96 = (const wchar_t **)&off_10256E820;
    do
    {
      PerfmonManager::AddInstance((PerfmonManager *)qword_102ECFB00, 0x11u, *v96, v95++);
      v96 += 2;
    }
    while ( v95 < 4 );
    v97 = 0;
    v98 = (const wchar_t **)&off_102694820;
    do
    {
      PerfmonManager::AddInstance((PerfmonManager *)qword_102ECFB00, 0xEu, *v98, v97++);
      v98 += 2;
    }
    while ( v97 < 5 );
    PerfmonManager::AddInstance((PerfmonManager *)qword_102ECFB00, 0x10u, L"_Total", 0);
    v99 = 0;
    v100 = &CCache::sm_rgpcsProcCache;
    do
    {
      v101 = (const wchar_t *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)*v100 + 16LL))(*(_QWORD *)*v100);
      PerfmonManager::AddInstance((PerfmonManager *)qword_102ECFB00, 0x10u, v101, ++v99);
      ++v100;
    }
    while ( v99 < 5 );
    v103 = 0;
    v104 = (const wchar_t **)&off_1023F5A90;
    do
    {
      if ( *((_DWORD *)v104 - 2) )
        PerfmonManager::AddInstance((PerfmonManager *)qword_102ECFB00, 0x29u, *v104, v103);
      ++v103;
      v104 += 4;
    }
    while ( v103 < 274 );
    if ( (*((_BYTE *)a1 + 24) & 2) != 0 )
      StartCMThread(*((const struct ConnectionManagerCallbacks **)a1 + 1));
    v105 = NtCurrentTeb()->ThreadLocalStoragePointer;
    v106 = SystemThread_TlsIndex;
    v107 = v105[SystemThread_TlsIndex] + SystemThread_TlsOffset;
    v108 = *(_QWORD *)(v107 + 256);
    if ( !v108 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v108 = *(_QWORD *)(v107 + 256);
    }
    v109 = *(_QWORD *)(v108 + 992);
    v110 = (PerProcessGlobals *)SOS_OS::GetClientProcessGlobals(v106, v105, v102);
    v111 = PerProcessGlobals::GetDefaultMemoryClerksForNode(v110, *(_WORD *)(v109 + 160));
    SOS_OS::GetClientProcessGlobals(v113, v112, v114);
    v115 = v111[6];
    v116 = (char *)v115 + 64;
    if ( !v115 )
      v116 = 0;
    LOWORD(v159) = 128;
    v118 = MemoryObjectFactory::CreateMemObject(441, 66, v116, 8, v159);
    if ( !v118 )
    {
      LOBYTE(v117) = 65;
      ex_raise_oom(v117);
    }
    qword_103096348 = v118;
    if ( (*((_BYTE *)a1 + 24) & 4) != 0 )
    {
      if ( (*((_BYTE *)qword_102ECFB10 + 816) & 2) == 0 )
      {
        v119 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                         + SystemThread_TlsOffset);
        if ( !v119
          || (v120 = **(struct CSessionTraceFlags ***)(v119 + 56)) == 0
          || !CSessionTraceFlags::CheckSessionTraceInternal(v120, 0x1981u) )
        {
          v172 = 0;
          v121 = SOS_OS::EnqueueTask(TryLoadClr, 0, 0, &v172, -1);
          if ( v121 )
          {
            scierrlog(0x2860u, v121);
          }
          else
          {
            v122 = (__int64 *)v172;
            if ( _InterlockedExchangeAdd(v172 + 10, 0xFFFFFFFF) == 1 )
            {
              if ( v122[3] )
              {
                TListElem<TList<SOS_Scheduler,SOS_Task,16,TListSLock>>::RemoveAndDestroy(v122 + 2);
              }
              else
              {
                if ( *((_DWORD *)v122 + 46) == 2 )
                {
                  v168 = (volatile signed __int64 *)(v122[20] + 4952);
                  v169 = 0;
                  QuadPart = 0;
                  UniqueThread_low = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
                  if ( *(_DWORD *)v168 || _InterlockedCompareExchange64(v168, UniqueThread_low, 0) )
                  {
                    v125 = 0;
                    if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
                    {
                      v126 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                           + SystemThread_TlsOffset;
                      if ( v126 && *(_QWORD *)(v126 + 272) == v126 )
                        v125 = *(_QWORD *)(v126 + 256);
                      if ( v125 )
                      {
                        if ( Base_PublicGlobals::sm_invariantTscAvailable )
                        {
                          QueryPerformanceCounter(&PerformanceCount);
                          QuadPart = (CSbTransportMgr *)PerformanceCount.QuadPart;
                        }
                        else
                        {
                          QuadPart = MEMORY[0x7FFE0008];
                        }
                      }
                    }
                    if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
                      Spinlock<11,2,268435714>::SpinToAcquireWithExponentialBackoff(v168, UniqueThread_low);
                    else
                      Spinlock<11,2,268435714>::SpinToAcquireOptimistic(v168, v125, UniqueThread_low);
                    if ( v125 )
                    {
                      if ( Base_PublicGlobals::sm_invariantTscAvailable )
                      {
                        QueryPerformanceCounter(&v173);
                        v127 = (CSbTransportMgr *)v173.QuadPart;
                      }
                      else
                      {
                        v127 = MEMORY[0x7FFE0008];
                      }
                      v128 = 0;
                      if ( v127 >= QuadPart )
                        v128 = v127 - QuadPart;
                      *(_QWORD *)(v125 + 3192) += v128;
                    }
                  }
                  v169 = 1;
                  v129 = (_QWORD *)v122[1];
                  v130 = *v122;
                  *(_QWORD *)(v130 + 8) = v129;
                  *v129 = v130;
                  v122[1] = 0;
                  *v122 = 0;
                  SpinlockHolder<11,2,268435714>::~SpinlockHolder<11,2,268435714>(&v168);
                }
                v131 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                     + SystemThread_TlsOffset;
                if ( v131
                  && *(_QWORD *)(v131 + 272) == v131
                  && (v132 = *(_QWORD *)(v131 + 256)) != 0
                  && *(__int64 **)(v132 + 528) == v122 )
                {
                  v133 = (ISOSHost_TaskImpl *)(v122 - 1);
                  if ( !v122 )
                    v133 = 0;
                  ISOSHost_TaskImpl::`scalar deleting destructor'(v133, 0);
                }
                else
                {
                  v134 = (SOS_Node *)v122[21];
                  if ( v134 && *((_QWORD *)v134 + 30) && !SOS_Node::IsTaskStoreDisabled(v134) )
                  {
                    v135 = *(_QWORD *)(v122[21] + 240);
                    v136 = v122 - 1;
                    ISOSHost_TaskImpl::`scalar deleting destructor'((ISOSHost_TaskImpl *)(v122 - 1), 0);
                    v137 = *(_QWORD *)(v135 + 2016);
                    v138 = 0;
                    v139 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
                    if ( *(_DWORD *)(v137 + 40)
                      || _InterlockedCompareExchange64((volatile signed __int64 *)(v137 + 40), v139, 0) )
                    {
                      v140 = 0;
                      if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
                      {
                        v141 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset;
                        if ( v141 && *(_QWORD *)(v141 + 272) == v141 )
                          v140 = *(_QWORD *)(v141 + 256);
                        if ( v140 )
                        {
                          if ( Base_PublicGlobals::sm_invariantTscAvailable )
                          {
                            QueryPerformanceCounter(&v165);
                            v138 = (CSbTransportMgr *)v165.QuadPart;
                          }
                          else
                          {
                            v138 = MEMORY[0x7FFE0008];
                          }
                        }
                      }
                      v142 = v137 + 40;
                      if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
                        Spinlock<34,1,268435714>::SpinToAcquireWithExponentialBackoff(v142, v139);
                      else
                        Spinlock<34,1,268435714>::SpinToAcquireOptimistic(v142, v140, v139);
                      if ( v140 )
                      {
                        if ( Base_PublicGlobals::sm_invariantTscAvailable )
                        {
                          QueryPerformanceCounter(&v166);
                          v143 = (CSbTransportMgr *)v166.QuadPart;
                        }
                        else
                        {
                          v143 = MEMORY[0x7FFE0008];
                        }
                        v144 = 0;
                        if ( v143 >= v138 )
                          v144 = v143 - v138;
                        *(_QWORD *)(v140 + 3192) += v144;
                      }
                    }
                    if ( *(_QWORD *)(v137 + 8) >= *(_QWORD *)v137 )
                    {
                      if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
                      {
                        v153 = rand();
                        if ( v153 == 5 * (v153 / 5) )
                          Spinlock<34,1,268435714>::UpdateStatSnapshot();
                      }
                      *(_QWORD *)(v137 + 40) = 0;
                      (*(void (__fastcall **)(__int64 *))(v137 + 48))(v136);
                    }
                    else
                    {
                      if ( *(_BYTE *)(*(_QWORD *)(v137 + 32) + 5820LL) )
                      {
                        v145 = (__int64 *)(v137 + 16 * ((*(_DWORD *)(v137 + 1176) & 0x3F) + 9LL));
                        *v136 = *v145;
                        if ( !*v145 )
                          v145[1] = (__int64)v136;
                        *v145 = (__int64)v136;
                        ++*(_QWORD *)(v137 + 1176);
                        VirtualProtect(v136, 0x1000u, 1u, &flOldProtect);
                      }
                      else
                      {
                        *v136 = *(_QWORD *)(v137 + 128);
                        if ( !*(_QWORD *)(v137 + 128) )
                          *(_QWORD *)(v137 + 136) = v136;
                        *(_QWORD *)(v137 + 128) = v136;
                      }
                      v146 = *(_QWORD *)(v137 + 1168) + 1LL;
                      ++*(_QWORD *)(v137 + 8);
                      v147 = *(SOS_ObjectStore **)(v137 + 32);
                      if ( !*((_BYTE *)v147 + 5820) && v146 >= 0x20 )
                      {
                        PoolIdForObject = SOS_ObjectStore::GetPoolIdForObject(v147, (struct SList *)v136);
                        v149 = *(_QWORD *)(v137 + 128);
                        v150 = *(_QWORD **)(v137 + 136);
                        if ( v150 != (_QWORD *)(v137 + 128) && v150 )
                        {
                          *v150 = *(_QWORD *)(v137 + 8 * PoolIdForObject + 1184);
                          *(_QWORD *)(v137 + 8 * PoolIdForObject + 1184) = v149;
                        }
                        *(_QWORD *)(v137 + 128) = 0;
                        *(_QWORD *)(v137 + 136) = v137 + 128;
                        v146 = 0;
                        v151 = *(_QWORD *)(v137 + 1696);
                        if ( (v151 & (1LL << PoolIdForObject)) == 0 )
                          *(_QWORD *)(v137 + 1696) = (1LL << PoolIdForObject) | v151;
                      }
                      *(_QWORD *)(v137 + 1168) = v146;
                      if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
                      {
                        v152 = rand();
                        if ( v152 == 5 * (v152 / 5) )
                          Spinlock<34,1,268435714>::UpdateStatSnapshot();
                      }
                      *(_QWORD *)(v137 + 40) = 0;
                    }
                  }
                  else
                  {
                    v154 = v122 - 1;
                    if ( (SOS_Tracing_osTrace & 0x1000) != 0 )
                    {
                      VirtualFree(v154, 0, 0x8000u);
                    }
                    else if ( v122 != (__int64 *)8 )
                    {
                      ISOSHost_TaskImpl::`scalar deleting destructor'((ISOSHost_TaskImpl *)v154, 1u);
                    }
                  }
                }
              }
            }
          }
        }
      }
      qword_102F3EDF0 = 30000;
      IServerConfiguration::GetDynamicInt64Setting(
        s_pServerConf,
        L"SQLFrontendSettings",
        L"CompileCpuTimeShallowScanInViewThresholdMillisec",
        &qword_102F3EDF0,
        1,
        0);
      dword_102F3EDF8 = 5;
      LOBYTE(v160) = 1;
      (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, int *, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
        s_pServerConf,
        L"SQLFrontendSettings",
        L"ScanInViewErrorCountThreshold",
        &dword_102F3EDF8,
        v160,
        0);
      dword_102F3EDFC = 0x2000;
      LOBYTE(v161) = 1;
      (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, int *, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
        s_pServerConf,
        L"SQLFrontendSettings",
        L"ParserMemoryUsageThresholdTelemetry",
        &dword_102F3EDFC,
        v161,
        0);
      dword_102F3EE00 = 0x8000;
      LOBYTE(v162) = 1;
      (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, int *, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
        s_pServerConf,
        L"SQLFrontendSettings",
        L"AlgebrizerMemoryUsageThresholdTelemetry",
        &dword_102F3EE00,
        v162,
        0);
      if ( !byte_102EDCF36 || (v155 = (*((_BYTE *)qword_102ECFB10 + 1290) & 2) == 0, byte_102F3EE04 = 1, !v155) )
        byte_102F3EE04 = 0;
    }
  }
}

```

## disassembly

```asm
0x101e44f90  mov     rax, rsp
0x101e44f93  push    rbp
0x101e44f94  push    r12
0x101e44f96  push    r13
0x101e44f98  push    r14
0x101e44f9a  push    r15
0x101e44f9c  lea     rbp, [rax-208h]
0x101e44fa3  sub     rsp, 2E0h
0x101e44faa  mov     [rbp+200h+var_260], 0FFFFFFFFFFFFFFFEh
0x101e44fb2  mov     [rax+10h], rbx
0x101e44fb6  mov     [rax+18h], rsi
0x101e44fba  mov     [rax+20h], rdi
0x101e44fbe  mov     rax, cs:__security_cookie
0x101e44fc5  xor     rax, rsp
0x101e44fc8  mov     [rbp+200h+var_30], rax
0x101e44fcf  mov     r13, rcx
0x101e44fd2  test    dword ptr [rcx+18h], 8000h
0x101e44fd9  jnz     loc_101E46475
0x101e44fdf  mov     ecx, [rcx+4]; unsigned int
0x101e44fe2  call    ?InitSharedResource@@YAXK@Z; InitSharedResource(ulong)
0x101e44fe7  lea     rcx, off_102FEF4E8
0x101e44fee  call    cs:__imp_?SetExtenderInterface@CSqlTypeSystemHost@@SAXPEAUISqlTypeSystemExtender_IDbAndSetOptsProvider@@@Z; CSqlTypeSystemHost::SetExtenderInterface(ISqlTypeSystemExtender_IDbAndSetOptsProvider *)
0x101e44ff4  lea     rcx, off_102FDFDA8
0x101e44ffb  call    cs:__imp_?SetExtenderInterface@CSqlTypeSystemHost@@SAXPEAUISqlTypeSystemExtender_IXMLTypeProvider@@@Z; CSqlTypeSystemHost::SetExtenderInterface(ISqlTypeSystemExtender_IXMLTypeProvider *)
0x101e45001  lea     rcx, off_102FD94E0
0x101e45008  call    cs:__imp_?SetExtenderInterface@CSqlTypeSystemHost@@SAXPEAUISqlTypeSystemExtender_IExecControl@@@Z; CSqlTypeSystemHost::SetExtenderInterface(ISqlTypeSystemExtender_IExecControl *)
0x101e4500e  lea     rcx, off_102FD63B8
0x101e45015  call    cs:__imp_?SetExtenderInterface@CSqlTypeSystemHost@@SAXPEAUISqlTypeSystemExtender_ITDSFormatter@@@Z; CSqlTypeSystemHost::SetExtenderInterface(ISqlTypeSystemExtender_ITDSFormatter *)
0x101e4501b  lea     rcx, off_102FDE070
0x101e45022  call    cs:__imp_?SetExtenderInterface@CSqlTypeSystemHost@@SAXPEAUISqlTypeSystemExtender_IOLEDB@@@Z; CSqlTypeSystemHost::SetExtenderInterface(ISqlTypeSystemExtender_IOLEDB *)
0x101e45028  lea     rcx, off_102FD9810
0x101e4502f  call    cs:__imp_?SetExtenderInterface@CSqlTypeSystemHost@@SAXPEAUISqlTypeSystemExtender_IUdtProvider@@@Z; CSqlTypeSystemHost::SetExtenderInterface(ISqlTypeSystemExtender_IUdtProvider *)
0x101e45035  lea     rcx, ?x_tsContextProvider@CContextProviderForTypeSystem@@0V1@A; CContextProviderForTypeSystem CContextProviderForTypeSystem::x_tsContextProvider
0x101e4503c  call    cs:__imp_?SetExtenderInterface@CSqlTypeSystemHost@@SAXPEAUISqlTypeSystemExtender_ContextProvider@@@Z; CSqlTypeSystemHost::SetExtenderInterface(ISqlTypeSystemExtender_ContextProvider *)
0x101e45042  lea     rcx, off_102FD6C00
0x101e45049  call    cs:__imp_?SetExtenderInterface@CSqlTypeSystemHost@@SAXPEAUISqlTypeSystemExtender_IJsonTypeProvider@@@Z; CSqlTypeSystemHost::SetExtenderInterface(ISqlTypeSystemExtender_IJsonTypeProvider *)
0x101e4504f  lea     rcx, ?CreateSQLAutoSetupContextForInternalTasks@@YAPEAVIAutoSetupExecContextsForInternalTasksImpl@@W4thread_type@@FPEB_W@Z; CreateSQLAutoSetupContextForInternalTasks(thread_type,short,wchar_t const *)
0x101e45056  mov     rax, cs:__imp_?g_pfnAutoSetupContextForInternalTasksFactory@@3P6APEAVIAutoSetupExecContextsForInternalTasksImpl@@W4thread_type@@FPEB_W@ZEA; IAutoSetupExecContextsForInternalTasksImpl * (*g_pfnAutoSetupContextForInternalTasksFactory)(thread_type,short,wchar_t const *)
0x101e4505d  mov     [rax], rcx
0x101e45060  lea     rcx, ?CreateAutoSetXLvlIntCtxtImpl@@YAPEAVIAutoSetXLvlIntCtxt@@PEAVIMemObj@@PEAVCSession@@PEAVCBatch@@@Z; CreateAutoSetXLvlIntCtxtImpl(IMemObj *,CSession *,CBatch *)
0x101e45067  mov     rax, cs:__imp_?s_pfnCreateAutoSetXLvlIntCtxt@@3P6APEAVIAutoSetXLvlIntCtxt@@PEAVIMemObj@@PEAVCSession@@PEAVCBatch@@@ZEA; IAutoSetXLvlIntCtxt * (*s_pfnCreateAutoSetXLvlIntCtxt)(IMemObj *,CSession *,CBatch *)
0x101e4506e  mov     [rax], rcx
0x101e45071  lea     rcx, off_102FDDA48
0x101e45078  call    cs:__imp_?SetSqlHandleModuleConverter@EngineCommonComponentInitializers@@YAXPEAUICurrentSqlToTextConverter@@@Z; EngineCommonComponentInitializers::SetSqlHandleModuleConverter(ICurrentSqlToTextConverter *)
0x101e4507e  mov     rdx, [r13+28h]; void (*)(void)
0x101e45082  mov     rcx, [r13+20h]; void (*)(const struct _EXCEPTION_POINTERS *)
0x101e45086  call    ?SqlDumpInit@@YAXP6AXPEBU_EXCEPTION_POINTERS@@@ZP6AXXZ@Z; SqlDumpInit(void (*)(_EXCEPTION_POINTERS const *),void (*)(void))
0x101e4508b  call    ?IsHekatonEnabled@@YA_NXZ; IsHekatonEnabled(void)
0x101e45090  xor     r12d, r12d
0x101e45093  mov     esi, 80h
0x101e45098  lea     r14d, [r12+1]
0x101e4509d  test    al, al
0x101e4509f  jz      loc_101E45211
0x101e450a5  call    cs:__imp_?HkHostGetGlobalThreadInfo@@YAPEAUHkHostThreadInfo@@XZ; HkHostGetGlobalThreadInfo(void)
0x101e450ab  call    cs:__imp_?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ; SOS_OS::GetClientProcessGlobals(void)
0x101e450b1  mov     rcx, rax
0x101e450b4  movzx   edx, r12w
0x101e450b8  call    cs:__imp_?GetDefaultMemoryClerksForNode@PerProcessGlobals@@QEAAPEAPEAVMemoryClerk@@G@Z; PerProcessGlobals::GetDefaultMemoryClerksForNode(ushort)
0x101e450be  mov     rbx, rax
0x101e450c1  call    cs:__imp_?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ; SOS_OS::GetClientProcessGlobals(void)
0x101e450c7  mov     rax, [rbx+100h]
0x101e450ce  lea     r9d, [r12+8]
0x101e450d3  lea     r8, [rax+40h]
0x101e450d7  test    rax, rax
0x101e450da  cmovz   r8, r12
0x101e450de  mov     word ptr [rsp+300h+var_2E0], si
0x101e450e3  lea     edx, [rsi-7Eh]
0x101e450e6  mov     ecx, 111h
0x101e450eb  call    cs:__imp_?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z; MemoryObjectFactory::CreateMemObject(SOSHOST_MEMOBJ_ID,ulong,PageAllocator *,short,short)
0x101e450f1  mov     cs:qword_102F11700, rax
0x101e450f8  test    rax, rax
0x101e450fb  jz      short loc_101E4515E
0x101e450fd  mov     dword ptr [rsp+300h+var_2E0], 100h
0x101e45105  mov     r9d, 118h
0x101e4510b  mov     r8, cs:?sm_PartitionedObjectSize@?$TDelayedPartitionedStack@VCMsqlExecContext@@$0CI@@@0_KA; unsigned __int64 TDelayedPartitionedStack<CMsqlExecContext,40>::sm_PartitionedObjectSize
0x101e45112  mov     edx, r14d
0x101e45115  lea     ecx, [rsi-7Bh]
0x101e45118  call    cs:__imp_?Create@SOS_PartitionedHeap@@SAPEAV1@W4SOS_PARTITIONEDHEAP@@W4PARTITIONING_TYPE@@_KW4SOSHOST_MEMOBJ_ID@@I@Z; SOS_PartitionedHeap::Create(SOS_PARTITIONEDHEAP,PARTITIONING_TYPE,unsigned __int64,SOSHOST_MEMOBJ_ID,uint)
0x101e4511e  mov     cs:?sm_ParHeap@HkProcCache@@0PEAVSOS_PartitionedHeap@@EA, rax; SOS_PartitionedHeap * HkProcCache::sm_ParHeap
0x101e45125  test    rax, rax
0x101e45128  jz      short loc_101E4515E
0x101e4512a  mov     rax, cs:qword_102ECFB00
0x101e45131  cmp     [rax+38A8h], r12d
0x101e45138  jz      short loc_101E4514D
0x101e4513a  mov     cs:?sm_isStmtStatsEnabled@HkProcCache@@0_NA, r14b; bool HkProcCache::sm_isStmtStatsEnabled
0x101e45141  movzx   eax, r14b
0x101e45145  mov     cs:?sm_isProcStatsEnabled@HkProcCache@@0_NA, al; bool HkProcCache::sm_isProcStatsEnabled
0x101e4514b  jmp     short loc_101E45180
0x101e4514d  mov     cs:?sm_isStmtStatsEnabled@HkProcCache@@0_NA, r12b; bool HkProcCache::sm_isStmtStatsEnabled
0x101e45154  xor     al, al
0x101e45156  mov     cs:?sm_isProcStatsEnabled@HkProcCache@@0_NA, al; bool HkProcCache::sm_isProcStatsEnabled
0x101e4515c  jmp     short loc_101E45180
0x101e4515e  lea     rdx, aHkproccacheIni; "HkProcCache::Init"
0x101e45165  mov     ecx, 42F2h; unsigned int
0x101e4516a  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x101e4516f  xor     edx, edx
0x101e45171  lea     ecx, [rdx+6Ah]
0x101e45174  mov     r8d, 8007000Eh
0x101e4517a  call    cs:__imp_?SQLExit@@YAXW4SQLEXITCODE@@KK@Z; SQLExit(SQLEXITCODE,ulong,ulong)
0x101e45180  lea     rax, ?g_sqlHostIntrinsics@@3USqlHostIntrinsics@@A; SqlHostIntrinsics g_sqlHostIntrinsics
0x101e45187  mov     qword ptr [rsp+300h+var_2B8], rax
0x101e4518c  mov     rax, cs:__imp_?g_pmoGlobal@@3PEAVIMemObj@@EA; IMemObj * g_pmoGlobal
0x101e45193  mov     rdx, [rax]
0x101e45196  mov     cs:qword_102FD96C0, rdx
0x101e4519d  mov     [rsp+300h+var_2D0], 51h ; 'Q'
0x101e451a5  mov     [rsp+300h+var_2E0], 3
0x101e451aa  mov     r9d, 51h ; 'Q'
0x101e451b0  lea     r8, aSqlNtdbmsHekat_8; "sql\\ntdbms\\Hekaton\\sqlhost\\sqllang"...
0x101e451b7  lea     ecx, [r9-29h]
0x101e451bb  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new(unsigned __int64,IMemObj *,char const *,int,uchar)
0x101e451c1  mov     rbx, rax
0x101e451c4  mov     qword ptr [rsp+300h+var_2C0], rax
0x101e451c9  test    rax, rax
0x101e451cc  jz      short loc_101E45207
0x101e451ce  mov     rcx, cs:qword_102FD96C0
0x101e451d5  mov     qword ptr [rbp+200h+var_280], rax
0x101e451d9  mov     [rax], rcx
0x101e451dc  movzx   ecx, word ptr [rsp+300h+var_2D0]
0x101e451e1  mov     [rax+8], cx
0x101e451e5  mov     [rax+0Ch], r12d
0x101e451e9  mov     [rax+10h], r12
0x101e451ed  mov     [rax+18h], r12
0x101e451f1  mov     [rax+20h], r12d
0x101e451f5  xor     r8d, r8d
0x101e451f8  lea     edx, [r8+28h]
0x101e451fc  mov     rcx, rax
0x101e451ff  call    ?Resize@?$CTHashTable@U?$Pair@PEAVCValRef@@PEAV?$CTSingleColumnPredicateCombiner@VCIntervalForCE@@@@@@VCEntryHashFn@?$CTMap@PEAVCValRef@@PEAV?$CTSingleColumnPredicateCombiner@VCIntervalForCE@@@@VCFnH_Pointer@@V?$CFnC_Default@PEAVCValRef@@@@V?$CFnI_Default@PEAV?$CTSingleColumnPredicateCombiner@VCIntervalForCE@@@@@@V?$CFnD_Noop@PEAVCValRef@@@@V?$CFnD_Ptr@V?$CTSingleColumnPredicateCombiner@VCIntervalForCE@@@@@@V?$CMemObjAlloc@$0A@@@@@VCEntryCmpFn@3@VCEntryInvalidFn@3@VCEntryDestroyFn@3@V?$CMemObjAlloc@$0A@@@@@AEAAXKPEAV?$CMemObjAlloc@$0A@@@@Z; CTHashTable<Pair<CValRef *,CTSingleColumnPredicateCombiner<CIntervalForCE> *>,CTMap<CValRef *,CTSingleColumnPredicateCombiner<CIntervalForCE> *,CFnH_Pointer,CFnC_Default<CValRef *>,CFnI_Default<CTSingleColumnPredicateCombiner<CIntervalForCE> *>,CFnD_Noop<CValRef *>,CFnD_Ptr<CTSingleColumnPredicateCombiner<CIntervalForCE>>,CMemObjAlloc<0>>::CEntryHashFn,CTMap<CValRef *,CTSingleColumnPredicateCombiner<CIntervalForCE> *,CFnH_Pointer,CFnC_Default<CValRef *>,CFnI_Default<CTSingleColumnPredicateCombiner<CIntervalForCE> *>,CFnD_Noop<CValRef *>,CFnD_Ptr<CTSingleColumnPredicateCombiner<CIntervalForCE>>,CMemObjAlloc<0>>::CEntryCmpFn,CTMap<CValRef *,CTSingleColumnPredicateCombiner<CIntervalForCE> *,CFnH_Pointer,CFnC_Default<CValRef *>,CFnI_Default<CTSingleColumnPredicateCombiner<CIntervalForCE> *>,CFnD_Noop<CValRef *>,CFnD_Ptr<CTSingleColumnPredicateCombiner<CIntervalForCE>>,CMemObjAlloc<0>>::CEntryInvalidFn,CTMap<CValRef *,CTSingleColumnPredicateCombiner<CIntervalForCE> *,CFnH_Pointer,CFnC_Default<CValRef *>,CFnI_Default<CTSingleColumnPredicateCombiner<CIntervalForCE> *>,CFnD_Noop<CValRef *>,CFnD_Ptr<CTSingleColumnPredicateCombiner<CIntervalForCE>>,CMemObjAlloc<0>>::CEntryDestroyFn,CMemObjAlloc<0>>::Resize(ulong,CMemObjAlloc<0> *)
0x101e45204  nop
0x101e45205  jmp     short loc_101E4520A
0x101e45207  mov     rbx, r12
0x101e4520a  mov     cs:qword_102FD96C8, rbx
0x101e45211  mov     ecx, [r13+0]; int
0x101e45215  call    ?SetupSessions@@YAXJ@Z; SetupSessions(long)
0x101e4521a  mov     rax, cs:__imp_?g_pmoGlobal@@3PEAVIMemObj@@EA; IMemObj * g_pmoGlobal
0x101e45221  mov     rdx, [rax]
0x101e45224  mov     qword ptr [rsp+300h+var_2B8], rdx
0x101e45229  mov     [rsp+300h+var_2D0], 28h ; '('
0x101e45231  mov     [rsp+300h+var_2E0], 3
0x101e45236  mov     r9d, 28h ; '('
0x101e4523c  lea     r8, aSqlNtdbmsMsqlU_23; "sql\\ntdbms\\msql\\utils\\dbccdll.cpp"
0x101e45243  lea     ecx, [r9+48h]
0x101e45247  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new(unsigned __int64,IMemObj *,char const *,int,uchar)
0x101e4524d  mov     rdi, rax
0x101e45250  mov     qword ptr [rsp+300h+var_2C0], rax
0x101e45255  mov     r15, 0FFFFFFFFFFFFFFFFh
0x101e4525c  test    rax, rax
0x101e4525f  jz      loc_101E4534B
0x101e45265  mov     dword ptr [rax+18h], 2Ch ; ','
0x101e4526c  mov     [rax+8], r12
0x101e45270  mov     [rax+10h], r12
0x101e45274  mov     [rax], r12
0x101e45277  mov     [rax+20h], r12
0x101e4527b  mov     [rax+28h], r12d
0x101e4527f  mov     [rax+30h], r12d
0x101e45283  mov     [rax+38h], r12
0x101e45287  mov     [rax+40h], r12
0x101e4528b  mov     eax, [rax+58h]
0x101e4528e  mov     [rdi+48h], eax
0x101e45291  mov     [rdi+50h], r12
0x101e45295  mov     dword ptr [rdi+58h], 0FFFFFFFFh
0x101e4529c  lea     rax, [rdi+60h]
0x101e452a0  mov     [rax+8], rax
0x101e452a4  mov     [rax], rax
0x101e452a7  mov     rbx, cs:__imp_?x_pDefAllocMemObj@@3PEAVIMemObj@@EA; IMemObj * x_pDefAllocMemObj
0x101e452ae  mov     rbx, [rbx]
0x101e452b1  mov     [rbp+200h+var_258], rbx
0x101e452b5  mov     esi, r14d
0x101e452b8  add     esi, esi
0x101e452ba  cmp     esi, 1Fh
0x101e452bd  jl      short loc_101E452B8
0x101e452bf  lea     eax, [rsi-1]
0x101e452c2  mov     [rdi+2Ch], eax
0x101e452c5  movsxd  r14, esi
0x101e452c8  mov     eax, 10h
0x101e452cd  mul     r14
0x101e452d0  cmovo   rax, r15
0x101e452d4  mov     byte ptr [rsp+300h+var_2D8], 3
0x101e452d9  mov     dword ptr [rsp+300h+var_2E0], 7Fh
0x101e452e1  lea     r9, aSqlDktempBaseI; "Sql\\DkTemp\\base\\include\\sehash.inl"
0x101e452e8  mov     r8d, 1
0x101e452ee  mov     rdx, rbx
0x101e452f1  mov     rcx, rax
0x101e452f4  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new[](unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x101e452fa  mov     [rsp+300h+var_2C8], rax
0x101e452ff  test    rax, rax
0x101e45302  jz      short loc_101E45323
0x101e45304  mov     rcx, rax
0x101e45307  nop     word ptr [rax+rax+00000000h]
0x101e45310  mov     [rcx+8], rcx
0x101e45314  mov     [rcx], rcx
0x101e45317  add     rcx, 10h
0x101e4531b  sub     r14, 1
0x101e4531f  jnz     short loc_101E45310
0x101e45321  jmp     short loc_101E45326
0x101e45323  mov     rax, r12
0x101e45326  mov     [rdi+20h], rax
0x101e4532a  test    rax, rax
0x101e4532d  jz      short loc_101E45338
0x101e4532f  mov     [rdi+28h], esi
0x101e45332  mov     [rdi+38h], rbx
0x101e45336  jmp     short loc_101E45340
0x101e45338  mov     cl, 0E1h
0x101e4533a  call    ?ex_raise_oom@@YAXW4OOM_EXCEPTIONS@@@Z; ex_raise_oom(OOM_EXCEPTIONS)
0x101e4533f  nop
0x101e45340  mov     esi, 80h
0x101e45345  lea     r14d, [rsi-7Fh]
0x101e45349  jmp     short loc_101E4534E
0x101e4534b  mov     rdi, r12
0x101e4534e  mov     cs:?g_pDLLHashTable@@3PEAVHashDLL@@EA, rdi; HashDLL * g_pDLLHashTable
0x101e45355  call    ?FInitLpeEventsSubSystem@LpeEvents@@YAHXZ; LpeEvents::FInitLpeEventsSubSystem(void)
0x101e4535a  test    eax, eax
0x101e4535c  jnz     short loc_101E45380
0x101e4535e  lea     rdx, aServerEventsSu; "Server events subsystem"
0x101e45365  mov     ecx, 42F2h; unsigned int
0x101e4536a  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x101e4536f  xor     edx, edx
0x101e45371  lea     ecx, [rdx+6Bh]
0x101e45374  mov     r8d, 8007000Eh
0x101e4537a  call    cs:__imp_?SQLExit@@YAXW4SQLEXITCODE@@KK@Z; SQLExit(SQLEXITCODE,ulong,ulong)
0x101e45380  mov     r8d, r14d
0x101e45383  mov     edx, 59h ; 'Y'
0x101e45388  lea     rcx, aMemoryclerkDek; "MemoryClerk DEK"
0x101e4538f  call    cs:__imp_?CreateMemoryClerk@SOS_Node@@SAPEAVMemoryClerk@@PEB_WW4SOSHOST_MEMORYCLERK_TYPE@@W4SOS_CallerType@@@Z; SOS_Node::CreateMemoryClerk(wchar_t const *,SOSHOST_MEMORYCLERK_TYPE,SOS_CallerType)
0x101e45395  mov     cs:?s_memoryClerkDEK@CSECDEK@@0PEAVMemoryClerk@@EA, rax; MemoryClerk * CSECDEK::s_memoryClerkDEK
0x101e4539c  test    rax, rax
0x101e4539f  jz      short loc_101E453D2
0x101e453a1  or      dword ptr [rax+624h], 10h
0x101e453a8  lea     r8, [rax+40h]
0x101e453ac  mov     r9d, 8
0x101e453b2  mov     word ptr [rsp+300h+var_2E0], si
0x101e453b7  lea     edx, [r9-2]
0x101e453bb  mov     ecx, 1A0h
0x101e453c0  call    cs:__imp_?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z; MemoryObjectFactory::CreateMemObject(SOSHOST_MEMOBJ_ID,ulong,PageAllocator *,short,short)
0x101e453c6  mov     cs:?s_pmoDEK@CSECDEK@@0PEAVIMemObj@@EA, rax; IMemObj * CSECDEK::s_pmoDEK
0x101e453cd  test    rax, rax
0x101e453d0  jnz     short loc_101E453F4
0x101e453d2  lea     rdx, aDekMemoryObjec; "DEK memory object"
0x101e453d9  mov     ecx, 42F2h; unsigned int
0x101e453de  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x101e453e3  xor     edx, edx
0x101e453e5  lea     ecx, [rdx+6Ch]
0x101e453e8  mov     r8d, 8007000Eh
0x101e453ee  call    cs:__imp_?SQLExit@@YAXW4SQLEXITCODE@@KK@Z; SQLExit(SQLEXITCODE,ulong,ulong)
0x101e453f4  mov     r8d, r14d
0x101e453f7  mov     edx, 5Dh ; ']'
0x101e453fc  lea     rcx, aMemoryclerkSec; "MemoryClerk Security"
0x101e45403  call    cs:__imp_?CreateMemoryClerk@SOS_Node@@SAPEAVMemoryClerk@@PEB_WW4SOSHOST_MEMORYCLERK_TYPE@@W4SOS_CallerType@@@Z; SOS_Node::CreateMemoryClerk(wchar_t const *,SOSHOST_MEMORYCLERK_TYPE,SOS_CallerType)
0x101e45409  mov     cs:?s_memoryClerkSec@SecThreadSafePmo@@0PEAVMemoryClerk@@EA, rax; MemoryClerk * SecThreadSafePmo::s_memoryClerkSec
0x101e45410  test    rax, rax
0x101e45413  jz      short loc_101E4543F
0x101e45415  lea     r8, [rax+40h]
0x101e45419  mov     r9d, 8
0x101e4541f  mov     word ptr [rsp+300h+var_2E0], si
0x101e45424  lea     edx, [r9-2]
0x101e45428  mov     ecx, 1ACh
0x101e4542d  call    cs:__imp_?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z; MemoryObjectFactory::CreateMemObject(SOSHOST_MEMOBJ_ID,ulong,PageAllocator *,short,short)
0x101e45433  mov     cs:?s_pmoSec@SecThreadSafePmo@@0PEAVIMemObj@@EA, rax; IMemObj * SecThreadSafePmo::s_pmoSec
0x101e4543a  test    rax, rax
0x101e4543d  jnz     short loc_101E45463
0x101e4543f  lea     rdx, aSecMemoryObjec; "Sec memory object"
0x101e45446  mov     ecx, 42F2h; unsigned int
0x101e4544b  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x101e45450  xor     edx, edx
0x101e45452  mov     ecx, 147h
0x101e45457  mov     r8d, 8007000Eh
0x101e4545d  call    cs:__imp_?SQLExit@@YAXW4SQLEXITCODE@@KK@Z; SQLExit(SQLEXITCODE,ulong,ulong)
0x101e45463  call    cs:__imp_?InitXPMO@@YAHXZ; InitXPMO(void)
0x101e45469  test    eax, eax
0x101e4546b  jnz     short loc_101E4548F
0x101e4546d  lea     rdx, aXpMemoryObject; "XP memory object"
0x101e45474  mov     ecx, 42F2h; unsigned int
0x101e45479  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x101e4547e  xor     edx, edx
0x101e45480  lea     ecx, [rdx+6Dh]
0x101e45483  mov     r8d, 8007000Eh
0x101e45489  call    cs:__imp_?SQLExit@@YAXW4SQLEXITCODE@@KK@Z; SQLExit(SQLEXITCODE,ulong,ulong)
0x101e4548f  mov     rax, [r13+10h]
0x101e45493  mov     rcx, [rax]
0x101e45496  mov     cs:?m_sdServerStartTime@CDiagnosticsBase@@1USQLDATE@@A, rcx; SQLDATE CDiagnosticsBase::m_sdServerStartTime
0x101e4549d  mov     rdx, gs:58h
0x101e454a6  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101e454ad  mov     ecx, [rax]
0x101e454af  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101e454b6  mov     ebx, [rax]
0x101e454b8  add     rbx, [rdx+rcx*8]
0x101e454bc  mov     rax, [rbx+100h]
0x101e454c3  test    rax, rax
0x101e454c6  jnz     short loc_101E454D7
0x101e454c8  xor     ecx, ecx
0x101e454ca  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x101e454d0  mov     rax, [rbx+100h]
0x101e454d7  mov     rax, [rax+3E0h]
0x101e454de  mov     r10, [rax+140h]
0x101e454e5  mov     [rbp+200h+var_268], r10
0x101e454e9  mov     rax, cs:__imp_?s_pServerConf@@3PEAVIServerConfiguration@@EA; IServerConfiguration * s_pServerConf
0x101e454f0  mov     rcx, [rax]
0x101e454f3  mov     eax, cs:?m_cBuckets@CDiagManager@@0KA; ulong CDiagManager::m_cBuckets
0x101e454f9  mov     edx, 64h ; 'd'
0x101e454fe  cmp     dword ptr [rcx+8], 0
0x101e45502  cmovz   eax, edx
  ... truncated ...
```
