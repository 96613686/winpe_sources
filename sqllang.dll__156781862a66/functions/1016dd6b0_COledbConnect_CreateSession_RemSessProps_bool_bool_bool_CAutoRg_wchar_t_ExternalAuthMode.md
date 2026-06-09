# COledbConnect::CreateSession(RemSessProps &,bool,bool,bool,CAutoRg<wchar_t> &,ExternalAuthMode)

- ea: `0x1016dd6b0`
- end: `0x1016df6a9`
- name: `?CreateSession@COledbConnect@@AEBAPEAVCRemSess@@AEAURemSessProps@@_N11AEAV?$CAutoRg@_W@@W4ExternalAuthMode@@@Z`
- size: `8185`
- prototype: ``
- caller_count: `1`
- callee_count: `36`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1016dc000`

## callees

- `0x100401070`
- `0x100401090`
- `0x100401433`
- `0x100403080`
- `0x1004132a0`
- `0x100430960`
- `0x100430d60`
- `0x10057ada0`
- `0x10058c1a0`
- `0x100860500`
- `0x100a1c790`
- `0x100d08fa0`
- `0x100d09430`
- `0x100d0a730`
- `0x10139bbf0`
- `0x1015670a0`
- `0x1015696e0`
- `0x10156ae10`
- `0x1016c8390`
- `0x1016c9c80`
- `0x1016d8890`
- `0x1016dd280`
- `0x1016dd4e0`
- `0x1016dd6b0`
- `0x1016df6b0`
- `0x1016dfb80`
- `0x1016e69f0`
- `0x1016e6a80`
- `0x1016e8c10`
- `0x1016e9330`
- `0x1016ea1c0`
- `0x101e5a890`
- `0x101e5a920`
- `0x101e5ab80`
- `0x101e5ad30`
- `0x101e5b830`

## import_xrefs

- `Secur32!LsaFreeReturnBuffer` at `0x1016df647`
- `Secur32!LsaFreeReturnBuffer` at `0x1016df647`
- `Secur32!LsaDeregisterLogonProcess` at `0x1016df65e`
- `Secur32!LsaDeregisterLogonProcess` at `0x1016df65e`
- `KERNEL32!CloseHandle` at `0x1016df631`
- `KERNEL32!CloseHandle` at `0x1016df631`
- `ole32!CoCreateInstanceEx` at `0x1016de1ed`
- `ole32!CoCreateInstanceEx` at `0x1016de1ed`
- `OLEAUT32!__imp_SysFreeString` at `0x1016df13a`
- `OLEAUT32!__imp_SysFreeString` at `0x1016df13a`
- `OLEAUT32!__imp_VariantInit` at `0x1016df3d6`
- `OLEAUT32!__imp_VariantInit` at `0x1016df3d6`
- `OLEAUT32!__imp_VariantClear` at `0x1016de7a7`
- `OLEAUT32!__imp_VariantClear` at `0x1016de7a7`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x1016dd77c`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x1016de981`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x1016dda03`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x1016ddba0`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x1016ddd13`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x1016dda03`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x1016ddba0`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x1016ddd13`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1016dde4c`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1016de088`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1016de2c0`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1016dde4c`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1016de088`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1016de2c0`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016dd776`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016dd7d3`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016dd8c7`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016dd9b6`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016ddbf3`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016de138`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016de5ac`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016de734`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016de76e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016de7d8`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016de87e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016de941`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016dea97`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016deb1e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016decdd`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016dedea`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016dee23`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016df0c0`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016df175`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016df2cb`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016df305`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016df4c2`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016df4fc`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016dd776`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016dd7d3`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016dd8c7`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016dd9b6`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016ddbf3`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016de138`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016de5ac`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016de734`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016de76e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016de7d8`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016de87e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016de941`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016dea97`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016deb1e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016decdd`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016dedea`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016dee23`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016df0c0`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016df175`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016df2cb`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016df305`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016df4c2`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016df4fc`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1016ddb86`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1016ddcf9`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1016ddb86`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1016ddcf9`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x1016dddd1`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x1016dddea`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x1016de00d`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x1016de026`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x1016de245`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x1016de25e`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x1016dddd1`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x1016dddea`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x1016de00d`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x1016de026`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x1016de245`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x1016de25e`
- `sqldk!?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z` at `0x1016dde12`
- `sqldk!?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z` at `0x1016de04e`
- `sqldk!?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z` at `0x1016de286`
- `sqldk!?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z` at `0x1016dde12`
- `sqldk!?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z` at `0x1016de04e`
- `sqldk!?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z` at `0x1016de286`
- `sqldk!SystemThread_TlsIndex` at `0x1016ddb29`
- `sqldk!SystemThread_TlsIndex` at `0x1016ddc9c`
- `sqldk!SystemThread_TlsIndex` at `0x1016ddd9b`
- `sqldk!SystemThread_TlsIndex` at `0x1016ddfd5`
- `sqldk!SystemThread_TlsIndex` at `0x1016de20d`
- `sqldk!SystemThread_TlsIndex` at `0x1016de80d`
- `sqldk!SystemThread_TlsIndex` at `0x1016de8c2`
- `sqldk!SystemThread_TlsIndex` at `0x1016de950`
- `sqldk!SystemThread_TlsIndex` at `0x1016de9dd`
- `sqldk!SystemThread_TlsIndex` at `0x1016debff`
- `sqldk!SystemThread_TlsIndex` at `0x1016def20`
- `sqldk!SystemThread_TlsIndex` at `0x1016def88`
- `sqldk!SystemThread_TlsIndex` at `0x1016df5e5`
- `sqldk!SystemThread_TlsOffset` at `0x1016ddb32`
- `sqldk!SystemThread_TlsOffset` at `0x1016ddca5`
- `sqldk!SystemThread_TlsOffset` at `0x1016ddda4`
- `sqldk!SystemThread_TlsOffset` at `0x1016ddfde`
- `sqldk!SystemThread_TlsOffset` at `0x1016de216`
- `sqldk!SystemThread_TlsOffset` at `0x1016de816`
- `sqldk!SystemThread_TlsOffset` at `0x1016de8cb`
- `sqldk!SystemThread_TlsOffset` at `0x1016de959`
- `sqldk!SystemThread_TlsOffset` at `0x1016de9e6`
- `sqldk!SystemThread_TlsOffset` at `0x1016dec08`
- `sqldk!SystemThread_TlsOffset` at `0x1016def29`
- `sqldk!SystemThread_TlsOffset` at `0x1016def91`
- `sqldk!SystemThread_TlsOffset` at `0x1016df5ee`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016ddb4b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016ddcbe`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016dddbd`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016ddff9`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016de231`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016de831`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016de8e4`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016de974`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016de9ff`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016dec21`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016def42`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016defaa`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016ddb4b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016ddcbe`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016dddbd`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016ddff9`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016de231`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016de831`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016de8e4`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016de974`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016de9ff`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016dec21`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016def42`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016defaa`
- `sqldk!?GetDefaultMemoryClerksForNode@PerProcessGlobals@@QEAAPEAPEAVMemoryClerk@@G@Z` at `0x1016ddde1`
- `sqldk!?GetDefaultMemoryClerksForNode@PerProcessGlobals@@QEAAPEAPEAVMemoryClerk@@G@Z` at `0x1016de01d`
- `sqldk!?GetDefaultMemoryClerksForNode@PerProcessGlobals@@QEAAPEAPEAVMemoryClerk@@G@Z` at `0x1016de255`
- `sqldk!?GetDefaultMemoryClerksForNode@PerProcessGlobals@@QEAAPEAPEAVMemoryClerk@@G@Z` at `0x1016ddde1`
- `sqldk!?GetDefaultMemoryClerksForNode@PerProcessGlobals@@QEAAPEAPEAVMemoryClerk@@G@Z` at `0x1016de01d`
- `sqldk!?GetDefaultMemoryClerksForNode@PerProcessGlobals@@QEAAPEAPEAVMemoryClerk@@G@Z` at `0x1016de255`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016ddb96`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016ddd09`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016ddedc`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016de5b5`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016de77c`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016debac`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016debb6`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016debc0`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016deceb`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016decf6`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016dee31`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016df180`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016df313`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016df50a`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016df5bf`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016ddb96`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016ddd09`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016ddedc`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016de5b5`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016de77c`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016debac`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016debb6`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016debc0`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016deceb`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016decf6`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016dee31`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016df180`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016df313`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016df50a`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016df5bf`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x1016dda9c`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x1016ddac8`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x1016dda9c`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x1016ddac8`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x1016dee60`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x1016dee60`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp_l` at `0x1016dda1c`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp_l` at `0x1016dda1c`
- `api-ms-win-crt-time-l1-1-0!_mktime64` at `0x1016deb9c`
- `api-ms-win-crt-time-l1-1-0!_mktime64` at `0x1016deb9c`
- `sqlmin!?FUseReplicatedServerContext@@YA_NXZ` at `0x1016dd7f3`
- `sqlmin!?FUseReplicatedServerContext@@YA_NXZ` at `0x1016dd7f3`
- `sqlmin!?TaskFree@@YAXPEAX@Z` at `0x1016de68b`
- `sqlmin!?TaskFree@@YAXPEAX@Z` at `0x1016de698`
- `sqlmin!?TaskFree@@YAXPEAX@Z` at `0x1016de7b4`
- `sqlmin!?TaskFree@@YAXPEAX@Z` at `0x1016de7be`
- `sqlmin!?TaskFree@@YAXPEAX@Z` at `0x1016df14d`
- `sqlmin!?TaskFree@@YAXPEAX@Z` at `0x1016de68b`

## string_xrefs

- `0x1016de9a6`: `ServicePrincipalName`
- `0x1016decb2`: `ServicePrincipalName`
- `0x1016ddc01`: `;OLE DB Services=-5`

## pseudocode

```c
// Hidden C++ exception states: #wind=31
struct CRemSess *__fastcall COledbConnect::CreateSession(
        __int64 a1,
        __int64 a2,
        char a3,
        char a4,
        char a5,
        __int64 *a6,
        int a7)
{
  char v8; // r13
  int v11; // r12d
  __int64 v12; // rax
  BOOL v13; // edx
  int v14; // r14d
  BOOL v15; // ebx
  const wchar_t *v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rax
  struct CRemSess *result; // rax
  __int64 v20; // rax
  bool v21; // cl
  bool v22; // al
  bool v23; // bl
  __int64 v24; // rbx
  __int64 v25; // rax
  unsigned int v26; // r14d
  COledbConnect *v27; // rcx
  const wchar_t *v28; // rbx
  __crt_locale_pointers *v29; // rax
  struct IDataInitialize *Service; // r13
  __int64 v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // rax
  int v34; // edi
  __int64 v35; // rbx
  __int64 v36; // rcx
  unsigned __int64 v37; // rdi
  unsigned __int64 v38; // rax
  wchar_t *v39; // rbx
  struct __crt_locale_pointers *v40; // rax
  __int64 v41; // r8
  __int64 v42; // rdx
  __int64 v43; // rcx
  __int64 v44; // rax
  int v45; // edi
  __int64 v46; // rbx
  __int64 v47; // rcx
  unsigned __int64 v48; // rdi
  unsigned __int64 v49; // rax
  struct __crt_locale_pointers *DefaultLocale; // rax
  _QWORD *ThreadLocalStoragePointer; // r8
  __int64 v52; // rdx
  __int64 v53; // rbx
  __int64 v54; // rcx
  __int64 v55; // rbx
  PerProcessGlobals *ClientProcessGlobals; // rax
  struct MemoryClerk **DefaultMemoryClerksForNode; // rbx
  __int64 v58; // rdx
  __int64 v59; // rcx
  __int64 v60; // r8
  __int64 v61; // r8
  __int64 v62; // rcx
  struct IMemObj *MemObject; // r15
  struct IUnknown *v64; // r14
  __int128 v65; // xmm6
  bool v66; // di
  __int64 v67; // rbx
  __int64 v68; // rax
  __int64 *v69; // rcx
  __int64 v70; // r8
  _QWORD *v71; // rdx
  __int64 v72; // rcx
  __int64 v73; // rbx
  __int64 v74; // rax
  __int64 v75; // rbx
  PerProcessGlobals *v76; // rax
  struct MemoryClerk **v77; // rbx
  __int64 v78; // rdx
  __int64 v79; // rcx
  __int64 v80; // r8
  __int64 v81; // r8
  __int64 v82; // rcx
  struct IMemObj *v83; // r15
  struct IUnknown *v84; // r14
  __int128 v85; // xmm6
  bool v86; // di
  __int64 v87; // rbx
  __int64 v88; // rax
  __int64 v89; // rax
  struct IDataInitialize *v90; // rbx
  struct IDataInitialize *v91; // rax
  HRESULT v92; // eax
  __int64 v93; // r8
  _QWORD *v94; // rdx
  __int64 v95; // rcx
  __int64 v96; // rbx
  __int64 v97; // rax
  __int64 v98; // rbx
  PerProcessGlobals *v99; // rax
  struct MemoryClerk **v100; // rbx
  __int64 v101; // rdx
  __int64 v102; // rcx
  __int64 v103; // r8
  __int64 v104; // r8
  __int64 v105; // rcx
  struct IMemObj *v106; // r15
  struct IUnknown *v107; // r14
  __int128 v108; // xmm6
  bool v109; // di
  __int64 v110; // rbx
  __int64 v111; // rax
  int v112; // r13d
  __int64 v113; // rax
  char *v114; // rdx
  __int64 v115; // rcx
  int v116; // ecx
  char **v117; // rax
  __int64 v118; // rax
  char *v119; // rdx
  __int64 v120; // rcx
  int v121; // ecx
  char **v122; // rax
  char **v123; // rcx
  __int64 v124; // rbx
  __int64 v125; // rax
  struct IUnknown *Interface; // rax
  struct IUnknown *v127; // r12
  int v128; // edi
  void **v129; // rdx
  __int64 v130; // rbx
  __int64 v131; // rax
  VARIANTARG *v132; // rcx
  int v133; // ebx
  __int64 v134; // r14
  __int64 v135; // rbx
  __int64 v136; // rdx
  __int64 v137; // rbx
  __int64 v138; // rcx
  __int64 v139; // rbx
  __int64 v140; // r9
  char v141; // al
  void *v142; // r15
  __int64 v143; // rbx
  __int64 v144; // rcx
  void *v145; // rdi
  int AccessTokenForApplicationUsingSecret; // eax
  _BYTE *v147; // rbx
  __int64 v148; // rdx
  _WORD *v149; // rcx
  __int16 v150; // ax
  int v151; // eax
  __int64 v152; // rbx
  __int64 v153; // rcx
  char v154; // dl
  int v155; // edi
  __int64 v156; // rbx
  __int64 v157; // rax
  const wchar_t *v158; // r8
  struct IUnknown *v159; // r15
  __int64 v160; // rbx
  __int64 v161; // rcx
  int v162; // edi
  __int64 v163; // rbx
  __int64 v164; // rcx
  int v165; // r14d
  __int64 v166; // rcx
  __int64 v167; // rbx
  __int64 v168; // rax
  char v169; // al
  struct tagDBPROP *v170; // r14
  __int64 v171; // rdi
  BSTR *p_bstrVal; // rbx
  struct IUnknown *v173; // rbx
  struct IUnknown *v174; // rdi
  int v175; // r14d
  __int64 v176; // rbx
  __int64 v177; // rax
  __int64 v178; // r8
  __int64 v179; // rdx
  struct IUnknown *v180; // rdi
  int v181; // r14d
  __int64 v182; // rbx
  __int64 v183; // rax
  bool v184; // r9
  struct CRemSess *Session; // rbx
  signed __int32 v186[8]; // [rsp+0h] [rbp-120h] BYREF
  DWORD dwCount[2]; // [rsp+20h] [rbp-100h]
  MULTI_QI *pResults; // [rsp+28h] [rbp-F8h]
  char v189[8]; // [rsp+30h] [rbp-F0h]
  __int64 v190; // [rsp+38h] [rbp-E8h]
  GUID *rguid; // [rsp+40h] [rbp-E0h]
  char v192[8]; // [rsp+48h] [rbp-D8h]
  __int64 v193; // [rsp+50h] [rbp-D0h]
  bool v194; // [rsp+A0h] [rbp-80h]
  char v195; // [rsp+A1h] [rbp-7Fh]
  int v196; // [rsp+A4h] [rbp-7Ch] BYREF
  int v197; // [rsp+A8h] [rbp-78h] BYREF
  int v198; // [rsp+ACh] [rbp-74h] BYREF
  struct IUnknown *v199; // [rsp+B0h] [rbp-70h]
  __int64 v200; // [rsp+B8h] [rbp-68h] BYREF
  void **v201; // [rsp+C0h] [rbp-60h] BYREF
  struct IUnknown *v202; // [rsp+C8h] [rbp-58h] BYREF
  __int64 v203; // [rsp+D0h] [rbp-50h] BYREF
  struct RemSessProps *v204; // [rsp+D8h] [rbp-48h]
  wchar_t *Source; // [rsp+E0h] [rbp-40h] BYREF
  int v206; // [rsp+E8h] [rbp-38h] BYREF
  int v207; // [rsp+ECh] [rbp-34h] BYREF
  __int64 v208; // [rsp+F0h] [rbp-30h] BYREF
  unsigned int v209; // [rsp+F8h] [rbp-28h] BYREF
  void *v210; // [rsp+100h] [rbp-20h]
  __int64 v211; // [rsp+108h] [rbp-18h] BYREF
  __int64 v212; // [rsp+110h] [rbp-10h] BYREF
  wchar_t *v213; // [rsp+118h] [rbp-8h]
  __int64 v214; // [rsp+120h] [rbp+0h] BYREF
  struct IDataInitialize *v215; // [rsp+128h] [rbp+8h]
  _BYTE *v216; // [rsp+130h] [rbp+10h] BYREF
  __int64 *v217; // [rsp+138h] [rbp+18h]
  void *v218; // [rsp+140h] [rbp+20h]
  __int64 v219; // [rsp+148h] [rbp+28h] BYREF
  __int64 v220; // [rsp+150h] [rbp+30h] BYREF
  struct IUnknown *v221; // [rsp+158h] [rbp+38h]
  struct IUnknown *v222; // [rsp+160h] [rbp+40h]
  struct IUnknown *v223; // [rsp+168h] [rbp+48h]
  _QWORD v224[2]; // [rsp+170h] [rbp+50h] BYREF
  int v225; // [rsp+180h] [rbp+60h]
  __int64 v226; // [rsp+188h] [rbp+68h]
  __int64 v227; // [rsp+190h] [rbp+70h]
  void *v228; // [rsp+198h] [rbp+78h]
  __int64 v229; // [rsp+1A0h] [rbp+80h]
  int v230; // [rsp+1A8h] [rbp+88h]
  int v231; // [rsp+1ACh] [rbp+8Ch]
  __int64 v232; // [rsp+1B0h] [rbp+90h]
  int v233; // [rsp+1B8h] [rbp+98h]
  char v234; // [rsp+1BCh] [rbp+9Ch]
  MULTI_QI v235; // [rsp+1C0h] [rbp+A0h] BYREF
  _QWORD v236[2]; // [rsp+1E0h] [rbp+C0h] BYREF
  int v237; // [rsp+1F0h] [rbp+D0h]
  __int64 v238; // [rsp+1F8h] [rbp+D8h]
  __int64 v239; // [rsp+200h] [rbp+E0h]
  void *v240; // [rsp+208h] [rbp+E8h]
  __int64 v241; // [rsp+210h] [rbp+F0h]
  int v242; // [rsp+218h] [rbp+F8h]
  int v243; // [rsp+21Ch] [rbp+FCh]
  __int64 v244; // [rsp+220h] [rbp+100h]
  int v245; // [rsp+228h] [rbp+108h]
  char v246; // [rsp+22Ch] [rbp+10Ch]
  char v247[8]; // [rsp+230h] [rbp+110h] BYREF
  void *v248; // [rsp+238h] [rbp+118h] BYREF
  struct tagDBPROP *v249; // [rsp+240h] [rbp+120h] BYREF
  struct IUnknown *v250; // [rsp+248h] [rbp+128h]
  _QWORD v251[2]; // [rsp+250h] [rbp+130h] BYREF
  int v252; // [rsp+260h] [rbp+140h]
  __int64 v253; // [rsp+268h] [rbp+148h]
  __int64 v254; // [rsp+270h] [rbp+150h]
  void *v255; // [rsp+278h] [rbp+158h]
  __int64 v256; // [rsp+280h] [rbp+160h]
  int v257; // [rsp+288h] [rbp+168h]
  int v258; // [rsp+28Ch] [rbp+16Ch]
  __int64 v259; // [rsp+290h] [rbp+170h]
  int v260; // [rsp+298h] [rbp+178h]
  char v261; // [rsp+29Ch] [rbp+17Ch]
  _QWORD v262[2]; // [rsp+2A0h] [rbp+180h] BYREF
  int v263; // [rsp+2B0h] [rbp+190h]
  __int64 v264; // [rsp+2B8h] [rbp+198h]
  __int64 v265; // [rsp+2C0h] [rbp+1A0h]
  void *v266; // [rsp+2C8h] [rbp+1A8h]
  __int64 v267; // [rsp+2D0h] [rbp+1B0h]
  int v268; // [rsp+2D8h] [rbp+1B8h]
  int v269; // [rsp+2DCh] [rbp+1BCh]
  __int64 v270; // [rsp+2E0h] [rbp+1C0h]
  int v271; // [rsp+2E8h] [rbp+1C8h]
  char v272; // [rsp+2ECh] [rbp+1CCh]
  _QWORD v273[2]; // [rsp+2F0h] [rbp+1D0h] BYREF
  int v274; // [rsp+300h] [rbp+1E0h]
  __int64 v275; // [rsp+308h] [rbp+1E8h]
  __int64 v276; // [rsp+310h] [rbp+1F0h]
  void *v277; // [rsp+318h] [rbp+1F8h]
  __int64 v278; // [rsp+320h] [rbp+200h]
  int v279; // [rsp+328h] [rbp+208h]
  int v280; // [rsp+32Ch] [rbp+20Ch]
  __int64 v281; // [rsp+330h] [rbp+210h]
  int v282; // [rsp+338h] [rbp+218h]
  char v283; // [rsp+33Ch] [rbp+21Ch]
  __int64 v284; // [rsp+340h] [rbp+220h]
  GUID *v285; // [rsp+348h] [rbp+228h]
  int v286; // [rsp+350h] [rbp+230h]
  __int64 v287; // [rsp+358h] [rbp+238h]
  __int64 v288; // [rsp+360h] [rbp+240h]
  __int64 v289; // [rsp+368h] [rbp+248h]
  __int64 v290; // [rsp+370h] [rbp+250h]
  int v291; // [rsp+378h] [rbp+258h]
  int v292; // [rsp+37Ch] [rbp+25Ch]
  __int64 v293; // [rsp+380h] [rbp+260h]
  int v294; // [rsp+388h] [rbp+268h]
  char v295; // [rsp+38Ch] [rbp+26Ch]
  __int64 v296; // [rsp+390h] [rbp+270h]
  void *v297; // [rsp+398h] [rbp+278h]
  __int128 v298; // [rsp+3A0h] [rbp+280h] BYREF
  __int128 v299; // [rsp+3B0h] [rbp+290h] BYREF
  __int128 v300; // [rsp+3C0h] [rbp+2A0h] BYREF
  GUID v301; // [rsp+3D0h] [rbp+2B0h] BYREF
  __int64 v302[2]; // [rsp+3E0h] [rbp+2C0h] BYREF
  char v303[8]; // [rsp+3F0h] [rbp+2D0h] BYREF
  int v304; // [rsp+3F8h] [rbp+2D8h]
  int v305; // [rsp+400h] [rbp+2E0h]
  char **v306; // [rsp+408h] [rbp+2E8h]
  char *v307; // [rsp+410h] [rbp+2F0h]
  __int64 v308; // [rsp+418h] [rbp+2F8h]
  char *v309; // [rsp+420h] [rbp+300h] BYREF
  int v310; // [rsp+428h] [rbp+308h]
  int v311; // [rsp+42Ch] [rbp+30Ch]
  __int64 v312; // [rsp+430h] [rbp+310h]
  int v313; // [rsp+438h] [rbp+318h]
  int v314; // [rsp+43Ch] [rbp+31Ch]
  __int64 v315; // [rsp+440h] [rbp+320h]
  int v316; // [rsp+448h] [rbp+328h]
  int v317; // [rsp+44Ch] [rbp+32Ch]
  GUID *v318; // [rsp+450h] [rbp+330h]
  int v319; // [rsp+458h] [rbp+338h]
  int v320; // [rsp+45Ch] [rbp+33Ch]
  char v321; // [rsp+460h] [rbp+340h] BYREF
  __int64 v322; // [rsp+640h] [rbp+520h]
  __int64 v323; // [rsp+648h] [rbp+528h]
  char v324; // [rsp+650h] [rbp+530h] BYREF
  __int16 v325; // [rsp+651h] [rbp+531h]
  char v326; // [rsp+653h] [rbp+533h]
  int v327; // [rsp+654h] [rbp+534h]
  int *v328; // [rsp+670h] [rbp+550h] BYREF
  int v329; // [rsp+678h] [rbp+558h]
  GUID v330; // [rsp+67Ch] [rbp+55Ch]
  struct tm Tm; // [rsp+690h] [rbp+570h] BYREF
  unsigned __int64 v332; // [rsp+6B8h] [rbp+598h] BYREF
  unsigned __int16 v333; // [rsp+6C0h] [rbp+5A0h]
  unsigned __int16 v334; // [rsp+6C2h] [rbp+5A2h]
  unsigned __int16 v335; // [rsp+6C4h] [rbp+5A4h]
  GUID v336; // [rsp+6C8h] [rbp+5A8h] BYREF
  SOS_ExternalAutoWait *v337[2]; // [rsp+6E0h] [rbp+5C0h]
  int v338; // [rsp+6F0h] [rbp+5D0h] BYREF
  __int64 v339; // [rsp+6F8h] [rbp+5D8h]
  __int64 v340; // [rsp+700h] [rbp+5E0h]
  __int64 v341; // [rsp+708h] [rbp+5E8h]
  __int64 v342; // [rsp+710h] [rbp+5F0h]
  char v343[56]; // [rsp+718h] [rbp+5F8h] BYREF
  __int64 v344; // [rsp+750h] [rbp+630h] BYREF
  HANDLE hObject; // [rsp+760h] [rbp+640h] BYREF
  int v346; // [rsp+768h] [rbp+648h]
  PVOID Buffer; // [rsp+770h] [rbp+650h]
  __int64 v348; // [rsp+778h] [rbp+658h]
  int v349; // [rsp+780h] [rbp+660h]
  HANDLE LsaHandle; // [rsp+788h] [rbp+668h]
  int v351; // [rsp+AE8h] [rbp+9C8h]
  char v352; // [rsp+AECh] [rbp+9CCh]
  bool v353; // [rsp+AEDh] [rbp+9CDh]
  bool v354; // [rsp+AEEh] [rbp+9CEh]
  __int64 v355; // [rsp+AF0h] [rbp+9D0h] BYREF
  int v356; // [rsp+AF8h] [rbp+9D8h]
  DBID v357; // [rsp+B00h] [rbp+9E0h]
  VARIANTARG pvarg; // [rsp+B20h] [rbp+A00h] BYREF
  __int64 *v359; // [rsp+B40h] [rbp+A20h] BYREF
  int v360; // [rsp+B48h] [rbp+A28h]
  GUID v361; // [rsp+B4Ch] [rbp+A2Ch]
  __int128 v362; // [rsp+B60h] [rbp+A40h] BYREF
  int v363; // [rsp+B70h] [rbp+A50h]
  wchar_t v364; // [rsp+B74h] [rbp+A54h]
  _OWORD v365[2]; // [rsp+B78h] [rbp+A58h] BYREF
  __int64 v366; // [rsp+B98h] [rbp+A78h]
  _WORD v367[2048]; // [rsp+BA0h] [rbp+A80h] BYREF
  wchar_t Destination[4008]; // [rsp+1BA0h] [rbp+1A80h] BYREF
  wchar_t v369[4008]; // [rsp+3AF0h] [rbp+39D0h] BYREF

  v296 = -2;
  v8 = a3;
  v195 = a3;
  v204 = (struct RemSessProps *)a2;
  v217 = a6;
  v11 = 0;
  HIDWORD(v208) = 0;
  memset_0(Destination, 0, 0x1F42u);
  if ( g_statCOM != 1 && g_statCOM != 3 )
    FInitDCOM();
  _InterlockedOr(v186, 0);
  if ( g_statCOM != 1 )
    ex_raise(74, 4, 16, 1);
  if ( *((_DWORD *)s_pServerConf + 3) == 1 )
  {
    v190 = *(_QWORD *)(qword_102ECFB00 + 11728);
    *(_DWORD *)v189 = *(_DWORD *)(qword_102ECFB00 + 11736);
    ex_raise(5, 34, 16, 1, 94, L"Distributed Query or Remote Procedure Execution", *(_QWORD *)v189, v190);
  }
  if ( *(_BYTE *)(a1 + 141)
    && CPolybaseFeatureManager::IsPolybaseProvisioned((CPolybaseFeatureManager *)g_PolybaseFeatureManager, 1)
    && (FUseReplicatedServerContext() ? (v12 = qword_102ECFB00 + 28520) : (v12 = qword_102ECFB00 + 14864),
        *(_BYTE *)(v12 + 13645)) )
  {
    v14 = a7;
  }
  else
  {
    v13 = *(_QWORD *)&CLSID_MSOLEDBSQL.Data1 == *(_QWORD *)(a1 + 16)
       && *(_QWORD *)CLSID_MSOLEDBSQL.Data4 == *(_QWORD *)(a1 + 24)
       || *(_QWORD *)(a1 + 16) == 0x45EB837A726D00DELL && *(_QWORD *)(a1 + 24) == 0x9C07F941D2ED8CAEuLL;
    v14 = a7;
    if ( !v8 && !a4 && !a7 )
    {
      v15 = 1;
      v16 = *(const wchar_t **)(a1 + 32);
      if ( v16 )
        v15 = FValidateOpenDatasourceString(v16, v13) != 0;
      if ( *(_DWORD *)(a1 + 80) != -1 )
      {
        v17 = *(_QWORD *)(a2 + 32);
        if ( !v17 )
          goto LABEL_31;
        v18 = -1;
        do
          ++v18;
        while ( *(_WORD *)(v17 + 2 * v18) );
        if ( !(_DWORD)v18 )
          goto LABEL_31;
      }
      if ( !v15 )
      {
LABEL_31:
        v11 = -2147467259;
        ex_raise(74, 16, 16, 2);
      }
    }
  }
  result = CRemSess::FindSession((const struct RemSessProps *)a2, (struct COledbConnect *)a1);
  if ( !result )
  {
    v202 = 0;
    v20 = *(unsigned __int8 *)(a2 + 8);
    v21 = (v20 & 2) != 0 || v14;
    v22 = (v20 & 1) != 0 || v8 && *(_DWORD *)(a1 + 80) == -1;
    hObject = (HANDLE)-1LL;
    v346 = 0;
    Buffer = 0;
    v348 = 0;
    v349 = 0;
    LsaHandle = (HANDLE)-1LL;
    v351 = 0;
    v352 = 0;
    v353 = v22;
    v354 = v21;
    v23 = CSECAutoImpersonateForDQ::Impersonate((CSECAutoImpersonateForDQ *)&hObject);
    v194 = v23;
    if ( !v23 && v8 && (*(_BYTE *)(a2 + 8) & 1) != 0 )
    {
      v24 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 24LL))(a1);
      v25 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 40LL))(a1);
      ex_raise(74, 13, 16, 2, v25, v24);
      v23 = v194;
    }
    v26 = 20;
    if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a1 + 56LL))(a1) )
      v26 = 23;
    v27 = 0;
    v199 = 0;
    if ( (*(_BYTE *)(a2 + 8) & 0x40) != 0 )
    {
      if ( v8 && v23 || a4 || (v28 = *(const wchar_t **)(a1 + 32), !*v28) )
      {
LABEL_56:
        v210 = 0;
        Service = COledbConnect::PdatiniGetService(v27, 1, v26);
        v210 = Service;
        v213 = 0;
        v362 = *(_OWORD *)L";PROVIDER=";
        v363 = *(_DWORD *)L"R=";
        v364 = aProvider_1[10];
        if ( CompareStringWEnglishNoCase(1u, 0, *(const wchar_t **)(a1 + 8), -1, L"MSOLEDBSQL", -1) == 2
          || CompareStringWEnglishNoCase(1u, 0, *(const wchar_t **)(a1 + 8), -1, L"MSOLEDBSQL", -1) == 2 )
        {
          v365[0] = *(_OWORD *)L";OLE DB Services=-5";
          v365[1] = *(_OWORD *)L"Services=-5";
          v366 = *(_QWORD *)L"=-5";
          v41 = -1;
          do
            ++v41;
          while ( *(_WORD *)(*(_QWORD *)(a1 + 32) + 2 * v41) );
          v42 = -1;
          do
            ++v42;
          while ( *((_WORD *)&v362 + v42) );
          v43 = -1;
          do
            ++v43;
          while ( *(_WORD *)(*(_QWORD *)(a1 + 8) + 2 * v43) );
          v44 = -1;
          do
            ++v44;
          while ( *((_WORD *)v365 + v44) );
          v45 = v44 + v43 + v41 + v42;
          v46 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
          v47 = *(_QWORD *)(v46 + 256);
          if ( !v47 )
          {
            SystemThread::MakeMiniSOSThread(0);
            v47 = *(_QWORD *)(v46 + 256);
          }
          v48 = v45 + 1;
          v49 = 2 * v48;
          if ( !is_mul_ok(v48, 2u) )
            v49 = -1;
          v39 = (wchar_t *)operator new[](
                             v49,
                             *(struct IMemObj **)(v47 + 1000),
                             "sql\\ntdbms\\msql\\utils\\oledbconn.cpp",
                             3550,
                             3u);
          if ( v39 )
            operator delete[](0);
          v213 = v39;
          DefaultLocale = GetDefaultLocale();
          StringCchPrintf_lW(
            v39,
            v48,
            L"%s%s%s%s",
            DefaultLocale,
            *(_QWORD *)(a1 + 32),
            &v362,
            *(_QWORD *)(a1 + 8),
            v365);
        }
        else
        {
          v31 = -1;
          do
            ++v31;
          while ( *(_WORD *)(*(_QWORD *)(a1 + 32) + 2 * v31) );
          v32 = -1;
          do
            ++v32;
          while ( *((_WORD *)&v362 + v32) );
          v33 = -1;
          do
            ++v33;
          while ( *(_WORD *)(*(_QWORD *)(a1 + 8) + 2 * v33) );
          v34 = v33 + v32 + v31;
          v35 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
          v36 = *(_QWORD *)(v35 + 256);
          if ( !v36 )
          {
            SystemThread::MakeMiniSOSThread(0);
            v36 = *(_QWORD *)(v35 + 256);
          }
          v37 = v34 + 1;
          v38 = 2 * v37;
          if ( !is_mul_ok(v37, 2u) )
            v38 = -1;
          v39 = (wchar_t *)operator new[](
                             v38,
                             *(struct IMemObj **)(v36 + 1000),
                             "sql\\ntdbms\\msql\\utils\\oledbconn.cpp",
                             3561,
                             3u);
          if ( v39 )
            operator delete[](0);
          v213 = v39;
          v40 = GetDefaultLocale();
          StringCchPrintf_lW(v39, v37, L"%s%s%s", v40, *(_QWORD *)(a1 + 32), &v362, *(_QWORD *)(a1 + 8));
        }
        v212 = 0;
        v11 = ((__int64 (__fastcall *)(struct IDataInitialize *, _QWORD, __int64, wchar_t *, GUID *, __int64 *))Service->lpVtbl->GetDataSource)(
                Service,
                0,
                23,
                v39,
                &IID_IUnknown,
                &v212);
        if ( v212 )
        {
          ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
          v52 = SystemThread_TlsIndex;
          v53 = ThreadLocalStoragePointer[SystemThread_TlsIndex] + SystemThread_TlsOffset;
          v54 = *(_QWORD *)(v53 + 256);
          if ( !v54 )
          {
            SystemThread::MakeMiniSOSThread(0);
            v54 = *(_QWORD *)(v53 + 256);
          }
          v55 = *(_QWORD *)(v54 + 992);
          ClientProcessGlobals = (PerProcessGlobals *)SOS_OS::GetClientProcessGlobals(
                                                        v54,
                                                        v52,
                                                        ThreadLocalStoragePointer);
          DefaultMemoryClerksForNode = PerProcessGlobals::GetDefaultMemoryClerksForNode(
                                         ClientProcessGlobals,
                                         *(_WORD *)(v55 + 160));
          SOS_OS::GetClientProcessGlobals(v59, v58, v60);
          v61 = (__int64)*DefaultMemoryClerksForNode + 64;
          if ( !*DefaultMemoryClerksForNode )
            v61 = 0;
          LOWORD(dwCount[0]) = 128;
          MemObject = (struct IMemObj *)MemoryObjectFactory::CreateMemObject(103, 2, v61, 8, dwCount[0]);
          if ( !MemObject )
          {
            LOBYTE(v62) = 65;
            ex_raise_oom(v62);
          }
          Source = (wchar_t *)MemObject;
          v197 = 3581;
          v64 = (struct IUnknown *)operator new(0x60u, MemObject, "sql\\ntdbms\\msql\\utils\\oledbconn.cpp", 3581, 3u);
          v215 = (struct IDataInitialize *)v64;
          if ( v64 )
          {
            v65 = *(_OWORD *)(a1 + 16);
            v66 = COledbConnect::FSupportsUms((COledbConnect *)a1);
            v67 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 40LL))(a1);
            v68 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 24LL))(a1);
            v298 = v65;
            IWrapInterface<IDBCreateSession>::IWrapInterface<IDBCreateSession>(
              (_DWORD)v64,
              (_DWORD)MemObject,
              v212,
              (unsigned int)&v298,
              v68,
              v67,
              !v66);
            v64->lpVtbl = (struct IUnknownVtbl *)&CWrapIGetDataSource::`vftable';
            (*((void (__fastcall **)(struct IUnknownVtbl *))v64[3].lpVtbl->QueryInterface + 2))(v64[3].lpVtbl);
          }
          else
          {
            v64 = 0;
          }
          v199 = v64;
          v39 = v213;
        }
        operator delete[](v39);
        ((void (__fastcall *)(struct IDataInitialize *))Service->lpVtbl->Release)(Service);
        v8 = v195;
      }
      else
      {
        while ( 1 )
        {
          v29 = GetDefaultLocale();
          if ( !_wcsnicmp_l(v28, L"trusted_connection", 0x12u, v29) )
            break;
          if ( !*++v28 )
            goto LABEL_56;
        }
        v11 = -2147467259;
        ex_raise(74, 16, 16, 3);
      }
    }
    else if ( *(_QWORD *)&CLSID_MSOLEDBSQL.Data1 == *(_QWORD *)(a1 + 16)
           && *(_QWORD *)CLSID_MSOLEDBSQL.Data4 == *(_QWORD *)(a1 + 24)
           || *(_QWORD *)(a1 + 16) == 0x45EB837A726D00DELL && *(_QWORD *)(a1 + 24) == 0x9C07F941D2ED8CAEuLL )
    {
      if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a1 + 56LL))(a1) )
      {
        if ( *(_QWORD *)&CLSID_MSOLEDBSQL.Data1 == *(_QWORD *)(a1 + 16)
          && *(_QWORD *)CLSID_MSOLEDBSQL.Data4 == *(_QWORD *)(a1 + 24)
          || *(_QWORD *)(a1 + 16) != 0x45EB837A726D00DELL
          || *(_QWORD *)(a1 + 24) != 0x9C07F941D2ED8CAEuLL )
        {
          v69 = (__int64 *)&g_clsfacLuxor;
          v11 = (int)g_hrLuxorFactory;
        }
        else
        {
          v11 = dword_103082150;
          v69 = &qword_103082140;
        }
        if ( v11 >= 0 )
        {
          v214 = 0;
          v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, __int64 *))(*(_QWORD *)*v69 + 24LL))(
                  *v69,
                  0,
                  &IID_IDBInitialize,
                  &v214);
          if ( v214 )
          {
            v71 = NtCurrentTeb()->ThreadLocalStoragePointer;
            v72 = SystemThread_TlsIndex;
            v73 = v71[SystemThread_TlsIndex] + SystemThread_TlsOffset;
            v74 = *(_QWORD *)(v73 + 256);
            if ( !v74 )
            {
              SystemThread::MakeMiniSOSThread(0);
              v74 = *(_QWORD *)(v73 + 256);
            }
            v75 = *(_QWORD *)(v74 + 992);
            v76 = (PerProcessGlobals *)SOS_OS::GetClientProcessGlobals(v72, v71, v70);
            v77 = PerProcessGlobals::GetDefaultMemoryClerksForNode(v76, *(_WORD *)(v75 + 160));
            SOS_OS::GetClientProcessGlobals(v79, v78, v80);
            v81 = (__int64)*v77 + 64;
            if ( !*v77 )
              v81 = 0;
            LOWORD(dwCount[0]) = 128;
            v83 = (struct IMemObj *)MemoryObjectFactory::CreateMemObject(104, 2, v81, 8, dwCount[0]);
            if ( !v83 )
            {
              LOBYTE(v82) = 65;
              ex_raise_oom(v82);
            }
            Source = (wchar_t *)v83;
            v197 = 3617;
            v84 = (struct IUnknown *)operator new(0x60u, v83, "sql\\ntdbms\\msql\\utils\\oledbconn.cpp", 3617, 3u);
            v210 = v84;
            if ( v84 )
            {
              v85 = *(_OWORD *)(a1 + 16);
              v86 = COledbConnect::FSupportsUms((COledbConnect *)a1);
              v87 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 40LL))(a1);
              v88 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 24LL))(a1);
              v299 = v85;
              IWrapInterface<ISchemaLock>::IWrapInterface<ISchemaLock>(
                (_DWORD)v84,
                (_DWORD)v83,
                v214,
                (unsigned int)&v299,
                v88,
                v87,
                !v86);
              v84->lpVtbl = (struct IUnknownVtbl *)&CWrapIDBInitialize::`vftable';
              (*((void (__fastcall **)(struct IUnknownVtbl *))v84[3].lpVtbl->QueryInterface + 2))(v84[3].lpVtbl);
            }
            else
            {
              v84 = 0;
            }
            v199 = v84;
          }
        }
      }
      else
      {
        v89 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 24LL))(a1);
        ex_raise(74, 30, 16, 3, v89);
      }
    }
    else
    {
      v336 = IID_IUnknown;
      v235.pIID = &v336;
      v235.pItf = 0;
      v235.hr = 0;
      v90 = 0;
      v215 = 0;
      if ( (*(_BYTE *)(a1 + 149) & 4) != 0
        && (v91 = COledbConnect::PdatiniGetService(0, 0, v26), v90 = v91, (v215 = v91) != 0) )
      {
        v92 = ((__int64 (__fastcall *)(struct IDataInitialize *, __int64, _QWORD, __int64, _QWORD, _QWORD, int, MULTI_QI *))v91->lpVtbl->CreateDBInstanceEx)(
                v91,
                a1 + 16,
                0,
                23,
                0,
                0,
                1,
                &v235);
      }
      else
      {
        v92 = CoCreateInstanceEx((const IID *const)(a1 + 16), 0, v26, 0, 1u, &v235);
      }
      v11 = v92;
      if ( v235.pItf )
      {
        v94 = NtCurrentTeb()->ThreadLocalStoragePointer;
        v95 = SystemThread_TlsIndex;
        v96 = v94[SystemThread_TlsIndex] + SystemThread_TlsOffset;
        v97 = *(_QWORD *)(v96 + 256);
        if ( !v97 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v97 = *(_QWORD *)(v96 + 256);
        }
        v98 = *(_QWORD *)(v97 + 992);
        v99 = (PerProcessGlobals *)SOS_OS::GetClientProcessGlobals(v95, v94, v93);
        v100 = PerProcessGlobals::GetDefaultMemoryClerksForNode(v99, *(_WORD *)(v98 + 160));
        SOS_OS::GetClientProcessGlobals(v102, v101, v103);
        v104 = (__int64)*v100 + 64;
        if ( !*v100 )
          v104 = 0;
        LOWORD(dwCount[0]) = 128;
        v106 = (struct IMemObj *)MemoryObjectFactory::CreateMemObject(104, 2, v104, 8, dwCount[0]);
        if ( !v106 )
        {
          LOBYTE(v105) = 65;
          ex_raise_oom(v105);
        }
        Source = (wchar_t *)v106;
        v197 = 3669;
        v107 = (struct IUnknown *)operator new(0x60u, v106, "sql\\ntdbms\\msql\\utils\\oledbconn.cpp", 3669, 3u);
        v210 = v107;
        if ( v107 )
        {
          v108 = *(_OWORD *)(a1 + 16);
          v109 = COledbConnect::FSupportsUms((COledbConnect *)a1);
          v110 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 40LL))(a1);
          v111 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 24LL))(a1);
          v300 = v108;
          IWrapInterface<ISchemaLock>::IWrapInterface<ISchemaLock>(
            (_DWORD)v107,
            (_DWORD)v106,
            v235.pItf,
            (unsigned int)&v300,
            v111,
            v110,
            !v109);
          v107->lpVtbl = (struct IUnknownVtbl *)&CWrapIDBInitialize::`vftable';
          (*((void (__fastcall **)(struct IUnknownVtbl *))v107[3].lpVtbl->QueryInterface + 2))(v107[3].lpVtbl);
        }
        else
        {
          v107 = 0;
        }
        v199 = v107;
        v90 = v215;
      }
      if ( v90 )
        ((void (__fastcall *)(struct IDataInitialize *))v90->lpVtbl->Release)(v90);
    }
    if ( (dword_102EDC9F8 & 0x10000) != 0 )
    {
      v304 = 0x40000;
      v305 = 0;
      v306 = &v309;
      v307 = &v321;
      v322 = 0;
      v308 = 0;
      v323 = 0;
      v309 = &v324;
      v310 = 32;
      v311 = 3;
      v312 = 0;
      v313 = 0;
      v314 = 4;
      v315 = 0;
      v316 = 0;
      v317 = 5;
      v318 = &Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
      v319 = 16;
      v320 = 6;
      v324 = v8;
      v112 = a7;
      v325 = a7;
      v326 = a5;
      v327 = v11;
      v113 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 40LL))(a1);
      v114 = (char *)v113;
      if ( v113 )
      {
        v115 = -1;
        do
          ++v115;
        while ( *(_WORD *)(v113 + 2 * v115) );
        v116 = 2 * v115;
      }
      else
      {
        v116 = 0;
      }
      v117 = v306;
      v306[2] = v114;
      *((_DWORD *)v117 + 6) = v116;
      *((_DWORD *)v117 + 7) = 4;
      v118 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 24LL))(a1);
      v119 = (char *)v118;
      if ( v118 )
      {
        v120 = -1;
        do
          ++v120;
        while ( *(_WORD *)(v118 + 2 * v120) );
        v121 = 2 * v120;
      }
      else
      {
        v121 = 0;
      }
      v122 = v306;
      v306[4] = v119;
      *((_DWORD *)v122 + 10) = v121;
      *((_DWORD *)v122 + 11) = 5;
      v123 = v306;
      v306[6] = (char *)(a1 + 16);
      *((_DWORD *)v123 + 14) = 16;
      *((_DWORD *)v123 + 15) = 6;
      XeSqlPkg::oledb_provider_initialized::Publish((XeSqlPkg::oledb_provider_initialized *)v303);
    }
    else
    {
      v112 = a7;
    }
    if ( v11 < 0 )
    {
      _mm_lfence();
      v124 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 40LL))(a1);
      v125 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 24LL))(a1);
      v284 = 0;
      v285 = &IID_IUnknown;
      v286 = 0;
      v287 = v125;
      v288 = v124;
      v289 = 0;
      v290 = 0;
      v291 = 0;
      v292 = -1;
      v293 = 0;
      v294 = 0;
      v295 &= ~1u;
      ex_raise(73, 2, 16, 1, v125, v124);
      operator delete[](0);
    }
    v222 = 0;
    Interface = COledbConnect::GetInterface((COledbConnect *)a1, &IID_IDBProperties, v199, &IID_IUnknown, 1);
    v127 = Interface;
    v222 = Interface;
    if ( (*((_BYTE *)v204 + 8) & 0x40) == 0 || v194 )
    {
LABEL_175:
      v134 = 0;
      v200 = 0;
      v198 = 0;
      v196 = 0;
      switch ( v112 )
      {
        case 1:
          if ( byte_102EDCD2D )
          {
            v135 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                 + SystemThread_TlsOffset;
            v136 = *(_QWORD *)(v135 + 256);
            if ( !v136 )
            {
              SystemThread::MakeMiniSOSThread(0);
              v136 = *(_QWORD *)(v135 + 256);
            }
            pResults = (MULTI_QI *)&v196;
            *(_QWORD *)dwCount = &v198;
            if ( (int)COledbConnect::ModifyAndResignToken(
                        a1,
                        *(_QWORD *)(v136 + 1000),
                        *v217,
                        (unsigned int)&v200,
                        (__int64)&v198,
                        (__int64)&v196) < 0 )
              ex_raise(74, 41, 16, 2);
            v134 = v200;
          }
          else
          {
            v134 = *v217;
          }
          break;
        case 4:
          v218 = 0;
          v216 = 0;
          v301 = Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
          v137 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
          v138 = *(_QWORD *)(v137 + 256);
          if ( !v138 )
          {
            SystemThread::MakeMiniSOSThread(0);
            v138 = *(_QWORD *)(v137 + 256);
          }
          if ( (unsigned int)JSONWebTokenService::GetTenantUri(*(struct IMemObj **)(v138 + 1000), 0, 0, 0, 0, &v301, 0) )
            ex_raise(74, 41, 16, 3);
          v139 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
          v140 = *(_QWORD *)(v139 + 256);
          if ( !v140 )
          {
            SystemThread::MakeMiniSOSThread(0);
            v140 = *(_QWORD *)(v139 + 256);
          }
          v141 = (*(__int64 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, _QWORD, void **, _QWORD))(*(_QWORD *)s_pServerConf + 528LL))(
                   s_pServerConf,
                   L"FederatedAuthentication",
                   L"ServicePrincipalName",
                   *(_QWORD *)(v140 + 1000),
                   &v248,
                   0);
          v142 = v248;
          if ( !v141 )
            v142 = 0;
          v297 = v142;
          v143 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
          v144 = *(_QWORD *)(v143 + 256);
          if ( !v144 )
          {
            SystemThread::MakeMiniSOSThread(0);
            v144 = *(_QWORD *)(v143 + 256);
          }
          v193 = (__int64)&v216;
          *(_QWORD *)v192 = &v332;
          rguid = (GUID *)&v196;
          v190 = (__int64)v247;
          *(_QWORD *)v189 = &v200;
          pResults = (MULTI_QI *)&Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
          *(_QWORD *)dwCount = v142;
          v145 = v218;
          AccessTokenForApplicationUsingSecret = JSONWebTokenService::GetAccessTokenForApplicationUsingSecret(
                                                   *(_QWORD *)(v144 + 1000),
                                                   *((_QWORD *)v204 + 4),
                                                   *((_QWORD *)v204 + 5),
                                                   (_DWORD)v218,
                                                   (__int64)v142,
                                                   (__int64)&Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val,
                                                   (__int64)&v200,
                                                   (__int64)v247,
                                                   (__int64)&v196,
                                                   (__int64)&v332,
                                                   (__int64)&v216);
          v147 = v216;
          if ( AccessTokenForApplicationUsingSecret )
          {
            if ( ((AccessTokenForApplicationUsingSecret + 895352831) & 0xFFFFFFF7) != 0 )
            {
              ex_raise(74, 41, 16, 4);
            }
            else
            {
              v367[0] = 0;
              if ( v216 )
              {
                v148 = 2048;
                v149 = v367;
                while ( v148 != -2147481598 )
                {
                  v150 = *(_WORD *)((char *)v149 + v147 - (_BYTE *)v367);
                  if ( !v150 )
                    break;
                  *v149++ = v150;
                  if ( !--v148 )
                  {
                    --v149;
                    break;
                  }
                }
                *v149 = 0;
              }
              ex_raise(74, 45, 16, 1, v367);
            }
          }
          Tm.tm_sec = v335;
          Tm.tm_min = v334;
          Tm.tm_hour = v333;
          Tm.tm_mday = HIWORD(v332);
          Tm.tm_mon = WORD1(v332) - 1;
          Tm.tm_year = (unsigned __int16)v332 - 1900;
          Tm.tm_isdst = -1;
          v151 = _mktime64(&Tm);
          v134 = v200;
          v198 = v151;
          operator delete[](v142);
          operator delete[](v147);
          operator delete[](v145);
          break;
        case 3:
          v220 = 0;
          LODWORD(v211) = 0;
          v219 = 0;
          LODWORD(v208) = 0;
          *(GUID *)v302 = Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
          v152 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
          v153 = *(_QWORD *)(v152 + 256);
          if ( !v153 )
          {
            SystemThread::MakeMiniSOSThread(0);
            v153 = *(_QWORD *)(v152 + 256);
          }
          if ( (unsigned int)JSONWebTokenService::GetAccessTokenForAADTenantSpecificSQLServicePrincipal(
                               *(struct IMemObj **)(v153 + 1000),
                               0,
                               0,
                               0,
                               (__int64)&v200,
                               (__int64)&v211,
                               (__int64)&v344,
                               (__int64)&v219,
                               (__int64)&v208,
                               (__int64)&v196,
                               (__int64)&v220,
                               0,
                               (__int64)v302,
                               0,
                               0,
                               0) )
            ex_raise(74, 41, 16, v196 + 10);
          v134 = v200;
          operator delete[]((void *)v219);
          operator delete[]((void *)v220);
          break;
      }
      v154 = *((_BYTE *)v204 + 8);
      LOBYTE(v190) = (v154 & 2) != 0;
      v189[0] = (v154 & 0x40) != 0;
      LOBYTE(pResults) = v154 & 1;
      v155 = COledbConnect::SetINITProps(
               a1,
               v127,
               *((_QWORD *)v204 + 4),
               *((_QWORD *)v204 + 5),
               v134,
               (_DWORD)pResults,
               *(_DWORD *)v189,
               v190,
               v112);
      if ( v155 < 0 )
      {
        _mm_lfence();
        v156 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 40LL))(a1);
        v157 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 24LL))(a1);
        v251[0] = v127;
        v251[1] = &IID_IDBProperties;
        v252 = v155;
        v253 = v157;
        v254 = v156;
        v255 = 0;
        v256 = 0;
        v257 = 0;
        v258 = -1;
        v259 = 0;
        v260 = 0;
        v261 &= ~1u;
        if ( COledbError::FPrintSQLServerError((COledbError *)v251) )
          ex_raise(73, 73, 25, 1);
        COledbError::PrintMsgUsingHRESULT((COledbError *)v251);
        ex_raise(73, 73, 16, 2, v253, v254);
        operator delete[](v255);
      }
      v158 = *(const wchar_t **)(a1 + 40);
      if ( !v158 )
      {
        v158 = *(const wchar_t **)(a1 + 128);
        if ( !v158 )
          v158 = *(const wchar_t **)(a1 + 8);
      }
      wcsncpy_s(Destination, 0xFA1u, v158, 0xFA0u);
      Destination[4000] = 0;
      v221 = 0;
      v159 = COledbConnect::GetInterface((COledbConnect *)a1, &IID_IDBInitialize, v199, &IID_IUnknown, 1);
      v221 = v159;
      v203 = 0;
      ((void (__fastcall *)(struct IUnknown *, GUID *, __int64 *))v159->lpVtbl->QueryInterface)(
        v159,
        &IID_ISSAsynchStatus,
        &v203);
      v337[1] = 0;
      v338 = 4194508;
      v339 = 0;
      v341 = 0;
      v340 = 0;
      v342 = 0;
      v337[0] = (SOS_ExternalAutoWait *)&v338;
      v337[1] = SOS_ExternalAutoWait::SOS_ExternalAutoWait((SOS_ExternalAutoWait *)v343, (struct SOS_WaitInfo *)&v338);
      Source = Destination;
      v160 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v161 = *(_QWORD *)(v160 + 256);
      if ( !v161 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v161 = *(_QWORD *)(v160 + 256);
      }
      memcpy_s((void *const)(v161 + 3128), 0x1Eu, &Source, 8u);
      v162 = ((__int64 (__fastcall *)(struct IUnknown *))v159->lpVtbl[1].QueryInterface)(v159);
      if ( v337[1] )
      {
        v163 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        v164 = *(_QWORD *)(v163 + 256);
        if ( !v164 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v164 = *(_QWORD *)(v163 + 256);
        }
        *(_QWORD *)(v164 + 3128) = 0;
        SOS_ExternalAutoWait::~SOS_ExternalAutoWait(v337[1]);
      }
      if ( v162 == 265936 )
      {
        v165 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v203 + 40LL))(v203, 0xFFFFFFFFLL);
        v166 = v203;
        v203 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v166 + 16LL))(v166);
        if ( v165 < 0 )
          goto LABEL_229;
      }
      else if ( v162 < 0 )
      {
LABEL_229:
        v167 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 40LL))(a1);
        v168 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 24LL))(a1);
        v224[0] = v159;
        v224[1] = &IID_IDBInitialize;
        v225 = v162;
        v226 = v168;
        v227 = v167;
        v228 = 0;
        v229 = 0;
        v230 = 0;
        v231 = -1;
        v232 = 0;
        v233 = 0;
        v234 &= ~1u;
        v169 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 88LL))(a1);
        v234 ^= (v234 ^ v169) & 1;
        if ( COledbError::FPrintSQLServerError((COledbError *)v224) )
        {
          if ( (v234 & 1) != 0 )
            COledbError::SendOriginalErrorInStretchTelemetry(v224, 0);
          ex_raise(73, 3, 25, 1);
        }
        COledbError::PrintMsgUsingHRESULT((COledbError *)v224);
        memset_0(v369, 0, 0x1F42u);
        if ( v225 == -2147217887 )
        {
          COledbError::GatherPropsInError((COledbError *)v224, &v209, &v249);
          dwCount[0] = 4001;
          v170 = v249;
          v171 = v209;
          COledbError::CwchFormatPropertyUser((COledbError *)v224, v209, v249, v369, *(rsize_t *)dwCount);
          if ( (_DWORD)v171 )
          {
            p_bstrVal = &v170->vValue.bstrVal;
            do
            {
              if ( *((_WORD *)p_bstrVal - 4) == 8 )
                SysFreeString(*p_bstrVal);
              p_bstrVal += 9;
              --v171;
            }
            while ( v171 );
          }
          TaskFree(v170);
        }
        ex_raise(73, 3, 16, 1, v226, v227);
        operator delete[](v228);
      }
      v221 = 0;
      ((void (__fastcall *)(struct IUnknown *))v159->lpVtbl->Release)(v159);
      v222 = 0;
      ((void (__fastcall *)(struct IUnknown *))v127->lpVtbl->Release)(v127);
      v223 = 0;
      v173 = v199;
      v174 = COledbConnect::GetInterface((COledbConnect *)a1, &IID_IDBCreateSession, v199, &IID_IUnknown, 1);
      v223 = v174;
      v199 = 0;
      ((void (__fastcall *)(struct IUnknown *))v173->lpVtbl->Release)(v173);
      v175 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, GUID *, struct IUnknown **))v174->lpVtbl[1].QueryInterface)(
               v174,
               0,
               &IID_IUnknown,
               &v202);
      if ( v175 < 0 )
      {
        _mm_lfence();
        v176 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 40LL))(a1);
        v177 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 24LL))(a1);
        v236[0] = v174;
        v236[1] = &IID_IDBCreateSession;
        v237 = v175;
        v238 = v177;
        v239 = v176;
        v240 = 0;
        v241 = 0;
        v242 = 0;
        v243 = -1;
        v244 = 0;
        v245 = 0;
        v246 &= ~1u;
        LOBYTE(v176) = v246;
        v246 = v176 ^ (v176 ^ (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 88LL))(a1)) & 1;
        if ( COledbError::FPrintSQLServerError((COledbError *)v236) )
        {
          if ( (v246 & 1) != 0 )
            COledbError::SendOriginalErrorInStretchTelemetry(v236, 0);
          ex_raise(73, 4, 25, 1);
        }
        COledbError::PrintMsgUsingHRESULT((COledbError *)v236);
        ex_raise(73, 4, 16, 2, v238, v239);
        operator delete[](v240);
      }
      v223 = 0;
      ((void (__fastcall *)(struct IUnknown *))v174->lpVtbl->Release)(v174);
      v178 = *(_QWORD *)&CLSID_MSOLEDBSQL.Data1;
      v179 = *(_QWORD *)CLSID_MSOLEDBSQL.Data4;
      if ( *(_QWORD *)&CLSID_MSOLEDBSQL.Data1 == *(_QWORD *)(a1 + 16)
        && *(_QWORD *)CLSID_MSOLEDBSQL.Data4 == *(_QWORD *)(a1 + 24)
        || *(_QWORD *)(a1 + 16) == 0x45EB837A726D00DELL && *(_QWORD *)(a1 + 24) == 0x9C07F941D2ED8CAEuLL )
      {
        v250 = 0;
        v180 = COledbConnect::GetInterface((COledbConnect *)a1, &IID_ISessionProperties, v202, &IID_IUnknown, 1);
        v250 = v180;
        v355 = 3;
        v356 = 0;
        v357 = DB_NULLID;
        VariantInit(&pvarg);
        pvarg.vt = 11;
        pvarg.iVal = -1;
        v359 = &v355;
        v360 = 1;
        v361 = DBPROPSET_SQLSERVERSESSION;
        v181 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, __int64 **))v180->lpVtbl[1].AddRef)(v180, 1, &v359);
        if ( v181 < 0 )
        {
          _mm_lfence();
          v182 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 40LL))(a1);
          v183 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 24LL))(a1);
          v273[0] = v180;
          v273[1] = &IID_ISessionProperties;
          v274 = v181;
          v275 = v183;
          v276 = v182;
          v277 = 0;
          v278 = 0;
          v279 = 0;
          v280 = -1;
          v281 = 0;
          v282 = 0;
          v283 &= ~1u;
          if ( COledbError::FPrintSQLServerError((COledbError *)v273) )
            ex_raise(73, 74, 25, 1);
          COledbError::PrintMsgUsingHRESULT((COledbError *)v273);
          ex_raise(73, 74, 16, 2, v275, v276);
          operator delete[](v277);
        }
        COledbConnect::GenerateWaitMessageForSpid((COledbConnect *)a1, v202, Destination, 0xFA1u);
        ((void (__fastcall *)(struct IUnknown *))v180->lpVtbl->Release)(v180);
        v179 = *(_QWORD *)CLSID_MSOLEDBSQL.Data4;
        v178 = *(_QWORD *)&CLSID_MSOLEDBSQL.Data1;
      }
      v184 = 0;
      if ( v178 == *(_QWORD *)(a1 + 16) && v179 == *(_QWORD *)(a1 + 24)
        || *(_QWORD *)(a1 + 16) == 0x45EB837A726D00DELL && *(_QWORD *)(a1 + 24) == 0x9C07F941D2ED8CAEuLL )
      {
        v197 = 0;
        if ( COledbConnect::FIsSQLServer((COledbConnect *)a1, v202, &v197) && v197 >= 7 )
          v184 = 1;
      }
      Session = CRemSess::MakeSession(v204, v202, Destination, v184, v198);
      if ( v203 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v203 + 16LL))(v203);
      operator delete[]((void *)v200);
      CSECAutoImpersonateForDQ::Revert((CSECAutoImpersonateForDQ *)&hObject);
      if ( v351 )
      {
        intnl_revert_to_self(
          *(struct CSession **)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                          + SystemThread_TlsOffset)
                              + 72LL),
          1);
        v351 = 0;
      }
      CAutoLogin::Revert((CAutoLogin *)&hObject);
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hObject);
      if ( (_DWORD)v348 )
        LsaFreeReturnBuffer(Buffer);
      if ( (char *)LsaHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        LsaDeregisterLogonProcess(LsaHandle);
      if ( v202 )
        ((void (__fastcall *)(struct IUnknown *))v202->lpVtbl->Release)(v202);
      return Session;
    }
    v206 = 7;
    v328 = &v206;
    v329 = 1;
    v330 = DBPROPSET_DBINIT;
    v207 = 0;
    v201 = 0;
    v128 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, int **, int *, void ***))Interface->lpVtbl[1].QueryInterface)(
             Interface,
             1,
             &v328,
             &v207,
             &v201);
    v129 = v201;
    if ( (int)(v128 + 0x80000000) < 0 || v128 == -2147217887 )
    {
      if ( !v201 )
      {
LABEL_165:
        v130 = (*(__int64 (__fastcall **)(__int64, void **))(*(_QWORD *)a1 + 40LL))(a1, v129);
        v131 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 24LL))(a1);
        v262[0] = v127;
        v262[1] = &IID_IDBProperties;
        v263 = v128;
        v264 = v131;
        v265 = v130;
        v266 = 0;
        v267 = 0;
        v268 = 0;
        v269 = -1;
        v270 = 0;
        v271 = 0;
        v272 &= ~1u;
        if ( COledbError::FPrintSQLServerError((COledbError *)v262) )
          ex_raise(73, 72, 25, 1);
        COledbError::PrintMsgUsingHRESULT((COledbError *)v262);
        ex_raise(73, 72, 16, 2, v264, v265);
        operator delete[](v266);
        v129 = v201;
        goto LABEL_168;
      }
      if ( *((_DWORD *)v201 + 2) == 1 )
      {
LABEL_168:
        v132 = (VARIANTARG *)((char *)*v129 + 48);
        if ( *((_DWORD *)*v129 + 2) || (v133 = 1, !v132->vt) )
          v133 = 0;
        if ( *((_DWORD *)v129 + 2) )
        {
          VariantClear(v132);
          v129 = v201;
        }
        TaskFree(*v129);
        TaskFree(v201);
        if ( v133 )
          ex_raise(74, 9, 16, 1);
        goto LABEL_175;
      }
    }
    if ( v201 )
    {
      if ( *v201 )
      {
        TaskFree(*v201);
        v129 = v201;
      }
      TaskFree(v129);
    }
    goto LABEL_165;
  }
  return result;
}

```

