# SEInit(IFTServiceMgr *,StorageEngineStartupCallbacks &)

- ea: `0x101ba9540`
- end: `0x101baaa12`
- name: `?SEInit@@YAXPEAVIFTServiceMgr@@AEAUStorageEngineStartupCallbacks@@@Z`
- size: `5330`
- prototype: `void __fastcall(struct IFTServiceMgr *, struct StorageEngineStartupCallbacks *)`
- caller_count: `1`
- callee_count: `42`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1023ab1f0`

## callees

- `0x100401490`
- `0x100402000`
- `0x100424500`
- `0x100428760`
- `0x1005d28e0`
- `0x10063dc00`
- `0x1007736c0`
- `0x1007a86f0`
- `0x1007c67d0`
- `0x101105780`
- `0x1011fea10`
- `0x1012540f0`
- `0x101254e50`
- `0x1012552c0`
- `0x1014d4110`
- `0x101577e40`
- `0x1016cb3e0`
- `0x1016ed710`
- `0x101877090`
- `0x1018785f0`
- `0x10189e6d0`
- `0x1019ea760`
- `0x1019f7d80`
- `0x101b6fcc0`
- `0x101ba8b70`
- `0x101ba9340`
- `0x101ba9540`
- `0x101c6a8c0`
- `0x101c8e170`
- `0x101d31b40`
- `0x101fe2720`
- `0x102067020`
- `0x10217db20`
- `0x1022c7320`
- `0x1022cc960`
- `0x1022d6ee0`
- `0x102324760`
- `0x10239ade0`
- `0x1023aea90`
- `0x1023aecb0`
- `0x1023aee60`
- `0x10249b1f0`

## import_xrefs

- `KERNEL32!CreateEventA` at `0x101baa803`
- `KERNEL32!CreateEventA` at `0x101baa803`
- `KERNEL32!QueryPerformanceFrequency` at `0x101baa2c3`
- `KERNEL32!QueryPerformanceFrequency` at `0x101baa2c3`
- `KERNEL32!QueryPerformanceCounter` at `0x101ba9ab6`
- `KERNEL32!QueryPerformanceCounter` at `0x101ba9ab6`
- `KERNEL32!GetLastError` at `0x101baa815`
- `KERNEL32!GetLastError` at `0x101baa815`
- `sqldk!?CreateMemoryObject@SOS_UserStore@@QEAAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KFF@Z` at `0x101ba9b0e`
- `sqldk!?CreateMemoryObject@SOS_UserStore@@QEAAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KFF@Z` at `0x101ba9be9`
- `sqldk!?CreateMemoryObject@SOS_UserStore@@QEAAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KFF@Z` at `0x101ba9b0e`
- `sqldk!?CreateMemoryObject@SOS_UserStore@@QEAAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KFF@Z` at `0x101ba9be9`
- `sqldk!??2@YAPEAX_K@Z` at `0x101ba9eda`
- `sqldk!??2@YAPEAX_K@Z` at `0x101ba9eda`
- `sqldk!?CreateStore@SOS_CacheStore@@SAPEAV1@PEB_WW4SOSHOST_CACHESTORE_TYPE@@K_JPEBUSOSHost_CacheStoreHashTableDescriptor@@P6AXPEAXW4destroy_type@@@ZKW4SOSHOST_MEMOBJ_ID@@PEAVSOS_StoreAndClockAlgorithmControlInterface@@@Z` at `0x101ba9b95`
- `sqldk!?CreateStore@SOS_CacheStore@@SAPEAV1@PEB_WW4SOSHOST_CACHESTORE_TYPE@@K_JPEBUSOSHost_CacheStoreHashTableDescriptor@@P6AXPEAXW4destroy_type@@@ZKW4SOSHOST_MEMOBJ_ID@@PEAVSOS_StoreAndClockAlgorithmControlInterface@@@Z` at `0x101ba9b95`
- `sqldk!?StaticInit@GlobalCacheActivenessStats@@SA_N_K0@Z` at `0x101ba9a3b`
- `sqldk!?StaticInit@GlobalCacheActivenessStats@@SA_N_K0@Z` at `0x101ba9a3b`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x101baa893`
- `sqldk!?sm_ResourceManager@SOS_PublicGlobals@@2VSOS_ResourceManager@@A` at `0x101baa449`
- `sqldk!?sm_cpuCount@SOS_PublicGlobals@@2KA` at `0x101baa3b3`
- `sqldk!?SOS_OS_MemoryModel@@3W4SOS_MemoryModel@@A` at `0x101ba959a`
- `sqldk!?MemoryNode_MemoryTargetPages@@3_JA` at `0x101ba9941`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101ba9a72`
- `sqldk!?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A` at `0x101ba9a7e`
- `sqldk!?UpdateGlobalMemoryStatus@MemoryNode@@SAXXZ` at `0x101ba9900`
- `sqldk!?UpdateGlobalMemoryStatus@MemoryNode@@SAXXZ` at `0x101ba9900`
- `sqldk!?GetGlobalMemoryStatus@MemoryNode@@SAXPEAU_MEMORYSTATUSEX@@PEAU_PROCESS_MEMORY_COUNTERS_EX@@PEAU_JOBOBJECT_EXTENDED_LIMIT_INFORMATION@@PEAHPEA_J@Z` at `0x101ba9929`
- `sqldk!?GetGlobalMemoryStatus@MemoryNode@@SAXPEAU_MEMORYSTATUSEX@@PEAU_PROCESS_MEMORY_COUNTERS_EX@@PEAU_JOBOBJECT_EXTENDED_LIMIT_INFORMATION@@PEAHPEA_J@Z` at `0x101ba9929`
- `sqldk!?LookupGroup@SOS_ResourceManager@@QEAA?AW4SOS_RESULT@@PEB_W_JPEAPEAVSOS_ResourceGroup@@@Z` at `0x101baa482`
- `sqldk!?LookupGroup@SOS_ResourceManager@@QEAA?AW4SOS_RESULT@@PEB_W_JPEAPEAVSOS_ResourceGroup@@@Z` at `0x101baa482`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x101ba9cc9`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x101baa568`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x101ba9cc9`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x101baa568`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x101baa82a`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x101baa82a`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101baa130`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101baa506`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101baa130`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101baa506`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ba97d7`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ba98ee`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ba9c4f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ba9ecf`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101baa046`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101baa072`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ba97d7`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ba98ee`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ba9c4f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101ba9ecf`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101baa046`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101baa072`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101baa226`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101baa226`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x101ba96a7`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x101ba96c0`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x101ba975c`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x101ba9775`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x101ba987c`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x101ba9895`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x101ba9d6c`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x101ba9d85`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x101ba9e32`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x101ba9e4b`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x101ba9f95`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x101ba9fae`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x101baa0b9`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x101baa0d2`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x101baa30f`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x101baa328`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x101ba96a7`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x101ba96c0`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x101ba975c`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x101ba9775`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x101ba987c`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x101ba9895`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x101ba9d6c`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x101ba9d85`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x101ba9e32`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x101ba9e4b`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x101ba9f95`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x101ba9fae`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x101baa0b9`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x101baa0d2`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x101baa30f`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x101baa328`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101ba997e`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101ba9a63`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101ba9b3e`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101ba9bc5`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101ba9c17`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101ba9deb`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101ba9ea3`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101baa01a`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101baa177`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101baa1da`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101baa2b9`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101baa383`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101baa6a7`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101baa7bc`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101baa7f2`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101baa854`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101baa87f`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101baa8f5`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101baa9d4`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101ba997e`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101ba9a63`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101ba9b3e`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101ba9bc5`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101ba9c17`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101ba9deb`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101ba9ea3`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101baa01a`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101baa177`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101baa1da`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101baa2b9`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101baa383`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101baa6a7`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101baa7bc`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101baa7f2`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101baa854`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101baa87f`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101baa8f5`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101baa9d4`
- `sqldk!?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z` at `0x101ba96ed`
- `sqldk!?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z` at `0x101ba97a2`
- `sqldk!?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z` at `0x101ba98c2`
- `sqldk!?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z` at `0x101ba9dbb`
- `sqldk!?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z` at `0x101ba9e73`
- `sqldk!?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z` at `0x101ba9fd6`
- `sqldk!?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z` at `0x101baa0fc`
- `sqldk!?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z` at `0x101baa355`
- `sqldk!?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z` at `0x101ba96ed`
- `sqldk!?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z` at `0x101ba97a2`
- `sqldk!?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z` at `0x101ba98c2`
- `sqldk!?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z` at `0x101ba9dbb`
- `sqldk!?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z` at `0x101ba9e73`
- `sqldk!?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z` at `0x101ba9fd6`
- `sqldk!?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z` at `0x101baa0fc`
- `sqldk!?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z` at `0x101baa355`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x101baa286`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x101baa286`
- `sqldk!SystemThread_TlsIndex` at `0x101ba966f`
- `sqldk!SystemThread_TlsIndex` at `0x101ba9724`
- `sqldk!SystemThread_TlsIndex` at `0x101ba97e8`
- `sqldk!SystemThread_TlsIndex` at `0x101ba9844`
- `sqldk!SystemThread_TlsIndex` at `0x101ba9c5e`
- `sqldk!SystemThread_TlsIndex` at `0x101ba9d34`
- `sqldk!SystemThread_TlsIndex` at `0x101ba9dfa`
- `sqldk!SystemThread_TlsIndex` at `0x101ba9f5d`
- `sqldk!SystemThread_TlsIndex` at `0x101baa081`
- `sqldk!SystemThread_TlsIndex` at `0x101baa1f7`
- `sqldk!SystemThread_TlsIndex` at `0x101baa2d7`
- `sqldk!SystemThread_TlsIndex` at `0x101baa70b`
- `sqldk!SystemThread_TlsOffset` at `0x101ba9678`
- `sqldk!SystemThread_TlsOffset` at `0x101ba972d`
- `sqldk!SystemThread_TlsOffset` at `0x101ba97f1`
- `sqldk!SystemThread_TlsOffset` at `0x101ba984d`
- `sqldk!SystemThread_TlsOffset` at `0x101ba9c67`
- `sqldk!SystemThread_TlsOffset` at `0x101ba9d3d`
- `sqldk!SystemThread_TlsOffset` at `0x101ba9e03`
- `sqldk!SystemThread_TlsOffset` at `0x101ba9f66`
- `sqldk!SystemThread_TlsOffset` at `0x101baa08a`
- `sqldk!SystemThread_TlsOffset` at `0x101baa200`
- `sqldk!SystemThread_TlsOffset` at `0x101baa2e0`
- `sqldk!SystemThread_TlsOffset` at `0x101baa714`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101ba9693`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101ba9748`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101ba980c`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101ba9868`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101ba9c82`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101ba9d58`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101ba9e1e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101ba9f81`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101baa0a5`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101baa2fb`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101baa72f`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101ba9693`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101ba9748`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101ba980c`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101ba9868`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101ba9c82`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101ba9d58`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101ba9e1e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101ba9f81`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101baa0a5`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101baa2fb`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101baa72f`
- `sqldk!?GetDefaultMemoryClerksForNode@PerProcessGlobals@@QEAAPEAPEAVMemoryClerk@@G@Z` at `0x101ba96b7`
- `sqldk!?GetDefaultMemoryClerksForNode@PerProcessGlobals@@QEAAPEAPEAVMemoryClerk@@G@Z` at `0x101ba976c`
- `sqldk!?GetDefaultMemoryClerksForNode@PerProcessGlobals@@QEAAPEAPEAVMemoryClerk@@G@Z` at `0x101ba988c`
- `sqldk!?GetDefaultMemoryClerksForNode@PerProcessGlobals@@QEAAPEAPEAVMemoryClerk@@G@Z` at `0x101ba9d7c`
- `sqldk!?GetDefaultMemoryClerksForNode@PerProcessGlobals@@QEAAPEAPEAVMemoryClerk@@G@Z` at `0x101ba9e42`
- `sqldk!?GetDefaultMemoryClerksForNode@PerProcessGlobals@@QEAAPEAPEAVMemoryClerk@@G@Z` at `0x101ba9fa5`
- `sqldk!?GetDefaultMemoryClerksForNode@PerProcessGlobals@@QEAAPEAPEAVMemoryClerk@@G@Z` at `0x101baa0c9`
- `sqldk!?GetDefaultMemoryClerksForNode@PerProcessGlobals@@QEAAPEAPEAVMemoryClerk@@G@Z` at `0x101baa31f`
- `sqldk!?GetDefaultMemoryClerksForNode@PerProcessGlobals@@QEAAPEAPEAVMemoryClerk@@G@Z` at `0x101ba96b7`
- `sqldk!?GetDefaultMemoryClerksForNode@PerProcessGlobals@@QEAAPEAPEAVMemoryClerk@@G@Z` at `0x101ba976c`
- `sqldk!?GetDefaultMemoryClerksForNode@PerProcessGlobals@@QEAAPEAPEAVMemoryClerk@@G@Z` at `0x101ba988c`

## string_xrefs

- `0x101ba9a45`: `GlobalCacheActivenessStats`
- `0x101baa555`: `Sql\Ntdbms\storeng\dfs\access\multithreadedversioncleaner.cpp`
- `0x101baa4af`: `MULTITHREADED VERSIONCLEANUP WORKER POOL`
- `0x101baa863`: `BlobAccess`
- `0x101ba9e85`: `SubprocessDescriptor memory object`
- `0x101ba9cb7`: `Sql\Ntdbms\storeng\dfs\access\FcsMetadataCache\FcsMetadataCacheCore.cpp`
- `0x101baa276`: `sql\ntdbms\storeng\dfs\alloc\ExtentCache.cpp`
- `0x101ba9bfb`: `Schema Manager SEColumn Store Metadata Cache memory object`
- `0x101ba9b20`: `Schema Manager SEColumn Metadata Cache memory object`
- `0x101ba9ba7`: `Schema Manager SEColumn Metadata Cache cache store`
- `0x101ba9b8e`: `SESHAREDCOLMETADATACACHE`
- `0x101baa833`: `StartUp::CreateStartupEvents()`
- `0x101ba9a29`: `Init GlobalCacheActivenessStats: %d cores %d partitions %d interval period seconds.\n`
- `0x101baa6de`: `Failed to initialize the fast RBPEX reads`
- `0x101baa762`: `[%hs] Log replica instance initialization completed with result: %lx`
- `0x101baa29d`: `Extent Cache`
- `0x101baa689`: `Remote block IO subsystem configuration`
- `0x101baa367`: `Columnstore Lob Compression`
- `0x101baa9b8`: `Fido Transport Layer Configuration`
- `0x101ba98dd`: `sqlstorecachestats.cpp`
- `0x101ba9c3e`: `FcsMetadataCacheCore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall SEInit(struct IFTServiceMgr *a1, struct StorageEngineStartupCallbacks *a2)
{
  char *v4; // rbx
  __int64 v5; // rbx
  __int64 v6; // rax
  __int64 v7; // rbx
  PerProcessGlobals *ClientProcessGlobals; // rax
  struct MemoryClerk **DefaultMemoryClerksForNode; // rbx
  struct MemoryClerk *v10; // rax
  char *v11; // r8
  __int64 v12; // rcx
  __int64 MemObject; // rbx
  __int64 v14; // rbx
  __int64 v15; // rax
  __int64 v16; // rbx
  PerProcessGlobals *v17; // rax
  struct MemoryClerk **v18; // rbx
  struct MemoryClerk *v19; // rax
  char *v20; // r8
  struct IMemObj *v21; // rax
  __int64 v22; // rbx
  __int64 v23; // rax
  __int64 v24; // rbx
  __int64 v25; // rax
  __int64 v26; // rbx
  PerProcessGlobals *v27; // rax
  struct MemoryClerk **v28; // rbx
  struct MemoryClerk *v29; // rax
  char *v30; // r8
  unsigned __int64 v31; // rbx
  double v32; // xmm1_8
  unsigned __int64 v33; // rax
  unsigned __int64 v34; // r10
  unsigned __int64 v35; // rdi
  unsigned __int64 v36; // rbx
  LONGLONG v37; // rax
  DirtyPageMgr *QuadPart; // rax
  __int64 v39; // rbx
  __int64 v40; // rax
  struct IMemObj *v41; // rbx
  struct FcsMetadataCaches *v42; // rax
  FcsMetadataCaches *v43; // rcx
  struct ReportFailure *v44; // rcx
  bool v45; // di
  __int64 v46; // rbx
  __int64 v47; // rax
  __int64 v48; // rbx
  PerProcessGlobals *v49; // rax
  struct MemoryClerk **v50; // rbx
  struct MemoryClerk *v51; // rax
  unsigned int v52; // edi
  char *v53; // r8
  __int64 v54; // rbx
  __int64 v55; // rax
  __int64 v56; // rbx
  PerProcessGlobals *v57; // rax
  struct MemoryClerk **v58; // rbx
  __int64 v59; // r8
  BadPageList *v60; // rax
  BadPageList *v61; // rdi
  __int64 v62; // rbx
  __int64 v63; // rax
  __int64 v64; // rbx
  PerProcessGlobals *v65; // rax
  struct MemoryClerk **v66; // rbx
  struct MemoryClerk *v67; // rax
  char *v68; // r8
  __int64 v69; // rbx
  __int64 v70; // rax
  __int64 v71; // rbx
  PerProcessGlobals *v72; // rax
  struct MemoryClerk **v73; // rbx
  struct MemoryClerk *v74; // rax
  char *v75; // r8
  struct IMemObj *v76; // rax
  CorruptedPageList *v77; // rax
  CorruptedPageList *v78; // rax
  __int64 v79; // rdx
  struct CSessionTraceFlags *v80; // rcx
  unsigned __int64 v81; // rdx
  unsigned __int64 v82; // rax
  __int64 v83; // rbx
  __int64 v84; // rax
  __int64 v85; // rbx
  PerProcessGlobals *v86; // rax
  struct MemoryClerk **v87; // rbx
  struct MemoryClerk *v88; // rax
  char *v89; // r8
  int v90; // eax
  ParallelVersionCleanerMgr *v91; // rax
  ParallelVersionCleanerMgr *v92; // rbx
  int v93; // edi
  struct IMemObj *v94; // rax
  __int64 v95; // rax
  struct CUcsManager *v96; // rbx
  __int64 v97; // rax
  int v98; // eax
  struct CUcsManager *v99; // rax
  int v100; // eax
  __int64 v101; // rbx
  __int64 v102; // rax
  __int64 v103; // rbx
  DWORD LastError; // eax
  wchar_t *OSErrString; // rax
  struct CUcsManager *v106; // rbx
  __int64 v107; // rax
  int v108; // eax
  int v109; // [rsp+20h] [rbp-E0h]
  int v110; // [rsp+20h] [rbp-E0h]
  int v111; // [rsp+20h] [rbp-E0h]
  int v112; // [rsp+20h] [rbp-E0h]
  int v113; // [rsp+20h] [rbp-E0h]
  int v114; // [rsp+60h] [rbp-A0h] BYREF
  struct IMemObj *v115; // [rsp+68h] [rbp-98h]
  __int64 v116; // [rsp+70h] [rbp-90h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+78h] [rbp-88h] BYREF
  void ***v118; // [rsp+80h] [rbp-80h] BYREF
  int v119; // [rsp+88h] [rbp-78h] BYREF
  __int64 (__fastcall *v120)(void *, void *); // [rsp+90h] [rbp-70h]
  __int64 v121; // [rsp+98h] [rbp-68h]
  __int64 v122; // [rsp+A0h] [rbp-60h] BYREF
  LARGE_INTEGER Frequency; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v124; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v125; // [rsp+C0h] [rbp-40h]
  int v126; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v127; // [rsp+2D8h] [rbp+1D8h]
  __int16 v128; // [rsp+2E0h] [rbp+1E0h]
  __int64 v129; // [rsp+328h] [rbp+228h]
  GUID v130; // [rsp+330h] [rbp+230h]
  GUID v131; // [rsp+340h] [rbp+240h]
  GUID v132; // [rsp+350h] [rbp+250h]
  __int64 v133; // [rsp+360h] [rbp+260h]
  int v134; // [rsp+368h] [rbp+268h]
  __int64 v135; // [rsp+370h] [rbp+270h]
  __int64 v136; // [rsp+378h] [rbp+278h]
  _QWORD v137[3]; // [rsp+380h] [rbp+280h] BYREF
  char v138; // [rsp+398h] [rbp+298h]
  char v139; // [rsp+399h] [rbp+299h]
  __int16 v140; // [rsp+39Ah] [rbp+29Ah]
  __int64 v141; // [rsp+5A8h] [rbp+4A8h]
  __int16 v142; // [rsp+5B0h] [rbp+4B0h]
  __int64 v143; // [rsp+5F8h] [rbp+4F8h]
  GUID v144; // [rsp+600h] [rbp+500h]
  GUID v145; // [rsp+610h] [rbp+510h]
  GUID v146; // [rsp+620h] [rbp+520h]
  __int64 v147; // [rsp+630h] [rbp+530h]
  int v148; // [rsp+638h] [rbp+538h]
  __int64 v149; // [rsp+640h] [rbp+540h]
  __int64 v150; // [rsp+648h] [rbp+548h]
  struct _MEMORYSTATUSEX v151; // [rsp+650h] [rbp+550h] BYREF
  struct _JOBOBJECT_EXTENDED_LIMIT_INFORMATION v152; // [rsp+690h] [rbp+590h] BYREF
  struct _PROCESS_MEMORY_COUNTERS_EX v153; // [rsp+720h] [rbp+620h] BYREF
  char v154[4096]; // [rsp+770h] [rbp+670h] BYREF

  v121 = -2;
  if ( SOS_OS_MemoryModel == 4 )
    BPool::RehydrateBufferPool(qword_10317B628);
  InitBPoolThreadPool();
  *(_OWORD *)&qword_1033C1260 = *(_OWORD *)a2;
  *(_OWORD *)&qword_1033C1270 = *((_OWORD *)a2 + 1);
  *(_OWORD *)&qword_1033C1280 = *((_OWORD *)a2 + 2);
  *(_OWORD *)&qword_1033C1290 = *((_OWORD *)a2 + 3);
  *(_OWORD *)&qword_1033C12A0 = *((_OWORD *)a2 + 4);
  *(_OWORD *)&qword_1033C12B0 = *((_OWORD *)a2 + 5);
  *(_OWORD *)&qword_1033C12C0 = *((_OWORD *)a2 + 6);
  *((_OWORD *)&qword_1033C12E0 - 1) = *((_OWORD *)a2 + 7);
  v4 = (char *)a2 + 128;
  *(_OWORD *)&qword_1033C12E0 = *(_OWORD *)v4;
  *(_OWORD *)&qword_1033C12F0 = *((_OWORD *)v4 + 1);
  *(_OWORD *)&qword_1033C1300 = *((_OWORD *)v4 + 2);
  qword_1033C1310 = *((_QWORD *)v4 + 6);
  PrintNodeConfiguration();
  CreateDTCStateAndInhibitIfReq();
  qword_103336CC8 = 0;
  qword_103336CD0 = 0;
  PerfLatch = 0;
  if ( dword_103172528 )
  {
    SloManager::Init((SloManager *)&SloManager::sm_sloManager);
    v5 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v6 = *(_QWORD *)(v5 + 256);
    if ( !v6 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v6 = *(_QWORD *)(v5 + 256);
    }
    v7 = *(_QWORD *)(v6 + 992);
    ClientProcessGlobals = (PerProcessGlobals *)SOS_OS::GetClientProcessGlobals();
    DefaultMemoryClerksForNode = PerProcessGlobals::GetDefaultMemoryClerksForNode(
                                   ClientProcessGlobals,
                                   *(_WORD *)(v7 + 160));
    SOS_OS::GetClientProcessGlobals();
    v10 = DefaultMemoryClerksForNode[34];
    v11 = (char *)v10 + 64;
    if ( !v10 )
      v11 = 0;
    MemObject = MemoryObjectFactory::CreateMemObject(304, 6, v11, 8, 128);
    if ( !MemObject )
    {
      LOBYTE(v12) = 65;
      ex_raise_oom(v12);
    }
    CloudRtResourceStatsManager::sm_cloudRtResourceStatsManager = MemObject;
    InitSqlRgHistoryRingBufferManager();
    if ( !qword_1031D4B10 )
    {
      v14 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v15 = *(_QWORD *)(v14 + 256);
      if ( !v15 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v15 = *(_QWORD *)(v14 + 256);
      }
      v16 = *(_QWORD *)(v15 + 992);
      v17 = (PerProcessGlobals *)SOS_OS::GetClientProcessGlobals();
      v18 = PerProcessGlobals::GetDefaultMemoryClerksForNode(v17, *(_WORD *)(v16 + 160));
      SOS_OS::GetClientProcessGlobals();
      v19 = v18[34];
      v20 = (char *)v19 + 64;
      if ( !v19 )
        v20 = 0;
      LOWORD(v109) = 128;
      v21 = (struct IMemObj *)MemoryObjectFactory::CreateMemObject(385, 6, v20, 8, v109);
      qword_1031D4B10 = v21;
      if ( dword_103172528 )
      {
        if ( !v21 )
          utassert_fail(1u, "m_pmo != nullptr", "sqlidlememorycollector.cpp", 101, 0);
      }
      else
      {
        v22 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        v23 = *(_QWORD *)(v22 + 256);
        if ( !v23 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v23 = *(_QWORD *)(v22 + 256);
        }
        qword_1031D4B10 = *(struct IMemObj **)(*(_QWORD *)(v23 + 992) + 320LL);
      }
    }
    if ( !qword_103333598 )
    {
      v24 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v25 = *(_QWORD *)(v24 + 256);
      if ( !v25 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v25 = *(_QWORD *)(v24 + 256);
      }
      v26 = *(_QWORD *)(v25 + 992);
      v27 = (PerProcessGlobals *)SOS_OS::GetClientProcessGlobals();
      v28 = PerProcessGlobals::GetDefaultMemoryClerksForNode(v27, *(_WORD *)(v26 + 160));
      SOS_OS::GetClientProcessGlobals();
      v29 = v28[34];
      v30 = (char *)v29 + 64;
      if ( !v29 )
        v30 = 0;
      LOWORD(v109) = 128;
      qword_103333598 = MemoryObjectFactory::CreateMemObject(394, 6, v30, 8, v109);
      if ( !qword_103333598 )
        utassert_fail(1u, "m_pmo != nullptr", "sqlstorecachestats.cpp", 78, 0);
    }
    v114 = 0;
    qword_1031C9790 = 0;
    MemoryNode::UpdateGlobalMemoryStatus();
    MemoryNode::GetGlobalMemoryStatus(&v151, &v153, &v152, &v114, &v122);
    qword_1031C9770 = v152.ProcessMemoryLimit >> 13;
    qword_1031C9778 = MemoryNode_MemoryTargetPages;
    if ( !AutoMemoryLeakDetector::Init((AutoMemoryLeakDetector *)&AutoMemoryLeakDetector::sm_memoryLeakDetector) )
    {
      scierrlog(0x42F2u, L"AutoMemoryLeakDetector");
      SQLExit(29, 0, 2147942414LL);
    }
    if ( dword_103186FD0 >= 0 || byte_10316E6B6 )
    {
      v31 = dword_103186EC8;
      v32 = fmax(1.0, SOS_OS::GetCPUCorePercentCap() / 100.0);
      v33 = 0;
      if ( v32 >= 9.223372036854776e18 )
      {
        v32 = v32 - 9.223372036854776e18;
        if ( v32 < 9.223372036854776e18 )
          v33 = 0x8000000000000000uLL;
      }
      v34 = v33 + (unsigned int)(int)v32;
      v35 = dword_103186ECC;
      v36 = (v34 + v31 - 1 - (v34 + v31 - 1) % v31) / v31;
      if ( !v36 )
        v36 = 1;
      if ( v36 > 0xA )
        v36 = 10;
      LogSystemMetadata(
        L"Init GlobalCacheActivenessStats: %d cores %d partitions %d interval period seconds.\n",
        v34,
        v36,
        dword_103186ECC);
      if ( !GlobalCacheActivenessStats::StaticInit(v36, v35) )
      {
        scierrlog(0x42F2u, L"GlobalCacheActivenessStats");
        SQLExit(371, 0, 2147942414LL);
      }
      if ( dword_103186FD0 >= 0 )
      {
        if ( Base_PublicGlobals::sm_invariantTscAvailable )
          v37 = 15 * Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
        else
          v37 = 150000000;
        qword_103328488 = v37;
        dword_1033284A0 = 0;
        qword_103328490 = v37;
        qword_103328498 = 0;
        if ( Base_PublicGlobals::sm_invariantTscAvailable )
        {
          QueryPerformanceCounter(&PerformanceCount);
          QuadPart = (DirtyPageMgr *)PerformanceCount.QuadPart;
        }
        else
        {
          QuadPart = MEMORY[0x7FFE0008];
        }
        qword_103328480 = (__int64)QuadPart;
        qword_1031C4BA8 = (__int64)&off_103328460;
      }
    }
  }
  NativeShuffleStatsManager::Init((NativeShuffleStatsManager *)&NativeShuffleStatsManager::sm_nativeShuffleStatsManager);
  SetupHoBtManager();
  qword_103172098 = SOS_UserStore::CreateMemoryObject(HoBtMgrUserStore, 52, 4194374);
  if ( !qword_103172098 )
  {
    scierrlog(0x42F2u, L"Schema Manager SEColumn Metadata Cache memory object");
    SQLExit(288, 0, 2147942414LL);
  }
  v119 = 256;
  v120 = HoBtColumnAttributeCache::CompareHoBtColumnAttributeCache;
  HoBtColumnAttributeCache::sm_sharedCachedStore = (MemoryClerkInternal *)SOS_CacheStore::CreateStore(
                                                                            L"SESHAREDCOLMETADATACACHE",
                                                                            31,
                                                                            0x2000,
                                                                            1,
                                                                            &v119,
                                                                            &HoBtColumnAttributeCache::DeleteHoBtColumnAttributeCache,
                                                                            33,
                                                                            183,
                                                                            0);
  if ( !HoBtColumnAttributeCache::sm_sharedCachedStore )
  {
    scierrlog(0x42F2u, L"Schema Manager SEColumn Metadata Cache cache store");
    SQLExit(207, 0, 2147942414LL);
  }
  qword_1031720A0 = (struct IMemObj *)SOS_UserStore::CreateMemoryObject(HoBtMgrUserStore, 431, 4194374);
  if ( !qword_1031720A0 )
  {
    scierrlog(0x42F2u, L"Schema Manager SEColumn Store Metadata Cache memory object");
    SQLExit(128, 0, 2147942414LL);
  }
  if ( IsFcsMetadataCacheEnabled() )
  {
    if ( FcsMetadataCaches::m_pSelfInstance )
      utassert_fail(1u, "!m_pSelfInstance", "FcsMetadataCacheCore.cpp", 91, 0);
    v39 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v40 = *(_QWORD *)(v39 + 256);
    if ( !v40 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v40 = *(_QWORD *)(v39 + 256);
    }
    v41 = *(struct IMemObj **)(*(_QWORD *)(v40 + 992) + 320LL);
    v115 = v41;
    v42 = (struct FcsMetadataCaches *)operator new(
                                        8u,
                                        v41,
                                        1,
                                        "Sql\\Ntdbms\\storeng\\dfs\\access\\FcsMetadataCache\\FcsMetadataCacheCore.cpp",
                                        99,
                                        5u);
    if ( v42 )
      *(_QWORD *)v42 = 0;
    else
      v42 = 0;
    FcsMetadataCaches::m_pSelfInstance = v42;
    if ( !v42 )
    {
      LOBYTE(v43) = -10;
      ex_raise_oom(v43);
    }
    FcsMetadataCaches::InitFcsAttributeCache(v43, v41);
  }
  if ( IsToadEnabled() )
    ToadMQ::Intialize();
  AutoTuner::Initialize();
  RegisterToadMessageHandlers();
  XcsSqlInitialize(v44);
  v45 = (unsigned __int8)byte_10317AD46 >> 7 == 0;
  v46 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v47 = *(_QWORD *)(v46 + 256);
  if ( !v47 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v47 = *(_QWORD *)(v46 + 256);
  }
  v48 = *(_QWORD *)(v47 + 992);
  v49 = (PerProcessGlobals *)SOS_OS::GetClientProcessGlobals();
  v50 = PerProcessGlobals::GetDefaultMemoryClerksForNode(v49, *(_WORD *)(v48 + 160));
  SOS_OS::GetClientProcessGlobals();
  v51 = v50[16];
  v52 = (v45 << 6) | 0xA;
  v53 = (char *)v51 + 64;
  if ( !v51 )
    v53 = 0;
  LOWORD(v110) = 1488;
  g_SETLSPmo = (struct IMemObj *)MemoryObjectFactory::CreateMemObject(55, v52, v53, 1488, v110);
  if ( !g_SETLSPmo )
  {
    scierrlog(0x42F2u, L"SEInternalTLS memory object");
    SQLExit(176, 0, 2147942414LL);
  }
  v54 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v55 = *(_QWORD *)(v54 + 256);
  if ( !v55 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v55 = *(_QWORD *)(v54 + 256);
  }
  v56 = *(_QWORD *)(v55 + 992);
  v57 = (PerProcessGlobals *)SOS_OS::GetClientProcessGlobals();
  v58 = PerProcessGlobals::GetDefaultMemoryClerksForNode(v57, *(_WORD *)(v56 + 160));
  SOS_OS::GetClientProcessGlobals();
  v59 = (__int64)*v58 + 64;
  if ( !*v58 )
    v59 = 0;
  LOWORD(v111) = 912;
  g_SubpDescPmo = (struct IMemObj *)MemoryObjectFactory::CreateMemObject(56, v52, v59, 912, v111);
  if ( !g_SubpDescPmo )
  {
    scierrlog(0x42F2u, L"SubprocessDescriptor memory object");
    SQLExit(177, 0, 2147942414LL);
  }
  if ( g_pBadPageList )
    utassert_fail(1u, "g_pBadPageList == NULL", "badpagelist.cpp", 55, 0);
  v60 = (BadPageList *)operator new(0x88u);
  v61 = v60;
  if ( v60 )
  {
    *((_QWORD *)v60 + 1) = 0;
    *((_QWORD *)v60 + 2) = 0;
    *(_QWORD *)v60 = &BadPageList::`vftable';
    *((_DWORD *)v60 + 14) = 75;
    *((_QWORD *)v60 + 5) = 0;
    *((_QWORD *)v60 + 6) = 0;
    *((_QWORD *)v60 + 4) = 0;
    *((_DWORD *)v60 + 22) = 75;
    *((_QWORD *)v60 + 9) = 0;
    *((_QWORD *)v60 + 10) = 0;
    *((_QWORD *)v60 + 8) = 0;
    *((_QWORD *)v60 + 13) = (char *)v60 + 96;
    *((_QWORD *)v60 + 12) = (char *)v60 + 96;
    *((_QWORD *)v60 + 14) = 0;
    *((_DWORD *)v60 + 30) = 0;
    *((_QWORD *)v60 + 5) = 0;
    *((_QWORD *)v60 + 6) = 0;
    *((_QWORD *)v60 + 4) = 0;
    *((_QWORD *)v60 + 9) = 0;
    *((_QWORD *)v60 + 10) = 0;
    *((_QWORD *)v60 + 8) = 0;
    v62 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v63 = *(_QWORD *)(v62 + 256);
    if ( !v63 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v63 = *(_QWORD *)(v62 + 256);
    }
    v64 = *(_QWORD *)(v63 + 992);
    v65 = (PerProcessGlobals *)SOS_OS::GetClientProcessGlobals();
    v66 = PerProcessGlobals::GetDefaultMemoryClerksForNode(v65, *(_WORD *)(v64 + 160));
    SOS_OS::GetClientProcessGlobals();
    v67 = v66[15];
    v68 = (char *)v67 + 64;
    if ( !v67 )
      v68 = 0;
    LOWORD(v112) = 128;
    *((_QWORD *)v61 + 16) = MemoryObjectFactory::CreateMemObject(69, 2, v68, 8, v112);
  }
  else
  {
    v61 = 0;
  }
  g_pBadPageList = v61;
  if ( !v61 || !*((_QWORD *)v61 + 16) )
  {
    scierrlog(0x42F2u, L"BadPageList Initialization");
    SQLExit(30, 0, 2147942414LL);
  }
  if ( CorruptedPageList::sm_pMO )
    utassert_fail(1u, "sm_pMO == nullptr", "CorruptedPagelist.cpp", 249, 0);
  if ( g_pCorruptedPageList )
    utassert_fail(1u, "g_pCorruptedPageList == nullptr", "CorruptedPagelist.cpp", 250, 0);
  v69 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v70 = *(_QWORD *)(v69 + 256);
  if ( !v70 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v70 = *(_QWORD *)(v69 + 256);
  }
  v71 = *(_QWORD *)(v70 + 992);
  v72 = (PerProcessGlobals *)SOS_OS::GetClientProcessGlobals();
  v73 = PerProcessGlobals::GetDefaultMemoryClerksForNode(v72, *(_WORD *)(v71 + 160));
  SOS_OS::GetClientProcessGlobals();
  v74 = v73[15];
  v75 = (char *)v74 + 64;
  if ( !v74 )
    v75 = 0;
  LOWORD(v112) = 128;
  v76 = (struct IMemObj *)MemoryObjectFactory::CreateMemObject(450, 2, v75, 8, v112);
  CorruptedPageList::sm_pMO = v76;
  if ( !v76
    || ((v77 = (CorruptedPageList *)operator new(
                                      0x60u,
                                      v76,
                                      "sql\\ntdbms\\storeng\\dmu\\dmpld\\src\\CorruptedPageList.cpp",
                                      262,
                                      5u)) == 0
      ? (v78 = 0)
      : (v78 = CorruptedPageList::CorruptedPageList(v77)),
        (g_pCorruptedPageList = v78) == 0) )
  {
    scierrlog(0x42F2u, L"CorruptedPageList Initialization");
    SQLExit(416, 0, 2147942414LL);
  }
  byte_10317F76C = (byte_10317AC16 & 4) != 0;
  byte_10318AB3A = (qword_10317AC17 & 0x1000000000LL) != 0;
  LockManager::Init((LockManager *)&theLockManager);
  if ( (unsigned int)SuperLatchManager::Init(&off_1031895E0) != 1 )
  {
    scierrlog(0x42F2u, L"Superlatch Manager");
    SQLExit(31, 0, 2147942414LL);
  }
  if ( (byte_10317AC09 & 0x20) != 0
    || (v79 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset,
        *(_QWORD *)v79)
    && (v80 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v79 + 56LL)) != 0
    && CSessionTraceFlags::CheckSessionTraceInternal(v80, 0x44Du) )
  {
    v81 = 4096;
  }
  else
  {
    v81 = 64;
  }
  dword_1031E0A98 = v81;
  v82 = 16 * v81;
  if ( !is_mul_ok(v81, 0x10u) )
    v82 = -1;
  v115 = (struct IMemObj *)operator new[](
                             v82,
                             qword_103172088,
                             1,
                             "sql\\ntdbms\\storeng\\dfs\\alloc\\ExtentCache.cpp",
                             44,
                             5u);
  qword_1031E0A90 = (__int64)v115;
  if ( !v115 )
  {
    scierrlog(0x42F2u, L"Extent Cache");
    SQLExit(32, 0, 2147942414LL);
  }
  QueryPerformanceFrequency(&Frequency);
  BackupWorkerPool::Init();
  v83 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v84 = *(_QWORD *)(v83 + 256);
  if ( !v84 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v84 = *(_QWORD *)(v83 + 256);
  }
  v85 = *(_QWORD *)(v84 + 992);
  v86 = (PerProcessGlobals *)SOS_OS::GetClientProcessGlobals();
  v87 = PerProcessGlobals::GetDefaultMemoryClerksForNode(v86, *(_WORD *)(v85 + 160));
  SOS_OS::GetClientProcessGlobals();
  v88 = v87[36];
  v89 = (char *)v88 + 64;
  if ( !v88 )
    v89 = 0;
  LOWORD(v113) = 40;
  ColumnStoreLockBytesSS::sm_pmoXpressBlockInfo = (struct IMemObj *)MemoryObjectFactory::CreateMemObject(
                                                                      327,
                                                                      74,
                                                                      v89,
                                                                      40,
                                                                      v113);
  if ( !ColumnStoreLockBytesSS::sm_pmoXpressBlockInfo )
  {
    scierrlog(0x42F2u, L"Columnstore Lob Compression");
    SQLExit(33, 0, 2147942414LL);
  }
  if ( (byte_10316E9FF || (qword_10317AD33 & 0x40) != 0)
    && (qword_10317AD33 & 0x10) == 0
    && SOS_PublicGlobals::sm_cpuCount >= 2
    && (!byte_10316E7AD || !dword_103185704 || !dword_103172528)
    && ParallelRedoWorkerPool::StartPool(&qword_1031C40F8, L"PARALLEL REDO WORKER POOL") )
  {
    if ( (byte_10316E9FD || (qword_10317AD33 & 0x40) != 0) && (qword_10317AD33 & 0x20) == 0 )
      ParallelRedoWorkerPool::StartPool(&qword_1031C4100, L"PARALLEL REDO HELPER POOL");
    if ( !qword_1031C4100 )
    {
      qword_1031C4100 = qword_1031C40F8;
      _InterlockedIncrement((volatile signed __int32 *)(qword_1031C40F8 + 32));
    }
  }
  v116 = 0;
  if ( !byte_10316E7AD || !dword_103185704 || !dword_103172528 )
  {
    do
      v90 = SOS_ResourceManager::LookupGroup(
              SOS_PublicGlobals::sm_ResourceManager,
              L"PVSCleanerGroup",
              SOS_PublicGlobals::sm_ResourceManager,
              &v116);
    while ( v90 == 0x80000000 );
    if ( v90 && dword_103172528 )
      log_unlocalized_systemmetadata(
        L"%ls",
        L"PVSCleanerGroup Lookup Failed. MTVC if enabled uses internal resource group!");
    VersionCleanupWorkerPool::StartPool(&qword_1031C4720, L"MULTITHREADED VERSIONCLEANUP WORKER POOL");
  }
  SOS_AutoReleaseResourceGroup::UnhookAndRelease((SOS_AutoReleaseResourceGroup *)&v116);
  if ( qword_1031C4720 )
  {
    v91 = (ParallelVersionCleanerMgr *)operator new(
                                         0xE0u,
                                         qword_103172088,
                                         "sql\\ntdbms\\storeng\\dfs\\startup\\startup.cpp",
                                         12223,
                                         5u);
    v115 = v91;
    if ( v91 )
      v92 = ParallelVersionCleanerMgr::ParallelVersionCleanerMgr(v91, qword_103172088);
    else
      v92 = 0;
    g_parallelVersionCleanerMgr = v92;
    v93 = 0;
    while ( 1 )
    {
      v94 = (struct IMemObj *)operator new(
                                0x98u,
                                *((struct IMemObj **)v92 + 2),
                                1,
                                "Sql\\Ntdbms\\storeng\\dfs\\access\\multithreadedversioncleaner.cpp",
                                733,
                                5u);
      v115 = v94;
      v95 = v94
          ? ParallelVersionCleanupWorkerContext::ParallelVersionCleanupWorkerContext(
              v94,
              *((_QWORD *)v92 + 2),
              v92,
              qword_1031C4720)
          : 0LL;
      if ( !v95 )
        break;
      _InterlockedIncrement((volatile signed __int32 *)(v95 + 8));
      SEListSizedSLock<ParallelVersionCleanupWorkerContext,96,SEListSLock>::Append((char *)v92 + 96, v95);
      ++*((_DWORD *)v92 + 22);
      if ( (unsigned int)++v93 >= 0x14 )
        goto LABEL_159;
    }
    if ( g_parallelVersionCleanerMgr )
      (**(void (__fastcall ***)(ParallelVersionCleanerMgr *, __int64))g_parallelVersionCleanerMgr)(
        g_parallelVersionCleanerMgr,
        1);
  }
LABEL_159:
  v124 = 0;
  v125 = 0;
  v126 = 0;
  v129 = 0;
  v130 = GUID_NULL;
  v131 = GUID_NULL;
  v132 = GUID_NULL;
  v133 = 0;
  v134 = 0;
  v135 = 0;
  v136 = 0;
  v127 = 0;
  v128 = 0;
  if ( !(unsigned int)retrieveRbIoConfigPath(261, (char *)&v126 + 2) )
  {
    *(_QWORD *)&v124 = &g_SeReportFailure;
    word_103215504 = 257;
    v96 = UcsManager();
    v97 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v96 + 6) + 96LL))(*((_QWORD *)v96 + 6));
    if ( !v97 )
      v97 = (__int64)v96 + 4544;
    *((_QWORD *)&v124 + 1) = v97;
    v98 = RbIoInitializeAsClient(&v124, 0);
    if ( v98 < 0 )
    {
      _mm_lfence();
      scierrlog(0xC30Eu, L"Remote block IO subsystem configuration", (unsigned int)v98);
      SQLExit(372, 0, 2147942487LL);
    }
    v99 = UcsManager();
    RbIoConfigureUcsTransportMgr((char *)v99 + 4544);
  }
  if ( (byte_10316EA6C || (qword_10317B10F & 8) != 0) && (qword_10317B10F & 0x10) == 0 )
  {
    v100 = InitializeRbpexFastReads();
    CheckHrFailAndExit(v100, "Failed to initialize the fast RBPEX reads");
  }
  if ( dword_103185704 && dword_103172528 )
  {
    v101 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v102 = *(_QWORD *)(v101 + 256);
    if ( !v102 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v102 = *(_QWORD *)(v101 + 256);
    }
    v103 = (unsigned int)LogReplicaHost::InitializeInstance(
                           (LogReplicaHost *)&off_10333CE00,
                           *(struct IMemObj **)(*(_QWORD *)(v102 + 992) + 320LL));
    LogSystemMetadata(L"[%hs] Log replica instance initialization completed with result: %lx", "SEInit", v103);
    CheckHrFailAndExit(v103, "Failed to initialize log replica.");
  }
  if ( byte_10316EB33 || (qword_10317B10F & 0x2000) != 0 )
  {
    v118 = &g_SeReportFailure;
    if ( (int)StripedInitialize(&v118) < 0 )
    {
      scierrlog(0x42F2u, L"Striped filesystem");
      SQLExit(35, 0, 2147942414LL);
    }
  }
  if ( byte_10316EB36 && !SQLMemoryReport::StaticInit() )
  {
    scierrlog(0x42F2u, L"SQLMemoryReport::StaticInit");
    SQLExit(408, 0, 2147942414LL);
  }
  StartUp::sm_eventDBMSReadyForSNI = CreateEventA(0, 1, 0, 0);
  if ( !StartUp::sm_eventDBMSReadyForSNI )
  {
    LastError = GetLastError();
    OSErrString = GetOSErrString(LastError, (struct ErrorStringHolder *)v154, 0, 0);
    scierrlog(0x429Du, L"StartUp::CreateStartupEvents()", OSErrString);
    SQLExit(366, 17053, 1066);
  }
  if ( !(unsigned int)BlobAccess_Init() )
  {
    scierrlog(0x42F2u, L"BlobAccess");
    SQLExit(36, 0, 2147942414LL);
  }
  AzureFileMetadataAccess_Init();
  if ( (dword_103172538
     || *((_BYTE *)s_pServerConf + 17)
     && !dword_10316ECB4
     && !dword_10317253C
     && !dword_103172574
     && (!dword_103185704 || !dword_103172528))
    && !InitHekaton() )
  {
    scierrlog(0x42F2u, L"HK Boot");
    SQLExit(37, 0, 2147942414LL);
  }
  if ( byte_1031852E4 )
  {
    v137[2] = 0;
    v139 = 0;
    v143 = 0;
    v144 = GUID_NULL;
    v145 = GUID_NULL;
    v146 = GUID_NULL;
    v147 = 0;
    v148 = 0;
    v149 = 0;
    v150 = 0;
    v140 = 0;
    v141 = 0;
    v142 = 0;
    v137[0] = &g_SeReportFailure;
    v106 = UcsManager();
    v107 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v106 + 6) + 96LL))(*((_QWORD *)v106 + 6));
    if ( !v107 )
      v107 = (__int64)v106 + 4544;
    v137[1] = v107;
    v138 = 1;
    v108 = FidoTransportInitialize(v137);
    if ( v108 < 0 )
    {
      _mm_lfence();
      scierrlog(0xC30Eu, L"Fido Transport Layer Configuration", (unsigned int)v108);
      SQLExit(38, 0, 2147942487LL);
    }
  }
  StartDBMSThreads(a1);
}

```

## disassembly

```asm
0x101ba9540  push    rbp
0x101ba9542  push    r14
0x101ba9544  push    r15
0x101ba9546  lea     rbp, [rsp-1680h]
0x101ba954e  mov     eax, 1780h
0x101ba9553  call    _alloca_probe
0x101ba9558  sub     rsp, rax
0x101ba955b  mov     [rbp+1690h+var_16F8], 0FFFFFFFFFFFFFFFEh
0x101ba9563  mov     [rsp+1790h+arg_0], rbx
0x101ba956b  mov     [rsp+1790h+arg_8], rsi
0x101ba9573  mov     [rsp+1790h+arg_10], rdi
0x101ba957b  mov     [rsp+1790h+arg_18], r12
0x101ba9583  mov     rax, cs:__security_cookie
0x101ba958a  xor     rax, rsp
0x101ba958d  mov     [rbp+1690h+var_20], rax
0x101ba9594  mov     rbx, rdx
0x101ba9597  mov     rsi, rcx
0x101ba959a  mov     rax, cs:__imp_?SOS_OS_MemoryModel@@3W4SOS_MemoryModel@@A; SOS_MemoryModel SOS_OS_MemoryModel
0x101ba95a1  cmp     dword ptr [rax], 4
0x101ba95a4  jnz     short loc_101BA95B2
0x101ba95a6  mov     rcx, cs:qword_10317B628; this
0x101ba95ad  call    ?RehydrateBufferPool@BPool@@QEAAXXZ; BPool::RehydrateBufferPool(void)
0x101ba95b2  call    ?InitBPoolThreadPool@@YAXXZ; InitBPoolThreadPool(void)
0x101ba95b7  lea     rdx, qword_1033C1260
0x101ba95be  movups  xmm0, xmmword ptr [rbx]
0x101ba95c1  movups  xmmword ptr [rdx], xmm0
0x101ba95c4  movups  xmm1, xmmword ptr [rbx+10h]
0x101ba95c8  movups  xmmword ptr [rdx+10h], xmm1
0x101ba95cc  movups  xmm0, xmmword ptr [rbx+20h]
0x101ba95d0  movups  xmmword ptr [rdx+20h], xmm0
0x101ba95d4  movups  xmm1, xmmword ptr [rbx+30h]
0x101ba95d8  movups  xmmword ptr [rdx+30h], xmm1
0x101ba95dc  movups  xmm0, xmmword ptr [rbx+40h]
0x101ba95e0  movups  xmmword ptr [rdx+40h], xmm0
0x101ba95e4  movups  xmm1, xmmword ptr [rbx+50h]
0x101ba95e8  movups  xmmword ptr [rdx+50h], xmm1
0x101ba95ec  movups  xmm0, xmmword ptr [rbx+60h]
0x101ba95f0  movups  xmmword ptr [rdx+60h], xmm0
0x101ba95f4  mov     r12d, 80h
0x101ba95fa  add     rdx, r12
0x101ba95fd  movups  xmm0, xmmword ptr [rbx+70h]
0x101ba9601  movups  xmmword ptr [rdx-10h], xmm0
0x101ba9605  add     rbx, r12
0x101ba9608  movups  xmm1, xmmword ptr [rbx]
0x101ba960b  movups  xmmword ptr [rdx], xmm1
0x101ba960e  movups  xmm0, xmmword ptr [rbx+10h]
0x101ba9612  movups  xmmword ptr [rdx+10h], xmm0
0x101ba9616  movups  xmm1, xmmword ptr [rbx+20h]
0x101ba961a  movups  xmmword ptr [rdx+20h], xmm1
0x101ba961e  mov     rax, [rbx+30h]
0x101ba9622  mov     [rdx+30h], rax
0x101ba9626  call    ?PrintNodeConfiguration@@YAXXZ; PrintNodeConfiguration(void)
0x101ba962b  call    ?CreateDTCStateAndInhibitIfReq@@YAXXZ; CreateDTCStateAndInhibitIfReq(void)
0x101ba9630  xor     r14d, r14d
0x101ba9633  mov     cs:qword_103336CC8, r14
0x101ba963a  mov     cs:qword_103336CD0, r14
0x101ba9641  mov     cs:?PerfLatch@@3VLatchBase@@A, r14; LatchBase PerfLatch
0x101ba9648  lea     r15d, [r12-7Fh]
0x101ba964d  cmp     cs:dword_103172528, r14d
0x101ba9654  jz      loc_101BA9AE0
0x101ba965a  lea     rcx, ?sm_sloManager@SloManager@@0V1@A; this
0x101ba9661  call    ?Init@SloManager@@QEAAXXZ; SloManager::Init(void)
0x101ba9666  mov     rdx, gs:58h
0x101ba966f  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101ba9676  mov     ecx, [rax]
0x101ba9678  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101ba967f  mov     ebx, [rax]
0x101ba9681  add     rbx, [rdx+rcx*8]
0x101ba9685  mov     rax, [rbx+100h]
0x101ba968c  test    rax, rax
0x101ba968f  jnz     short loc_101BA96A0
0x101ba9691  xor     ecx, ecx
0x101ba9693  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x101ba9699  mov     rax, [rbx+100h]
0x101ba96a0  mov     rbx, [rax+3E0h]
0x101ba96a7  call    cs:__imp_?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ; SOS_OS::GetClientProcessGlobals(void)
0x101ba96ad  mov     rcx, rax
0x101ba96b0  movzx   edx, word ptr [rbx+0A0h]
0x101ba96b7  call    cs:__imp_?GetDefaultMemoryClerksForNode@PerProcessGlobals@@QEAAPEAPEAVMemoryClerk@@G@Z; PerProcessGlobals::GetDefaultMemoryClerksForNode(ushort)
0x101ba96bd  mov     rbx, rax
0x101ba96c0  call    cs:__imp_?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ; SOS_OS::GetClientProcessGlobals(void)
0x101ba96c6  mov     rax, [rbx+110h]
0x101ba96cd  mov     r9d, 8
0x101ba96d3  lea     r8, [rax+40h]
0x101ba96d7  test    rax, rax
0x101ba96da  cmovz   r8, r14
0x101ba96de  mov     word ptr [rsp+1790h+var_1770], r12w
0x101ba96e4  lea     edx, [r9-2]
0x101ba96e8  mov     ecx, 130h
0x101ba96ed  call    cs:__imp_?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z; MemoryObjectFactory::CreateMemObject(SOSHOST_MEMOBJ_ID,ulong,PageAllocator *,short,short)
0x101ba96f3  mov     rbx, rax
0x101ba96f6  test    rax, rax
0x101ba96f9  jnz     short loc_101BA9702
0x101ba96fb  mov     cl, 41h ; 'A'
0x101ba96fd  call    ?ex_raise_oom@@YAXW4OOM_EXCEPTIONS@@@Z; ex_raise_oom(OOM_EXCEPTIONS)
0x101ba9702  mov     cs:?sm_cloudRtResourceStatsManager@CloudRtResourceStatsManager@@0V1@A, rbx; CloudRtResourceStatsManager CloudRtResourceStatsManager::sm_cloudRtResourceStatsManager
0x101ba9709  call    ?InitSqlRgHistoryRingBufferManager@@YAXXZ; InitSqlRgHistoryRingBufferManager(void)
0x101ba970e  cmp     cs:qword_1031D4B10, r14
0x101ba9715  jnz     loc_101BA982E
0x101ba971b  mov     rdx, gs:58h
0x101ba9724  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101ba972b  mov     ecx, [rax]
0x101ba972d  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101ba9734  mov     ebx, [rax]
0x101ba9736  add     rbx, [rdx+rcx*8]
0x101ba973a  mov     rax, [rbx+100h]
0x101ba9741  test    rax, rax
0x101ba9744  jnz     short loc_101BA9755
0x101ba9746  xor     ecx, ecx
0x101ba9748  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x101ba974e  mov     rax, [rbx+100h]
0x101ba9755  mov     rbx, [rax+3E0h]
0x101ba975c  call    cs:__imp_?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ; SOS_OS::GetClientProcessGlobals(void)
0x101ba9762  mov     rcx, rax
0x101ba9765  movzx   edx, word ptr [rbx+0A0h]
0x101ba976c  call    cs:__imp_?GetDefaultMemoryClerksForNode@PerProcessGlobals@@QEAAPEAPEAVMemoryClerk@@G@Z; PerProcessGlobals::GetDefaultMemoryClerksForNode(ushort)
0x101ba9772  mov     rbx, rax
0x101ba9775  call    cs:__imp_?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ; SOS_OS::GetClientProcessGlobals(void)
0x101ba977b  mov     rax, [rbx+110h]
0x101ba9782  mov     r9d, 8
0x101ba9788  lea     r8, [rax+40h]
0x101ba978c  test    rax, rax
0x101ba978f  cmovz   r8, r14
0x101ba9793  mov     word ptr [rsp+1790h+var_1770], r12w
0x101ba9799  lea     edx, [r9-2]
0x101ba979d  mov     ecx, 181h
0x101ba97a2  call    cs:__imp_?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z; MemoryObjectFactory::CreateMemObject(SOSHOST_MEMOBJ_ID,ulong,PageAllocator *,short,short)
0x101ba97a8  mov     cs:qword_1031D4B10, rax
0x101ba97af  cmp     cs:dword_103172528, r14d
0x101ba97b6  jz      short loc_101BA97DF
0x101ba97b8  test    rax, rax
0x101ba97bb  jnz     short loc_101BA982E
0x101ba97bd  mov     [rsp+1790h+var_1770], r14
0x101ba97c2  lea     r9d, [rax+65h]
0x101ba97c6  lea     r8, aSqlidlememoryc_0; "sqlidlememorycollector.cpp"
0x101ba97cd  lea     rdx, aMPmoNullptr; "m_pmo != nullptr"
0x101ba97d4  mov     ecx, r15d
0x101ba97d7  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x101ba97dd  jmp     short loc_101BA982E
0x101ba97df  mov     rdx, gs:58h
0x101ba97e8  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101ba97ef  mov     ecx, [rax]
0x101ba97f1  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101ba97f8  mov     ebx, [rax]
0x101ba97fa  add     rbx, [rdx+rcx*8]
0x101ba97fe  mov     rax, [rbx+100h]
0x101ba9805  test    rax, rax
0x101ba9808  jnz     short loc_101BA9819
0x101ba980a  xor     ecx, ecx
0x101ba980c  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x101ba9812  mov     rax, [rbx+100h]
0x101ba9819  mov     rax, [rax+3E0h]
0x101ba9820  mov     rcx, [rax+140h]
0x101ba9827  mov     cs:qword_1031D4B10, rcx
0x101ba982e  cmp     cs:qword_103333598, r14
0x101ba9835  jnz     loc_101BA98F4
0x101ba983b  mov     rdx, gs:58h
0x101ba9844  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101ba984b  mov     ecx, [rax]
0x101ba984d  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101ba9854  mov     ebx, [rax]
0x101ba9856  add     rbx, [rdx+rcx*8]
0x101ba985a  mov     rax, [rbx+100h]
0x101ba9861  test    rax, rax
0x101ba9864  jnz     short loc_101BA9875
0x101ba9866  xor     ecx, ecx
0x101ba9868  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x101ba986e  mov     rax, [rbx+100h]
0x101ba9875  mov     rbx, [rax+3E0h]
0x101ba987c  call    cs:__imp_?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ; SOS_OS::GetClientProcessGlobals(void)
0x101ba9882  mov     rcx, rax
0x101ba9885  movzx   edx, word ptr [rbx+0A0h]
0x101ba988c  call    cs:__imp_?GetDefaultMemoryClerksForNode@PerProcessGlobals@@QEAAPEAPEAVMemoryClerk@@G@Z; PerProcessGlobals::GetDefaultMemoryClerksForNode(ushort)
0x101ba9892  mov     rbx, rax
0x101ba9895  call    cs:__imp_?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ; SOS_OS::GetClientProcessGlobals(void)
0x101ba989b  mov     rax, [rbx+110h]
0x101ba98a2  mov     r9d, 8
0x101ba98a8  lea     r8, [rax+40h]
0x101ba98ac  test    rax, rax
0x101ba98af  cmovz   r8, r14
0x101ba98b3  mov     word ptr [rsp+1790h+var_1770], r12w
0x101ba98b9  lea     edx, [r9-2]
0x101ba98bd  mov     ecx, 18Ah
0x101ba98c2  call    cs:__imp_?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z; MemoryObjectFactory::CreateMemObject(SOSHOST_MEMOBJ_ID,ulong,PageAllocator *,short,short)
0x101ba98c8  mov     cs:qword_103333598, rax
0x101ba98cf  test    rax, rax
0x101ba98d2  jnz     short loc_101BA98F4
0x101ba98d4  mov     [rsp+1790h+var_1770], r14
0x101ba98d9  lea     r9d, [rax+4Eh]
0x101ba98dd  lea     r8, aSqlstorecaches; "sqlstorecachestats.cpp"
0x101ba98e4  lea     rdx, aMPmoNullptr; "m_pmo != nullptr"
0x101ba98eb  mov     ecx, r15d
0x101ba98ee  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x101ba98f4  mov     [rsp+1790h+var_1730], r14d
0x101ba98f9  mov     cs:qword_1031C9790, r14
0x101ba9900  call    cs:__imp_?UpdateGlobalMemoryStatus@MemoryNode@@SAXXZ; MemoryNode::UpdateGlobalMemoryStatus(void)
0x101ba9906  lea     rax, [rbp+1690h+var_16F0]
0x101ba990a  mov     [rsp+1790h+var_1770], rax
0x101ba990f  lea     r9, [rsp+1790h+var_1730]
0x101ba9914  lea     r8, [rbp+1690h+var_1100]
0x101ba991b  lea     rdx, [rbp+1690h+var_1070]
0x101ba9922  lea     rcx, [rbp+1690h+var_1140]
0x101ba9929  call    cs:__imp_?GetGlobalMemoryStatus@MemoryNode@@SAXPEAU_MEMORYSTATUSEX@@PEAU_PROCESS_MEMORY_COUNTERS_EX@@PEAU_JOBOBJECT_EXTENDED_LIMIT_INFORMATION@@PEAHPEA_J@Z; MemoryNode::GetGlobalMemoryStatus(_MEMORYSTATUSEX *,_PROCESS_MEMORY_COUNTERS_EX *,_JOBOBJECT_EXTENDED_LIMIT_INFORMATION *,int *,__int64 *)
0x101ba992f  mov     rax, [rbp+1690h+var_1090]
0x101ba9936  shr     rax, 0Dh
0x101ba993a  mov     cs:qword_1031C9770, rax
0x101ba9941  mov     rax, cs:__imp_?MemoryNode_MemoryTargetPages@@3_JA; __int64 MemoryNode_MemoryTargetPages
0x101ba9948  mov     rcx, [rax]
0x101ba994b  mov     cs:qword_1031C9778, rcx
0x101ba9952  lea     rcx, ?sm_memoryLeakDetector@AutoMemoryLeakDetector@@0V1@A; this
0x101ba9959  call    ?Init@AutoMemoryLeakDetector@@QEAA_NXZ; AutoMemoryLeakDetector::Init(void)
0x101ba995e  test    al, al
0x101ba9960  jnz     short loc_101BA9984
0x101ba9962  lea     rdx, aAutomemoryleak; "AutoMemoryLeakDetector"
0x101ba9969  mov     ecx, 42F2h; unsigned int
0x101ba996e  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x101ba9973  xor     edx, edx
0x101ba9975  lea     ecx, [rdx+1Dh]
0x101ba9978  mov     r8d, 8007000Eh
0x101ba997e  call    cs:__imp_?SQLExit@@YAXW4SQLEXITCODE@@KK@Z; SQLExit(SQLEXITCODE,ulong,ulong)
0x101ba9984  cmp     cs:dword_103186FD0, r14d
0x101ba998b  jge     short loc_101BA999A
0x101ba998d  cmp     cs:byte_10316E6B6, r14b
0x101ba9994  jz      loc_101BA9AE0
0x101ba999a  movsxd  rbx, cs:dword_103186EC8
0x101ba99a1  call    ?GetCPUCorePercentCap@SOS_OS@@SANXZ; SOS_OS::GetCPUCorePercentCap(void)
0x101ba99a6  divsd   xmm0, cs:__real@4059000000000000
0x101ba99ae  movsd   xmm1, cs:__real@3ff0000000000000
0x101ba99b6  maxsd   xmm1, xmm0
0x101ba99ba  xor     eax, eax
0x101ba99bc  movsd   xmm0, cs:__real@43e0000000000000
0x101ba99c4  comisd  xmm1, xmm0
0x101ba99c8  jb      short loc_101BA99E1
0x101ba99ca  subsd   xmm1, xmm0
0x101ba99ce  comisd  xmm1, xmm0
0x101ba99d2  jnb     short loc_101BA99E1
0x101ba99d4  mov     rcx, 8000000000000000h
0x101ba99de  mov     rax, rcx
0x101ba99e1  cvttsd2si r10, xmm1
0x101ba99e6  add     r10, rax
0x101ba99e9  movsxd  rdi, cs:dword_103186ECC
0x101ba99f0  lea     rcx, [rbx-1]
0x101ba99f4  add     rcx, r10
0x101ba99f7  xor     edx, edx
0x101ba99f9  mov     rax, rcx
0x101ba99fc  div     rbx
0x101ba99ff  sub     rcx, rdx
0x101ba9a02  xor     edx, edx
0x101ba9a04  mov     rax, rcx
0x101ba9a07  div     rbx
0x101ba9a0a  mov     rbx, rax
0x101ba9a0d  cmp     rax, r15
0x101ba9a10  cmovb   rbx, r15
0x101ba9a14  mov     eax, 0Ah
0x101ba9a19  cmp     rbx, rax
0x101ba9a1c  cmova   rbx, rax
0x101ba9a20  mov     r9, rdi
0x101ba9a23  mov     r8, rbx
0x101ba9a26  mov     rdx, r10
0x101ba9a29  lea     rcx, aInitGlobalcach; "Init GlobalCacheActivenessStats: %d cor"...
0x101ba9a30  call    ?LogSystemMetadata@@YAXPEB_WZZ; LogSystemMetadata(wchar_t const *,...)
0x101ba9a35  mov     rdx, rdi
0x101ba9a38  mov     rcx, rbx
0x101ba9a3b  call    cs:__imp_?StaticInit@GlobalCacheActivenessStats@@SA_N_K0@Z; GlobalCacheActivenessStats::StaticInit(unsigned __int64,unsigned __int64)
0x101ba9a41  test    al, al
0x101ba9a43  jnz     short loc_101BA9A69
0x101ba9a45  lea     rdx, aGlobalcacheact; "GlobalCacheActivenessStats"
0x101ba9a4c  mov     ecx, 42F2h; unsigned int
0x101ba9a51  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x101ba9a56  xor     edx, edx
0x101ba9a58  mov     ecx, 173h
0x101ba9a5d  mov     r8d, 8007000Eh
0x101ba9a63  call    cs:__imp_?SQLExit@@YAXW4SQLEXITCODE@@KK@Z; SQLExit(SQLEXITCODE,ulong,ulong)
0x101ba9a69  cmp     cs:dword_103186FD0, r14d
0x101ba9a70  jl      short loc_101BA9AE0
0x101ba9a72  mov     rcx, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x101ba9a79  cmp     [rcx], r14d
0x101ba9a7c  jz      short loc_101BA9A8B
0x101ba9a7e  mov     rax, cs:__imp_?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A; _LARGE_INTEGER Base_PublicGlobals::sm_QueryPerformanceFrequency
0x101ba9a85  imul    rax, [rax], 0Fh
0x101ba9a89  jmp     short loc_101BA9A90
0x101ba9a8b  mov     eax, 8F0D180h
0x101ba9a90  mov     cs:qword_103328488, rax
0x101ba9a97  mov     cs:dword_1033284A0, r14d
0x101ba9a9e  mov     cs:qword_103328490, rax
0x101ba9aa5  mov     cs:qword_103328498, r14
0x101ba9aac  cmp     [rcx], r14d
0x101ba9aaf  jz      short loc_101BA9AC3
0x101ba9ab1  lea     rcx, [rsp+1790h+PerformanceCount]; lpPerformanceCount
0x101ba9ab6  call    cs:__imp_QueryPerformanceCounter
0x101ba9abc  mov     rax, qword ptr [rsp+1790h+PerformanceCount]
0x101ba9ac1  jmp     short loc_101BA9ACB
0x101ba9ac3  mov     rax, ds:7FFE0008h
0x101ba9acb  mov     cs:qword_103328480, rax
0x101ba9ad2  lea     rax, off_103328460
0x101ba9ad9  mov     cs:qword_1031C4BA8, rax
0x101ba9ae0  lea     rcx, ?sm_nativeShuffleStatsManager@NativeShuffleStatsManager@@0V1@A; this
0x101ba9ae7  call    ?Init@NativeShuffleStatsManager@@QEAAXXZ; NativeShuffleStatsManager::Init(void)
0x101ba9aec  call    ?SetupHoBtManager@@YAXXZ; SetupHoBtManager(void)
0x101ba9af1  mov     r9d, 8
  ... truncated ...
```
