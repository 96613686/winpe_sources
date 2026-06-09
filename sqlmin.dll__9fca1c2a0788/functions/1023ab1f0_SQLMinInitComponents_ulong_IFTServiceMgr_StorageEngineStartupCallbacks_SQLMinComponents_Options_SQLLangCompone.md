# SQLMinInitComponents(ulong,IFTServiceMgr *,StorageEngineStartupCallbacks &,SQLMinComponents::Options,SQLLangComponents::Options,wchar_t *,NonYieldingConfigurationFunctions *)

- ea: `0x1023ab1f0`
- end: `0x1023abd48`
- name: `?SQLMinInitComponents@@YAXKPEAVIFTServiceMgr@@AEAUStorageEngineStartupCallbacks@@W4Options@SQLMinComponents@@W43SQLLangComponents@@PEA_WPEAUNonYieldingConfigurationFunctions@@@Z`
- size: `2904`
- prototype: ``
- caller_count: `0`
- callee_count: `25`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x100401fcf`
- `0x100415c30`
- `0x100428760`
- `0x1005c68f0`
- `0x10061fc70`
- `0x10072cac0`
- `0x10072ec10`
- `0x1007727c0`
- `0x1009e0660`
- `0x100ccd890`
- `0x100d0e120`
- `0x101182c90`
- `0x101207a00`
- `0x101a438d0`
- `0x101a89c50`
- `0x101ba9540`
- `0x101ca52a0`
- `0x101da4c10`
- `0x101f344c0`
- `0x1023ab1f0`
- `0x1023aea90`
- `0x1023aec40`
- `0x1023b0110`
- `0x1023b19c0`
- `0x1024a1890`

## import_xrefs

- `KERNEL32!GetModuleHandleA` at `0x1023ab35b`
- `KERNEL32!GetModuleHandleA` at `0x1023ab35b`
- `sqlTsEs!?SetExtenderInterface@CSqlTypeSystemHost@@SAXPEAUISqlTypeSystemExtender_IDbTableOptionsProvider@@@Z` at `0x1023ab4e6`
- `sqlTsEs!?SetExtenderInterface@CSqlTypeSystemHost@@SAXPEAUISqlTypeSystemExtender_IDbTableOptionsProvider@@@Z` at `0x1023ab4e6`
- `sqlTsEs!?SetExtenderInterface@CSqlTypeSystemHost@@SAXPEAUISqlTypeSystemExtender_IEngineConfiguration@@@Z` at `0x1023ab5e6`
- `sqlTsEs!?SetExtenderInterface@CSqlTypeSystemHost@@SAXPEAUISqlTypeSystemExtender_IEngineConfiguration@@@Z` at `0x1023ab5e6`
- `sqldk!?HRESULT_FROM_SOS_RESULT_Uncommon@@YAJW4SOS_RESULT@@@Z` at `0x1023abc73`
- `sqldk!?HRESULT_FROM_SOS_RESULT_Uncommon@@YAJW4SOS_RESULT@@@Z` at `0x1023abc73`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x1023ab507`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x1023ab9a4`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x1023ab9e0`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x1023aba1c`
- `sqldk!?g_pmoGlobal@@3PEAVIMemObj@@EA` at `0x1023abd16`
- `sqldk!?sm_cpuCount@SOS_PublicGlobals@@2KA` at `0x1023ab562`
- `sqldk!?g_featureSwitchesDk@@3VCFeatureSwitchesDk@@A` at `0x1023abb2d`
- `sqldk!?g_metadataFactory@@3UMetadataFactory@@A` at `0x1023ab5f3`
- `sqldk!?g_metadataFactory@@3UMetadataFactory@@A` at `0x1023ab604`
- `sqldk!?g_metadataFactory@@3UMetadataFactory@@A` at `0x1023ab616`
- `sqldk!?g_metadataFactory@@3UMetadataFactory@@A` at `0x1023ab628`
- `sqldk!?g_metadataFactory@@3UMetadataFactory@@A` at `0x1023ab63a`
- `sqldk!?g_metadataFactory@@3UMetadataFactory@@A` at `0x1023ab64c`
- `sqldk!?g_metadataFactory@@3UMetadataFactory@@A` at `0x1023ab65e`
- `sqldk!?g_metadataFactory@@3UMetadataFactory@@A` at `0x1023ab670`
- `sqldk!?g_pAutoXactFactory@@3PEAVIAutoXactFactory@@EA` at `0x1023ab4f3`
- `sqldk!?Create@SOS_RingBuffer@@CAPEAV1@W4RINGBUFFER_TYPE@@KKKP6AXPEAVSOS_RingBufferRecord@@PEA_W_KPEAPEA_WPEA_K@ZPEAVIMemObj@@@Z` at `0x1023ab724`
- `sqldk!?Create@SOS_RingBuffer@@CAPEAV1@W4RINGBUFFER_TYPE@@KKKP6AXPEAVSOS_RingBufferRecord@@PEA_W_KPEAPEA_WPEA_K@ZPEAVIMemObj@@@Z` at `0x1023ab724`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x1023ab3cf`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x1023ab460`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x1023abbba`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x1023ab3cf`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x1023ab460`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x1023abbba`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1023ab32e`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1023ab32e`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1023ab2c9`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1023abac6`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1023ab2c9`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1023abac6`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x1023ab4d9`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x1023ab5d9`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x1023ab773`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x1023ab7af`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x1023ab4d9`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x1023ab5d9`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x1023ab773`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x1023ab7af`
- `sqldk!SystemThread_TlsIndex` at `0x1023ab253`
- `sqldk!SystemThread_TlsIndex` at `0x1023ab684`
- `sqldk!SystemThread_TlsIndex` at `0x1023ab6c5`
- `sqldk!SystemThread_TlsIndex` at `0x1023ab95e`
- `sqldk!SystemThread_TlsIndex` at `0x1023abb5c`
- `sqldk!SystemThread_TlsIndex` at `0x1023abc10`
- `sqldk!SystemThread_TlsOffset` at `0x1023ab25c`
- `sqldk!SystemThread_TlsOffset` at `0x1023ab68d`
- `sqldk!SystemThread_TlsOffset` at `0x1023ab6ce`
- `sqldk!SystemThread_TlsOffset` at `0x1023ab967`
- `sqldk!SystemThread_TlsOffset` at `0x1023abb65`
- `sqldk!SystemThread_TlsOffset` at `0x1023abc19`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1023ab277`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1023ab6a8`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1023ab6e9`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1023ab980`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1023abb80`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1023abc32`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1023ab277`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1023ab6a8`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1023ab6e9`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1023ab980`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1023abb80`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1023abc32`
- `qds!InitializeMinimalQDSManagerIfNecessary` at `0x1023ab994`
- `qds!InitializeMinimalQDSManagerIfNecessary` at `0x1023ab994`
- `sqllang!?InitImageHelper@@YAHXZ` at `0x1023ab74b`
- `sqllang!?InitImageHelper@@YAHXZ` at `0x1023ab74b`
- `sqllang!?RegisterPtrEsFn@CEsIntrinsicManager@@YAXHP6AXPEAVCEsExec@@PEAVCXVariant@@@Z@Z` at `0x1023ab7e6`
- `sqllang!?RegisterPtrEsFn@CEsIntrinsicManager@@YAXHP6AXPEAVCEsExec@@PEAVCXVariant@@@Z@Z` at `0x1023ab7f8`
- `sqllang!?RegisterPtrEsFn@CEsIntrinsicManager@@YAXHP6AXPEAVCEsExec@@PEAVCXVariant@@@Z@Z` at `0x1023ab80a`
- `sqllang!?RegisterPtrEsFn@CEsIntrinsicManager@@YAXHP6AXPEAVCEsExec@@PEAVCXVariant@@@Z@Z` at `0x1023ab81c`
- `sqllang!?RegisterPtrEsFn@CEsIntrinsicManager@@YAXHP6AXPEAVCEsExec@@PEAVCXVariant@@@Z@Z` at `0x1023ab82e`
- `sqllang!?RegisterPtrEsFn@CEsIntrinsicManager@@YAXHP6AXPEAVCEsExec@@PEAVCXVariant@@@Z@Z` at `0x1023ab840`
- `sqllang!?RegisterPtrEsFn@CEsIntrinsicManager@@YAXHP6AXPEAVCEsExec@@PEAVCXVariant@@@Z@Z` at `0x1023ab852`
- `sqllang!?RegisterPtrEsFn@CEsIntrinsicManager@@YAXHP6AXPEAVCEsExec@@PEAVCXVariant@@@Z@Z` at `0x1023ab864`
- `sqllang!?RegisterPtrEsFn@CEsIntrinsicManager@@YAXHP6AXPEAVCEsExec@@PEAVCXVariant@@@Z@Z` at `0x1023ab876`
- `sqllang!?RegisterPtrEsFn@CEsIntrinsicManager@@YAXHP6AXPEAVCEsExec@@PEAVCXVariant@@@Z@Z` at `0x1023ab888`
- `sqllang!?RegisterPtrEsFn@CEsIntrinsicManager@@YAXHP6AXPEAVCEsExec@@PEAVCXVariant@@@Z@Z` at `0x1023ab89a`
- `sqllang!?RegisterPtrEsFn@CEsIntrinsicManager@@YAXHP6AXPEAVCEsExec@@PEAVCXVariant@@@Z@Z` at `0x1023ab8ac`
- `sqllang!?RegisterPtrEsFn@CEsIntrinsicManager@@YAXHP6AXPEAVCEsExec@@PEAVCXVariant@@@Z@Z` at `0x1023ab8be`
- `sqllang!?RegisterPtrEsFn@CEsIntrinsicManager@@YAXHP6AXPEAVCEsExec@@PEAVCXVariant@@@Z@Z` at `0x1023ab8d0`
- `sqllang!?RegisterPtrEsFn@CEsIntrinsicManager@@YAXHP6AXPEAVCEsExec@@PEAVCXVariant@@@Z@Z` at `0x1023ab8e2`
- `sqllang!?RegisterPtrEsFn@CEsIntrinsicManager@@YAXHP6AXPEAVCEsExec@@PEAVCXVariant@@@Z@Z` at `0x1023ab8f4`
- `sqllang!?RegisterPtrEsFn@CEsIntrinsicManager@@YAXHP6AXPEAVCEsExec@@PEAVCXVariant@@@Z@Z` at `0x1023ab906`
- `sqllang!?RegisterPtrEsFn@CEsIntrinsicManager@@YAXHP6AXPEAVCEsExec@@PEAVCXVariant@@@Z@Z` at `0x1023ab918`
- `sqllang!?RegisterPtrEsFn@CEsIntrinsicManager@@YAXHP6AXPEAVCEsExec@@PEAVCXVariant@@@Z@Z` at `0x1023ab7c2`
- `sqllang!?RegisterPtrEsFn@CEsIntrinsicManager@@YAXHP6AXPEAVCEsExec@@PEAVCXVariant@@@Z@Z` at `0x1023ab7ce`
- `sqllang!?RegisterPtrEsFn@CEsIntrinsicManager@@YAXHP6AXPEAVCEsExec@@PEAVCXVariant@@@Z@Z` at `0x1023ab7e6`
- `sqllang!?RegisterPtrEsFn@CEsIntrinsicManager@@YAXHP6AXPEAVCEsExec@@PEAVCXVariant@@@Z@Z` at `0x1023ab7f8`
- `sqllang!?RegisterPtrEsFn@CEsIntrinsicManager@@YAXHP6AXPEAVCEsExec@@PEAVCXVariant@@@Z@Z` at `0x1023ab80a`
- `sqllang!?RegisterPtrEsFn@CEsIntrinsicManager@@YAXHP6AXPEAVCEsExec@@PEAVCXVariant@@@Z@Z` at `0x1023ab81c`
- `sqllang!?RegisterPtrEsFn@CEsIntrinsicManager@@YAXHP6AXPEAVCEsExec@@PEAVCXVariant@@@Z@Z` at `0x1023ab82e`
- `sqllang!?RegisterPtrEsFn@CEsIntrinsicManager@@YAXHP6AXPEAVCEsExec@@PEAVCXVariant@@@Z@Z` at `0x1023ab840`
- `sqllang!?RegisterPtrEsFn@CEsIntrinsicManager@@YAXHP6AXPEAVCEsExec@@PEAVCXVariant@@@Z@Z` at `0x1023ab852`
- `sqllang!?RegisterPtrEsFn@CEsIntrinsicManager@@YAXHP6AXPEAVCEsExec@@PEAVCXVariant@@@Z@Z` at `0x1023ab864`
- `sqllang!?RegisterPtrEsFn@CEsIntrinsicManager@@YAXHP6AXPEAVCEsExec@@PEAVCXVariant@@@Z@Z` at `0x1023ab876`
- `sqllang!?RegisterPtrEsFn@CEsIntrinsicManager@@YAXHP6AXPEAVCEsExec@@PEAVCXVariant@@@Z@Z` at `0x1023ab888`
- `sqllang!?RegisterPtrEsFn@CEsIntrinsicManager@@YAXHP6AXPEAVCEsExec@@PEAVCXVariant@@@Z@Z` at `0x1023ab89a`
- `sqllang!?RegisterPtrEsFn@CEsIntrinsicManager@@YAXHP6AXPEAVCEsExec@@PEAVCXVariant@@@Z@Z` at `0x1023ab8ac`
- `sqllang!?RegisterPtrEsFn@CEsIntrinsicManager@@YAXHP6AXPEAVCEsExec@@PEAVCXVariant@@@Z@Z` at `0x1023ab8be`
- `sqllang!?RegisterPtrEsFn@CEsIntrinsicManager@@YAXHP6AXPEAVCEsExec@@PEAVCXVariant@@@Z@Z` at `0x1023ab8d0`
- `sqllang!?RegisterPtrEsFn@CEsIntrinsicManager@@YAXHP6AXPEAVCEsExec@@PEAVCXVariant@@@Z@Z` at `0x1023ab8e2`
- `sqllang!?RegisterPtrEsFn@CEsIntrinsicManager@@YAXHP6AXPEAVCEsExec@@PEAVCXVariant@@@Z@Z` at `0x1023ab8f4`
- `sqllang!?RegisterPtrEsFn@CEsIntrinsicManager@@YAXHP6AXPEAVCEsExec@@PEAVCXVariant@@@Z@Z` at `0x1023ab906`
- `sqllang!?RegisterPtrEsFn@CEsIntrinsicManager@@YAXHP6AXPEAVCEsExec@@PEAVCXVariant@@@Z@Z` at `0x1023ab918`
- `sqllang!?RegisterPtrEsFn@CEsIntrinsicManager@@YAXHP6AXPEAVCEsExec@@PEAVCXVariant@@@Z@Z` at `0x1023ab91e`
- `sqllang!?InitBuiltins@@YAXXZ` at `0x1023ab92a`
- `sqllang!?InitBuiltins@@YAXXZ` at `0x1023ab92a`
- `sqllang!?InitializeServerHeartbeat@@YAXXZ` at `0x1023ab782`
- `sqllang!?InitializeServerHeartbeat@@YAXXZ` at `0x1023ab782`
- `sqllang!?SetDbccCommandEntryPoint@@YAXW4DBCC_COMMANDS@@P6AXPEAVCXVariant@@H@Z@Z` at `0x1023ab93a`

## string_xrefs

- `0x1023ab31f`: `Sql\Ntdbms\common\bits\src\bitvector.cpp`
- `0x1023abab8`: `sql\ntdbms\storeng\dfs\remoteCS\GarbageCollection\RemoteCSGarbageCollectionTask.cpp`
- `0x1023ab5bb`: `xact cache`
- `0x1023ab791`: `article cache`
- `0x1023ab354`: `sqllang.dll`
- `0x1023ab366`: `sqllang.dll`
- `0x1023abc83`: `IntelligentDb.MaxDopFeedback.SettingsRegistry.dll`
- `0x1023abcb5`: `WorkloadOptimizationService feedback channel initialization failed hr = 0x%08lx`
- `0x1023abc96`: `WorkloadOptimizationService feedback channel initialization is done`
- `0x1023abb47`: `Initializing WorkloadOptimizationService feedback channel...`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
// Hidden C++ exception states: #wind=8
void __fastcall SQLMinInitComponents(
        unsigned int a1,
        struct IFTServiceMgr *a2,
        struct StorageEngineStartupCallbacks *a3,
        int a4,
        int a5,
        __int64 a6,
        __int64 a7)
{
  __int64 v10; // rbx
  __int64 v11; // rdi
  __int64 v12; // rax
  struct IMemObj *v13; // rsi
  struct IMemObj *v14; // rax
  CBitVector *v15; // rdi
  struct IMemObj *v16; // rsi
  struct IMemObj *v17; // rdi
  _OWORD *v18; // rax
  _QWORD *v19; // rcx
  _QWORD *v20; // rax
  int v21; // edx
  __int16 v22; // ax
  unsigned __int16 v23; // di
  __int64 v24; // rdi
  __int64 v25; // rax
  __int64 v26; // rsi
  __int64 v27; // rdi
  __int64 v28; // rax
  _QWORD *v29; // rax
  void (*v30)(int, void (*)(struct CEsMDIntrinsicParams *, struct CDataArray *)); // rdx
  void (*v31)(int, void (*)(struct CEsMDIntrinsicParams *, struct CDataArray *)); // rdx
  void (*v32)(int, void (*)(struct CEsMDIntrinsicParams *, struct CDataArray *)); // rdx
  char v33; // al
  __int64 v34; // rdi
  __int64 v35; // rcx
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38; // rax
  struct IMemObj *v39; // rax
  __int64 v40; // rdi
  unsigned int v41; // edx
  __int64 v42; // rdi
  __int64 v43; // rax
  Mlos::Core::MlosContext *v44; // rax
  Mlos::Core::MlosContext *v45; // rdi
  int v46; // eax
  Mlos::Core::MlosContext *v47; // rsi
  __int64 v48; // rdi
  __int64 v49; // rcx
  unsigned int v50; // eax
  int v51; // ecx
  unsigned int v52; // eax
  ToadMQ *v53; // rdx
  signed __int32 v54[8]; // [rsp+0h] [rbp-68h] BYREF
  __int64 v55; // [rsp+20h] [rbp-48h]
  __int64 v56; // [rsp+30h] [rbp-38h]
  struct IMemObj *v57; // [rsp+38h] [rbp-30h]
  struct IMemObj *MemoryObject; // [rsp+40h] [rbp-28h]

  v56 = -2;
  dword_1033C2910 = a4;
  dword_103220560 = a5;
  qword_1033C2918 = a7;
  v10 = 0;
  if ( (unsigned int)IsContainedAGEnabledInstance() )
  {
    v11 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v12 = *(_QWORD *)(v11 + 256);
    if ( !v12 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v12 = *(_QWORD *)(v11 + 256);
    }
    v13 = *(struct IMemObj **)(*(_QWORD *)(v12 + 992) + 320LL);
    v57 = v13;
    if ( !qword_1031B9C80 )
    {
      v14 = (struct IMemObj *)operator new(0x38u, v13, "sql\\ntdbms\\bin\\sqlmin\\sqlmininit.cpp", 1155, 6u);
      v15 = v14;
      MemoryObject = v14;
      if ( v14 )
      {
        *(_DWORD *)v14 = 0;
        *((_DWORD *)v14 + 2) = 0;
        *((_QWORD *)v14 + 2) = 0;
        *((_DWORD *)v14 + 12) = 114;
        *((_QWORD *)v14 + 4) = 0;
        *((_QWORD *)v14 + 5) = 0;
        *((_QWORD *)v14 + 3) = 0;
        *((_QWORD *)v14 + 4) = 0;
        *((_QWORD *)v14 + 5) = 0;
        *((_QWORD *)v14 + 3) = 0;
      }
      else
      {
        v15 = 0;
      }
      qword_1031B9C80 = v15;
      *((_QWORD *)v15 + 2) = v13;
      *(_QWORD *)v15 = operator new[](0x1000u, v13, "Sql\\Ntdbms\\common\\bits\\src\\bitvector.cpp", 86, 3u);
      *((_DWORD *)v15 + 2) = 32765;
      CBitVector::ReInit(v15, 0);
    }
  }
  if ( dword_103220560 != 0x8000 && GetModuleHandleA("sqllang.dll") )
    _HrLoadAllImportsForDll("sqllang.dll");
  if ( (dword_1033C2910 & 0x8000) == 0 )
  {
    InitSharedResource(a1);
    v16 = qword_103172088;
    MemoryObject = qword_103172088;
    if ( pXVM )
      goto LABEL_22;
    v17 = (struct IMemObj *)operator new(
                              0x60u,
                              qword_103172088,
                              1,
                              "sql\\ntdbms\\storeng\\dfs\\trans\\XactVerMgr.cpp",
                              2203,
                              5u);
    v57 = v17;
    if ( v17 )
    {
      *(_QWORD *)v17 = &XVMgr::`vftable';
      *((_QWORD *)v17 + 1) = 0;
      *((_QWORD *)v17 + 2) = 0;
      *((_QWORD *)v17 + 3) = 1;
      *((_QWORD *)v17 + 4) = 0;
      *((_QWORD *)v17 + 5) = 0;
      *((_QWORD *)v17 + 6) = 0;
      *((_QWORD *)v17 + 7) = 0;
      *((_QWORD *)v17 + 8) = 0;
      *((_QWORD *)v17 + 9) = 0;
      *((_DWORD *)v17 + 20) = 0;
      *((_BYTE *)v17 + 84) = 0;
      *((_BYTE *)v17 + 88) = 0;
    }
    else
    {
      v17 = 0;
    }
    pXVM = v17;
    if ( !v17 )
      goto LABEL_22;
    v18 = operator new(0x30u, v16, 1, "sql\\ntdbms\\storeng\\dfs\\trans\\XactVerMgr.cpp", 2275, 5u);
    v19 = v18;
    v57 = (struct IMemObj *)v18;
    if ( v18 )
    {
      *v18 = 0;
      v18[1] = 0;
      v18[2] = 0;
      *(_DWORD *)v18 = 1;
      v20 = (_QWORD *)v18 + 1;
      v20[1] = v20;
      *v20 = v20;
      v19[4] = v19 + 3;
      v19[3] = v19 + 3;
      v19[5] = 0;
    }
    else
    {
      v19 = 0;
    }
    *((_QWORD *)v17 + 1) = v19;
    *((_BYTE *)v17 + 88) = 1;
    if ( !*((_BYTE *)pXVM + 88) )
    {
LABEL_22:
      scierrlog(0x42F2u, L"transaction version manager");
      SQLExit(136, 0, 2147942414LL);
    }
    CSqlTypeSystemHost::SetExtenderInterface((struct ISqlTypeSystemExtender_IDbTableOptionsProvider *)&x_DbTableExtender);
    g_pAutoXactFactory = (struct IAutoXactFactory *)&g_sqlAutoXactFactory;
    if ( theXactCache )
    {
      if ( theXactCache != 2 )
        goto LABEL_40;
    }
    else
    {
      v21 = *((_DWORD *)s_pServerConf + 2);
      if ( v21 == 3 || (unsigned int)(*((_DWORD *)s_pServerConf + 3) - 1) <= 1 || (qword_10317AD66 & 0x100000000LL) != 0 )
      {
        theXactCache = 1;
        goto LABEL_40;
      }
      if ( v21 != 2 || (qword_10317AD66 & 0x400000000LL) != 0 )
      {
        theXactCache = 3;
        goto LABEL_40;
      }
      theXactCache = 2;
    }
    v22 = 129;
    if ( (int)SOS_PublicGlobals::sm_cpuCount < 129 )
      v22 = SOS_PublicGlobals::sm_cpuCount;
    word_1031B9C58 = v22;
    v23 = 0;
    if ( v22 )
    {
      while ( XactCache::InitObjectStoreForIndividualPartition((XactCache *)&theXactCache, v23) )
      {
        if ( ++v23 >= (unsigned __int16)word_1031B9C58 )
          goto LABEL_40;
      }
      theXactCache = 1;
      scierrlog(0x42F2u, L"xact cache");
      SQLExit(137, 0, 2147942414LL);
    }