## disassembly

```asm
0x1016dd6b0  push    rbp
0x1016dd6b2  push    rsi
0x1016dd6b3  push    rdi
0x1016dd6b4  push    r12
0x1016dd6b6  push    r13
0x1016dd6b8  push    r14
0x1016dd6ba  push    r15
0x1016dd6bc  lea     rbp, [rsp-5940h]
0x1016dd6c4  mov     eax, 5A60h
0x1016dd6c9  call    _alloca_probe
0x1016dd6ce  sub     rsp, rax
0x1016dd6d1  mov     [rbp+5970h+var_5700], 0FFFFFFFFFFFFFFFEh
0x1016dd6dc  mov     [rsp+5A90h+arg_10], rbx
0x1016dd6e4  movaps  [rsp+5A90h+var_40], xmm6
0x1016dd6ec  mov     rax, cs:__security_cookie
0x1016dd6f3  xor     rax, rsp
0x1016dd6f6  mov     [rbp+5970h+var_50], rax
0x1016dd6fd  movzx   edi, r9b
0x1016dd701  movzx   r13d, r8b
0x1016dd705  mov     [rbp+5970h+var_59EF], r8b
0x1016dd709  mov     r15, rdx
0x1016dd70c  mov     [rbp+5970h+var_59B8], rdx
0x1016dd710  mov     rsi, rcx
0x1016dd713  mov     rax, [rbp+5970h+arg_28]
0x1016dd71a  mov     [rbp+5970h+var_5958], rax
0x1016dd71e  xor     ebx, ebx
0x1016dd720  mov     r12d, ebx
0x1016dd723  mov     dword ptr [rbp+5970h+var_59A0+4], ebx
0x1016dd726  xor     edx, edx; Val
0x1016dd728  mov     r8d, 1F42h; Size
0x1016dd72e  lea     rcx, [rbp+5970h+Destination]; void *
0x1016dd735  call    memset_0
0x1016dd73a  mov     eax, cs:?g_statCOM@@3JC; long volatile g_statCOM
0x1016dd740  cmp     eax, 1
0x1016dd743  jz      short loc_1016DD755
0x1016dd745  mov     eax, cs:?g_statCOM@@3JC; long volatile g_statCOM
0x1016dd74b  cmp     eax, 3
0x1016dd74e  jz      short loc_1016DD755
0x1016dd750  call    ?FInitDCOM@@YAHXZ; FInitDCOM(void)
0x1016dd755  lock or [rsp+5A90h+var_5A90], ebx
0x1016dd759  mov     eax, cs:?g_statCOM@@3JC; long volatile g_statCOM
0x1016dd75f  mov     ecx, 4
0x1016dd764  cmp     eax, 1
0x1016dd767  jz      short loc_1016DD77C
0x1016dd769  lea     r9d, [rcx-3]
0x1016dd76d  lea     r8d, [rcx+0Ch]
0x1016dd771  mov     edx, ecx
0x1016dd773  lea     ecx, [rdx+46h]
0x1016dd776  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x1016dd77c  mov     rax, cs:__imp_?s_pServerConf@@3PEAVIServerConfiguration@@EA; IServerConfiguration * s_pServerConf
0x1016dd783  mov     rcx, [rax]
0x1016dd786  mov     r10d, 5
0x1016dd78c  cmp     dword ptr [rcx+0Ch], 1
0x1016dd790  jnz     short loc_1016DD7D9
0x1016dd792  mov     rax, cs:qword_102ECFB00
0x1016dd799  mov     rcx, [rax+2DD0h]
0x1016dd7a0  mov     [rsp+5A90h+var_5A58], rcx
0x1016dd7a5  mov     ecx, [rax+2DD8h]
0x1016dd7ab  mov     dword ptr [rsp+5A90h+var_5A60], ecx
0x1016dd7af  lea     rax, aDistributedQue_4; "Distributed Query or Remote Procedure E"...
0x1016dd7b6  mov     [rsp+5A90h+pResults], rax
0x1016dd7bb  mov     qword ptr [rsp+5A90h+dwCount], 5Eh ; '^'
0x1016dd7c4  lea     edx, [r10+1Dh]
0x1016dd7c8  lea     r9d, [r10-4]
0x1016dd7cc  lea     r8d, [r10+0Bh]
0x1016dd7d0  mov     ecx, r10d
0x1016dd7d3  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x1016dd7d9  cmp     [rsi+8Dh], bl
0x1016dd7df  jz      short loc_1016DD81E
0x1016dd7e1  mov     dl, 1; bool
0x1016dd7e3  lea     rcx, ?g_PolybaseFeatureManager@@3VCPolybaseFeatureManager@@A; this
0x1016dd7ea  call    ?IsPolybaseProvisioned@CPolybaseFeatureManager@@QEAA_N_N@Z; CPolybaseFeatureManager::IsPolybaseProvisioned(bool)
0x1016dd7ef  test    al, al
0x1016dd7f1  jz      short loc_1016DD81E
0x1016dd7f3  call    cs:__imp_?FUseReplicatedServerContext@@YA_NXZ; FUseReplicatedServerContext(void)
0x1016dd7f9  test    al, al
0x1016dd7fb  mov     rax, cs:qword_102ECFB00
0x1016dd802  jnz     short loc_1016DD80C
0x1016dd804  add     rax, 3A10h
0x1016dd80a  jmp     short loc_1016DD812
0x1016dd80c  add     rax, 6F68h
0x1016dd812  cmp     [rax+354Dh], bl
0x1016dd818  jnz     loc_1016DD8F9
0x1016dd81e  mov     rax, qword ptr cs:CLSID_MSOLEDBSQL.Data1
0x1016dd825  cmp     rax, [rsi+10h]
0x1016dd829  jnz     short loc_1016DD838
0x1016dd82b  mov     rax, qword ptr cs:CLSID_MSOLEDBSQL.Data4
0x1016dd832  cmp     rax, [rsi+18h]
0x1016dd836  jz      short loc_1016DD852
0x1016dd838  mov     rax, qword ptr cs:rclsid.Data1
0x1016dd83f  cmp     rax, [rsi+10h]
0x1016dd843  jnz     short loc_1016DD859
0x1016dd845  mov     rax, qword ptr cs:rclsid.Data4
0x1016dd84c  cmp     rax, [rsi+18h]
0x1016dd850  jnz     short loc_1016DD859
0x1016dd852  mov     edx, 1
0x1016dd857  jmp     short loc_1016DD85B
0x1016dd859  mov     edx, ebx; int
0x1016dd85b  mov     r14d, [rbp+5970h+arg_30]
0x1016dd862  test    r13b, r13b
0x1016dd865  jnz     short loc_1016DD8CF
0x1016dd867  test    dil, dil
0x1016dd86a  jnz     short loc_1016DD8CF
0x1016dd86c  test    r14d, r14d
0x1016dd86f  jnz     short loc_1016DD8CF
0x1016dd871  lea     ebx, [r14+1]
0x1016dd875  mov     rcx, [rsi+20h]; String1
0x1016dd879  test    rcx, rcx
0x1016dd87c  jz      short loc_1016DD889
0x1016dd87e  call    ?FValidateOpenDatasourceString@@YAHPEB_WH@Z; FValidateOpenDatasourceString(wchar_t const *,int)
0x1016dd883  test    eax, eax
0x1016dd885  cmovz   ebx, r12d
0x1016dd889  cmp     dword ptr [rsi+50h], 0FFFFFFFFh
0x1016dd88d  jz      short loc_1016DD8AE
0x1016dd88f  mov     rcx, [r15+20h]
0x1016dd893  test    rcx, rcx
0x1016dd896  jz      short loc_1016DD8B2
0x1016dd898  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1016dd89f  nop
0x1016dd8a0  inc     rax
0x1016dd8a3  cmp     [rcx+rax*2], r12w
0x1016dd8a8  jnz     short loc_1016DD8A0
0x1016dd8aa  test    eax, eax
0x1016dd8ac  jz      short loc_1016DD8B2
0x1016dd8ae  test    ebx, ebx
0x1016dd8b0  jnz     short loc_1016DD8CD
0x1016dd8b2  mov     edx, 10h
0x1016dd8b7  lea     ecx, [rdx+3Ah]
0x1016dd8ba  mov     r12d, 80004005h
0x1016dd8c0  lea     r9d, [rdx-0Eh]
0x1016dd8c4  mov     r8d, edx
0x1016dd8c7  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x1016dd8cd  xor     ebx, ebx
0x1016dd8cf  mov     rdx, rsi; struct COledbConnect *
0x1016dd8d2  mov     rcx, r15; struct RemSessProps *
0x1016dd8d5  call    ?FindSession@CRemSess@@SAPEAV1@AEBURemSessProps@@PEAVCOledbConnect@@@Z; CRemSess::FindSession(RemSessProps const &,COledbConnect *)
0x1016dd8da  test    rax, rax
0x1016dd8dd  jnz     loc_1016DF677
0x1016dd8e3  mov     [rbp+5970h+var_59C8], rbx
0x1016dd8e7  movzx   eax, byte ptr [r15+8]
0x1016dd8ec  test    al, 2
0x1016dd8ee  jnz     short loc_1016DD902
0x1016dd8f0  test    r14d, r14d
0x1016dd8f3  jnz     short loc_1016DD902
0x1016dd8f5  xor     cl, cl
0x1016dd8f7  jmp     short loc_1016DD904
0x1016dd8f9  mov     r14d, [rbp+5970h+arg_30]
0x1016dd900  jmp     short loc_1016DD8CF
0x1016dd902  mov     cl, 1
0x1016dd904  test    al, 1
0x1016dd906  jnz     short loc_1016DD917
0x1016dd908  test    r13b, r13b
0x1016dd90b  jz      short loc_1016DD913
0x1016dd90d  cmp     dword ptr [rsi+50h], 0FFFFFFFFh
0x1016dd911  jz      short loc_1016DD917
0x1016dd913  xor     al, al
0x1016dd915  jmp     short loc_1016DD919
0x1016dd917  mov     al, 1
0x1016dd919  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x1016dd920  mov     [rbp+5970h+hObject], rdx
0x1016dd927  mov     [rbp+5970h+var_5328], ebx
0x1016dd92d  mov     [rbp+5970h+Buffer], rbx
0x1016dd934  mov     [rbp+5970h+var_5318], 0
0x1016dd93f  mov     [rbp+5970h+var_5310], ebx
0x1016dd945  mov     [rbp+5970h+LsaHandle], rdx
0x1016dd94c  mov     [rbp+5970h+var_4FA8], ebx
0x1016dd952  mov     [rbp+5970h+var_4FA4], 0
0x1016dd959  mov     [rbp+5970h+var_4FA3], al
0x1016dd95f  mov     [rbp+5970h+var_4FA2], cl
0x1016dd965  lea     rcx, [rbp+5970h+hObject]; this
0x1016dd96c  call    ?Impersonate@CSECAutoImpersonateForDQ@@QEAA_NXZ; CSECAutoImpersonateForDQ::Impersonate(void)
0x1016dd971  movzx   ebx, al
0x1016dd974  mov     [rbp+5970h+var_59F0], al
0x1016dd977  test    al, al
0x1016dd979  jnz     short loc_1016DD9C0
0x1016dd97b  test    r13b, r13b
0x1016dd97e  jz      short loc_1016DD9C0
0x1016dd980  test    byte ptr [r15+8], 1
0x1016dd985  jz      short loc_1016DD9C0
0x1016dd987  mov     rdx, [rsi]
0x1016dd98a  mov     rcx, rsi
0x1016dd98d  call    qword ptr [rdx+18h]
0x1016dd990  mov     rbx, rax
0x1016dd993  mov     rdx, [rsi]
0x1016dd996  mov     rcx, rsi
0x1016dd999  call    qword ptr [rdx+28h]
0x1016dd99c  mov     [rsp+5A90h+pResults], rbx
0x1016dd9a1  mov     qword ptr [rsp+5A90h+dwCount], rax
0x1016dd9a6  mov     edx, 0Dh
0x1016dd9ab  lea     ecx, [rdx+3Dh]
0x1016dd9ae  lea     r9d, [rdx-0Bh]
0x1016dd9b2  lea     r8d, [rdx+3]
0x1016dd9b6  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x1016dd9bc  movzx   ebx, [rbp+5970h+var_59F0]
0x1016dd9c0  mov     r14d, 14h
0x1016dd9c6  mov     rax, [rsi]
0x1016dd9c9  mov     rcx, rsi
0x1016dd9cc  call    qword ptr [rax+38h]
0x1016dd9cf  mov     ecx, 17h
0x1016dd9d4  test    al, al
0x1016dd9d6  cmovnz  r14d, ecx
0x1016dd9da  xor     ecx, ecx; this
0x1016dd9dc  mov     [rbp+5970h+var_59E0], rcx
0x1016dd9e0  test    byte ptr [r15+8], 40h
0x1016dd9e5  jz      loc_1016DDEFA
0x1016dd9eb  test    r13b, r13b
0x1016dd9ee  jz      short loc_1016DD9F4
0x1016dd9f0  test    bl, bl
0x1016dd9f2  jnz     short loc_1016DDA34
0x1016dd9f4  test    dil, dil
0x1016dd9f7  jnz     short loc_1016DDA34
0x1016dd9f9  mov     rbx, [rsi+20h]
0x1016dd9fd  cmp     word ptr [rbx], 0
0x1016dda01  jz      short loc_1016DDA34
0x1016dda03  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x1016dda09  mov     r9, rax; Locale
0x1016dda0c  mov     r8d, 12h; MaxCount
0x1016dda12  lea     rdx, aTrustedConnect; "trusted_connection"
0x1016dda19  mov     rcx, rbx; String1
0x1016dda1c  call    cs:__imp__wcsnicmp_l
0x1016dda22  test    eax, eax
0x1016dda24  jz      loc_1016DDBDE
0x1016dda2a  add     rbx, 2
0x1016dda2e  cmp     word ptr [rbx], 0
0x1016dda32  jnz     short loc_1016DDA03
0x1016dda34  xor     r15d, r15d
0x1016dda37  mov     [rbp+5970h+var_5990], r15
0x1016dda3b  mov     r8d, r14d; unsigned int
0x1016dda3e  mov     dl, 1; bool
0x1016dda40  call    ?PdatiniGetService@COledbConnect@@AEBAPEAUIDataInitialize@@_NK@Z; COledbConnect::PdatiniGetService(bool,ulong)
0x1016dda45  mov     r13, rax
0x1016dda48  mov     [rbp+5970h+var_5990], rax
0x1016dda4c  mov     [rbp+5970h+var_5978], r15
0x1016dda50  movups  xmm0, xmmword ptr cs:aProvider_1; ";PROVIDER="
0x1016dda57  movups  [rbp+5970h+var_4F30], xmm0
0x1016dda5e  mov     ecx, dword ptr cs:aProvider_1+10h; "R="
0x1016dda64  mov     [rbp+5970h+var_4F20], ecx
0x1016dda6a  movzx   ecx, word ptr cs:aProvider_1+14h; ""
0x1016dda71  mov     [rbp+5970h+var_4F1C], cx
0x1016dda78  mov     r14, 0FFFFFFFFFFFFFFFFh
0x1016dda7f  mov     dword ptr [rsp+5A90h+pResults], r14d
0x1016dda84  lea     rax, ?x_wszSSProvider@@3QB_WB; "MSOLEDBSQL"
0x1016dda8b  mov     qword ptr [rsp+5A90h+dwCount], rax
0x1016dda90  mov     r9d, r14d
0x1016dda93  mov     r8, [rsi+8]
0x1016dda97  xor     edx, edx
0x1016dda99  lea     ecx, [rdx+1]
0x1016dda9c  call    cs:__imp_?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z; CompareStringWEnglishNoCase(ulong,uchar,wchar_t const *,int,wchar_t const *,int)
0x1016ddaa2  cmp     eax, 2
0x1016ddaa5  jz      loc_1016DDC01
0x1016ddaab  mov     dword ptr [rsp+5A90h+pResults], r14d
0x1016ddab0  lea     rax, ?x_wszMSOleDbSqlProvider@@3QB_WB; "MSOLEDBSQL"
0x1016ddab7  mov     qword ptr [rsp+5A90h+dwCount], rax
0x1016ddabc  mov     r9d, r14d
0x1016ddabf  mov     r8, [rsi+8]
0x1016ddac3  xor     edx, edx
0x1016ddac5  lea     ecx, [rdx+1]
0x1016ddac8  call    cs:__imp_?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z; CompareStringWEnglishNoCase(ulong,uchar,wchar_t const *,int,wchar_t const *,int)
0x1016ddace  cmp     eax, 2
0x1016ddad1  jz      loc_1016DDC01
0x1016ddad7  mov     rax, [rsi+20h]
0x1016ddadb  mov     rdx, r14
0x1016ddade  xchg    ax, ax
0x1016ddae0  lea     rdx, [rdx+1]
0x1016ddae4  cmp     word ptr [rax+rdx*2], 0
0x1016ddae9  jnz     short loc_1016DDAE0
0x1016ddaeb  lea     rax, [rbp+5970h+var_4F30]
0x1016ddaf2  mov     rcx, r14
0x1016ddaf5  lea     rcx, [rcx+1]
0x1016ddaf9  cmp     word ptr [rax+rcx*2], 0
0x1016ddafe  jnz     short loc_1016DDAF5
0x1016ddb00  mov     r8, [rsi+8]
0x1016ddb04  mov     rax, r14
0x1016ddb07  nop     word ptr [rax+rax+00000000h]
0x1016ddb10  inc     rax
0x1016ddb13  cmp     word ptr [r8+rax*2], 0
0x1016ddb19  jnz     short loc_1016DDB10
0x1016ddb1b  lea     edi, [rcx+rdx]
0x1016ddb1e  add     edi, eax
0x1016ddb20  mov     rdx, gs:58h
0x1016ddb29  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1016ddb30  mov     ecx, [rax]
0x1016ddb32  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1016ddb39  mov     ebx, [rax]
0x1016ddb3b  add     rbx, [rdx+rcx*8]
0x1016ddb3f  mov     rcx, [rbx+100h]
0x1016ddb46  test    rcx, rcx
0x1016ddb49  jnz     short loc_1016DDB58
0x1016ddb4b  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1016ddb51  mov     rcx, [rbx+100h]
0x1016ddb58  lea     eax, [rdi+1]
0x1016ddb5b  movsxd  rdi, eax
0x1016ddb5e  mov     eax, 2
0x1016ddb63  mul     rdi
0x1016ddb66  cmovo   rax, r14
0x1016ddb6a  mov     byte ptr [rsp+5A90h+dwCount], 3
0x1016ddb6f  mov     r9d, 0DE9h
0x1016ddb75  lea     r8, aSqlNtdbmsMsqlU_4; "sql\\ntdbms\\msql\\utils\\oledbconn.cpp"
0x1016ddb7c  mov     rdx, [rcx+3E8h]
0x1016ddb83  mov     rcx, rax
  ... truncated ...
```
