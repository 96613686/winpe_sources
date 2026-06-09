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
  __int64 v51; // rbx
  __int64 v52; // rcx
  __int64 v53; // rbx
  PerProcessGlobals *ClientProcessGlobals; // rax
  __int64 v55; // rcx
  __int64 v56; // rcx
  struct IMemObj *MemObject; // r15
  struct IUnknown *v58; // r14
  __int128 v59; // xmm6
  bool v60; // di
  __int64 v61; // rbx
  __int64 v62; // rax
  struct IClassFactory **v63; // rcx
  __int64 v64; // rcx
  __int64 v65; // rbx
  __int64 v66; // rax
  __int64 v67; // rbx
  PerProcessGlobals *v68; // rax
  __int64 v69; // rcx
  __int64 v70; // rcx
  struct IMemObj *v71; // r15
  struct IUnknown *v72; // r14
  __int128 v73; // xmm6
  bool v74; // di
  __int64 v75; // rbx
  __int64 v76; // rax
  __int64 v77; // rax
  struct IDataInitialize *v78; // rbx
  struct IDataInitialize *v79; // rax
  HRESULT v80; // eax
  __int64 v81; // rcx
  __int64 v82; // rbx
  __int64 v83; // rax
  __int64 v84; // rbx
  PerProcessGlobals *v85; // rax
  __int64 v86; // rcx
  __int64 v87; // rcx
  struct IMemObj *v88; // r15
  struct IUnknown *v89; // r14
  __int128 v90; // xmm6
  bool v91; // di
  __int64 v92; // rbx
  __int64 v93; // rax
  int v94; // r13d
  __int64 v95; // rax
  char *v96; // rdx
  __int64 v97; // rcx
  int v98; // ecx
  char **v99; // rax
  __int64 v100; // rax
  char *v101; // rdx
  __int64 v102; // rcx
  int v103; // ecx
  char **v104; // rax
  char **v105; // rcx
  __int64 v106; // rbx
  __int64 v107; // rax
  struct IUnknown *Interface; // rax
  struct IUnknown *v109; // r12
  int v110; // edi
  void **v111; // rdx
  __int64 v112; // rbx
  __int64 v113; // rax
  VARIANTARG *v114; // rcx
  int v115; // ebx
  __int64 v116; // r14
  __int64 v117; // rbx
  __int64 v118; // rdx
  __int64 v119; // rbx
  __int64 v120; // rcx
  __int64 v121; // rbx
  __int64 v122; // r9
  char v123; // al
  void *v124; // r15
  __int64 v125; // rbx
  __int64 v126; // rcx
  void *v127; // rdi
  int AccessTokenForApplicationUsingSecret; // eax
  _BYTE *v129; // rbx
  __int64 v130; // rdx
  _WORD *v131; // rcx
  __int16 v132; // ax
  int v133; // eax
  __int64 v134; // rbx
  __int64 v135; // rcx
  char v136; // dl
  int v137; // edi
  __int64 v138; // rbx
  __int64 v139; // rax
  const wchar_t *v140; // r8
  struct IUnknown *v141; // r15
  __int64 v142; // rbx
  __int64 v143; // rcx
  int v144; // edi
  __int64 v145; // rbx
  __int64 v146; // rcx
  int v147; // r14d
  __int64 v148; // rcx
  __int64 v149; // rbx
  __int64 v150; // rax
  char v151; // al
  struct tagDBPROP *v152; // r14
  __int64 v153; // rdi
  BSTR *p_bstrVal; // rbx
  struct IUnknown *v155; // rbx
  struct IUnknown *v156; // rdi
  int v157; // r14d
  __int64 v158; // rbx
  __int64 v159; // rax
  __int64 v160; // r8
  __int64 v161; // rdx
  struct IUnknown *v162; // rdi
  int v163; // r14d
  __int64 v164; // rbx
  __int64 v165; // rax
  bool v166; // r9
  struct CRemSess *Session; // rbx
  signed __int32 v168[8]; // [rsp+0h] [rbp-120h] BYREF
  DWORD dwCount[2]; // [rsp+20h] [rbp-100h]
  MULTI_QI *pResults; // [rsp+28h] [rbp-F8h]
  char v171[8]; // [rsp+30h] [rbp-F0h]
  __int64 v172; // [rsp+38h] [rbp-E8h]
  GUID *rguid; // [rsp+40h] [rbp-E0h]
  char v174[8]; // [rsp+48h] [rbp-D8h]
  __int64 v175; // [rsp+50h] [rbp-D0h]
  bool v176; // [rsp+A0h] [rbp-80h]
  char v177; // [rsp+A1h] [rbp-7Fh]
  int v178; // [rsp+A4h] [rbp-7Ch] BYREF
  int v179; // [rsp+A8h] [rbp-78h] BYREF
  int v180; // [rsp+ACh] [rbp-74h] BYREF
  struct IUnknown *v181; // [rsp+B0h] [rbp-70h]
  __int64 v182; // [rsp+B8h] [rbp-68h] BYREF
  void **v183; // [rsp+C0h] [rbp-60h] BYREF
  struct IUnknown *v184; // [rsp+C8h] [rbp-58h] BYREF
  __int64 v185; // [rsp+D0h] [rbp-50h] BYREF
  struct RemSessProps *v186; // [rsp+D8h] [rbp-48h]
  wchar_t *Source; // [rsp+E0h] [rbp-40h] BYREF
  int v188; // [rsp+E8h] [rbp-38h] BYREF
  int v189; // [rsp+ECh] [rbp-34h] BYREF
  __int64 v190; // [rsp+F0h] [rbp-30h] BYREF
  unsigned int v191; // [rsp+F8h] [rbp-28h] BYREF
  void *v192; // [rsp+100h] [rbp-20h]
  __int64 v193; // [rsp+108h] [rbp-18h] BYREF
  __int64 v194; // [rsp+110h] [rbp-10h] BYREF
  wchar_t *v195; // [rsp+118h] [rbp-8h]
  __int64 v196; // [rsp+120h] [rbp+0h] BYREF
  struct IDataInitialize *v197; // [rsp+128h] [rbp+8h]
  _BYTE *v198; // [rsp+130h] [rbp+10h] BYREF
  __int64 *v199; // [rsp+138h] [rbp+18h]
  void *v200; // [rsp+140h] [rbp+20h]
  __int64 v201; // [rsp+148h] [rbp+28h] BYREF
  __int64 v202; // [rsp+150h] [rbp+30h] BYREF
  struct IUnknown *v203; // [rsp+158h] [rbp+38h]
  struct IUnknown *v204; // [rsp+160h] [rbp+40h]
  struct IUnknown *v205; // [rsp+168h] [rbp+48h]
  _QWORD v206[2]; // [rsp+170h] [rbp+50h] BYREF
  int v207; // [rsp+180h] [rbp+60h]
  __int64 v208; // [rsp+188h] [rbp+68h]
  __int64 v209; // [rsp+190h] [rbp+70h]
  void *v210; // [rsp+198h] [rbp+78h]
  __int64 v211; // [rsp+1A0h] [rbp+80h]
  int v212; // [rsp+1A8h] [rbp+88h]
  int v213; // [rsp+1ACh] [rbp+8Ch]
  __int64 v214; // [rsp+1B0h] [rbp+90h]
  int v215; // [rsp+1B8h] [rbp+98h]
  char v216; // [rsp+1BCh] [rbp+9Ch]
  MULTI_QI v217; // [rsp+1C0h] [rbp+A0h] BYREF
  _QWORD v218[2]; // [rsp+1E0h] [rbp+C0h] BYREF
  int v219; // [rsp+1F0h] [rbp+D0h]
  __int64 v220; // [rsp+1F8h] [rbp+D8h]
  __int64 v221; // [rsp+200h] [rbp+E0h]
  void *v222; // [rsp+208h] [rbp+E8h]
  __int64 v223; // [rsp+210h] [rbp+F0h]
  int v224; // [rsp+218h] [rbp+F8h]
  int v225; // [rsp+21Ch] [rbp+FCh]
  __int64 v226; // [rsp+220h] [rbp+100h]
  int v227; // [rsp+228h] [rbp+108h]
  char v228; // [rsp+22Ch] [rbp+10Ch]
  char v229[8]; // [rsp+230h] [rbp+110h] BYREF
  void *v230; // [rsp+238h] [rbp+118h] BYREF
  struct tagDBPROP *v231; // [rsp+240h] [rbp+120h] BYREF
  struct IUnknown *v232; // [rsp+248h] [rbp+128h]
  _QWORD v233[2]; // [rsp+250h] [rbp+130h] BYREF
  int v234; // [rsp+260h] [rbp+140h]
  __int64 v235; // [rsp+268h] [rbp+148h]
  __int64 v236; // [rsp+270h] [rbp+150h]
  void *v237; // [rsp+278h] [rbp+158h]
  __int64 v238; // [rsp+280h] [rbp+160h]
  int v239; // [rsp+288h] [rbp+168h]
  int v240; // [rsp+28Ch] [rbp+16Ch]
  __int64 v241; // [rsp+290h] [rbp+170h]
  int v242; // [rsp+298h] [rbp+178h]
  char v243; // [rsp+29Ch] [rbp+17Ch]
  _QWORD v244[2]; // [rsp+2A0h] [rbp+180h] BYREF
  int v245; // [rsp+2B0h] [rbp+190h]
  __int64 v246; // [rsp+2B8h] [rbp+198h]
  __int64 v247; // [rsp+2C0h] [rbp+1A0h]
  void *v248; // [rsp+2C8h] [rbp+1A8h]
  __int64 v249; // [rsp+2D0h] [rbp+1B0h]
  int v250; // [rsp+2D8h] [rbp+1B8h]
  int v251; // [rsp+2DCh] [rbp+1BCh]
  __int64 v252; // [rsp+2E0h] [rbp+1C0h]
  int v253; // [rsp+2E8h] [rbp+1C8h]
  char v254; // [rsp+2ECh] [rbp+1CCh]
  _QWORD v255[2]; // [rsp+2F0h] [rbp+1D0h] BYREF
  int v256; // [rsp+300h] [rbp+1E0h]
  __int64 v257; // [rsp+308h] [rbp+1E8h]
  __int64 v258; // [rsp+310h] [rbp+1F0h]
  void *v259; // [rsp+318h] [rbp+1F8h]
  __int64 v260; // [rsp+320h] [rbp+200h]
  int v261; // [rsp+328h] [rbp+208h]
  int v262; // [rsp+32Ch] [rbp+20Ch]
  __int64 v263; // [rsp+330h] [rbp+210h]
  int v264; // [rsp+338h] [rbp+218h]
  char v265; // [rsp+33Ch] [rbp+21Ch]
  __int64 v266; // [rsp+340h] [rbp+220h]
  GUID *v267; // [rsp+348h] [rbp+228h]
  int v268; // [rsp+350h] [rbp+230h]
  __int64 v269; // [rsp+358h] [rbp+238h]
  __int64 v270; // [rsp+360h] [rbp+240h]
  __int64 v271; // [rsp+368h] [rbp+248h]
  __int64 v272; // [rsp+370h] [rbp+250h]
  int v273; // [rsp+378h] [rbp+258h]
  int v274; // [rsp+37Ch] [rbp+25Ch]
  __int64 v275; // [rsp+380h] [rbp+260h]
  int v276; // [rsp+388h] [rbp+268h]
  char v277; // [rsp+38Ch] [rbp+26Ch]
  __int64 v278; // [rsp+390h] [rbp+270h]
  void *v279; // [rsp+398h] [rbp+278h]
  __int128 v280; // [rsp+3A0h] [rbp+280h] BYREF
  __int128 v281; // [rsp+3B0h] [rbp+290h] BYREF
  __int128 v282; // [rsp+3C0h] [rbp+2A0h] BYREF
  GUID v283; // [rsp+3D0h] [rbp+2B0h] BYREF
  __int64 v284[2]; // [rsp+3E0h] [rbp+2C0h] BYREF
  char v285[8]; // [rsp+3F0h] [rbp+2D0h] BYREF
  int v286; // [rsp+3F8h] [rbp+2D8h]
  int v287; // [rsp+400h] [rbp+2E0h]
  char **v288; // [rsp+408h] [rbp+2E8h]
  char *v289; // [rsp+410h] [rbp+2F0h]
  __int64 v290; // [rsp+418h] [rbp+2F8h]
  char *v291; // [rsp+420h] [rbp+300h] BYREF
  int v292; // [rsp+428h] [rbp+308h]
  int v293; // [rsp+42Ch] [rbp+30Ch]
  __int64 v294; // [rsp+430h] [rbp+310h]
  int v295; // [rsp+438h] [rbp+318h]
  int v296; // [rsp+43Ch] [rbp+31Ch]
  __int64 v297; // [rsp+440h] [rbp+320h]
  int v298; // [rsp+448h] [rbp+328h]
  int v299; // [rsp+44Ch] [rbp+32Ch]
  GUID *v300; // [rsp+450h] [rbp+330h]
  int v301; // [rsp+458h] [rbp+338h]
  int v302; // [rsp+45Ch] [rbp+33Ch]
  char v303; // [rsp+460h] [rbp+340h] BYREF
  __int64 v304; // [rsp+640h] [rbp+520h]
  __int64 v305; // [rsp+648h] [rbp+528h]
  char v306; // [rsp+650h] [rbp+530h] BYREF
  __int16 v307; // [rsp+651h] [rbp+531h]
  char v308; // [rsp+653h] [rbp+533h]
  int v309; // [rsp+654h] [rbp+534h]
  int *v310; // [rsp+670h] [rbp+550h] BYREF
  int v311; // [rsp+678h] [rbp+558h]
  GUID v312; // [rsp+67Ch] [rbp+55Ch]
  struct tm Tm; // [rsp+690h] [rbp+570h] BYREF
  unsigned __int64 v314; // [rsp+6B8h] [rbp+598h] BYREF
  unsigned __int16 v315; // [rsp+6C0h] [rbp+5A0h]
  unsigned __int16 v316; // [rsp+6C2h] [rbp+5A2h]
  unsigned __int16 v317; // [rsp+6C4h] [rbp+5A4h]
  GUID v318; // [rsp+6C8h] [rbp+5A8h] BYREF
  SOS_ExternalAutoWait *v319[2]; // [rsp+6E0h] [rbp+5C0h]
  int v320; // [rsp+6F0h] [rbp+5D0h] BYREF
  __int64 v321; // [rsp+6F8h] [rbp+5D8h]
  __int64 v322; // [rsp+700h] [rbp+5E0h]
  __int64 v323; // [rsp+708h] [rbp+5E8h]
  __int64 v324; // [rsp+710h] [rbp+5F0h]
  char v325[56]; // [rsp+718h] [rbp+5F8h] BYREF
  __int64 v326; // [rsp+750h] [rbp+630h] BYREF
  HANDLE hObject; // [rsp+760h] [rbp+640h] BYREF
  int v328; // [rsp+768h] [rbp+648h]
  PVOID Buffer; // [rsp+770h] [rbp+650h]
  __int64 v330; // [rsp+778h] [rbp+658h]
  int v331; // [rsp+780h] [rbp+660h]
  HANDLE LsaHandle; // [rsp+788h] [rbp+668h]
  int v333; // [rsp+AE8h] [rbp+9C8h]
  char v334; // [rsp+AECh] [rbp+9CCh]
  bool v335; // [rsp+AEDh] [rbp+9CDh]
  bool v336; // [rsp+AEEh] [rbp+9CEh]
  __int64 v337; // [rsp+AF0h] [rbp+9D0h] BYREF
  int v338; // [rsp+AF8h] [rbp+9D8h]
  DBID v339; // [rsp+B00h] [rbp+9E0h]
  VARIANTARG pvarg; // [rsp+B20h] [rbp+A00h] BYREF
  __int64 *v341; // [rsp+B40h] [rbp+A20h] BYREF
  int v342; // [rsp+B48h] [rbp+A28h]
  GUID v343; // [rsp+B4Ch] [rbp+A2Ch]
  __int128 v344; // [rsp+B60h] [rbp+A40h] BYREF
  int v345; // [rsp+B70h] [rbp+A50h]
  wchar_t v346; // [rsp+B74h] [rbp+A54h]
  _OWORD v347[2]; // [rsp+B78h] [rbp+A58h] BYREF
  __int64 v348; // [rsp+B98h] [rbp+A78h]
  _WORD v349[2048]; // [rsp+BA0h] [rbp+A80h] BYREF
  wchar_t Destination[4008]; // [rsp+1BA0h] [rbp+1A80h] BYREF
  wchar_t v351[4008]; // [rsp+3AF0h] [rbp+39D0h] BYREF

  v278 = -2;
  v8 = a3;
  v177 = a3;
  v186 = (struct RemSessProps *)a2;
  v199 = a6;
  v11 = 0;
  HIDWORD(v190) = 0;
  memset_0(Destination, 0, 0x1F42u);
  if ( g_statCOM != 1 && g_statCOM != 3 )
    FInitDCOM();
  _InterlockedOr(v168, 0);
  if ( g_statCOM != 1 )
    ex_raise(74, 4, 16, 1);
  if ( *((_DWORD *)s_pServerConf + 3) == 1 )
  {
    v172 = *(_QWORD *)(qword_102ECFB00 + 11728);
    *(_DWORD *)v171 = *(_DWORD *)(qword_102ECFB00 + 11736);
    ex_raise(5, 34, 16, 1, 94, L"Distributed Query or Remote Procedure Execution", *(_QWORD *)v171, v172);
  }
  if ( *(_BYTE *)(a1 + 141)
    && CPolybaseFeatureManager::IsPolybaseProvisioned((CPolybaseFeatureManager *)&g_PolybaseFeatureManager, 1)
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
    v184 = 0;
    v20 = *(unsigned __int8 *)(a2 + 8);
    v21 = (v20 & 2) != 0 || v14;
    v22 = (v20 & 1) != 0 || v8 && *(_DWORD *)(a1 + 80) == -1;
    hObject = (HANDLE)-1LL;
    v328 = 0;
    Buffer = 0;
    v330 = 0;
    v331 = 0;
    LsaHandle = (HANDLE)-1LL;
    v333 = 0;
    v334 = 0;
    v335 = v22;
    v336 = v21;
    v23 = CSECAutoImpersonateForDQ::Impersonate((CSECAutoImpersonateForDQ *)&hObject);
    v176 = v23;
    if ( !v23 && v8 && (*(_BYTE *)(a2 + 8) & 1) != 0 )
    {
      v24 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 24LL))(a1);
      v25 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 40LL))(a1);
      ex_raise(74, 13, 16, 2, v25, v24);
      v23 = v176;
    }
    v26 = 20;
    if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a1 + 56LL))(a1) )
      v26 = 23;
    v27 = 0;
    v181 = 0;
    if ( (*(_BYTE *)(a2 + 8) & 0x40) != 0 )
    {
      if ( v8 && v23 || a4 || (v28 = *(const wchar_t **)(a1 + 32), !*v28) )
      {
LABEL_56:
        v192 = 0;
        Service = COledbConnect::PdatiniGetService(v27, 1, v26);
        v192 = Service;
        v195 = 0;
        v344 = *(_OWORD *)L";PROVIDER=";
        v345 = *(_DWORD *)L"R=";
        v346 = aProvider_1[10];
        if ( CompareStringWEnglishNoCase(1u, 0, *(const wchar_t **)(a1 + 8), -1, L"MSOLEDBSQL", -1) == 2
          || CompareStringWEnglishNoCase(1u, 0, *(const wchar_t **)(a1 + 8), -1, L"MSOLEDBSQL", -1) == 2 )
        {
          v347[0] = *(_OWORD *)L";OLE DB Services=-5";
          v347[1] = *(_OWORD *)L"Services=-5";
          v348 = *(_QWORD *)L"=-5";
          v41 = -1;
          do
            ++v41;
          while ( *(_WORD *)(*(_QWORD *)(a1 + 32) + 2 * v41) );
          v42 = -1;
          do
            ++v42;
          while ( *((_WORD *)&v344 + v42) );
          v43 = -1;
          do
            ++v43;
          while ( *(_WORD *)(*(_QWORD *)(a1 + 8) + 2 * v43) );
          v44 = -1;
          do
            ++v44;
          while ( *((_WORD *)v347 + v44) );
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
          v195 = v39;
          DefaultLocale = GetDefaultLocale();
          StringCchPrintf_lW(
            v39,
            v48,
            L"%s%s%s%s",
            DefaultLocale,
            *(_QWORD *)(a1 + 32),
            &v344,
            *(_QWORD *)(a1 + 8),
            v347);
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
          while ( *((_WORD *)&v344 + v32) );
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
          v195 = v39;
          v40 = GetDefaultLocale();
          StringCchPrintf_lW(v39, v37, L"%s%s%s", v40, *(_QWORD *)(a1 + 32), &v344, *(_QWORD *)(a1 + 8));
        }
        v194 = 0;
        v11 = ((__int64 (__fastcall *)(struct IDataInitialize *, _QWORD, __int64, wchar_t *, GUID *, __int64 *))Service->lpVtbl->GetDataSource)(
                Service,
                0,
                23,
                v39,
                &IID_IUnknown,
                &v194);
        if ( v194 )
        {
          v51 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
          v52 = *(_QWORD *)(v51 + 256);
          if ( !v52 )
          {
            SystemThread::MakeMiniSOSThread(0);
            v52 = *(_QWORD *)(v51 + 256);
          }
          v53 = *(_QWORD *)(v52 + 992);
          ClientProcessGlobals = (PerProcessGlobals *)SOS_OS::GetClientProcessGlobals(v52);
          PerProcessGlobals::GetDefaultMemoryClerksForNode(ClientProcessGlobals, *(_WORD *)(v53 + 160));
          SOS_OS::GetClientProcessGlobals(v55);
          LOWORD(dwCount[0]) = 128;
          MemObject = (struct IMemObj *)MemoryObjectFactory::CreateMemObject(103);
          if ( !MemObject )
          {
            LOBYTE(v56) = 65;
            ex_raise_oom(v56);
          }
          Source = (wchar_t *)MemObject;
          v179 = 3581;
          v58 = (struct IUnknown *)operator new(0x60u, MemObject, "sql\\ntdbms\\msql\\utils\\oledbconn.cpp", 3581, 3u);
          v197 = (struct IDataInitialize *)v58;
          if ( v58 )
          {
            v59 = *(_OWORD *)(a1 + 16);
            v60 = COledbConnect::FSupportsUms((COledbConnect *)a1);
            v61 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 40LL))(a1);
            v62 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 24LL))(a1);
            v280 = v59;
            IWrapInterface<IDBCreateSession>::IWrapInterface<IDBCreateSession>(
              (_DWORD)v58,
              (_DWORD)MemObject,
              v194,
              (unsigned int)&v280,
              v62,
              v61,
              !v60);
            v58->lpVtbl = (struct IUnknownVtbl *)&CWrapIGetDataSource::`vftable';
            (*((void (__fastcall **)(struct IUnknownVtbl *))v58[3].lpVtbl->QueryInterface + 2))(v58[3].lpVtbl);
          }
          else
          {
            v58 = 0;
          }
          v181 = v58;
          v39 = v195;
        }
        operator delete[](v39);
        ((void (__fastcall *)(struct IDataInitialize *))Service->lpVtbl->Release)(Service);
        v8 = v177;
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
          v63 = &g_clsfacLuxor;
          v11 = (int)g_hrLuxorFactory;
        }
        else
        {
          v11 = dword_103082150;
          v63 = (struct IClassFactory **)&unk_103082140;
        }
        if ( v11 >= 0 )
        {
          v196 = 0;
          v11 = ((__int64 (__fastcall *)(struct IClassFactory *, _QWORD, GUID *, __int64 *))(*v63)->lpVtbl->CreateInstance)(
                  *v63,
                  0,
                  &IID_IDBInitialize,
                  &v196);
          if ( v196 )
          {
            v64 = SystemThread_TlsIndex;
            v65 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                + SystemThread_TlsOffset;
            v66 = *(_QWORD *)(v65 + 256);
            if ( !v66 )
            {
              SystemThread::MakeMiniSOSThread(0);
              v66 = *(_QWORD *)(v65 + 256);
            }
            v67 = *(_QWORD *)(v66 + 992);
            v68 = (PerProcessGlobals *)SOS_OS::GetClientProcessGlobals(v64);
            PerProcessGlobals::GetDefaultMemoryClerksForNode(v68, *(_WORD *)(v67 + 160));
            SOS_OS::GetClientProcessGlobals(v69);
            LOWORD(dwCount[0]) = 128;
            v71 = (struct IMemObj *)MemoryObjectFactory::CreateMemObject(104);
            if ( !v71 )
            {
              LOBYTE(v70) = 65;
              ex_raise_oom(v70);
            }
            Source = (wchar_t *)v71;
            v179 = 3617;
            v72 = (struct IUnknown *)operator new(0x60u, v71, "sql\\ntdbms\\msql\\utils\\oledbconn.cpp", 3617, 3u);
            v192 = v72;
            if ( v72 )
            {
              v73 = *(_OWORD *)(a1 + 16);
              v74 = COledbConnect::FSupportsUms((COledbConnect *)a1);
              v75 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 40LL))(a1);
              v76 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 24LL))(a1);
              v281 = v73;
              IWrapInterface<ISchemaLock>::IWrapInterface<ISchemaLock>(
                (_DWORD)v72,
                (_DWORD)v71,
                v196,
                (unsigned int)&v281,
                v76,
                v75,
                !v74);
              v72->lpVtbl = (struct IUnknownVtbl *)&CWrapIDBInitialize::`vftable';
              (*((void (__fastcall **)(struct IUnknownVtbl *))v72[3].lpVtbl->QueryInterface + 2))(v72[3].lpVtbl);
            }
            else
            {
              v72 = 0;
            }
            v181 = v72;
          }
        }
      }
      else
      {
        v77 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 24LL))(a1);
        ex_raise(74, 30, 16, 3, v77);
      }
    }
    else
    {
      v318 = IID_IUnknown;
      v217.pIID = &v318;
      v217.pItf = 0;
      v217.hr = 0;
      v78 = 0;
      v197 = 0;
      if ( (*(_BYTE *)(a1 + 149) & 4) != 0
        && (v79 = COledbConnect::PdatiniGetService(0, 0, v26), v78 = v79, (v197 = v79) != 0) )
      {
        v80 = ((__int64 (__fastcall *)(struct IDataInitialize *, __int64, _QWORD, __int64, _QWORD, _QWORD, int, MULTI_QI *))v79->lpVtbl->CreateDBInstanceEx)(
                v79,
                a1 + 16,
                0,
                23,
                0,
                0,
                1,
                &v217);
      }
      else
      {
        v80 = CoCreateInstanceEx((const IID *const)(a1 + 16), 0, v26, 0, 1u, &v217);
      }
      v11 = v80;
      if ( v217.pItf )
      {
        v81 = SystemThread_TlsIndex;
        v82 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        v83 = *(_QWORD *)(v82 + 256);
        if ( !v83 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v83 = *(_QWORD *)(v82 + 256);
        }
        v84 = *(_QWORD *)(v83 + 992);
        v85 = (PerProcessGlobals *)SOS_OS::GetClientProcessGlobals(v81);
        PerProcessGlobals::GetDefaultMemoryClerksForNode(v85, *(_WORD *)(v84 + 160));
        SOS_OS::GetClientProcessGlobals(v86);
        LOWORD(dwCount[0]) = 128;
        v88 = (struct IMemObj *)MemoryObjectFactory::CreateMemObject(104);
        if ( !v88 )
        {
          LOBYTE(v87) = 65;
          ex_raise_oom(v87);
        }
        Source = (wchar_t *)v88;
        v179 = 3669;
        v89 = (struct IUnknown *)operator new(0x60u, v88, "sql\\ntdbms\\msql\\utils\\oledbconn.cpp", 3669, 3u);
        v192 = v89;
        if ( v89 )
        {
          v90 = *(_OWORD *)(a1 + 16);
          v91 = COledbConnect::FSupportsUms((COledbConnect *)a1);
          v92 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 40LL))(a1);
          v93 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 24LL))(a1);
          v282 = v90;
          IWrapInterface<ISchemaLock>::IWrapInterface<ISchemaLock>(
            (_DWORD)v89,
            (_DWORD)v88,
            v217.pItf,
            (unsigned int)&v282,
            v93,
            v92,
            !v91);
          v89->lpVtbl = (struct IUnknownVtbl *)&CWrapIDBInitialize::`vftable';
          (*((void (__fastcall **)(struct IUnknownVtbl *))v89[3].lpVtbl->QueryInterface + 2))(v89[3].lpVtbl);
        }
        else
        {
          v89 = 0;
        }
        v181 = v89;
        v78 = v197;
      }
      if ( v78 )
        ((void (__fastcall *)(struct IDataInitialize *))v78->lpVtbl->Release)(v78);
    }
    if ( (dword_102EDC9F8 & 0x10000) != 0 )
    {
      v286 = 0x40000;
      v287 = 0;
      v288 = &v291;
      v289 = &v303;
      v304 = 0;
      v290 = 0;
      v305 = 0;
      v291 = &v306;
      v292 = 32;
      v293 = 3;
      v294 = 0;
      v295 = 0;
      v296 = 4;
      v297 = 0;
      v298 = 0;
      v299 = 5;
      v300 = &Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
      v301 = 16;
      v302 = 6;
      v306 = v8;
      v94 = a7;
      v307 = a7;
      v308 = a5;
      v309 = v11;
      v95 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 40LL))(a1);
      v96 = (char *)v95;
      if ( v95 )
      {
        v97 = -1;
        do
          ++v97;
        while ( *(_WORD *)(v95 + 2 * v97) );
        v98 = 2 * v97;
      }
      else
      {
        v98 = 0;
      }
      v99 = v288;
      v288[2] = v96;
      *((_DWORD *)v99 + 6) = v98;
      *((_DWORD *)v99 + 7) = 4;
      v100 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 24LL))(a1);
      v101 = (char *)v100;
      if ( v100 )
      {
        v102 = -1;
        do
          ++v102;
        while ( *(_WORD *)(v100 + 2 * v102) );
        v103 = 2 * v102;
      }
      else
      {
        v103 = 0;
      }
      v104 = v288;
      v288[4] = v101;
      *((_DWORD *)v104 + 10) = v103;
      *((_DWORD *)v104 + 11) = 5;
      v105 = v288;
      v288[6] = (char *)(a1 + 16);
      *((_DWORD *)v105 + 14) = 16;
      *((_DWORD *)v105 + 15) = 6;
      XeSqlPkg::oledb_provider_initialized::Publish((XeSqlPkg::oledb_provider_initialized *)v285);
    }
    else
    {
      v94 = a7;
    }
    if ( v11 < 0 )
    {
      _mm_lfence();
      v106 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 40LL))(a1);
      v107 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 24LL))(a1);
      v266 = 0;
      v267 = &IID_IUnknown;
      v268 = 0;
      v269 = v107;
      v270 = v106;
      v271 = 0;
      v272 = 0;
      v273 = 0;
      v274 = -1;
      v275 = 0;
      v276 = 0;
      v277 &= ~1u;
      ex_raise(73, 2, 16, 1, v107, v106);
      operator delete[](0);
    }
    v204 = 0;
    Interface = COledbConnect::GetInterface((COledbConnect *)a1, &IID_IDBProperties, v181, &IID_IUnknown, 1);
    v109 = Interface;
    v204 = Interface;
    if ( (*((_BYTE *)v186 + 8) & 0x40) == 0 || v176 )
    {
LABEL_169:
      v116 = 0;
      v182 = 0;
      v180 = 0;
      v178 = 0;
      switch ( v94 )
      {
        case 1:
          if ( byte_102EDCD2D )
          {
            v117 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                 + SystemThread_TlsOffset;
            v118 = *(_QWORD *)(v117 + 256);
            if ( !v118 )
            {
              SystemThread::MakeMiniSOSThread(0);
              v118 = *(_QWORD *)(v117 + 256);
            }
            pResults = (MULTI_QI *)&v178;
            *(_QWORD *)dwCount = &v180;
            if ( (int)COledbConnect::ModifyAndResignToken(
                        a1,
                        *(_QWORD *)(v118 + 1000),
                        *v199,
                        (unsigned int)&v182,
                        (__int64)&v180,
                        (__int64)&v178) < 0 )
              ex_raise(74, 41, 16, 2);
            v116 = v182;
          }
          else
          {
            v116 = *v199;
          }
          break;
        case 4:
          v200 = 0;
          v198 = 0;
          v283 = Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
          v119 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
          v120 = *(_QWORD *)(v119 + 256);
          if ( !v120 )
          {
            SystemThread::MakeMiniSOSThread(0);
            v120 = *(_QWORD *)(v119 + 256);
          }
          if ( (unsigned int)JSONWebTokenService::GetTenantUri(*(struct IMemObj **)(v120 + 1000), 0, 0, 0, 0, &v283, 0) )
            ex_raise(74, 41, 16, 3);
          v121 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
          v122 = *(_QWORD *)(v121 + 256);
          if ( !v122 )
          {
            SystemThread::MakeMiniSOSThread(0);
            v122 = *(_QWORD *)(v121 + 256);
          }
          v123 = (*(__int64 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, _QWORD, void **, _QWORD))(*(_QWORD *)s_pServerConf + 528LL))(
                   s_pServerConf,
                   L"FederatedAuthentication",
                   L"ServicePrincipalName",
                   *(_QWORD *)(v122 + 1000),
                   &v230,
                   0);
          v124 = v230;
          if ( !v123 )
            v124 = 0;
          v279 = v124;
          v125 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
          v126 = *(_QWORD *)(v125 + 256);
          if ( !v126 )
          {
            SystemThread::MakeMiniSOSThread(0);
            v126 = *(_QWORD *)(v125 + 256);
          }
          v175 = (__int64)&v198;
          *(_QWORD *)v174 = &v314;
          rguid = (GUID *)&v178;
          v172 = (__int64)v229;
          *(_QWORD *)v171 = &v182;
          pResults = (MULTI_QI *)&Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
          *(_QWORD *)dwCount = v124;
          v127 = v200;
          AccessTokenForApplicationUsingSecret = JSONWebTokenService::GetAccessTokenForApplicationUsingSecret(
                                                   *(_QWORD *)(v126 + 1000),
                                                   *((_QWORD *)v186 + 4),
                                                   *((_QWORD *)v186 + 5),
                                                   (_DWORD)v200,
                                                   (__int64)v124,
                                                   (__int64)&Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val,
                                                   (__int64)&v182,
                                                   (__int64)v229,
                                                   (__int64)&v178,
                                                   (__int64)&v314,
                                                   (__int64)&v198);
          v129 = v198;
          if ( AccessTokenForApplicationUsingSecret )
          {
            if ( ((AccessTokenForApplicationUsingSecret + 895352831) & 0xFFFFFFF7) != 0 )
            {
              ex_raise(74, 41, 16, 4);
            }
            else
            {
              v349[0] = 0;
              if ( v198 )
              {
                v130 = 2048;
                v131 = v349;
                while ( v130 != -2147481598 )
                {
                  v132 = *(_WORD *)((char *)v131 + v129 - (_BYTE *)v349);
                  if ( !v132 )
                    break;
                  *v131++ = v132;
                  if ( !--v130 )
                  {
                    --v131;
                    break;
                  }
                }
                *v131 = 0;
              }
              ex_raise(74, 45, 16, 1, v349);
            }
          }
          Tm.tm_sec = v317;
          Tm.tm_min = v316;
          Tm.tm_hour = v315;
          Tm.tm_mday = HIWORD(v314);
          Tm.tm_mon = WORD1(v314) - 1;
          Tm.tm_year = (unsigned __int16)v314 - 1900;
          Tm.tm_isdst = -1;
          v133 = _mktime64(&Tm);
          v116 = v182;
          v180 = v133;
          operator delete[](v124);
          operator delete[](v129);
          operator delete[](v127);
          break;
        case 3:
          v202 = 0;
          LODWORD(v193) = 0;
          v201 = 0;
          LODWORD(v190) = 0;
          *(GUID *)v284 = Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
          v134 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
          v135 = *(_QWORD *)(v134 + 256);
          if ( !v135 )
          {
            SystemThread::MakeMiniSOSThread(0);
            v135 = *(_QWORD *)(v134 + 256);
          }
          if ( (unsigned int)JSONWebTokenService::GetAccessTokenForAADTenantSpecificSQLServicePrincipal(
                               *(struct IMemObj **)(v135 + 1000),
                               0,
                               0,
                               0,
                               (__int64)&v182,
                               (__int64)&v193,
                               (__int64)&v326,
                               (__int64)&v201,
                               (__int64)&v190,
                               (__int64)&v178,
                               (__int64)&v202,
                               0,
                               (__int64)v284,
                               0,
                               0,
                               0) )
            ex_raise(74, 41, 16, v178 + 10);
          v116 = v182;
          operator delete[]((void *)v201);
          operator delete[]((void *)v202);
          break;
      }
      v136 = *((_BYTE *)v186 + 8);
      LOBYTE(v172) = (v136 & 2) != 0;
      v171[0] = (v136 & 0x40) != 0;
      LOBYTE(pResults) = v136 & 1;
      v137 = COledbConnect::SetINITProps(
               a1,
               v109,
               *((_QWORD *)v186 + 4),
               *((_QWORD *)v186 + 5),
               v116,
               (_DWORD)pResults,
               *(_DWORD *)v171,
               v172,
               v94);
      if ( v137 < 0 )
      {
        _mm_lfence();
        v138 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 40LL))(a1);
        v139 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 24LL))(a1);
        v233[0] = v109;
        v233[1] = &IID_IDBProperties;
        v234 = v137;
        v235 = v139;
        v236 = v138;
        v237 = 0;
        v238 = 0;
        v239 = 0;
        v240 = -1;
        v241 = 0;
        v242 = 0;
        v243 &= ~1u;
        if ( COledbError::FPrintSQLServerError((COledbError *)v233) )
          ex_raise(73, 73, 25, 1);
        COledbError::PrintMsgUsingHRESULT((COledbError *)v233);
        ex_raise(73, 73, 16, 2, v235, v236);
        operator delete[](v237);
      }
      v140 = *(const wchar_t **)(a1 + 40);
      if ( !v140 )
      {
        v140 = *(const wchar_t **)(a1 + 128);
        if ( !v140 )
          v140 = *(const wchar_t **)(a1 + 8);
      }
      wcsncpy_s(Destination, 0xFA1u, v140, 0xFA0u);
      Destination[4000] = 0;
      v203 = 0;
      v141 = COledbConnect::GetInterface((COledbConnect *)a1, &IID_IDBInitialize, v181, &IID_IUnknown, 1);
      v203 = v141;
      v185 = 0;
      ((void (__fastcall *)(struct IUnknown *, GUID *, __int64 *))v141->lpVtbl->QueryInterface)(
        v141,
        &IID_ISSAsynchStatus,
        &v185);
      v319[1] = 0;
      v320 = 4194508;
      v321 = 0;
      v323 = 0;
      v322 = 0;
      v324 = 0;
      v319[0] = (SOS_ExternalAutoWait *)&v320;
      v319[1] = SOS_ExternalAutoWait::SOS_ExternalAutoWait((SOS_ExternalAutoWait *)v325, (struct SOS_WaitInfo *)&v320);
      Source = Destination;
      v142 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v143 = *(_QWORD *)(v142 + 256);
      if ( !v143 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v143 = *(_QWORD *)(v142 + 256);
      }
      memcpy_s((void *const)(v143 + 3128), 0x1Eu, &Source, 8u);
      v144 = ((__int64 (__fastcall *)(struct IUnknown *))v141->lpVtbl[1].QueryInterface)(v141);
      if ( v319[1] )
      {
        v145 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        v146 = *(_QWORD *)(v145 + 256);
        if ( !v146 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v146 = *(_QWORD *)(v145 + 256);
        }
        *(_QWORD *)(v146 + 3128) = 0;
        SOS_ExternalAutoWait::~SOS_ExternalAutoWait(v319[1]);
      }
      if ( v144 == 265936 )
      {
        v147 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v185 + 40LL))(v185, 0xFFFFFFFFLL);
        v148 = v185;
        v185 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v148 + 16LL))(v148);
        if ( v147 < 0 )
          goto LABEL_223;
      }
      else if ( v144 < 0 )
      {
LABEL_223:
        v149 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 40LL))(a1);
        v150 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 24LL))(a1);
        v206[0] = v141;
        v206[1] = &IID_IDBInitialize;
        v207 = v144;
        v208 = v150;
        v209 = v149;
        v210 = 0;
        v211 = 0;
        v212 = 0;
        v213 = -1;
        v214 = 0;
        v215 = 0;
        v216 &= ~1u;
        v151 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 88LL))(a1);
        v216 ^= (v216 ^ v151) & 1;
        if ( COledbError::FPrintSQLServerError((COledbError *)v206) )
        {
          if ( (v216 & 1) != 0 )
            COledbError::SendOriginalErrorInStretchTelemetry(v206, 0);
          ex_raise(73, 3, 25, 1);
        }
        COledbError::PrintMsgUsingHRESULT((COledbError *)v206);
        memset_0(v351, 0, 0x1F42u);
        if ( v207 == -2147217887 )
        {
          COledbError::GatherPropsInError((COledbError *)v206, &v191, &v231);
          dwCount[0] = 4001;
          v152 = v231;
          v153 = v191;
          COledbError::CwchFormatPropertyUser((COledbError *)v206, v191, v231, v351, *(rsize_t *)dwCount);
          if ( (_DWORD)v153 )
          {
            p_bstrVal = &v152->vValue.bstrVal;
            do
            {
              if ( *((_WORD *)p_bstrVal - 4) == 8 )
                SysFreeString(*p_bstrVal);
              p_bstrVal += 9;
              --v153;
            }
            while ( v153 );
          }
          TaskFree(v152);
        }
        ex_raise(73, 3, 16, 1, v208, v209);
        operator delete[](v210);
      }
      v203 = 0;
      ((void (__fastcall *)(struct IUnknown *))v141->lpVtbl->Release)(v141);
      v204 = 0;
      ((void (__fastcall *)(struct IUnknown *))v109->lpVtbl->Release)(v109);
      v205 = 0;
      v155 = v181;
      v156 = COledbConnect::GetInterface((COledbConnect *)a1, &IID_IDBCreateSession, v181, &IID_IUnknown, 1);
      v205 = v156;
      v181 = 0;
      ((void (__fastcall *)(struct IUnknown *))v155->lpVtbl->Release)(v155);
      v157 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, GUID *, struct IUnknown **))v156->lpVtbl[1].QueryInterface)(
               v156,
               0,
               &IID_IUnknown,
               &v184);
      if ( v157 < 0 )
      {
        _mm_lfence();
        v158 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 40LL))(a1);
        v159 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 24LL))(a1);
        v218[0] = v156;
        v218[1] = &IID_IDBCreateSession;
        v219 = v157;
        v220 = v159;
        v221 = v158;
        v222 = 0;
        v223 = 0;
        v224 = 0;
        v225 = -1;
        v226 = 0;
        v227 = 0;
        v228 &= ~1u;
        LOBYTE(v158) = v228;
        v228 = v158 ^ (v158 ^ (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 88LL))(a1)) & 1;
        if ( COledbError::FPrintSQLServerError((COledbError *)v218) )
        {
          if ( (v228 & 1) != 0 )
            COledbError::SendOriginalErrorInStretchTelemetry(v218, 0);
          ex_raise(73, 4, 25, 1);
        }
        COledbError::PrintMsgUsingHRESULT((COledbError *)v218);
        ex_raise(73, 4, 16, 2, v220, v221);
        operator delete[](v222);
      }
      v205 = 0;
      ((void (__fastcall *)(struct IUnknown *))v156->lpVtbl->Release)(v156);
      v160 = *(_QWORD *)&CLSID_MSOLEDBSQL.Data1;
      v161 = *(_QWORD *)CLSID_MSOLEDBSQL.Data4;
      if ( *(_QWORD *)&CLSID_MSOLEDBSQL.Data1 == *(_QWORD *)(a1 + 16)
        && *(_QWORD *)CLSID_MSOLEDBSQL.Data4 == *(_QWORD *)(a1 + 24)
        || *(_QWORD *)(a1 + 16) == 0x45EB837A726D00DELL && *(_QWORD *)(a1 + 24) == 0x9C07F941D2ED8CAEuLL )
      {
        v232 = 0;
        v162 = COledbConnect::GetInterface((COledbConnect *)a1, &IID_ISessionProperties, v184, &IID_IUnknown, 1);
        v232 = v162;
        v337 = 3;
        v338 = 0;
        v339 = DB_NULLID;
        VariantInit(&pvarg);
        pvarg.vt = 11;
        pvarg.iVal = -1;
        v341 = &v337;
        v342 = 1;
        v343 = DBPROPSET_SQLSERVERSESSION;
        v163 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, __int64 **))v162->lpVtbl[1].AddRef)(v162, 1, &v341);
        if ( v163 < 0 )
        {
          _mm_lfence();
          v164 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 40LL))(a1);
          v165 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 24LL))(a1);
          v255[0] = v162;
          v255[1] = &IID_ISessionProperties;
          v256 = v163;
          v257 = v165;
          v258 = v164;
          v259 = 0;
          v260 = 0;
          v261 = 0;
          v262 = -1;
          v263 = 0;
          v264 = 0;
          v265 &= ~1u;
          if ( COledbError::FPrintSQLServerError((COledbError *)v255) )
            ex_raise(73, 74, 25, 1);
          COledbError::PrintMsgUsingHRESULT((COledbError *)v255);
          ex_raise(73, 74, 16, 2, v257, v258);
          operator delete[](v259);
        }
        COledbConnect::GenerateWaitMessageForSpid((COledbConnect *)a1, v184, Destination, 0xFA1u);
        ((void (__fastcall *)(struct IUnknown *))v162->lpVtbl->Release)(v162);
        v161 = *(_QWORD *)CLSID_MSOLEDBSQL.Data4;
        v160 = *(_QWORD *)&CLSID_MSOLEDBSQL.Data1;
      }
      v166 = 0;
      if ( v160 == *(_QWORD *)(a1 + 16) && v161 == *(_QWORD *)(a1 + 24)
        || *(_QWORD *)(a1 + 16) == 0x45EB837A726D00DELL && *(_QWORD *)(a1 + 24) == 0x9C07F941D2ED8CAEuLL )
      {
        v179 = 0;
        if ( COledbConnect::FIsSQLServer((COledbConnect *)a1, v184, &v179) && v179 >= 7 )
          v166 = 1;
      }
      Session = CRemSess::MakeSession(v186, v184, Destination, v166, v180);
      if ( v185 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v185 + 16LL))(v185);
      operator delete[]((void *)v182);
      CSECAutoImpersonateForDQ::Revert((CSECAutoImpersonateForDQ *)&hObject);
      if ( v333 )
      {
        intnl_revert_to_self(
          *(struct CSession **)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                          + SystemThread_TlsOffset)
                              + 72LL),
          1);
        v333 = 0;
      }
      CAutoLogin::Revert((CAutoLogin *)&hObject);
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hObject);
      if ( (_DWORD)v330 )
        LsaFreeReturnBuffer(Buffer);
      if ( (char *)LsaHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        LsaDeregisterLogonProcess(LsaHandle);
      if ( v184 )
        ((void (__fastcall *)(struct IUnknown *))v184->lpVtbl->Release)(v184);
      return Session;
    }
    v188 = 7;
    v310 = &v188;
    v311 = 1;
    v312 = DBPROPSET_DBINIT;
    v189 = 0;
    v183 = 0;
    v110 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, int **, int *, void ***))Interface->lpVtbl[1].QueryInterface)(
             Interface,
             1,
             &v310,
             &v189,
             &v183);
    v111 = v183;
    if ( (int)(v110 + 0x80000000) < 0 || v110 == -2147217887 )
    {
      if ( !v183 )
      {
LABEL_159:
        v112 = (*(__int64 (__fastcall **)(__int64, void **))(*(_QWORD *)a1 + 40LL))(a1, v111);
        v113 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 24LL))(a1);
        v244[0] = v109;
        v244[1] = &IID_IDBProperties;
        v245 = v110;
        v246 = v113;
        v247 = v112;
        v248 = 0;
        v249 = 0;
        v250 = 0;
        v251 = -1;
        v252 = 0;
        v253 = 0;
        v254 &= ~1u;
        if ( COledbError::FPrintSQLServerError((COledbError *)v244) )
          ex_raise(73, 72, 25, 1);
        COledbError::PrintMsgUsingHRESULT((COledbError *)v244);
        ex_raise(73, 72, 16, 2, v246, v247);
        operator delete[](v248);
        v111 = v183;
        goto LABEL_162;
      }
      if ( *((_DWORD *)v183 + 2) == 1 )
      {
LABEL_162:
        v114 = (VARIANTARG *)((char *)*v111 + 48);
        if ( *((_DWORD *)*v111 + 2) || (v115 = 1, !v114->vt) )
          v115 = 0;
        if ( *((_DWORD *)v111 + 2) )
        {
          VariantClear(v114);
          v111 = v183;
        }
        TaskFree(*v111);
        TaskFree(v183);
        if ( v115 )
          ex_raise(74, 9, 16, 1);
        goto LABEL_169;
      }
    }
    if ( v183 )
    {
      if ( *v183 )
      {
        TaskFree(*v183);
        v111 = v183;
      }
      TaskFree(v111);
    }
    goto LABEL_159;
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