LABEL_40:
    CSqlTypeSystemHost::SetExtenderInterface((struct ISqlTypeSystemExtender_IEngineConfiguration *)&off_1031FF7E0);
    g_metadataFactory[0] = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))GetSqlServrIMetadataAccess;
    g_metadataFactory[1] = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))GetSqlServrIMetadataAccessSize;
    g_metadataFactory[2] = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))GetSqlServrIMetadataAccess;
    g_metadataFactory[3] = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))GetSqlServrIMetadataAccess;
    g_metadataFactory[5] = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))GetSqlServrIMetadataAccessPhysicalMaster;
    g_metadataFactory[6] = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))GetSqlServrIMetadataAccessReplicatedMaster;
    g_metadataFactory[7] = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))GetSqlServrIMetadataAccessAgMaster;
    g_metadataFactory[4] = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))GetSqlServrIMetadataAccessRemote;
    v24 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v25 = *(_QWORD *)(v24 + 256);
    if ( !v25 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v25 = *(_QWORD *)(v24 + 256);
    }
    v26 = *(_QWORD *)(v25 + 992);
    v27 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v28 = *(_QWORD *)(v27 + 256);
    if ( !v28 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v28 = *(_QWORD *)(v27 + 256);
    }
    v29 = (_QWORD *)SOS_RingBuffer::Create(
                      56,
                      56,
                      128,
                      1,
                      CMDEventRingBufferRecord::SerializeRecord,
                      *(_QWORD *)(*(_QWORD *)(v28 + 992) + 320LL),
                      v56,
                      v57,
                      MemoryObject);
    if ( v29 )
    {
      *v29 = 0;
      v29[1] = 0;
      TList<SOS_Node,SOS_RingBuffer,0,TListSLock>::AppendElem(v26 + 96, v29);
    }
    if ( (dword_1033C2910 & 1) != 0 && !InitImageHelper() )
    {
      scierrlog(0x42F2u, L"Image Helper initialization");
      SQLExit(138, 0, 2147942414LL);
    }
    if ( (dword_1033C2910 & 2) != 0 )
      InitializeServerHeartbeat();
    if ( !(unsigned int)InitReplication() )
    {
      scierrlog(0x42F2u, L"article cache");
      SQLExit(139, 0, 2147942414LL);
    }
    if ( (dword_1033C2910 & 8) != 0 )
    {
      InitializeMetadataEsIntrinsic(CEsIntrinsicManager::RegisterPtrEsFn, v30);
      InitializeQeCValEsIntrinsic(CEsIntrinsicManager::RegisterPtrEsFn, v31);
      CEsIntrinsicManager::RegisterPtrEsFn(2206, (void (*)(struct CEsExec *, struct CXVariant *))ShowplanXmlDecompress);
      CEsIntrinsicManager::RegisterPtrEsFn(
        2648,
        (void (*)(struct CEsExec *, struct CXVariant *))ContextFromDiagnosticLog);
      CEsIntrinsicManager::RegisterPtrEsFn(
        2689,
        (void (*)(struct CEsExec *, struct CXVariant *))ShowplanXmlFindAttribute);
      CEsIntrinsicManager::RegisterPtrEsFn(
        286,
        (void (*)(struct CEsExec *, struct CXVariant *))BytUpdateLineageBytBytI4);
      CEsIntrinsicManager::RegisterPtrEsFn(287, (void (*)(struct CEsExec *, struct CXVariant *))BytLineage90To80Byt);
      CEsIntrinsicManager::RegisterPtrEsFn(288, (void (*)(struct CEsExec *, struct CXVariant *))BytLineage80To90Byt);
      CEsIntrinsicManager::RegisterPtrEsFn(289, (void (*)(struct CEsExec *, struct CXVariant *))BytColv90To80BytI4);
      CEsIntrinsicManager::RegisterPtrEsFn(290, (void (*)(struct CEsExec *, struct CXVariant *))BytColv80To90Byt);
      CEsIntrinsicManager::RegisterPtrEsFn(
        291,
        (void (*)(struct CEsExec *, struct CXVariant *))BytReplnickArray90To80Byt);
      CEsIntrinsicManager::RegisterPtrEsFn(
        292,
        (void (*)(struct CEsExec *, struct CXVariant *))BytReplnickArray80To90Byt);
      CEsIntrinsicManager::RegisterPtrEsFn(293, (void (*)(struct CEsExec *, struct CXVariant *))I4Replnick90To80Byt);
      CEsIntrinsicManager::RegisterPtrEsFn(294, (void (*)(struct CEsExec *, struct CXVariant *))I4GetMaxVersionByt);
      CEsIntrinsicManager::RegisterPtrEsFn(
        295,
        (void (*)(struct CEsExec *, struct CXVariant *))BytUpdateColvbmBytBytBytBytI4);
      CEsIntrinsicManager::RegisterPtrEsFn(
        296,
        (void (*)(struct CEsExec *, struct CXVariant *))I4IntersectBitmapsBytByt);
      CEsIntrinsicManager::RegisterPtrEsFn(297, (void (*)(struct CEsExec *, struct CXVariant *))I4IsPALUser);
      CEsIntrinsicManager::RegisterPtrEsFn(
        1197,
        (void (*)(struct CEsExec *, struct CXVariant *))WstrPublishingServerName);
      CEsIntrinsicManager::RegisterPtrEsFn(
        1229,
        (void (*)(struct CEsExec *, struct CXVariant *))I4CTIsColumnInMaskI4Byt);
      CEsIntrinsicManager::RegisterPtrEsFn(1234, (void (*)(struct CEsExec *, struct CXVariant *))GetReplPeerVersion);
      InitializeSeEsIntrinsic(CEsIntrinsicManager::RegisterPtrEsFn, v32);
    }
    InitBuiltins();
    v33 = dword_1033C2910;
    if ( (dword_1033C2910 & 0x10) != 0 )
    {
      EnumerateDbccCommandsForSqlMin(SetDbccCommandEntryPoint);
      v33 = dword_1033C2910;
    }
    if ( (v33 & 0x20) != 0 )
      InitQeOnServerStart();
    v34 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v35 = *(_QWORD *)(v34 + 256);
    if ( !v35 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v35 = *(_QWORD *)(v34 + 256);
    }
    InitializeMinimalQDSManagerIfNecessary(*(struct IMemObj **)(v35 + 1000));
    dword_1031C91A8 = 300;
    v36 = *(_QWORD *)s_pServerConf;
    LOBYTE(v55) = 1;
    (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, int *, _DWORD, _QWORD))(v36 + 520))(
      s_pServerConf,
      L"SQL",
      L"AggregatedStatsIntervalSec",
      &dword_1031C91A8,
      v55,
      0);
    dword_1031C91AC = 60;
    v37 = *(_QWORD *)s_pServerConf;
    LOBYTE(v55) = 1;
    (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, int *, _DWORD, _QWORD))(v37 + 520))(
      s_pServerConf,
      L"SQL",
      L"AggregatedStatsPercentilesIntervalSec",
      &dword_1031C91AC,
      v55,
      0);
    dword_1031C91B0 = 5000;
    v38 = *(_QWORD *)s_pServerConf;
    LOBYTE(v55) = 1;
    (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, int *, _DWORD, _QWORD))(v38 + 520))(
      s_pServerConf,
      L"SQL",
      L"AggregatedStatsMonitorIntervalMs",
      &dword_1031C91B0,
      v55,
      0);
    SEInit(a2, a3);
    if ( ((dword_10317A9F4 & 1) != 0 || (dword_103172528 || !byte_1031852E4) && byte_1031852E4)
      && !byte_1031852E4
      && !qword_1033C1108 )
    {
      MemoryObject = RemoteCSGarbageCollectionUtilities::GetMemoryObject();
      v39 = (struct IMemObj *)operator new(
                                0x60u,
                                MemoryObject,
                                "sql\\ntdbms\\storeng\\dfs\\remoteCS\\GarbageCollection\\RemoteCSGarbageCollectionTask.cpp",
                                61,
                                5u);
      v40 = (__int64)v39;
      v57 = v39;
      if ( v39 )
      {
        v41 = 1800;
        if ( dword_103172528 )
          v41 = dword_103187570;
        *((_QWORD *)v39 + 1) = 0;
        *((_QWORD *)v39 + 2) = 0;
        *((_QWORD *)v39 + 9) = 0;
        *((_BYTE *)v39 + 80) = 1;
        *((_DWORD *)v39 + 21) = -1;
        *(_QWORD *)v39 = &RemoteCSGarbageCollectionTask::`vftable';
        TaskReqPktTimer::Init(v39, v41);
        qword_1031C4B68 = v40;
      }
      else
      {
        v40 = 0;
      }
      qword_1033C1108 = v40;
    }
    SqlPmmFlushInit();
    if ( !g_featureSwitchesDk[65] && (byte_10317B1FE & 0x20) == 0 )
      goto LABEL_87;
    log_unlocalized(L"Initializing WorkloadOptimizationService feedback channel...");
    v42 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v43 = *(_QWORD *)(v42 + 256);
    if ( !v43 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v43 = *(_QWORD *)(v42 + 256);
    }
    v44 = (Mlos::Core::MlosContext *)operator new(
                                       0x178u,
                                       *(struct IMemObj **)(*(_QWORD *)(v43 + 992) + 320LL),
                                       1,
                                       "sql\\ntdbms\\msql\\Mlos\\src\\Mlos.cpp",
                                       105,
                                       6u);
    v45 = v44;
    if ( v44 )
    {
      memset_0(v44, 0, 0x178u);
      g_pMlosInitializer = v45;
      v46 = Mlos::SqlOS::MlosSqlOSContext::Create(v45, 0x10000);
      if ( v46 >= 0 )
      {
        v47 = g_pMlosInitializer;
        a7 = 0;
        v48 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        v49 = *(_QWORD *)(v48 + 256);
        if ( !v49 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v49 = *(_QWORD *)(v48 + 256);
        }
        v50 = SOS_Node::EnqueueTaskDirect(*(_QWORD *)(v49 + 992), FeedbackChannelFunc, v47, 2, &a7, 0);
        if ( !v50 || (v46 = HRESULT_FROM_SOS_RESULT_Uncommon(v50), v46 >= 0) )
        {
          v46 = Mlos::Core::MlosContext::RegisterSettingsAssembly(
                  v47,
                  "IntelligentDb.MaxDopFeedback.SettingsRegistry.dll",
                  0x13u);
          if ( v46 >= 0 )
          {
            log_unlocalized(L"WorkloadOptimizationService feedback channel initialization is done");
LABEL_87:
            if ( IsToadEnabled() )
            {
              v51 = dword_1033BDB20;
              do
              {
                v52 = v51 & 0xFFFFFFFE;
                v53 = ToadMQ::s_pSelfInstance;
                _InterlockedOr(v54, 0);
                v51 = dword_1033BDB20;
              }
              while ( v52 != dword_1033BDB20 );
              if ( v53 && *((_QWORD *)v53 + 3) )
                v10 = *((_QWORD *)v53 + 3);
              *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v10 + 96LL) + 96LL) = ToadAutoStatsHandler::CreateAutoStatsHandler;
            }
            if ( byte_10316EB86 )
              OneLakeClientLibrary::StartProxy((OneLakeClientLibrary *)g_OneLakeClientLibrary, g_pmoGlobal);
            return;
          }
        }
      }
    }
    else
    {
      g_pMlosInitializer = 0;
      v46 = -2147024882;
    }
    _mm_lfence();
    log_unlocalized(
      L"WorkloadOptimizationService feedback channel initialization failed hr = 0x%08lx",
      (unsigned int)v46);
    goto LABEL_87;
  }
}

```

## disassembly

```asm
0x1023ab1f0  mov     rax, rsp
0x1023ab1f3  push    rdi
0x1023ab1f4  push    r14
0x1023ab1f6  push    r15
0x1023ab1f8  sub     rsp, 50h
0x1023ab1fc  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x1023ab204  mov     [rax+8], rbx
0x1023ab208  mov     [rax+10h], rbp
0x1023ab20c  mov     [rax+18h], rsi
0x1023ab210  mov     r14, r8
0x1023ab213  mov     r15, rdx
0x1023ab216  mov     ebp, ecx
0x1023ab218  mov     cs:dword_1033C2910, r9d
0x1023ab21f  mov     eax, [rsp+68h+arg_20]
0x1023ab226  mov     cs:dword_103220560, eax
0x1023ab22c  mov     rax, [rsp+68h+arg_30]
0x1023ab234  mov     cs:qword_1033C2918, rax
0x1023ab23b  call    ?IsContainedAGEnabledInstance@@YAHXZ; IsContainedAGEnabledInstance(void)
0x1023ab240  xor     ebx, ebx
0x1023ab242  test    eax, eax
0x1023ab244  jz      loc_1023AB348
0x1023ab24a  mov     rdx, gs:58h
0x1023ab253  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1023ab25a  mov     ecx, [rax]
0x1023ab25c  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1023ab263  mov     edi, [rax]
0x1023ab265  add     rdi, [rdx+rcx*8]
0x1023ab269  mov     rax, [rdi+100h]
0x1023ab270  test    rax, rax
0x1023ab273  jnz     short loc_1023AB284
0x1023ab275  xor     ecx, ecx
0x1023ab277  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1023ab27d  mov     rax, [rdi+100h]
0x1023ab284  mov     rax, [rax+3E0h]
0x1023ab28b  mov     rsi, [rax+140h]
0x1023ab292  mov     [rsp+68h+var_30], rsi
0x1023ab297  cmp     cs:qword_1031B9C80, rbx
0x1023ab29e  jnz     loc_1023AB348
0x1023ab2a4  mov     [rsp+68h+arg_20], 483h
0x1023ab2af  mov     byte ptr [rsp+68h+var_48], 6
0x1023ab2b4  mov     r9d, 483h
0x1023ab2ba  lea     r8, aSqlNtdbmsBinSq; "sql\\ntdbms\\bin\\sqlmin\\sqlmininit.cp"...
0x1023ab2c1  mov     rdx, rsi
0x1023ab2c4  mov     ecx, 38h ; '8'
0x1023ab2c9  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new(unsigned __int64,IMemObj *,char const *,int,uchar)
0x1023ab2cf  mov     rdi, rax
0x1023ab2d2  mov     [rsp+68h+var_28], rax
0x1023ab2d7  test    rax, rax
0x1023ab2da  jz      short loc_1023AB306
0x1023ab2dc  mov     [rax], ebx
0x1023ab2de  mov     [rax+8], ebx
0x1023ab2e1  mov     [rax+10h], rbx
0x1023ab2e5  mov     dword ptr [rax+30h], 72h ; 'r'
0x1023ab2ec  mov     [rax+20h], rbx
0x1023ab2f0  mov     [rax+28h], rbx
0x1023ab2f4  mov     [rax+18h], rbx
0x1023ab2f8  mov     [rax+20h], rbx
0x1023ab2fc  mov     [rax+28h], rbx
0x1023ab300  mov     [rax+18h], rbx
0x1023ab304  jmp     short loc_1023AB309
0x1023ab306  mov     rdi, rbx
0x1023ab309  mov     cs:qword_1031B9C80, rdi
0x1023ab310  mov     [rdi+10h], rsi
0x1023ab314  mov     byte ptr [rsp+68h+var_48], 3
0x1023ab319  mov     r9d, 56h ; 'V'
0x1023ab31f  lea     r8, aSqlNtdbmsCommo_22; "Sql\\Ntdbms\\common\\bits\\src\\bitvect"...
0x1023ab326  mov     rdx, rsi
0x1023ab329  mov     ecx, 1000h
0x1023ab32e  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x1023ab334  mov     [rdi], rax
0x1023ab337  mov     dword ptr [rdi+8], 7FFDh
0x1023ab33e  xor     edx, edx; bool
0x1023ab340  mov     rcx, rdi; this
0x1023ab343  call    ?ReInit@CBitVector@@QEAAX_N@Z; CBitVector::ReInit(bool)
0x1023ab348  cmp     cs:dword_103220560, 8000h
0x1023ab352  jz      short loc_1023AB372
0x1023ab354  lea     rcx, szDll; "sqllang.dll"
0x1023ab35b  call    cs:__imp_GetModuleHandleA
0x1023ab361  test    rax, rax
0x1023ab364  jz      short loc_1023AB372
0x1023ab366  lea     rcx, szDll; "sqllang.dll"
0x1023ab36d  call    __HrLoadAllImportsForDll
0x1023ab372  test    cs:dword_1033C2910, 8000h
0x1023ab37c  jnz     loc_1023ABD2C
0x1023ab382  mov     ecx, ebp; unsigned int
0x1023ab384  call    ?InitSharedResource@@YAXK@Z; InitSharedResource(ulong)
0x1023ab389  mov     rsi, cs:qword_103172088
0x1023ab390  mov     [rsp+68h+var_28], rsi
0x1023ab395  cmp     cs:?pXVM@@3PEAVXVMgr@@EA, 0; XVMgr * pXVM
0x1023ab39d  jnz     loc_1023AB4BB
0x1023ab3a3  mov     [rsp+68h+arg_20], 89Bh
0x1023ab3ae  mov     byte ptr [rsp+68h+var_40], 5
0x1023ab3b3  mov     dword ptr [rsp+68h+var_48], 89Bh
0x1023ab3bb  lea     r9, aSqlNtdbmsStore_657; "sql\\ntdbms\\storeng\\dfs\\trans\\XactV"...
0x1023ab3c2  mov     r8d, 1
0x1023ab3c8  mov     rdx, rsi
0x1023ab3cb  lea     ecx, [r8+5Fh]
0x1023ab3cf  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new(unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x1023ab3d5  mov     rdi, rax
0x1023ab3d8  mov     [rsp+68h+var_30], rax
0x1023ab3dd  test    rax, rax
0x1023ab3e0  jz      short loc_1023AB421
0x1023ab3e2  lea     rax, ??_7XVMgr@@6B@; const XVMgr::`vftable'
0x1023ab3e9  mov     [rdi], rax
0x1023ab3ec  mov     [rdi+8], rbx
0x1023ab3f0  mov     [rdi+10h], rbx
0x1023ab3f4  mov     qword ptr [rdi+18h], 1
0x1023ab3fc  mov     [rdi+20h], rbx
0x1023ab400  mov     [rdi+28h], rbx
0x1023ab404  mov     [rdi+30h], rbx
0x1023ab408  mov     [rdi+38h], rbx
0x1023ab40c  mov     [rdi+40h], rbx
0x1023ab410  mov     [rdi+48h], rbx
0x1023ab414  mov     [rdi+50h], ebx
0x1023ab417  mov     byte ptr [rdi+54h], 0
0x1023ab41b  mov     byte ptr [rdi+58h], 0
0x1023ab41f  jmp     short loc_1023AB424
0x1023ab421  mov     rdi, rbx
0x1023ab424  mov     cs:?pXVM@@3PEAVXVMgr@@EA, rdi; XVMgr * pXVM
0x1023ab42b  test    rdi, rdi
0x1023ab42e  jz      loc_1023AB4BB
0x1023ab434  mov     [rsp+68h+arg_20], 8E3h
0x1023ab43f  mov     byte ptr [rsp+68h+var_40], 5
0x1023ab444  mov     dword ptr [rsp+68h+var_48], 8E3h
0x1023ab44c  lea     r9, aSqlNtdbmsStore_657; "sql\\ntdbms\\storeng\\dfs\\trans\\XactV"...
0x1023ab453  mov     r8d, 1
0x1023ab459  mov     rdx, rsi
0x1023ab45c  lea     ecx, [r8+2Fh]
0x1023ab460  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new(unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x1023ab466  mov     rcx, rax
0x1023ab469  mov     [rsp+68h+var_30], rax
0x1023ab46e  test    rax, rax
0x1023ab471  jz      short loc_1023AB4A3
0x1023ab473  xorps   xmm0, xmm0
0x1023ab476  movups  xmmword ptr [rax], xmm0
0x1023ab479  movups  xmmword ptr [rax+10h], xmm0
0x1023ab47d  movups  xmmword ptr [rax+20h], xmm0
0x1023ab481  mov     dword ptr [rax], 1
0x1023ab487  add     rax, 8
0x1023ab48b  mov     [rax+8], rax
0x1023ab48f  mov     [rax], rax
0x1023ab492  lea     rax, [rcx+18h]
0x1023ab496  mov     [rax+8], rax
0x1023ab49a  mov     [rax], rax
0x1023ab49d  mov     [rcx+28h], rbx
0x1023ab4a1  jmp     short loc_1023AB4A6
0x1023ab4a3  mov     rcx, rbx
0x1023ab4a6  mov     [rdi+8], rcx
0x1023ab4aa  mov     byte ptr [rdi+58h], 1
0x1023ab4ae  mov     rax, cs:?pXVM@@3PEAVXVMgr@@EA; XVMgr * pXVM
0x1023ab4b5  cmp     byte ptr [rax+58h], 0
0x1023ab4b9  jnz     short loc_1023AB4DF
0x1023ab4bb  lea     rdx, aTransactionVer_0; "transaction version manager"
0x1023ab4c2  mov     ecx, 42F2h; unsigned int
0x1023ab4c7  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x1023ab4cc  xor     edx, edx
0x1023ab4ce  mov     ecx, 88h
0x1023ab4d3  mov     r8d, 8007000Eh
0x1023ab4d9  call    cs:__imp_?SQLExit@@YAXW4SQLEXITCODE@@KK@Z; SQLExit(SQLEXITCODE,ulong,ulong)
0x1023ab4df  lea     rcx, ?x_DbTableExtender@@3VCTsDbTableOptionsImpl@@A; CTsDbTableOptionsImpl x_DbTableExtender
0x1023ab4e6  call    cs:__imp_?SetExtenderInterface@CSqlTypeSystemHost@@SAXPEAUISqlTypeSystemExtender_IDbTableOptionsProvider@@@Z; CSqlTypeSystemHost::SetExtenderInterface(ISqlTypeSystemExtender_IDbTableOptionsProvider *)
0x1023ab4ec  lea     rcx, ?g_sqlAutoXactFactory@@3VSqlAutoXactFactory@@A; SqlAutoXactFactory g_sqlAutoXactFactory
0x1023ab4f3  mov     rax, cs:__imp_?g_pAutoXactFactory@@3PEAVIAutoXactFactory@@EA; IAutoXactFactory * g_pAutoXactFactory
0x1023ab4fa  mov     [rax], rcx
0x1023ab4fd  mov     eax, cs:?theXactCache@@3VXactCache@@A; XactCache theXactCache
0x1023ab503  test    eax, eax
0x1023ab505  jnz     short loc_1023AB55D
0x1023ab507  mov     rax, cs:__imp_?s_pServerConf@@3PEAVIServerConfiguration@@EA; IServerConfiguration * s_pServerConf
0x1023ab50e  mov     rcx, [rax]
0x1023ab511  mov     edx, [rcx+8]
0x1023ab514  cmp     edx, 3
0x1023ab517  jz      short loc_1023AB54E
0x1023ab519  mov     eax, [rcx+0Ch]
0x1023ab51c  dec     eax
0x1023ab51e  cmp     eax, 1
0x1023ab521  jbe     short loc_1023AB54E
0x1023ab523  movzx   eax, byte ptr cs:qword_10317AD66+4
0x1023ab52a  test    al, 1
0x1023ab52c  jnz     short loc_1023AB54E
0x1023ab52e  cmp     edx, 2
0x1023ab531  jnz     short loc_1023AB53F
0x1023ab533  test    al, 4
0x1023ab535  jnz     short loc_1023AB53F
0x1023ab537  mov     cs:?theXactCache@@3VXactCache@@A, edx; XactCache theXactCache
0x1023ab53d  jmp     short loc_1023AB562
0x1023ab53f  mov     cs:?theXactCache@@3VXactCache@@A, 3; XactCache theXactCache
0x1023ab549  jmp     loc_1023AB5DF
0x1023ab54e  mov     cs:?theXactCache@@3VXactCache@@A, 1; XactCache theXactCache
0x1023ab558  jmp     loc_1023AB5DF
0x1023ab55d  cmp     eax, 2
0x1023ab560  jnz     short loc_1023AB5DF
0x1023ab562  mov     rax, cs:__imp_?sm_cpuCount@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_cpuCount
0x1023ab569  mov     ecx, [rax]
0x1023ab56b  mov     eax, 81h
0x1023ab570  cmp     ecx, eax
0x1023ab572  cmovl   ax, cx
0x1023ab576  mov     cs:word_1031B9C58, ax
0x1023ab57d  movzx   edi, bx
0x1023ab580  cmp     bx, ax
0x1023ab583  jnb     short loc_1023AB5DF
0x1023ab585  nop     dword ptr [rax]
0x1023ab588  nop     dword ptr [rax+rax+00000000h]
0x1023ab590  movzx   edx, di; unsigned __int16
0x1023ab593  lea     rcx, ?theXactCache@@3VXactCache@@A; this
0x1023ab59a  call    ?InitObjectStoreForIndividualPartition@XactCache@@AEAA_NG@Z; XactCache::InitObjectStoreForIndividualPartition(ushort)
0x1023ab59f  test    al, al
0x1023ab5a1  jz      short loc_1023AB5B1
0x1023ab5a3  inc     di
0x1023ab5a6  cmp     di, cs:word_1031B9C58
0x1023ab5ad  jb      short loc_1023AB590
0x1023ab5af  jmp     short loc_1023AB5DF
0x1023ab5b1  mov     cs:?theXactCache@@3VXactCache@@A, 1; XactCache theXactCache
0x1023ab5bb  lea     rdx, aXactCache; "xact cache"
0x1023ab5c2  mov     ecx, 42F2h; unsigned int
0x1023ab5c7  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x1023ab5cc  xor     edx, edx
0x1023ab5ce  mov     ecx, 89h
0x1023ab5d3  mov     r8d, 8007000Eh
0x1023ab5d9  call    cs:__imp_?SQLExit@@YAXW4SQLEXITCODE@@KK@Z; SQLExit(SQLEXITCODE,ulong,ulong)
0x1023ab5df  lea     rcx, off_1031FF7E0
0x1023ab5e6  call    cs:__imp_?SetExtenderInterface@CSqlTypeSystemHost@@SAXPEAUISqlTypeSystemExtender_IEngineConfiguration@@@Z; CSqlTypeSystemHost::SetExtenderInterface(ISqlTypeSystemExtender_IEngineConfiguration *)
0x1023ab5ec  lea     rcx, ?GetSqlServrIMetadataAccess@@YAPEAVIMetadataAccess@@PEAVIMemObj@@PEAVBaseXact@@PEBDH@Z; GetSqlServrIMetadataAccess(IMemObj *,BaseXact *,char const *,int)
0x1023ab5f3  mov     rax, cs:__imp_?g_metadataFactory@@3UMetadataFactory@@A; MetadataFactory g_metadataFactory
0x1023ab5fa  mov     [rax], rcx
0x1023ab5fd  lea     rcx, ?GetSqlServrIMetadataAccessSize@@YA_KXZ; GetSqlServrIMetadataAccessSize(void)
0x1023ab604  mov     rax, cs:__imp_?g_metadataFactory@@3UMetadataFactory@@A; MetadataFactory g_metadataFactory
0x1023ab60b  mov     [rax+8], rcx
0x1023ab60f  lea     rcx, ?GetSqlServrIMetadataAccess@@YAPEAVIMetadataAccess@@PEAXKPEAVIMemObj@@PEAVBaseXact@@PEBDH@Z; GetSqlServrIMetadataAccess(void *,ulong,IMemObj *,BaseXact *,char const *,int)
0x1023ab616  mov     rax, cs:__imp_?g_metadataFactory@@3UMetadataFactory@@A; MetadataFactory g_metadataFactory
0x1023ab61d  mov     [rax+10h], rcx
0x1023ab621  lea     rcx, ?GetSqlServrIMetadataAccess@@YAPEAVIMetadataAccess@@PEAVIMemObj@@PEAVBaseXact@@KPEBDH@Z; GetSqlServrIMetadataAccess(IMemObj *,BaseXact *,ulong,char const *,int)
0x1023ab628  mov     rax, cs:__imp_?g_metadataFactory@@3UMetadataFactory@@A; MetadataFactory g_metadataFactory
0x1023ab62f  mov     [rax+18h], rcx
0x1023ab633  lea     rcx, ?GetSqlServrIMetadataAccessPhysicalMaster@@YAPEAVIMetadataAccess@@PEAVIMemObj@@PEAVBaseXact@@PEBDH@Z; GetSqlServrIMetadataAccessPhysicalMaster(IMemObj *,BaseXact *,char const *,int)
0x1023ab63a  mov     rax, cs:__imp_?g_metadataFactory@@3UMetadataFactory@@A; MetadataFactory g_metadataFactory
0x1023ab641  mov     [rax+28h], rcx
0x1023ab645  lea     rcx, ?GetSqlServrIMetadataAccessReplicatedMaster@@YAPEAVIMetadataAccess@@PEAVIMemObj@@PEAVBaseXact@@PEBDH@Z; GetSqlServrIMetadataAccessReplicatedMaster(IMemObj *,BaseXact *,char const *,int)
0x1023ab64c  mov     rax, cs:__imp_?g_metadataFactory@@3UMetadataFactory@@A; MetadataFactory g_metadataFactory
0x1023ab653  mov     [rax+30h], rcx
0x1023ab657  lea     rcx, ?GetSqlServrIMetadataAccessAgMaster@@YAPEAVIMetadataAccess@@PEAVIMemObj@@PEAVBaseXact@@KPEBDH@Z; GetSqlServrIMetadataAccessAgMaster(IMemObj *,BaseXact *,ulong,char const *,int)
0x1023ab65e  mov     rax, cs:__imp_?g_metadataFactory@@3UMetadataFactory@@A; MetadataFactory g_metadataFactory
0x1023ab665  mov     [rax+38h], rcx
0x1023ab669  lea     rcx, ?GetSqlServrIMetadataAccessRemote@@YAPEAVIMetadataAccess@@PEAVIMemObj@@PEAVBaseXact@@PEAVIMEDConnectionHandle@@PEBDH@Z; GetSqlServrIMetadataAccessRemote(IMemObj *,BaseXact *,IMEDConnectionHandle *,char const *,int)
0x1023ab670  mov     rax, cs:__imp_?g_metadataFactory@@3UMetadataFactory@@A; MetadataFactory g_metadataFactory
0x1023ab677  mov     [rax+20h], rcx
0x1023ab67b  mov     rdx, gs:58h
0x1023ab684  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1023ab68b  mov     ecx, [rax]
0x1023ab68d  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1023ab694  mov     edi, [rax]
0x1023ab696  add     rdi, [rdx+rcx*8]
0x1023ab69a  mov     rax, [rdi+100h]
0x1023ab6a1  test    rax, rax
0x1023ab6a4  jnz     short loc_1023AB6B5
0x1023ab6a6  xor     ecx, ecx
0x1023ab6a8  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1023ab6ae  mov     rax, [rdi+100h]
0x1023ab6b5  mov     rsi, [rax+3E0h]
0x1023ab6bc  mov     rdx, gs:58h
0x1023ab6c5  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1023ab6cc  mov     ecx, [rax]
0x1023ab6ce  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1023ab6d5  mov     edi, [rax]
0x1023ab6d7  add     rdi, [rdx+rcx*8]
0x1023ab6db  mov     rax, [rdi+100h]
0x1023ab6e2  test    rax, rax
0x1023ab6e5  jnz     short loc_1023AB6F6
0x1023ab6e7  xor     ecx, ecx
0x1023ab6e9  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1023ab6ef  mov     rax, [rdi+100h]
0x1023ab6f6  mov     rax, [rax+3E0h]
0x1023ab6fd  mov     rdx, [rax+140h]
0x1023ab704  mov     [rsp+68h+var_40], rdx
0x1023ab709  lea     rax, ?SerializeRecord@CMDEventRingBufferRecord@@SAXPEAVSOS_RingBufferRecord@@PEA_W_KPEAPEA_WPEA_K@Z; CMDEventRingBufferRecord::SerializeRecord(SOS_RingBufferRecord *,wchar_t *,unsigned __int64,wchar_t * *,unsigned __int64 *)
0x1023ab710  mov     [rsp+68h+var_48], rax
0x1023ab715  mov     edx, 38h ; '8'
0x1023ab71a  mov     ecx, edx
0x1023ab71c  lea     r9d, [rdx-37h]
0x1023ab720  lea     r8d, [rdx+48h]
0x1023ab724  call    cs:__imp_?Create@SOS_RingBuffer@@CAPEAV1@W4RINGBUFFER_TYPE@@KKKP6AXPEAVSOS_RingBufferRecord@@PEA_W_KPEAPEA_WPEA_K@ZPEAVIMemObj@@@Z; SOS_RingBuffer::Create(RINGBUFFER_TYPE,ulong,ulong,ulong,void (*)(SOS_RingBufferRecord *,wchar_t *,unsigned __int64,wchar_t * *,unsigned __int64 *),IMemObj *)
0x1023ab72a  test    rax, rax
0x1023ab72d  jz      short loc_1023AB742
0x1023ab72f  mov     [rax], rbx
0x1023ab732  mov     [rax+8], rbx
0x1023ab736  lea     rcx, [rsi+60h]
0x1023ab73a  mov     rdx, rax
0x1023ab73d  call    ?AppendElem@?$TList@VSOS_Node@@VSOS_RingBuffer@@$0A@UTListSLock@@@@QEAAXPEAVSOS_RingBuffer@@@Z; TList<SOS_Node,SOS_RingBuffer,0,TListSLock>::AppendElem(SOS_RingBuffer *)
0x1023ab742  test    byte ptr cs:dword_1033C2910, 1
0x1023ab749  jz      short loc_1023AB779
0x1023ab74b  call    cs:__imp_?InitImageHelper@@YAHXZ; InitImageHelper(void)
0x1023ab751  test    eax, eax
0x1023ab753  jnz     short loc_1023AB779
0x1023ab755  lea     rdx, aImageHelperIni; "Image Helper initialization"
0x1023ab75c  mov     ecx, 42F2h; unsigned int
0x1023ab761  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x1023ab766  xor     edx, edx
0x1023ab768  mov     ecx, 8Ah
0x1023ab76d  mov     r8d, 8007000Eh
0x1023ab773  call    cs:__imp_?SQLExit@@YAXW4SQLEXITCODE@@KK@Z; SQLExit(SQLEXITCODE,ulong,ulong)
0x1023ab779  test    byte ptr cs:dword_1033C2910, 2
  ... truncated ...
```
