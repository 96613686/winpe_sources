# login(IMemObj *,CBatch *,CConnection *,SNI_Conn *,CRoutingEnvChangeInfo *)

- ea: `0x100555e20`
- end: `0x100555e65`
- name: `?login@@YAJPEAVIMemObj@@PEAVCBatch@@PEAVCConnection@@PEAVSNI_Conn@@PEAVCRoutingEnvChangeInfo@@@Z`
- size: `69`
- prototype: `__int64 __fastcall(struct IMemObj *, struct CBatch *, struct CConnection *, struct SNI_Conn *, struct CRoutingEnvChangeInfo *)`
- caller_count: `1`
- callee_count: `90`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x100555dc0`

## callees

- `0x100401070`
- `0x100401090`
- `0x1004012d0`
- `0x100401340`
- `0x100401a90`
- `0x1004026b0`
- `0x1004036c0`
- `0x1004036f0`
- `0x1004039b0`
- `0x100403a10`
- `0x100403ba0`
- `0x100403f50`
- `0x100404500`
- `0x100404720`
- `0x100405480`
- `0x1004054f0`
- `0x100407ca0`
- `0x100409a70`
- `0x100409b70`
- `0x10040be50`
- `0x10041154d`
- `0x10041a970`
- `0x10041e0c0`
- `0x100431a00`
- `0x1004328c0`
- `0x100432a80`
- `0x1004339a0`
- `0x100435080`
- `0x100435220`
- `0x100435320`
- `0x100437a20`
- `0x10045c260`
- `0x100536250`
- `0x10054cf00`
- `0x10054cf90`
- `0x10054d070`
- `0x10054e6e0`
- `0x10054eec0`
- `0x10054f090`
- `0x10054fad0`
- `0x10054fe20`
- `0x1005503f0`
- `0x100550410`
- `0x100550650`
- `0x100555e20`
- `0x1005565a0`
- `0x100556620`
- `0x100556ce0`
- `0x100556d60`
- `0x100558eb0`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x10054a824`
- `KERNEL32!QueryPerformanceCounter` at `0x10054ab67`
- `KERNEL32!QueryPerformanceCounter` at `0x10054b1ff`
- `KERNEL32!QueryPerformanceCounter` at `0x10054b2a8`
- `KERNEL32!QueryPerformanceCounter` at `0x10054b36f`
- `KERNEL32!QueryPerformanceCounter` at `0x10054b402`
- `KERNEL32!QueryPerformanceCounter` at `0x10054b4c9`
- `KERNEL32!QueryPerformanceCounter` at `0x100f27cbd`
- `KERNEL32!QueryPerformanceCounter` at `0x100f2a26d`
- `KERNEL32!QueryPerformanceCounter` at `0x100f2a4a0`
- `KERNEL32!QueryPerformanceCounter` at `0x100f2a5d9`
- `KERNEL32!QueryPerformanceCounter` at `0x100f2a6fd`
- `KERNEL32!QueryPerformanceCounter` at `0x100f2aba9`
- `KERNEL32!QueryPerformanceCounter` at `0x10054a824`
- `KERNEL32!QueryPerformanceCounter` at `0x10054ab67`
- `KERNEL32!QueryPerformanceCounter` at `0x10054b1ff`
- `KERNEL32!QueryPerformanceCounter` at `0x10054b2a8`
- `KERNEL32!QueryPerformanceCounter` at `0x10054b36f`
- `KERNEL32!QueryPerformanceCounter` at `0x10054b402`
- `KERNEL32!QueryPerformanceCounter` at `0x10054b4c9`
- `KERNEL32!QueryPerformanceCounter` at `0x100f27cbd`
- `KERNEL32!QueryPerformanceCounter` at `0x100f2a26d`
- `KERNEL32!QueryPerformanceCounter` at `0x100f2a4a0`
- `KERNEL32!QueryPerformanceCounter` at `0x100f2a5d9`
- `KERNEL32!QueryPerformanceCounter` at `0x100f2a6fd`
- `KERNEL32!QueryPerformanceCounter` at `0x100f2aba9`
- `ADVAPI32!GetLengthSid` at `0x100f2821d`
- `ADVAPI32!GetLengthSid` at `0x100f2821d`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x10054a7e5`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x100f2ab17`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x10054a6f8`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x10054b0b6`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x100f28cae`
- `sqldk!?SOS_OS_OsInfo@@3VOsInfo@@A` at `0x100f28188`
- `sqldk!?SOS_OS_OsInfo@@3VOsInfo@@A` at `0x100f2819e`
- `sqldk!?SOS_OS_OsInfo@@3VOsInfo@@A` at `0x100f28302`
- `sqldk!?SOS_OS_OsInfo@@3VOsInfo@@A` at `0x100f28314`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10054a873`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10054abfa`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10054b251`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10054b333`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10054b3c1`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10054b48d`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10054b518`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x100f2a2f8`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x100f2a4f2`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x100f2a664`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x100f2a788`
- `sqldk!?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A` at `0x100f2abca`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10054a804`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10054ab47`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10054b1df`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10054b288`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10054b34f`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10054b3e2`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10054b4a9`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100f2a24d`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100f2a480`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100f2a5b3`
- `sqldk!?GetContainerType@OsInfo@@QEBA?BW4ContainerType@@XZ` at `0x100f2818f`
- `sqldk!?GetContainerType@OsInfo@@QEBA?BW4ContainerType@@XZ` at `0x100f281a5`
- `sqldk!?GetContainerType@OsInfo@@QEBA?BW4ContainerType@@XZ` at `0x100f28309`
- `sqldk!?GetContainerType@OsInfo@@QEBA?BW4ContainerType@@XZ` at `0x100f2831b`
- `sqldk!?GetContainerType@OsInfo@@QEBA?BW4ContainerType@@XZ` at `0x100f2818f`
- `sqldk!?GetContainerType@OsInfo@@QEBA?BW4ContainerType@@XZ` at `0x100f281a5`
- `sqldk!?GetContainerType@OsInfo@@QEBA?BW4ContainerType@@XZ` at `0x100f28309`
- `sqldk!?GetContainerType@OsInfo@@QEBA?BW4ContainerType@@XZ` at `0x100f2831b`
- `sqldk!?hdl_prntbackout@@YAHHHHHPEAD@Z` at `0x10054a529`
- `sqldk!?ex_trans_cexcept@@YAXIPEAU_EXCEPTION_POINTERS@@@Z` at `0x10054a50c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100f284e0`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100f284e0`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100f28b94`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100f28b94`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x100f2aac7`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x100f2aac7`
- `sqldk!SystemThread_TlsIndex` at `0x10054a1c2`
- `sqldk!SystemThread_TlsIndex` at `0x10054a359`
- `sqldk!SystemThread_TlsIndex` at `0x10054a417`
- `sqldk!SystemThread_TlsIndex` at `0x10054a4d7`
- `sqldk!SystemThread_TlsIndex` at `0x10054ac4b`
- `sqldk!SystemThread_TlsIndex` at `0x10054ad42`
- `sqldk!SystemThread_TlsIndex` at `0x10054b080`
- `sqldk!SystemThread_TlsIndex` at `0x10054b0d1`
- `sqldk!SystemThread_TlsIndex` at `0x10054b1ae`
- `sqldk!SystemThread_TlsIndex` at `0x10054b545`
- `sqldk!SystemThread_TlsIndex` at `0x10054b690`
- `sqldk!SystemThread_TlsIndex` at `0x10054b6e2`
- `sqldk!SystemThread_TlsIndex` at `0x10054b72d`
- `sqldk!SystemThread_TlsIndex` at `0x10054b784`
- `sqldk!SystemThread_TlsIndex` at `0x100f27e61`
- `sqldk!SystemThread_TlsIndex` at `0x100f2804b`
- `sqldk!SystemThread_TlsIndex` at `0x100f280c7`
- `sqldk!SystemThread_TlsIndex` at `0x100f2879e`
- `sqldk!SystemThread_TlsIndex` at `0x100f28d42`
- `sqldk!SystemThread_TlsIndex` at `0x100f2a21c`
- `sqldk!SystemThread_TlsIndex` at `0x100f2a982`
- `sqldk!SystemThread_TlsOffset` at `0x10054a1cb`
- `sqldk!SystemThread_TlsOffset` at `0x10054a36a`
- `sqldk!SystemThread_TlsOffset` at `0x10054a420`
- `sqldk!SystemThread_TlsOffset` at `0x10054a4e0`
- `sqldk!SystemThread_TlsOffset` at `0x10054ac54`
- `sqldk!SystemThread_TlsOffset` at `0x10054ad4b`
- `sqldk!SystemThread_TlsOffset` at `0x10054b089`
- `sqldk!SystemThread_TlsOffset` at `0x10054b0da`
- `sqldk!SystemThread_TlsOffset` at `0x10054b1b7`
- `sqldk!SystemThread_TlsOffset` at `0x10054b54e`
- `sqldk!SystemThread_TlsOffset` at `0x10054b699`
- `sqldk!SystemThread_TlsOffset` at `0x10054b6f3`
- `sqldk!SystemThread_TlsOffset` at `0x10054b736`
- `sqldk!SystemThread_TlsOffset` at `0x10054b78d`
- `sqldk!SystemThread_TlsOffset` at `0x100f27e6a`
- `sqldk!SystemThread_TlsOffset` at `0x100f28054`
- `sqldk!SystemThread_TlsOffset` at `0x100f280d0`
- `sqldk!SystemThread_TlsOffset` at `0x100f287a7`
- `sqldk!SystemThread_TlsOffset` at `0x100f28d4b`
- `sqldk!SystemThread_TlsOffset` at `0x100f2a225`
- `sqldk!SystemThread_TlsOffset` at `0x100f2a98b`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100f28c96`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100f2910c`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100f29570`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100f2aa93`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100f28c96`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100f2910c`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100f29570`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100f2aa93`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100f284ed`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100f287d2`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100f2aab4`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100f2ac2d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100f284ed`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100f287d2`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100f2aab4`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100f2ac2d`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100f27e90`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100f2807a`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100f280f6`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100f28362`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100f27e90`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100f2807a`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100f280f6`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100f28362`
- `sqldk!??_V@YAXPEAX@Z` at `0x10054b660`
- `sqldk!??_V@YAXPEAX@Z` at `0x100f28778`
- `sqldk!??_V@YAXPEAX@Z` at `0x100f28c8a`
- `sqldk!??_V@YAXPEAX@Z` at `0x100f290fe`
- `sqldk!??_V@YAXPEAX@Z` at `0x100f29562`
- `sqldk!??_V@YAXPEAX@Z` at `0x10054b660`
- `sqldk!??_V@YAXPEAX@Z` at `0x100f28778`
- `sqldk!??_V@YAXPEAX@Z` at `0x100f28c8a`
- `sqldk!??_V@YAXPEAX@Z` at `0x100f290fe`
- `sqldk!??_V@YAXPEAX@Z` at `0x100f29562`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x10054ae71`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x10054ae98`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x10054af33`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x10054af89`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x100f28afc`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x100f28dcf`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x100f29052`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x100f29097`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x100f2917b`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x100f291b7`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x10054ae71`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x10054ae98`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x10054af33`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x10054af89`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x100f28afc`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x100f28dcf`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x100f29052`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x100f29097`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x100f2917b`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x100f291b7`
- `sqlTsEs!?FEqIgnoreCaseW@CDefaultCollation@@QEBA_NPEB_WK0K@Z` at `0x100f28b19`
- `sqlTsEs!?FEqIgnoreCaseW@CDefaultCollation@@QEBA_NPEB_WK0K@Z` at `0x100f28ded`
- `sqlTsEs!?FEqIgnoreCaseW@CDefaultCollation@@QEBA_NPEB_WK0K@Z` at `0x100f29068`
- `sqlTsEs!?FEqIgnoreCaseW@CDefaultCollation@@QEBA_NPEB_WK0K@Z` at `0x100f290ad`
- `sqlTsEs!?FEqIgnoreCaseW@CDefaultCollation@@QEBA_NPEB_WK0K@Z` at `0x100f29191`
- `sqlTsEs!?FEqIgnoreCaseW@CDefaultCollation@@QEBA_NPEB_WK0K@Z` at `0x100f291cd`
- `sqlTsEs!?FEqIgnoreCaseW@CDefaultCollation@@QEBA_NPEB_WK0K@Z` at `0x100f28b19`
- `sqlTsEs!?FEqIgnoreCaseW@CDefaultCollation@@QEBA_NPEB_WK0K@Z` at `0x100f28ded`
- `sqlTsEs!?FEqIgnoreCaseW@CDefaultCollation@@QEBA_NPEB_WK0K@Z` at `0x100f29068`
- `sqlTsEs!?FEqIgnoreCaseW@CDefaultCollation@@QEBA_NPEB_WK0K@Z` at `0x100f290ad`
- `sqlTsEs!?FEqIgnoreCaseW@CDefaultCollation@@QEBA_NPEB_WK0K@Z` at `0x100f29191`
- `sqlTsEs!?FEqIgnoreCaseW@CDefaultCollation@@QEBA_NPEB_WK0K@Z` at `0x100f291cd`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x100f283bd`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x100f28625`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x100f28660`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x100f2869b`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x100f28f2b`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x100f283bd`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x100f28625`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x100f28660`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x100f2869b`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x100f28f2b`
- `sqlTsEs!?LCIDFromCID@@YAKK@Z` at `0x10054af43`
- `sqlTsEs!?LCIDFromCID@@YAKK@Z` at `0x10054af43`
- `sqlTsEs!?FUTF8Collation@@YA_NK@Z` at `0x10054ae82`
- `sqlTsEs!?FUTF8Collation@@YA_NK@Z` at `0x10054ae82`
- `sqlTsEs!?CSIDFromCID@@YAEK@Z` at `0x10054aebc`
- `sqlTsEs!?CSIDFromCID@@YAEK@Z` at `0x10054aebc`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x10054af79`

## string_xrefs

- `0x100f28b12`: `DwGen3TempDB`
- `0x100f284bd`: `SEParams is being installed more than once. Illegal usage.`

## pseudocode

```c
// Hidden C++ exception states: #wind=21 #try_helpers=1
__int64 __fastcall login(
        struct IMemObj *a1,
        struct CBatch *a2,
        struct CConnectionOutput **a3,
        struct SNI_Conn *a4,
        struct CRoutingEnvChangeInfo *a5)
{
  struct CBatch *v6; // rbx
  LARGE_INTEGER v7; // r14
  __int64 v8; // r12
  char v9; // al
  int v10; // ebx
  int v11; // eax
  int v12; // ebx
  __int64 v13; // rcx
  __int64 v14; // rcx
  int v15; // ebx
  __int64 v16; // rax
  struct SNI_Conn *v17; // rsi
  __int128 v18; // xmm6
  CConnection *v19; // rdi
  struct CDiagnostics *v20; // rax
  volatile signed __int32 *v21; // rbx
  __int64 v22; // rcx
  __int16 v23; // di
  __int64 v24; // rax
  __int64 v25; // rcx
  __int64 v26; // r9
  volatile signed __int32 *v27; // rbx
  char v28; // di
  volatile signed __int32 *v29; // rsi
  __int64 v30; // rbx
  struct XactWorkspace *v31; // rdi
  enum ISOLATIONLEVEL SessionIsolationLevel; // eax
  __int64 v33; // rbx
  __int64 v34; // rcx
  __int64 v35; // rdx
  __int64 v36; // rcx
  int v37; // edi
  __int64 v38; // rax
  const wchar_t *v39; // rbx
  GUID v40; // xmm1
  GUID v41; // xmm0
  __int64 v42; // rcx
  int v43; // esi
  __int64 v44; // rbx
  unsigned __int16 MasterDbId; // ax
  CSbTransportMgr *QuadPart; // rbx
  _QWORD *v47; // rbx
  __int64 v48; // rcx
  struct IMemObj *v49; // rdi
  __int64 v50; // rcx
  unsigned int Login; // esi
  __int64 v52; // rbx
  int v53; // edx
  char v54; // cl
  char v55; // bl
  unsigned int v56; // r13d
  __int64 v57; // rax
  const wchar_t *v58; // r12
  void *v59; // rbx
  CSbTransportMgr *v60; // rax
  _QWORD *v61; // rdx
  _QWORD *v62; // rbx
  int v63; // ebx
  int v64; // ecx
  int v65; // eax
  bool v66; // zf
  __int64 v67; // rcx
  __int64 v68; // rcx
  __int64 v69; // rcx
  unsigned int v70; // edx
  unsigned int v71; // ebx
  struct CConnectionOutput *v72; // rsi
  int v73; // edi
  int v74; // ebx
  unsigned int v75; // ecx
  int v76; // edi
  bool v77; // bl
  __int64 v78; // rax
  __int16 v79; // r9
  struct CUEnvTransient *v80; // rsi
  struct CRoutingEnvChangeInfo *v81; // rbx
  CSbTransportMgr *v82; // rbx
  _QWORD *v83; // rdi
  _QWORD *v84; // rbx
  CSbTransportMgr *v85; // rax
  _QWORD *v86; // rbx
  CSbTransportMgr *v87; // rbx
  _QWORD *v88; // rdi
  _QWORD *v89; // rbx
  CSbTransportMgr *v90; // rax
  _QWORD *v91; // rbx
  CSbTransportMgr *v92; // rbx
  _QWORD *v93; // rbx
  int v94; // eax
  struct CNetConnection *v95; // rax
  __int64 v96; // r12
  __int64 v97; // rbx
  struct Worker *v98; // rcx
  __int64 v99; // rbx
  __int64 v100; // rax
  __int64 *v101; // rdx
  __int64 v102; // rbx
  volatile signed __int32 *v103; // rbx
  __int64 v104; // rbx
  __int64 v105; // rbx
  unsigned int v107; // ebx
  __int64 v108; // rax
  const wchar_t *v109; // rdi
  __int64 v110; // rsi
  __int64 v111; // rcx
  int v112; // ecx
  __int64 v113; // rcx
  __int64 XdbServerGlobals; // rax
  __int64 v115; // rax
  struct CSessionTraceFlags *v116; // rcx
  __int64 v117; // rcx
  char v118; // al
  char v119; // cl
  __int64 v120; // rcx
  struct CSessionTraceFlags *v121; // rcx
  __int64 v122; // rax
  __int64 v123; // rdx
  struct CSessionTraceFlags *v124; // rcx
  char v125; // al
  char v126; // cl
  struct IMemObj *v127; // rdx
  struct _GUID *v128; // rcx
  DWORD LengthSid; // eax
  struct ImpliedLoginInfo *ImpliedLoginInfoFromCertificate; // rax
  char v131; // al
  __int64 v132; // rcx
  __int64 v133; // rax
  int v134; // ecx
  __int64 v135; // rax
  ImpliedAuthenticationManager *v136; // rcx
  struct CSessionTraceFlags *v137; // rcx
  __int64 v138; // rax
  const wchar_t *v139; // r8
  CConnection *v140; // rcx
  ExecutionContext *v141; // rcx
  __int64 v142; // rbx
  unsigned int v143; // edi
  __int64 v144; // rax
  const wchar_t *v145; // rbx
  bool ContainedAGSystemDbsId; // al
  bool v147; // r12
  unsigned int v148; // esi
  unsigned int v149; // eax
  __int64 v150; // rbx
  __int64 v151; // rax
  unsigned int v152; // eax
  __int64 v153; // rbx
  unsigned __int16 ReplicatedMasterDbId; // ax
  __int64 v155; // rax
  int v156; // r8d
  __int64 v157; // rax
  signed int v158; // edi
  const wchar_t *v159; // rbx
  CDefaultCollation *v160; // rax
  _QWORD *v161; // rax
  AutoReadOnlyXact *v162; // rbx
  __int64 v163; // rax
  void *v164; // rbx
  unsigned __int16 v165; // ax
  __int64 v166; // rax
  __int64 v167; // rbx
  unsigned int v168; // edi
  const wchar_t *v169; // rbx
  CDefaultCollation *v170; // rax
  char v171; // al
  __int64 v172; // rax
  const wchar_t *v173; // rbx
  int v174; // edi
  const wchar_t *v175; // rdx
  __int64 v176; // rax
  __int64 v177; // rax
  char v178; // al
  __int64 v179; // rax
  unsigned int v180; // edi
  CDefaultCollation *v181; // rax
  unsigned int v182; // edi
  CDefaultCollation *v183; // rax
  void *v184; // rbx
  void *v185; // rcx
  unsigned int v186; // edi
  CDefaultCollation *v187; // rax
  unsigned int v188; // edi
  CDefaultCollation *v189; // rax
  __int64 v190; // rcx
  __int64 v191; // rbx
  const wchar_t *v192; // rax
  __int64 v193; // rdx
  struct SNI_Conn *v194; // r12
  unsigned int v195; // eax
  int v196; // eax
  int v197; // r8d
  char v198; // al
  const void *v199; // rdx
  __int64 v200; // rax
  __int64 v201; // rax
  unsigned __int16 v203; // ax
  unsigned __int16 v204; // ax
  const struct CSession *v205; // rcx
  int v206; // eax
  __int64 v207; // rcx
  __int32 v208; // eax
  __int32 v209; // eax
  _QWORD *v210; // rax
  _QWORD *v211; // rax
  __int64 v212; // rax
  __int64 v213; // rcx
  __int64 v214; // rdi
  _QWORD *v215; // rcx
  _QWORD *v216; // rdx
  int v217; // r8d
  __int64 v218; // r8
  __int64 v219; // r8
  __int64 v220; // r8
  __int64 v221; // rdx
  __int64 v222; // rax
  unsigned int v223; // edi
  const wchar_t *v224; // rsi
  __int64 v225; // rbx
  unsigned int v226; // ebx
  __int64 v227; // rcx
  __int64 v228; // rcx
  __int64 v229; // rax
  int v230; // r8d
  CSbTransportMgr *v231; // rax
  _QWORD *v232; // rbx
  int v233; // r8d
  int v234; // r8d
  int v235; // r8d
  int v236; // r8d
  int v237; // r8d
  CSbTransportMgr *v238; // rbx
  _QWORD *v239; // rdi
  _QWORD *v240; // rbx
  int v241; // r8d
  char v242; // cl
  char v243; // cl
  char v244; // al
  CSbTransportMgr *v245; // rax
  _QWORD *v246; // rbx
  int v247; // r8d
  CSbTransportMgr *v248; // rax
  _QWORD *v249; // rbx
  int v250; // r8d
  __int64 v251; // rax
  void (__fastcall ***v252)(_QWORD, __int64); // rcx
  LONGLONG v253; // rax
  unsigned __int64 v254; // rax
  __int64 v255; // rbx
  CConnection *v256; // rcx
  ExecutionContext *v257; // rcx
  int v258; // [rsp+20h] [rbp-2DD8h]
  int v259; // [rsp+28h] [rbp-2DD0h]
  int v260; // [rsp+40h] [rbp-2DB8h]
  int v261; // [rsp+48h] [rbp-2DB0h]
  __int64 v262; // [rsp+58h] [rbp-2DA0h]
  __int64 v263; // [rsp+70h] [rbp-2D88h]
  int v264; // [rsp+88h] [rbp-2D70h]
  int v265; // [rsp+C0h] [rbp-2D38h] BYREF
  int v266; // [rsp+C4h] [rbp-2D34h]
  char v267; // [rsp+C8h] [rbp-2D30h]
  char v268; // [rsp+C9h] [rbp-2D2Fh]
  char v269; // [rsp+CAh] [rbp-2D2Eh]
  signed int v270; // [rsp+CCh] [rbp-2D2Ch]
  struct SNI_Conn *v271; // [rsp+D0h] [rbp-2D28h] BYREF
  int v272; // [rsp+D8h] [rbp-2D20h]
  int v273; // [rsp+DCh] [rbp-2D1Ch]
  int v274; // [rsp+E0h] [rbp-2D18h]
  unsigned int v275; // [rsp+E4h] [rbp-2D14h]
  int v276; // [rsp+E8h] [rbp-2D10h]
  struct CUEnvTransient *v277; // [rsp+F0h] [rbp-2D08h]
  CConnection *v278; // [rsp+F8h] [rbp-2D00h] BYREF
  struct IMemObj *v279; // [rsp+100h] [rbp-2CF8h]
  volatile signed __int32 *v280; // [rsp+108h] [rbp-2CF0h] BYREF
  int v281; // [rsp+110h] [rbp-2CE8h]
  bool v282; // [rsp+118h] [rbp-2CE0h]
  bool v283; // [rsp+119h] [rbp-2CDFh]
  bool v284; // [rsp+11Ah] [rbp-2CDEh]
  bool v285; // [rsp+11Bh] [rbp-2CDDh]
  bool v286; // [rsp+11Ch] [rbp-2CDCh]
  bool v287; // [rsp+11Dh] [rbp-2CDBh]
  bool v288; // [rsp+11Eh] [rbp-2CDAh]
  char v289; // [rsp+11Fh] [rbp-2CD9h]
  char v290; // [rsp+120h] [rbp-2CD8h]
  bool v292; // [rsp+122h] [rbp-2CD6h]
  int v293; // [rsp+124h] [rbp-2CD4h]
  bool v294; // [rsp+128h] [rbp-2CD0h]
  __int16 v295; // [rsp+12Ch] [rbp-2CCCh] BYREF
  bool v296; // [rsp+130h] [rbp-2CC8h]
  char v298; // [rsp+132h] [rbp-2CC6h]
  char v299; // [rsp+133h] [rbp-2CC5h]
  bool v300; // [rsp+134h] [rbp-2CC4h]
  char v301; // [rsp+135h] [rbp-2CC3h]
  unsigned __int8 v302; // [rsp+136h] [rbp-2CC2h]
  bool v303; // [rsp+137h] [rbp-2CC1h]
  bool v304; // [rsp+138h] [rbp-2CC0h]
  bool v305; // [rsp+139h] [rbp-2CBFh]
  struct ImpliedLoginInfo *v306; // [rsp+140h] [rbp-2CB8h]
  wchar_t *v307; // [rsp+148h] [rbp-2CB0h]
  AutoReadOnlyXact *v308; // [rsp+150h] [rbp-2CA8h] BYREF
  __int64 v309; // [rsp+158h] [rbp-2CA0h]
  unsigned int v310; // [rsp+160h] [rbp-2C98h] BYREF
  int v311; // [rsp+164h] [rbp-2C94h]
  struct CRoutingEnvChangeInfo *v312; // [rsp+168h] [rbp-2C90h]
  int v313; // [rsp+170h] [rbp-2C88h]
  struct CConnectionOutput *v314; // [rsp+178h] [rbp-2C80h]
  struct CBatch *v315; // [rsp+180h] [rbp-2C78h]
  CDbAndSetOpts *v316; // [rsp+188h] [rbp-2C70h]
  unsigned int v317; // [rsp+190h] [rbp-2C68h]
  int v318; // [rsp+194h] [rbp-2C64h]
  int v319; // [rsp+198h] [rbp-2C60h]
  unsigned int v320; // [rsp+19Ch] [rbp-2C5Ch] BYREF
  int v321; // [rsp+1A0h] [rbp-2C58h]
  unsigned int v322; // [rsp+1A4h] [rbp-2C54h]
  unsigned int v323; // [rsp+1A8h] [rbp-2C50h]
  unsigned int v324; // [rsp+1ACh] [rbp-2C4Ch]
  int v325; // [rsp+1B0h] [rbp-2C48h]
  unsigned int v326; // [rsp+1B4h] [rbp-2C44h]
  LARGE_INTEGER v327; // [rsp+1B8h] [rbp-2C40h] BYREF
  int v328; // [rsp+1C0h] [rbp-2C38h]
  int v329; // [rsp+1C4h] [rbp-2C34h]
  int v330; // [rsp+1C8h] [rbp-2C30h]
  wchar_t *v331; // [rsp+1D0h] [rbp-2C28h]
  __int64 v332; // [rsp+1D8h] [rbp-2C20h]
  __int64 v333; // [rsp+1E0h] [rbp-2C18h]
  __int64 v334; // [rsp+1E8h] [rbp-2C10h]
  signed int v335; // [rsp+1F0h] [rbp-2C08h]
  __int128 v336; // [rsp+1F8h] [rbp-2C00h] BYREF
  __int64 v337; // [rsp+208h] [rbp-2BF0h] BYREF
  int v338; // [rsp+210h] [rbp-2BE8h]
  SEParams *v339; // [rsp+218h] [rbp-2BE0h] BYREF
  __int64 v340; // [rsp+220h] [rbp-2BD8h]
  struct IMemObj *v341; // [rsp+228h] [rbp-2BD0h]
  int v342; // [rsp+230h] [rbp-2BC8h]
  int v343; // [rsp+234h] [rbp-2BC4h]
  unsigned int v344; // [rsp+238h] [rbp-2BC0h]
  int v345; // [rsp+23Ch] [rbp-2BBCh]
  unsigned int v346; // [rsp+240h] [rbp-2BB8h]
  int v347; // [rsp+244h] [rbp-2BB4h]
  unsigned int v348; // [rsp+248h] [rbp-2BB0h]
  int v349; // [rsp+24Ch] [rbp-2BACh]
  int v350; // [rsp+250h] [rbp-2BA8h]
  signed __int32 v351; // [rsp+258h] [rbp-2BA0h]
  int v353; // [rsp+264h] [rbp-2B94h]
  int v354; // [rsp+268h] [rbp-2B90h]
  int v355; // [rsp+26Ch] [rbp-2B8Ch]
  unsigned int v356; // [rsp+270h] [rbp-2B88h]
  unsigned int v357; // [rsp+274h] [rbp-2B84h]
  int v358; // [rsp+278h] [rbp-2B80h]
  int v359; // [rsp+280h] [rbp-2B78h]
  int v360; // [rsp+284h] [rbp-2B74h]
  int v361; // [rsp+288h] [rbp-2B70h]
  int v362; // [rsp+28Ch] [rbp-2B6Ch]
  int v363; // [rsp+290h] [rbp-2B68h]
  int v364; // [rsp+294h] [rbp-2B64h]
  LARGE_INTEGER v365; // [rsp+298h] [rbp-2B60h] BYREF
  CSbTransportMgr *v366; // [rsp+2A0h] [rbp-2B58h]
  CSbTransportMgr *v367; // [rsp+2A8h] [rbp-2B50h]
  LARGE_INTEGER v368; // [rsp+2B0h] [rbp-2B48h] BYREF
  CSbTransportMgr *v369; // [rsp+2B8h] [rbp-2B40h]
  CSbTransportMgr *v370; // [rsp+2C0h] [rbp-2B38h]
  CSbTransportMgr *v371; // [rsp+2C8h] [rbp-2B30h]
  CSbTransportMgr *v372; // [rsp+2D0h] [rbp-2B28h]
  LARGE_INTEGER v373; // [rsp+2D8h] [rbp-2B20h] BYREF
  CSbTransportMgr *v374; // [rsp+2E0h] [rbp-2B18h]
  int v375; // [rsp+2E8h] [rbp-2B10h]
  int v376; // [rsp+2ECh] [rbp-2B0Ch]
  int v377; // [rsp+2F0h] [rbp-2B08h]
  int v378; // [rsp+2F8h] [rbp-2B00h]
  int v379; // [rsp+300h] [rbp-2AF8h]
  const wchar_t *v380; // [rsp+308h] [rbp-2AF0h]
  const wchar_t *v381; // [rsp+310h] [rbp-2AE8h]
  LARGE_INTEGER PerformanceCount; // [rsp+318h] [rbp-2AE0h] BYREF
  CSbTransportMgr *v383; // [rsp+320h] [rbp-2AD8h]
  CSbTransportMgr *v384; // [rsp+328h] [rbp-2AD0h]
  const wchar_t *v385; // [rsp+330h] [rbp-2AC8h]
  _QWORD *v386; // [rsp+338h] [rbp-2AC0h]
  CSbTransportMgr *v387; // [rsp+340h] [rbp-2AB8h]
  const wchar_t *v388; // [rsp+348h] [rbp-2AB0h]
  const wchar_t *v389; // [rsp+350h] [rbp-2AA8h]
  LARGE_INTEGER v390; // [rsp+358h] [rbp-2AA0h] BYREF
  CSbTransportMgr *v391; // [rsp+360h] [rbp-2A98h]
  CSbTransportMgr *v392; // [rsp+368h] [rbp-2A90h]
  CSbTransportMgr *v393; // [rsp+370h] [rbp-2A88h]
  const void *v394; // [rsp+378h] [rbp-2A80h]
  const wchar_t *v395; // [rsp+380h] [rbp-2A78h]
  LARGE_INTEGER v396; // [rsp+388h] [rbp-2A70h] BYREF
  CSbTransportMgr *v397; // [rsp+390h] [rbp-2A68h]
  CSbTransportMgr *v398; // [rsp+398h] [rbp-2A60h]
  LARGE_INTEGER v399; // [rsp+3A0h] [rbp-2A58h] BYREF
  CSbTransportMgr *v400; // [rsp+3A8h] [rbp-2A50h]
  CSbTransportMgr *v401; // [rsp+3B0h] [rbp-2A48h]
  CSbTransportMgr *v402; // [rsp+3B8h] [rbp-2A40h]
  LARGE_INTEGER v403; // [rsp+3C0h] [rbp-2A38h] BYREF
  CSbTransportMgr *v404; // [rsp+3C8h] [rbp-2A30h]
  CSbTransportMgr *v405; // [rsp+3D0h] [rbp-2A28h]
  CSbTransportMgr *v406; // [rsp+3D8h] [rbp-2A20h]
  LARGE_INTEGER v407; // [rsp+3E0h] [rbp-2A18h] BYREF
  CSbTransportMgr *v408; // [rsp+3E8h] [rbp-2A10h]
  CSbTransportMgr *v409; // [rsp+3F0h] [rbp-2A08h]
  LARGE_INTEGER v410; // [rsp+3F8h] [rbp-2A00h] BYREF
  CSbTransportMgr *v411; // [rsp+400h] [rbp-29F8h]
  CSbTransportMgr *v412; // [rsp+408h] [rbp-29F0h]
  CSbTransportMgr *v413; // [rsp+410h] [rbp-29E8h]
  LARGE_INTEGER v414; // [rsp+418h] [rbp-29E0h] BYREF
  CSbTransportMgr *v415; // [rsp+420h] [rbp-29D8h]
  CSbTransportMgr *v416; // [rsp+428h] [rbp-29D0h]
  _OWORD v417[2]; // [rsp+430h] [rbp-29C8h] BYREF
  __int128 v418; // [rsp+450h] [rbp-29A8h] BYREF
  struct _GUID v419; // [rsp+460h] [rbp-2998h] BYREF
  struct _GUID v420; // [rsp+470h] [rbp-2988h] BYREF
  struct _GUID v421; // [rsp+480h] [rbp-2978h] BYREF
  __int128 v422; // [rsp+490h] [rbp-2968h] BYREF
  __int128 v423; // [rsp+4A0h] [rbp-2958h] BYREF
  __int128 v424; // [rsp+4B0h] [rbp-2948h] BYREF
  __int64 v425; // [rsp+4C0h] [rbp-2938h]
  __int64 v426; // [rsp+4C8h] [rbp-2930h]
  struct CDiagnostics *v427; // [rsp+4D0h] [rbp-2928h]
  __int64 v428; // [rsp+4D8h] [rbp-2920h]
  _QWORD *v429; // [rsp+4E0h] [rbp-2918h]
  __int64 v430; // [rsp+4E8h] [rbp-2910h]
  __int64 v431; // [rsp+4F0h] [rbp-2908h]
  __int64 v432; // [rsp+4F8h] [rbp-2900h]
  __int64 v433; // [rsp+500h] [rbp-28F8h]
  __int64 v434; // [rsp+508h] [rbp-28F0h]
  __int64 v435; // [rsp+510h] [rbp-28E8h]
  _QWORD *v436; // [rsp+518h] [rbp-28E0h]
  _QWORD *v437; // [rsp+520h] [rbp-28D8h]
  __int64 v438; // [rsp+528h] [rbp-28D0h]
  void *v439; // [rsp+530h] [rbp-28C8h]
  __int64 v440; // [rsp+538h] [rbp-28C0h]
  _QWORD *ThreadLocalStoragePointer; // [rsp+540h] [rbp-28B8h]
  __int64 *v442; // [rsp+548h] [rbp-28B0h]
  __int64 v443; // [rsp+550h] [rbp-28A8h]
  __int64 v444; // [rsp+558h] [rbp-28A0h]
  __int64 v445; // [rsp+560h] [rbp-2898h]
  __int64 v446; // [rsp+568h] [rbp-2890h]
  const wchar_t *v447; // [rsp+570h] [rbp-2888h]
  __int64 v448; // [rsp+578h] [rbp-2880h]
  const wchar_t *v449; // [rsp+580h] [rbp-2878h]
  const wchar_t *v450; // [rsp+588h] [rbp-2870h]
  __int64 v451; // [rsp+590h] [rbp-2868h]
  void *v452; // [rsp+598h] [rbp-2860h]
  const wchar_t *v453; // [rsp+5A0h] [rbp-2858h]
  const wchar_t *v454; // [rsp+5A8h] [rbp-2850h]
  __int64 v455; // [rsp+5B0h] [rbp-2848h]
  void *v456; // [rsp+5B8h] [rbp-2840h]
  __int64 v457; // [rsp+5C0h] [rbp-2838h]
  const wchar_t *v458; // [rsp+5C8h] [rbp-2830h]
  __int64 v459; // [rsp+5D0h] [rbp-2828h]
  void *v460; // [rsp+5D8h] [rbp-2820h]
  __int64 v461; // [rsp+5E0h] [rbp-2818h]
  struct ImpliedLoginInfo *v462; // [rsp+5E8h] [rbp-2810h]
  __int64 v463; // [rsp+5F0h] [rbp-2808h]
  __int64 v464; // [rsp+5F8h] [rbp-2800h]
  _QWORD *v465; // [rsp+600h] [rbp-27F8h]
  _QWORD *v466; // [rsp+608h] [rbp-27F0h]
  struct ImpliedLoginInfo **v467; // [rsp+610h] [rbp-27E8h]
  struct ImpliedLoginInfo *v468; // [rsp+618h] [rbp-27E0h]
  _QWORD *v469; // [rsp+620h] [rbp-27D8h]
  struct ImpliedLoginInfo **v470; // [rsp+628h] [rbp-27D0h]
  struct ImpliedLoginInfo *v471; // [rsp+630h] [rbp-27C8h]
  _QWORD *v472; // [rsp+638h] [rbp-27C0h]
  _QWORD *v473; // [rsp+640h] [rbp-27B8h]
  __int64 v474; // [rsp+648h] [rbp-27B0h]
  _QWORD *v475; // [rsp+650h] [rbp-27A8h]
  _QWORD *v476; // [rsp+658h] [rbp-27A0h]
  __int64 v477; // [rsp+660h] [rbp-2798h]
  __int64 v478; // [rsp+668h] [rbp-2790h]
  _DWORD *v479; // [rsp+670h] [rbp-2788h]
  unsigned int *v480; // [rsp+678h] [rbp-2780h]
  int *v481; // [rsp+680h] [rbp-2778h]
  __int64 v482; // [rsp+688h] [rbp-2770h]
  _QWORD *v483; // [rsp+690h] [rbp-2768h]
  __int64 v484; // [rsp+698h] [rbp-2760h]
  CDiagnostics *v485; // [rsp+6A0h] [rbp-2758h]
  _QWORD *v486; // [rsp+6A8h] [rbp-2750h]
  struct ImpliedLoginInfo **v487; // [rsp+6B0h] [rbp-2748h]
  struct ImpliedLoginInfo *v488; // [rsp+6B8h] [rbp-2740h]
  _QWORD *v489; // [rsp+6C0h] [rbp-2738h]
  __int64 v490; // [rsp+6C8h] [rbp-2730h]
  __int64 v491; // [rsp+6D0h] [rbp-2728h]
  __int64 v492; // [rsp+6D8h] [rbp-2720h]
  _QWORD *v493; // [rsp+6E0h] [rbp-2718h]
  _QWORD *v494; // [rsp+6E8h] [rbp-2710h]
  __int64 v495; // [rsp+6F0h] [rbp-2708h]
  __int64 v496; // [rsp+6F8h] [rbp-2700h]
  __int64 v497; // [rsp+700h] [rbp-26F8h]
  struct CUEnvTransient *v498; // [rsp+708h] [rbp-26F0h]
  __int64 v499; // [rsp+710h] [rbp-26E8h]
  __int64 v500; // [rsp+718h] [rbp-26E0h]
  _QWORD *v501; // [rsp+720h] [rbp-26D8h]
  __int64 v502; // [rsp+728h] [rbp-26D0h]
  struct CUEnvTransient *v503; // [rsp+730h] [rbp-26C8h]
  __int64 v504; // [rsp+738h] [rbp-26C0h]
  __int64 v505; // [rsp+740h] [rbp-26B8h]
  _QWORD *v506; // [rsp+748h] [rbp-26B0h]
  __int64 v507; // [rsp+750h] [rbp-26A8h]
  _QWORD *v508; // [rsp+758h] [rbp-26A0h]
  __int64 v509; // [rsp+760h] [rbp-2698h]
  struct CUEnvTransient *v510; // [rsp+768h] [rbp-2690h]
  __int64 v511; // [rsp+770h] [rbp-2688h]
  __int64 v512; // [rsp+778h] [rbp-2680h]
  _QWORD *v513; // [rsp+780h] [rbp-2678h]
  __int64 v514; // [rsp+788h] [rbp-2670h]
  _QWORD *v515; // [rsp+790h] [rbp-2668h]
  _QWORD *v516; // [rsp+798h] [rbp-2660h]
  __int64 v517; // [rsp+7A0h] [rbp-2658h]
  __int64 v518; // [rsp+7A8h] [rbp-2650h]
  __int64 v519; // [rsp+7B0h] [rbp-2648h]
  _QWORD *v520; // [rsp+7B8h] [rbp-2640h]
  __int64 v521; // [rsp+7C0h] [rbp-2638h]
  struct CUEnvTransient *v522; // [rsp+7C8h] [rbp-2630h]
  __int64 v523; // [rsp+7D0h] [rbp-2628h]
  __int64 v524; // [rsp+7D8h] [rbp-2620h]
  _QWORD *v525; // [rsp+7E0h] [rbp-2618h]
  __int64 v526; // [rsp+7E8h] [rbp-2610h]
  struct CUEnvTransient *v527; // [rsp+7F0h] [rbp-2608h]
  __int64 v528; // [rsp+7F8h] [rbp-2600h]
  __int64 v529; // [rsp+800h] [rbp-25F8h]
  _QWORD *v530; // [rsp+808h] [rbp-25F0h]
  __int64 v531; // [rsp+810h] [rbp-25E8h]
  _QWORD *v532; // [rsp+818h] [rbp-25E0h]
  __int64 *v533; // [rsp+820h] [rbp-25D8h]
  __int64 v534; // [rsp+828h] [rbp-25D0h]
  CSession *v535; // [rsp+830h] [rbp-25C8h]
  AutoReadOnlyXact *v536; // [rsp+838h] [rbp-25C0h]
  void (__fastcall ***v537)(_QWORD, __int64); // [rsp+840h] [rbp-25B8h]
  struct _GUID v538[2]; // [rsp+850h] [rbp-25A8h] BYREF
  struct _GUID v539; // [rsp+870h] [rbp-2588h] BYREF
  unsigned int v540; // [rsp+880h] [rbp-2578h] BYREF
  __int64 v541; // [rsp+888h] [rbp-2570h] BYREF
  unsigned int v542; // [rsp+890h] [rbp-2568h] BYREF
  unsigned __int16 v543; // [rsp+894h] [rbp-2564h] BYREF
  unsigned __int16 v544[2]; // [rsp+898h] [rbp-2560h] BYREF
  unsigned __int16 v545; // [rsp+89Ch] [rbp-255Ch] BYREF
  unsigned __int16 v546[2]; // [rsp+8A0h] [rbp-2558h] BYREF
  int v547; // [rsp+8A4h] [rbp-2554h] BYREF
  unsigned __int16 v548[2]; // [rsp+8A8h] [rbp-2550h] BYREF
  unsigned __int16 v549; // [rsp+8ACh] [rbp-254Ch] BYREF
  int v550; // [rsp+8B0h] [rbp-2548h] BYREF
  int v551[3]; // [rsp+8B4h] [rbp-2544h] BYREF
  __int64 v552; // [rsp+8C0h] [rbp-2538h] BYREF
  int v553; // [rsp+8C8h] [rbp-2530h] BYREF
  int v554; // [rsp+8CCh] [rbp-252Ch] BYREF
  struct _GUID v555; // [rsp+8D0h] [rbp-2528h] BYREF
  unsigned __int8 v556[8]; // [rsp+8E0h] [rbp-2518h] BYREF
  LARGE_INTEGER v557; // [rsp+8E8h] [rbp-2510h] BYREF
  int v558; // [rsp+8F0h] [rbp-2508h] BYREF
  int v559; // [rsp+8F4h] [rbp-2504h]
  __int16 v560; // [rsp+8F8h] [rbp-2500h]
  int v561; // [rsp+8FCh] [rbp-24FCh]
  __int16 v562; // [rsp+900h] [rbp-24F8h]
  int v563; // [rsp+904h] [rbp-24F4h]
  __int128 v564; // [rsp+908h] [rbp-24F0h]
  __int128 v565; // [rsp+918h] [rbp-24E0h]
  __int128 v566; // [rsp+928h] [rbp-24D0h]
  __int16 v567; // [rsp+938h] [rbp-24C0h]
  int v568; // [rsp+93Ch] [rbp-24BCh]
  __int128 v569; // [rsp+940h] [rbp-24B8h]
  __int128 v570; // [rsp+950h] [rbp-24A8h]
  __int128 v571; // [rsp+960h] [rbp-2498h]
  __int128 v572; // [rsp+970h] [rbp-2488h]
  __int128 v573; // [rsp+980h] [rbp-2478h]
  __int128 v574; // [rsp+990h] [rbp-2468h]
  __int16 v575; // [rsp+9A0h] [rbp-2458h]
  int v576; // [rsp+9A4h] [rbp-2454h]
  char v577; // [rsp+9A8h] [rbp-2450h]
  __int64 v578; // [rsp+9ACh] [rbp-244Ch]
  __int128 v579; // [rsp+9B4h] [rbp-2444h]
  __int128 v580; // [rsp+9C4h] [rbp-2434h]
  __int16 v581; // [rsp+9D4h] [rbp-2424h]
  int v582; // [rsp+9D8h] [rbp-2420h]
  char v583; // [rsp+9DCh] [rbp-241Ch]
  char v584; // [rsp+9DDh] [rbp-241Bh]
  int v585; // [rsp+9E0h] [rbp-2418h]
  int v586; // [rsp+9E4h] [rbp-2414h]
  char v587; // [rsp+9E8h] [rbp-2410h]
  struct _GUID v588; // [rsp+9F0h] [rbp-2408h] BYREF
  __int128 v589; // [rsp+A10h] [rbp-23E8h]
  __m128i si128; // [rsp+A40h] [rbp-23B8h] BYREF
  int v591; // [rsp+A50h] [rbp-23A8h]
  __int16 v592; // [rsp+A54h] [rbp-23A4h] BYREF
  __int64 v593; // [rsp+B58h] [rbp-22A0h]
  _BYTE v594[48]; // [rsp+B60h] [rbp-2298h] BYREF
  _BYTE v595[80]; // [rsp+B90h] [rbp-2268h] BYREF
  char v596[8]; // [rsp+BE0h] [rbp-2218h] BYREF
  int v597; // [rsp+BE8h] [rbp-2210h]
  int v598; // [rsp+BF0h] [rbp-2208h]
  _QWORD *v599; // [rsp+BF8h] [rbp-2200h]
  char *v600; // [rsp+C00h] [rbp-21F8h]
  __int64 v601; // [rsp+C08h] [rbp-21F0h]
  _QWORD v602[2]; // [rsp+C10h] [rbp-21E8h] BYREF
  char v603; // [rsp+C20h] [rbp-21D8h] BYREF
  __int64 v604; // [rsp+E30h] [rbp-1FC8h]
  __int64 v605; // [rsp+E38h] [rbp-1FC0h]
  unsigned __int64 v606; // [rsp+E40h] [rbp-1FB8h] BYREF
  bool v607; // [rsp+E48h] [rbp-1FB0h]
  char v608[8]; // [rsp+E50h] [rbp-1FA8h] BYREF
  __int16 v609; // [rsp+E58h] [rbp-1FA0h]
  __int16 v610; // [rsp+E5Ah] [rbp-1F9Eh]
  int v611; // [rsp+E60h] [rbp-1F98h]
  __int64 v612; // [rsp+E68h] [rbp-1F90h]
  char *v613; // [rsp+E70h] [rbp-1F88h]
  __int64 v614; // [rsp+E78h] [rbp-1F80h]
  char v615; // [rsp+E80h] [rbp-1F78h] BYREF
  int v616; // [rsp+10A0h] [rbp-1D58h]
  int v617; // [rsp+10A4h] [rbp-1D54h]
  __int64 v618; // [rsp+10A8h] [rbp-1D50h]
  _BYTE v619[24]; // [rsp+10B0h] [rbp-1D48h] BYREF
  _QWORD *v620; // [rsp+10C8h] [rbp-1D30h]
  __int32 v621; // [rsp+1310h] [rbp-1AE8h]
  __int32 v622; // [rsp+1314h] [rbp-1AE4h]
  char v623; // [rsp+1318h] [rbp-1AE0h]
  char v624; // [rsp+1319h] [rbp-1ADFh]
  void **v625; // [rsp+1340h] [rbp-1AB8h] BYREF
  char v626; // [rsp+1348h] [rbp-1AB0h]
  char v627[768]; // [rsp+1350h] [rbp-1AA8h] BYREF
  _BYTE v628[4496]; // [rsp+1650h] [rbp-17A8h] BYREF
  __int64 v629; // [rsp+27E0h] [rbp-618h]
  _OWORD pSid[4]; // [rsp+2850h] [rbp-5A8h] BYREF
  int v631; // [rsp+2890h] [rbp-568h]
  wchar_t Buffer[16]; // [rsp+28A0h] [rbp-558h] BYREF
  wchar_t Source[16]; // [rsp+28C0h] [rbp-538h] BYREF
  unsigned __int8 v634[96]; // [rsp+28E0h] [rbp-518h] BYREF
  unsigned __int8 v635[96]; // [rsp+2940h] [rbp-4B8h] BYREF
  wchar_t v636[128]; // [rsp+29A0h] [rbp-458h] BYREF
  wchar_t v637[128]; // [rsp+2AA0h] [rbp-358h] BYREF
  wchar_t v638[128]; // [rsp+2BA0h] [rbp-258h] BYREF
  wchar_t v639[128]; // [rsp+2CA0h] [rbp-158h] BYREF

  v426 = -2;
  v271 = a4;
  v278 = (CConnection *)a3;
  v6 = a2;
  v315 = a2;
  v279 = a1;
  v341 = a1;
  v312 = a5;
  v311 = 0;
  if ( (WORD2(qword_102EDC9FC) & 0x400) != 0 )
  {
    v311 = 1;
    QueryPerformanceCounter(&v557);
  }
  v314 = a3[3];
  v270 = 0;
  v7 = *(LARGE_INTEGER *)((char *)v6 + 24);
  v327 = v7;
  v265 = 0;
  v550 = 0;
  v269 = 0;
  v551[0] = 0;
  v554 = 0;
  v273 = 0;
  v313 = 0;
  v306 = 0;
  v310 = 0;
  v8 = *(_QWORD *)(v7.QuadPart + 96);
  v309 = v8;
  v9 = *(_BYTE *)(v8 + 49);
  if ( (v9 & 1) != 0 )
  {
    *(_BYTE *)(v7.QuadPart + 272) |= 0x10u;
    v9 = *(_BYTE *)(v8 + 49);
  }
  if ( (v9 & 2) != 0 )
    *(_BYTE *)(v7.QuadPart + 272) |= 0x20u;
  v542 = 1;
  v593 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v591 = 0;
  v592 = 0;
  v272 = 0;
  v276 = 0;
  if ( !*(_DWORD *)(qword_102ECFB00 + 14504) || (v10 = 1, !byte_102EDCEA9) )
    v10 = 0;
  v274 = v10;
  if ( *(_DWORD *)(v8 + 988) != 2
    || (LOBYTE(a2) = 2, v66 = CPhysicalConnection::GetFeatureExtension(v8, a2) == 0, v11 = 1, v66) )
  {
    v11 = 0;
  }
  v547 = v11;
  if ( !v10 || (v12 = 1, !v11) )
    v12 = 0;
  v266 = v12;
  if ( !*(_DWORD *)(GetXdbServerGlobals(a1) + 8308) )
  {
    if ( *(_DWORD *)(GetXdbServerGlobals(v13) + 11976) )
    {
      v118 = *(_BYTE *)(v7.QuadPart + 270) | 0x10;
      *(_BYTE *)(v7.QuadPart + 270) = v118;
      v119 = *(_BYTE *)(v7.QuadPart + 271) | 2;
      *(_BYTE *)(v7.QuadPart + 271) = v119;
      if ( *(_DWORD *)(v8 + 968) != 5 || v12 )
      {
        *(_BYTE *)(v7.QuadPart + 270) = v118 | 2;
        *(_BYTE *)(v7.QuadPart + 271) = v119 & 0xFD;
      }
      goto LABEL_16;
    }
    if ( *(_DWORD *)(qword_102ECFB00 + 14504)
      && (*(_BYTE *)(GetXdbServerGlobals(v14) + 12009) || *(_BYTE *)(GetXdbServerGlobals(v120) + 12008))
      && !*(_BYTE *)(GetXdbServerGlobals(v120) + 12004) )
    {
      if ( !*(_DWORD *)(qword_102ECFB00 + 14504)
        && (*((char *)qword_102ECFB10 + 1533) < 0
         || (v121 = (struct CSessionTraceFlags *)SystemThread_TlsIndex,
             (v122 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                               + SystemThread_TlsOffset)) != 0)
         && (v121 = **(struct CSessionTraceFlags ***)(v122 + 56)) != 0
         && CSessionTraceFlags::CheckSessionTraceInternal(v121, 0x2FEFu))
        || *(_BYTE *)(GetXdbServerGlobals(v121) + 12005) )
      {
        *(_BYTE *)(v7.QuadPart + 270) |= 8u;
      }
      if ( !*(_DWORD *)(qword_102ECFB00 + 14504)
        || !*(_BYTE *)(GetXdbServerGlobals(v121) + 12009)
        || (v123 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                 + SystemThread_TlsOffset,
            *(_QWORD *)v123)
        && (v124 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v123 + 56LL)) != 0
        && CSessionTraceFlags::CheckSessionTraceInternal(v124, 0x3275u) )
      {
        v126 = *(_BYTE *)(v7.QuadPart + 270);
      }
      else
      {
        v125 = *(_BYTE *)(v7.QuadPart + 270) | 0x80;
        *(_BYTE *)(v7.QuadPart + 270) = v125;
        v126 = v125;
        if ( *(_DWORD *)(v8 + 968) == 5 && !v12 )
        {
          *(_BYTE *)(v7.QuadPart + 270) = v125 | 0x40;
          goto LABEL_16;
        }
      }
      *(_BYTE *)(v7.QuadPart + 270) = v126 | 2;
      goto LABEL_16;
    }
    goto LABEL_16;
  }
  v107 = 0;
  v108 = *(_QWORD *)(v7.QuadPart + 192);
  if ( v108 )
  {
    v107 = 2 * *(unsigned __int16 *)(v108 + 70);
    v109 = (const wchar_t *)(v108 + *(unsigned __int16 *)(v108 + 68));
  }
  else
  {
    v109 = 0;
  }
  v110 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  v112 = *(_DWORD *)(GetXdbServerGlobals(v111) + 8196);
  v272 = v112;
  if ( *(_DWORD *)(v8 + 988) <= 1u )
  {
    if ( *(_DWORD *)(*(_QWORD *)(v110 + 520) + 20LL) )
    {
      *(_DWORD *)(v7.QuadPart + 404) = 1;
      v276 = v112;
      goto LABEL_16;
    }
    if ( v112 )
    {
LABEL_16:
      v15 = v266;
      goto LABEL_17;
    }
    *(_BYTE *)(v7.QuadPart + 270) |= 4u;
    *(_BYTE *)(v7.QuadPart + 271) |= 1u;
    v113 = (unsigned __int8)-*((_BYTE *)qword_102EF3550 + 453);
    *(_BYTE *)(v7.QuadPart + 271) = *(_BYTE *)(v7.QuadPart + 271) & 0xF7
                                  | (*((_BYTE *)qword_102EF3550 + 453) != 0 ? 8 : 0);
    v273 = 1;
    *(_DWORD *)(v7.QuadPart + 404) = 1;
    XdbServerGlobals = GetXdbServerGlobals(v113);
    v15 = v266;
    goto LABEL_207;
  }
  if ( !FPDWFeaturesExposed()
    || (*(_DWORD *)(v7.QuadPart + 400) & 0x8000) != 0
    || *(_DWORD *)(*(_QWORD *)(v110 + 520) + 20LL) )
  {
    if ( v272
      && FPDWFeaturesExposed()
      && v107 > 4
      && !wcsncmp(v109, L"b-", 2u)
      && *(_DWORD *)(*(_QWORD *)(v110 + 520) + 20LL) )
    {
      *(_BYTE *)(v7.QuadPart + 270) |= 4u;
      *(_BYTE *)(v7.QuadPart + 271) |= 1u;
      *(_BYTE *)(v7.QuadPart + 271) = *(_BYTE *)(v7.QuadPart + 271) & 0xF7
                                    | (*((_BYTE *)qword_102EF3550 + 453) != 0 ? 8 : 0);
      *(_DWORD *)(v7.QuadPart + 404) = 1;
    }
    else
    {
      *(_BYTE *)(v7.QuadPart + 270) |= 2u;
    }
    goto LABEL_16;
  }
  if ( (*((_BYTE *)qword_102ECFB10 + 1196) & 4) != 0
    || (v115 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                         + SystemThread_TlsOffset)) != 0
    && (v116 = **(struct CSessionTraceFlags ***)(v115 + 56)) != 0
    && CSessionTraceFlags::CheckSessionTraceInternal(v116, 0x2562u) )
  {
    v15 = v266;
    goto LABEL_221;
  }
  v15 = v266;
  if ( v266 )
  {
LABEL_221:
    *(_BYTE *)(v7.QuadPart + 270) |= 2u;
    goto LABEL_17;
  }
  *(_BYTE *)(v7.QuadPart + 270) |= 4u;
  *(_BYTE *)(v7.QuadPart + 271) |= 1u;
  v117 = (unsigned __int8)-*((_BYTE *)qword_102EF3550 + 453);
  *(_BYTE *)(v7.QuadPart + 271) = *(_BYTE *)(v7.QuadPart + 271) & 0xF7
                                | (*((_BYTE *)qword_102EF3550 + 453) != 0 ? 8 : 0);
  v273 = 1;
  *(_DWORD *)(v7.QuadPart + 404) = 1;
  XdbServerGlobals = GetXdbServerGlobals(v117);
LABEL_207:
  if ( *(_BYTE *)(XdbServerGlobals + 12004) )
    *(_BYTE *)(v7.QuadPart + 270) |= 8u;
LABEL_17:
  if ( !ImpliedAuthenticationManager::CanConnectionBeImpliedAuthInXdbOrLinux(
          (const struct CSession *)v7.QuadPart,
          (const struct CPhysicalConnection *)v8,
          0) )
    goto LABEL_18;
  if ( (*(_BYTE *)(v7.QuadPart + 270) & 2) != 0
    || IsWcowExtensibilityLoopback((const struct CSession *)v7.QuadPart, (const struct CPhysicalConnection *)v8) )
  {
    if ( (*(_BYTE *)(v7.QuadPart + 270) & 0x10) != 0
      && *(_DWORD *)(qword_102ECFB00 + 14504)
      && (unsigned int)OsInfo::GetContainerType(SOS_OS_OsInfo) != 2 )
    {
      OsInfo::GetContainerType(SOS_OS_OsInfo);
    }
    v135 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v7.QuadPart + 96) + 16LL))(*(_QWORD *)(v7.QuadPart + 96));
    ImpliedLoginInfoFromCertificate = ImpliedAuthenticationManager::GetImpliedLoginInfoFromCertificate(
                                        v136,
                                        *(const struct _CERT_CONTEXT **)(v135 + 1032));
    v306 = ImpliedLoginInfoFromCertificate;
  }
  else
  {
    if ( (*(_BYTE *)(v7.QuadPart + 270) & 0x10) == 0 )
      goto LABEL_271;
    if ( *(_DWORD *)(qword_102ECFB00 + 14504)
      && ((unsigned int)OsInfo::GetContainerType(SOS_OS_OsInfo) == 2
       || (unsigned int)OsInfo::GetContainerType(SOS_OS_OsInfo) == 3) )
    {
LABEL_265:
      v270 = 0;
      goto LABEL_18;
    }
    memset(pSid, 0, sizeof(pSid));
    v631 = 0;
    v320 = 68;
    if ( GetAppContainerSidFromSNIConnection(v128, v127, v271, (unsigned __int8 *)pSid, &v320) >= 0 )
    {
      LengthSid = GetLengthSid(pSid);
      ImpliedLoginInfoFromCertificate = ImpliedAuthenticationManager::GetImpliedLoginInfo(
                                          g_impliedAuthenticationManager,
                                          (unsigned __int8 *)pSid,
                                          LengthSid);
      v306 = ImpliedLoginInfoFromCertificate;
    }
    else
    {
LABEL_271:
      ImpliedLoginInfoFromCertificate = 0;
    }
  }
  v270 = 0;
  if ( ImpliedLoginInfoFromCertificate )
  {
    v313 = 1;
    v131 = *(_BYTE *)(v7.QuadPart + 270);
    v270 = 0;
    if ( (v131 & 0x10) == 0 )
    {
      *(_BYTE *)(v7.QuadPart + 270) = v131 | 4;
      *(_BYTE *)(v7.QuadPart + 271) |= 1u;
      v132 = (unsigned __int8)-*((_BYTE *)qword_102EF3550 + 453);
      *(_BYTE *)(v7.QuadPart + 271) = *(_BYTE *)(v7.QuadPart + 271) & 0xF7
                                    | (*((_BYTE *)qword_102EF3550 + 453) != 0 ? 8 : 0);
      v133 = GetXdbServerGlobals(v132);
      v134 = 3;
      if ( *(_DWORD *)(v133 + 8308) )
        v134 = 1;
      *(_DWORD *)(v7.QuadPart + 404) = v134;
      v276 = v272;
      goto LABEL_265;
    }
  }
LABEL_18:
  if ( (*((_BYTE *)qword_102ECFB10 + 1072) & 0x40) != 0
    || (v16 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                        + SystemThread_TlsOffset)) != 0
    && (v137 = **(struct CSessionTraceFlags ***)(v16 + 56)) != 0
    && CSessionTraceFlags::CheckSessionTraceInternal(v137, 0x2186u)
    || (unsigned int)IsReplicatedMasterEnabled() && (*(_BYTE *)(v7.QuadPart + 270) & 2) != 0 )
  {
    if ( (v138 = *(_QWORD *)(v7.QuadPart + 192)) != 0
      && (v139 = (const wchar_t *)(v138 + *(unsigned __int16 *)(v138 + 68)), *(_WORD *)(v138 + 70))
      && v139
      && CompareStringWEnglishNoCase(1u, 0, v139, *(unsigned __int16 *)(v138 + 70), L"PHYSMASTER", 10) == 2
      || v15 )
    {
      *(_BYTE *)(v7.QuadPart + 270) |= 0x20u;
    }
  }
  v336 = 0;
  v17 = v271;
  v18 = *(_OWORD *)((char *)v271 + 28);
  *(LARGE_INTEGER *)&v336 = v7;
  v19 = v278;
  *((_QWORD *)&v336 + 1) = v278;
  *((LARGE_INTEGER *)v278 + 1) = v7;
  *(_QWORD *)(v7.QuadPart + 480) = v19;
  _InterlockedIncrement((volatile signed __int32 *)v19 + 19);
  ITaskProxy::SetCurrentTaskProxy((struct ITaskProxy *)(v7.QuadPart + 504));
  if ( !(unsigned int)CConnection::FInitMainEc(v19, v279) )
    goto LABEL_284;
  v20 = CDiagnostics::PCreateInstanceNoX();
  v21 = (volatile signed __int32 *)v20;
  v427 = v20;
  if ( !v20 )
    goto LABEL_284;
  *((_QWORD *)v19 + 5) = v20;
  if ( !CSession::FInitForNewConnection((CSession *)v7.QuadPart)
    || !CSessionMgr::FAddSession((struct CSession *)v7.QuadPart) )
  {
    if ( _InterlockedExchangeAdd(v21 + 6, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)v21 + 40LL))(v21, 1);
LABEL_284:
    v140 = *(CConnection **)(v7.QuadPart + 480);
    if ( v140 )
      CConnection::Release(v140);
    *(_QWORD *)(v7.QuadPart + 480) = 0;
    *((_QWORD *)v19 + 1) = 0;
    v141 = (ExecutionContext *)*((_QWORD *)v19 + 6);
    if ( v141 )
    {
      ExecutionContext::CleanupAndDelete(v141, 1);
      *((_QWORD *)v19 + 6) = 0;
    }
    *((_QWORD *)v19 + 5) = 0;
    goto LABEL_289;
  }
  v22 = *(_QWORD *)(v7.QuadPart + 96);
  if ( v22 && (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22) )
  {
    v23 = *(_WORD *)(v7.QuadPart + 16);
    v24 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v7.QuadPart + 96) + 16LL))(*(_QWORD *)(v7.QuadPart + 96));
    *(_WORD *)(v24 + 684) = v23;
    v25 = *(_QWORD *)(v24 + 448);
    if ( v25 )
    {
      v295 = v23;
      SNISetInfo(v25, 28, &v295);
    }
    v19 = v278;
  }
  v418 = v18;
  ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))CDiagnostics::InitMainThread)(
    v21,
    (LARGE_INTEGER)v7.QuadPart,
    1,
    &v418,
    v17);
  CDiagManager::Add((struct CDiagThreadSafe *)v21);
  v336 = 0;
  if ( _InterlockedExchangeAdd(v21 + 6, 0xFFFFFFFF) == 1 )
    (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)v21 + 40LL))(v21, 1);
  CAutoSetupCXCtxtSingleThread::CAutoSetupCXCtxtSingleThread(
    (CAutoSetupCXCtxtSingleThread *)v628,
    v315,
    (struct CSession *)v7.QuadPart,
    v19);
  v26 = 8LL * SystemThread_TlsIndex;
  v277 = *(struct CUEnvTransient **)(*(_QWORD *)(SystemThread_TlsOffset
                                               + *(_QWORD *)((char *)NtCurrentTeb()->ThreadLocalStoragePointer + v26))
                                   + 120LL);
  v316 = **(CDbAndSetOpts ***)(*(_QWORD *)(*(_QWORD *)((char *)NtCurrentTeb()->ThreadLocalStoragePointer + v26)
                                         + SystemThread_TlsOffset)
                             + 64LL);
  v27 = 0;
  v280 = 0;
  v28 = 0;
  v281 = 0;
  v29 = *(volatile signed __int32 **)(v7.QuadPart + 648);
  if ( (*(unsigned __int8 (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)v29 + 24LL))(v29, 0) )
  {
    _InterlockedIncrement(v29 + 35);
    v27 = v29;
    v280 = v29;
    v28 = 1;
    v281 = 1;
  }
  if ( (v281 & 1) == 0 )
  {
    if ( (v28 & 1) != 0 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v27 + 32LL))(v27);
      if ( _InterlockedExchangeAdd(v27 + 35, 0xFFFFFFFF) == 1 )
      {
        v142 = *((_QWORD *)v280 + 1);
        (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)v280 + 40LL))(v280, 1);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v142 + 16LL))(v142);
      }
      v280 = 0;
      v281 &= ~1u;
    }
    CAutoSetupCXCtxtSingleThread::~CAutoSetupCXCtxtSingleThread((CAutoSetupCXCtxtSingleThread *)v628);
LABEL_289:
    ITaskProxy::SetCurrentTaskProxy(0);
    return 2147500037LL;
  }
  SEParams::SEParams((SEParams *)v595);
  v30 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                  + SystemThread_TlsOffset
                  + 80LL);
  v31 = (struct XactWorkspace *)(**(__int64 (__fastcall ***)(volatile signed __int32 *))v280)(v280);
  SessionIsolationLevel = getSessionIsolationLevel(*((_BYTE *)v316 + 76));
  SEParams::Init(
    (SEParams *)v595,
    0xFFFFFFFF,
    SessionIsolationLevel,
    0,
    v31,
    (struct SEExecutionStatistics *)(v30 + 256),
    0);
  v340 = 0;
  AutoInstallParams::Install((AutoInstallParams *)&v339, (struct SEParams *)v595);
  if ( v340 )
    utassert_fail(
      1u,
      "NULL == m_separamsPrev",
      "sephlpr.cpp",
      82,
      "SEParams is being installed more than once. Illegal usage.");
  CAutoSetXLvlIntCtxtImplNoException::CAutoSetXLvlIntCtxtImplNoException(
    (CAutoSetXLvlIntCtxtImplNoException *)&v625,
    (struct CSession *)v7.QuadPart,
    v315);
  v540 = 0;
  v33 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v34 = *(_QWORD *)(v33 + 256);
  if ( !v34 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v34 = *(_QWORD *)(v33 + 256);
  }
  v334 = *(_QWORD *)(v34 + 3208);
  v35 = v334;
  *(_QWORD *)(v34 + 3208) = ex_trans_cexcept;
  v428 = v35;
  ExcHandler::ExcHandler((ExcHandler *)v594, 0, 0, 0, (int (*)(int, int, int, int, char *))hdl_prntbackout, 0);
  v552 = 0;
  *(_DWORD *)v556 = 0;
  if ( !(unsigned int)IsContainedAGEnabledInstance() )
    goto LABEL_52;
  CSession::GetHadronAgId((CSession *)v7.QuadPart, &v555);
  if ( *(_QWORD *)&v555.Data1 == *(_QWORD *)&Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val.Data1
    && *(_QWORD *)v555.Data4 == *(_QWORD *)Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val.Data4 )
  {
    v37 = 0;
    v321 = 0;
    v38 = *(_QWORD *)(v7.QuadPart + 192);
    if ( v38 )
    {
      v37 = 2 * *(unsigned __int16 *)(v38 + 70);
      v321 = v37;
      v39 = (const wchar_t *)(v38 + *(unsigned __int16 *)(v38 + 68));
    }
    else
    {
      v39 = 0;
    }
    v380 = v39;
    v543 = 0;
    v544[0] = 0;
    v40 = Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
    v555 = Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
    if ( v39 && v37 )
    {
      if ( *(_BYTE *)(GetXdbServerGlobals(v36) + 12004) )
      {
        v40 = v555;
      }
      else
      {
        v40 = *HadrRuntimeCallbacks::GetContainedOrSystemAGId(v538, v39, v37, &v543, v544);
        v538[1] = v40;
        v555 = v40;
      }
    }
    if ( *(_QWORD *)&v40.Data1 == *(_QWORD *)&Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val.Data1
      && _mm_srli_si128((__m128i)v40, 8).m128i_u64[0] == *(_QWORD *)Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val.Data4 )
    {
      *(_BYTE *)(v7.QuadPart + 270) |= 0x20u;
      v41 = Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
      *(_WORD *)(v7.QuadPart + 4928) = 1;
      *(_WORD *)(v7.QuadPart + 4930) = 0;
LABEL_51:
      *(GUID *)(v7.QuadPart + 4912) = v41;
      goto LABEL_52;
    }
    *(GUID *)(v7.QuadPart + 4912) = v40;
    *(_WORD *)(v7.QuadPart + 4928) = v543;
    *(_WORD *)(v7.QuadPart + 4930) = v544[0];
LABEL_52:
    v629 = *(_QWORD *)(*(_QWORD *)(v7.QuadPart + 648) + 16LL);
    v417[0] = 0;
    v308 = 0;
    AutoInstallMsqlXact::InstallXactForLogin(
      (AutoInstallMsqlXact *)v417,
      *(struct CMsqlXactManager **)(v7.QuadPart + 648));
    v294 = CommonGlobalState::m_PerfCountersEnabled;
    if ( CommonGlobalState::m_PerfCountersEnabled )
      PerfmonManager::IncrementCounterValue((PerfmonManager *)qword_102ECFB00, 3u, 0x10u, 1, 0);
    v42 = *(_QWORD *)(v7.QuadPart + 192);
    *(_DWORD *)(v7.QuadPart + 400) = *(_DWORD *)(v42 + 24);
    v43 = 2 * *(unsigned __int16 *)(v42 + 42);
    v272 = v43;
    v293 = v43;
    v307 = (wchar_t *)(v42 + *(unsigned __int16 *)(v42 + 40));
    v331 = v307;
    if ( !(unsigned int)IsReplicatedMasterEnabled() || CSession::FPhysicalMasterUsageForced((CSession *)v7.QuadPart) )
    {
      v44 = qword_102ECFB00;
      v433 = qword_102ECFB00;
      MasterDbId = GetMasterDbId();
      DBMgr::OpenDB(*(_QWORD *)(v44 + 32), 0, MasterDbId, 14, 1, 16448);
    }
    else
    {
      if ( !(unsigned __int8)StartupDependencies::IsCompleted(16) )
      {
        Login = 40613;
        v265 = 40613;
        v542 = 162;
        goto LABEL_321;
      }
      v153 = qword_102ECFB00;
      v431 = qword_102ECFB00;
      ReplicatedMasterDbId = GetReplicatedMasterDbId();
      v155 = DBMgr::OpenDB(*(_QWORD *)(v153 + 32), 0, ReplicatedMasterDbId, 14, 0, 16448);
      v432 = v155;
      if ( !v155 || *(_DWORD *)(*(_QWORD *)(v155 + 4624) + 1656LL) )
      {
        Login = 40613;
        v265 = 40613;
        v542 = 169;
        goto LABEL_321;
      }
    }
    v269 = 1;
    if ( (*(_BYTE *)(qword_102ECFB00 + 48) & 0x40) != 0 )
    {
      user_log(17142, 14, 0, 0x42F6u);
      v542 = 13;
      Login = 40613;
      if ( !v273 )
        Login = 18456;
      v265 = Login;
      goto LABEL_321;
    }
    if ( (*(_BYTE *)(v7.QuadPart + 402) & 0xFu) >= 2 )
    {
      v542 = 14;
      goto LABEL_331;
    }
    v378 = GetMasterDbId();
    v434 = ((__int64 (*)(void))g_dbtableFactory[4])();
    *(_DWORD *)(v7.QuadPart + 224) = *(_DWORD *)(v434 + 544);
    v379 = Base_PublicGlobals::sm_invariantTscAvailable;
    if ( Base_PublicGlobals::sm_invariantTscAvailable )
    {
      QueryPerformanceCounter(&PerformanceCount);
      QuadPart = (CSbTransportMgr *)PerformanceCount.QuadPart;
      v384 = (CSbTransportMgr *)PerformanceCount.QuadPart;
    }
    else
    {
      v383 = MEMORY[0x7FFE0008];
      QuadPart = MEMORY[0x7FFE0008];
      v384 = MEMORY[0x7FFE0008];
      v307 = v331;
      v43 = v293;
      v272 = v293;
    }
    CNetConnection::GetLock(*(CNetConnection **)(v8 + 16));
    *(_QWORD *)(v8 + 240) = QuadPart;
    *(_DWORD *)(v8 + 256) = 1;
    v435 = *(_QWORD *)(v8 + 16);
    v47 = *(_QWORD **)(v435 + 392);
    v436 = v47;
    v48 = SOS_PublicGlobals::sm_SpinlockStatSnapshot;
    v296 = SOS_PublicGlobals::sm_SpinlockStatSnapshot;
    if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
    {
      v156 = rand();
      v48 = (unsigned int)(5 * (v156 / 5));
      if ( v156 == (_DWORD)v48 )
        Spinlock<114,16,258>::UpdateStatSnapshot();
    }
    *v47 = 0;
    if ( !*(_BYTE *)(GetXdbServerGlobals(v48) + 12004) )
      goto LABEL_62;
    v157 = *(_QWORD *)(v7.QuadPart + 192);
    if ( v157 )
    {
      v158 = 2 * *(unsigned __int16 *)(v157 + 70);
      v335 = v158;
      v159 = (const wchar_t *)(v157 + *(unsigned __int16 *)(v157 + 68));
    }
    else
    {
      v159 = 0;
      v158 = v335;
    }
    v385 = v159;
    if ( (*(_BYTE *)(v7.QuadPart + 270) & 4) != 0 )
    {
      v160 = (CDefaultCollation *)CDefaultCollation::PDCServer();
      if ( CDefaultCollation::FEqIgnoreCaseW(v160, L"DwGen3TempDB", 0x18u, v159, v158)
        || FisFidoSysDbName(v159, (unsigned __int64)v158 >> 1) )
      {
        v542 = 179;
        goto LABEL_331;
      }
    }
    if ( FIsDwFidoDatabaseType(v159, v158) )
    {
      v342 = 3558;
      v49 = v279;
      v161 = operator new(8u, v279, "sql\\ntdbms\\msql\\ods\\login.cpp", 3558, 3u);
      v437 = v161;
      if ( v161 )
        *v161 = 0;
      else
        v161 = 0;
      v386 = v161;
      CAutoP<AutoReadOnlyXact>::operator=(&v308, v161);
      v162 = v308;
      AutoReadOnlyXact::BeginCompatibleXact(v308, L"login", 12, 0);
      if ( *(_QWORD *)v162 )
        v163 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v162 + 72LL))(*(_QWORD *)v162);
      else
        v163 = 0;
      v541 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v163 + 296LL))(v163);
      StartDwFidoScanTran(&v541, 0, 0);
    }
    else
    {
LABEL_62:
      v49 = v279;
    }
    if ( v313 )
    {
      LoadSecContextFromImpliedLoginInfo((struct CSession *)v7.QuadPart, v271, v306);
      Login = v265;
    }
    else
    {
      if ( !v273 )
      {
        *(_QWORD *)&v551[1] = 0;
        v553 = *(_BYTE *)(v7.QuadPart + 403) & 1;
        LOBYTE(v263) = *(_DWORD *)(v8 + 988) <= 1u;
        LODWORD(v262) = 0;
        Login = FindLogin(
                  (int)v271,
                  (int)v307,
                  v43,
                  (int)&v550,
                  (enum ELoginFailedState *)&v542,
                  (__int64)&v553,
                  0,
                  (__int64)v636,
                  (__int64)v551,
                  (__int64)v637,
                  (__int64)&v554,
                  v262,
                  0,
                  0,
                  v263,
                  (__int64)&v551[1],
                  (__int64)&v552,
                  (__int64)v556);
        v265 = Login;
        if ( !Login && (v50 = *(unsigned __int8 *)(GetXdbServerGlobals(v50) + 12005), (v298 = v50) != 0) )
        {
          v52 = v552;
          if ( v552 )
          {
            v164 = *(void **)&v551[1];
            v438 = *(_QWORD *)&v551[1];
            if ( *(_QWORD *)&v551[1] )
            {
              v439 = *(void **)(*(_QWORD *)&v551[1] + 16LL);
              operator delete[](v439);
              operator delete(v164, Login + 24);
            }
            v63 = v276;
            goto LABEL_107;
          }
        }
        else
        {
          v52 = v552;
        }
        if ( byte_102EDCC61 || (*((_BYTE *)qword_102ECFB10 + 1559) & 8) != 0 )
        {
          v440 = v52;
          if ( !*(_DWORD *)(qword_102ECFB00 + 14504) )
          {
            GetMasterDbId();
            AuthenticateAgainstExtGovMD((_DWORD)v49, v53, (unsigned int)&v551[1], v52, (__int64)&v265, (__int64)&v542);
            Login = v265;
          }
          if ( *(_DWORD *)(GetXdbServerGlobals(v50) + 11976) )
          {
            v165 = GetReplicatedMasterDbId();
            ManagedInstanceAuthenticateAgainstExtGovMD(v49, v165, &v551[1], v52, &v265, &v542);
            Login = v265;
          }
        }
        if ( byte_102F1BB90 || (*((_BYTE *)qword_102ECFB10 + 1743) & 0x40) != 0 )
        {
          ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
          v442 = (__int64 *)(ThreadLocalStoragePointer[SystemThread_TlsIndex] + SystemThread_TlsOffset);
          v443 = *v442;
          v444 = *(_QWORD *)(*(_QWORD *)(v443 + 120) + 264LL);
          v166 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v444 + 232LL))(v50, 1);
          v167 = v166;
          v445 = v166;
          if ( v166
            && (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v166 + 8LL))(v166) == 4
            && (v168 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v167 + 32LL))(v167, 1),
                v169 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v167 + 24LL))(v167, 1),
                v170 = (CDefaultCollation *)CDefaultCollation::PDCServer(),
                CDefaultCollation::FEqIgnoreCaseW(v170, v169, v168, L"##MS_BluemoonCertificate##", 0x34u)) )
          {
            *(_BYTE *)(v7.QuadPart + 270) |= 4u;
            v171 = *(_BYTE *)(v7.QuadPart + 270);
            *(_BYTE *)(v7.QuadPart + 271) |= 1u;
            *(_BYTE *)(v7.QuadPart + 270) = v171 | 8;
            v307 = v331;
            v272 = v293;
          }
          else
          {
            v307 = v331;
            v272 = v293;
          }
          Login = v265;
        }
        if ( *((_BYTE *)qword_102EF3550 + 655) )
        {
          v172 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
          v446 = v172;
          if ( *(_DWORD *)(qword_102ECFB00 + 14504) )
          {
            if ( *(_DWORD *)(v8 + 988) <= 1u && *(_DWORD *)(*(_QWORD *)(v172 + 520) + 20LL) )
            {
              v173 = *(const wchar_t **)(v7.QuadPart + 960);
              if ( v173 )
              {
                v174 = *(_DWORD *)(v7.QuadPart + 968);
              }
              else
              {
                v179 = *(_QWORD *)(v7.QuadPart + 192);
                v174 = 2 * *(unsigned __int16 *)(v179 + 50);
                v173 = (const wchar_t *)(v179 + *(unsigned __int16 *)(v179 + 48));
              }
              v388 = v173;
              v325 = v174;
              v175 = *(const wchar_t **)(GetXdbServerGlobals(qword_102ECFB00) + 28360);
              v447 = v175;
              v176 = -1;
              do
                ++v176;
              while ( v175[v176] );
              v177 = 2 * v176;
              v448 = v177;
              if ( v174 == (_DWORD)v177 )
              {
                v343 = CompareStringWEnglishNoCase(
                         1u,
                         0,
                         v173,
                         (unsigned __int64)v174 >> 1,
                         v175,
                         (unsigned __int64)(int)v177 >> 1);
                if ( v343 == 2 )
                {
                  v178 = *(_BYTE *)(v7.QuadPart + 270);
                  if ( (v178 & 4) == 0 )
                  {
                    *(_BYTE *)(v7.QuadPart + 270) = v178 | 4;
                    *(_BYTE *)(v7.QuadPart + 271) |= 1u;
                  }
                }
              }
            }
          }
        }
        v299 = byte_102EDCDF0;
        v54 = *(_BYTE *)(v7.QuadPart + 270);
        v55 = v54 & 2;
        v268 = v54 & 2;
        if ( byte_102EDCDF0 && (v54 & 0x40) != 0 && !v55 && !Login )
        {
          v419 = *(struct _GUID *)((char *)v271 + 28);
          Login = AuthenticateLoginOnPolarisFrontend(
                    (struct CSession *)v7.QuadPart,
                    &v419,
                    v307,
                    v272,
                    v634,
                    (enum ELoginFailedState *)&v542);
          v265 = Login;
        }
        v56 = 0;
        v326 = 0;
        v57 = *(_QWORD *)(v7.QuadPart + 192);
        if ( v57 )
        {
          v56 = 2 * *(unsigned __int16 *)(v57 + 70);
          v326 = v56;
          v58 = (const wchar_t *)(v57 + *(unsigned __int16 *)(v57 + 68));
          v389 = v58;
        }
        else
        {
          v58 = 0;
          v389 = 0;
        }
        if ( (unsigned int)IsVDWFrontendInstance()
          && (*((_BYTE *)qword_102EF3550 + 1196) || IsSynapseSALEnabled())
          && !v55
          && !Login )
        {
          v180 = dword_102F1BBA4;
          v344 = dword_102F1BBA4;
          v449 = L"msdb";
          v181 = (CDefaultCollation *)CDefaultCollation::PDCServer();
          if ( CDefaultCollation::FEqIgnoreCaseW(v181, v58, v56, L"msdb", v180) && byte_102EDCE0D
            || (v182 = dword_102F1BB9C,
                v345 = dword_102F1BB9C,
                v450 = L"tempdb",
                v183 = (CDefaultCollation *)CDefaultCollation::PDCServer(),
                CDefaultCollation::FEqIgnoreCaseW(v183, v58, v56, L"tempdb", v182))
            && byte_102EDCE0E )
          {
            Login = 18456;
            v265 = 18456;
            v542 = 193;
            v184 = *(void **)&v551[1];
            v451 = *(_QWORD *)&v551[1];
            if ( !*(_QWORD *)&v551[1] )
              goto LABEL_321;
            v185 = *(void **)(*(_QWORD *)&v551[1] + 16LL);
            v452 = v185;
LABEL_393:
            operator delete[](v185);
            operator delete(v184, 0x18u);
            goto LABEL_321;
          }
          v55 = v268;
        }
        if ( IsTridentSqlFrontendSession()
          && (byte_102EDCC88 || (*((_BYTE *)qword_102ECFB10 + 1519) & 0x40) != 0)
          && !v55 )
        {
          if ( !Login )
          {
            if ( byte_102EDCEFD )
            {
              v186 = dword_102F1BBA4;
              v346 = dword_102F1BBA4;
              v453 = L"msdb";
              v187 = (CDefaultCollation *)CDefaultCollation::PDCServer();
              if ( CDefaultCollation::FEqIgnoreCaseW(v187, v58, v56, L"msdb", v186)
                || (v188 = dword_102F1BBA0,
                    v347 = dword_102F1BBA0,
                    v454 = L"model",
                    v189 = (CDefaultCollation *)CDefaultCollation::PDCServer(),
                    CDefaultCollation::FEqIgnoreCaseW(v189, v58, v56, L"model", v188)) )
              {
                Login = 18456;
                v265 = 18456;
                v542 = 193;
                v184 = *(void **)&v551[1];
                v455 = *(_QWORD *)&v551[1];
                if ( !*(_QWORD *)&v551[1] )
                  goto LABEL_321;
                v185 = *(void **)(*(_QWORD *)&v551[1] + 16LL);
                v456 = v185;
                goto LABEL_393;
              }
            }
            goto LABEL_82;
          }
        }
        else if ( !Login )
        {
LABEL_82:
          if ( *((_BYTE *)qword_102EF3550 + 1213) )
          {
            v191 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v7.QuadPart + 96) + 16LL))(*(_QWORD *)(v7.QuadPart + 96));
            v457 = v191;
            if ( *(_DWORD *)(v191 + 1088) )
            {
              v192 = (const wchar_t *)GetXdbServerGlobals(v190);
              v458 = v192;
              v193 = -1;
              do
                ++v193;
              while ( v192[v193] );
              v459 = 2 * v193;
              v558 = 0;
              v559 = 0;
              v560 = 0;
              v561 = 0;
              v562 = 0;
              v568 = 0;
              v576 = 0;
              v577 = 0;
              v578 = 0;
              v582 = 0;
              v583 = 0;
              v584 = 0;
              v585 = 0;
              v586 = 0;
              v587 = 0;
              v563 = 0;
              v564 = 0;
              v565 = 0;
              v566 = 0;
              v567 = 0;
              v569 = 0;
              v570 = 0;
              v571 = 0;
              v572 = 0;
              v573 = 0;
              v574 = 0;
              v575 = 0;
              v579 = 0;
              v580 = 0;
              v581 = 0;
              v194 = v271;
              v420 = *(struct _GUID *)((char *)v271 + 28);
              v195 = CCloudExtensions::PrivateEndpointsAccessLockdownCheck(
                       v192,
                       (unsigned __int16)(2 * v193),
                       &szPassword,
                       0,
                       (const wchar_t *)(v191 + 776),
                       *(_DWORD *)(v191 + 972),
                       &v420,
                       0,
                       (struct VnetPeerAddressInfo *)&v558,
                       (enum ELoginFailedState *)&v542);
              v348 = v195;
              if ( v195 )
              {
                Login = v195;
                v265 = v195;
              }
              else
              {
                *(_DWORD *)&v556[4] = v563;
                v196 = CNetConnection::SetEffectivePeerIPAddress((CNetConnection *)v191, &v556[4], 4u);
                v349 = v196;
                if ( v196 )
                {
                  v542 = 160;
                  v588 = *(struct _GUID *)((char *)v194 + 28);
                  XEventReportLoginSubstepFailureEvent(v196, 160, 0, 0, &v588, &szPassword, 0, &szPassword, 0);
                  Login = 40613;
                  v265 = 40613;
                }
              }
              v558 = 0;
              v559 = 0;
              v560 = 0;
              v561 = 0;
              v568 = 0;
              v576 = 0;
              v577 = 0;
              v582 = 0;
              v583 = 0;
              v563 = 0;
              v564 = 0;
              v565 = 0;
              v566 = 0;
              v567 = 0;
              v569 = 0;
              v570 = 0;
              v571 = 0;
              v572 = 0;
              v573 = 0;
              v574 = 0;
              v575 = 0;
              LODWORD(v578) = 0;
              v579 = 0;
              v580 = 0;
              v581 = 0;
            }
          }
        }
        v59 = *(void **)&v551[1];
        v425 = *(_QWORD *)&v551[1];
        if ( *(_QWORD *)&v551[1] )
        {
          v460 = *(void **)(*(_QWORD *)&v551[1] + 16LL);
          operator delete[](v460);
          operator delete(v59, 0x18u);
        }
        v8 = v309;
        goto LABEL_86;
      }
      Login = FindLoginXdb(
                v49,
                v271,
                (struct CSession *)v7.QuadPart,
                v307,
                v43,
                0,
                0,
                &v540,
                (enum ELoginFailedState *)&v542);
      v265 = Login;
      *(_DWORD *)(v7.QuadPart + 5076) = v540;
    }
LABEL_86:
    v350 = Base_PublicGlobals::sm_invariantTscAvailable;
    if ( Base_PublicGlobals::sm_invariantTscAvailable )
    {
      QueryPerformanceCounter(&v390);
      v60 = (CSbTransportMgr *)v390.QuadPart;
      v392 = (CSbTransportMgr *)v390.QuadPart;
    }
    else
    {
      v60 = MEMORY[0x7FFE0008];
      v391 = MEMORY[0x7FFE0008];
      v392 = MEMORY[0x7FFE0008];
      Login = v265;
    }
    v393 = v60;
    CNetConnection::GetLock(*(CNetConnection **)(v8 + 16));
    v61 = (_QWORD *)(v8 + 240);
    v461 = v8 + 240;
    if ( *(_DWORD *)(v8 + 256) )
    {
      if ( (unsigned __int64)v393 > *v61 )
      {
        v306 = (CSbTransportMgr *)((char *)v393 - *v61);
        v462 = v306;
        v463 = v8 + 248;
        *(_QWORD *)(v8 + 248) += v306;
      }
      *(_DWORD *)(v8 + 256) = 0;
    }
    v464 = *(_QWORD *)(v8 + 16);
    v62 = *(_QWORD **)(v464 + 392);
    v465 = v62;
    v300 = SOS_PublicGlobals::sm_SpinlockStatSnapshot;
    if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
    {
      v197 = rand();
      if ( v197 == 5 * (v197 / 5) )
        Spinlock<114,16,258>::UpdateStatSnapshot();
    }
    *v62 = 0;
    if ( byte_102EDCEE7 && Login != 40613 && Login != 40969 && v542 != 165 )
    {
      v421 = *(struct _GUID *)((char *)v271 + 28);
      CheckIfTdAuditSessionExists((struct CSession *)v7.QuadPart, &v540, &v421);
    }
    if ( Login )
      goto LABEL_321;
    v63 = v276;
    if ( v276 )
    {
      *(_BYTE *)(v7.QuadPart + 270) |= 4u;
      *(_BYTE *)(v7.QuadPart + 271) |= 1u;
      v198 = *(_BYTE *)(v7.QuadPart + 271) & 0xF7 | (*((_BYTE *)qword_102EF3550 + 453) != 0 ? 8 : 0);
      *(_BYTE *)(v7.QuadPart + 271) = v198;
      v273 = 1;
      *(_BYTE *)(v7.QuadPart + 271) = v198 | 4;
      if ( !FPDWFeaturesExposed() )
      {
        Login = RebuildSdsLoginToken((struct CSession *)v7.QuadPart, &v540, (enum ELoginFailedState *)&v542);
        v265 = Login;
        if ( Login )
          goto LABEL_321;
      }
    }
    v466 = NtCurrentTeb()->ThreadLocalStoragePointer;
    v467 = (struct ImpliedLoginInfo **)(v466[SystemThread_TlsIndex] + SystemThread_TlsOffset);
    v468 = *v467;
    v306 = v468;
    ContextAccessor::UpdateSecurityInfo(*(_QWORD *)(*(_QWORD *)(v7.QuadPart + 104) + 264LL));
    v64 = *(_DWORD *)(qword_102ECFB00 + 48);
    if ( (v64 & 1) != 0 || (v64 & 0x2000) != 0 )
    {
      Login = 18401;
      if ( (*(_DWORD *)(qword_102ECFB00 + 48) & 1) != 0 )
        Login = 18461;
      v317 = Login;
      if ( !(***(unsigned int (__fastcall ****)(_QWORD))(*(_QWORD *)(v7.QuadPart + 104) + 264LL))(*(_QWORD *)(*(_QWORD *)(v7.QuadPart + 104) + 264LL)) )
      {
        v265 = Login;
        goto LABEL_427;
      }
      if ( (*(_DWORD *)(qword_102ECFB00 + 48) & 0x2000) != 0 && (*(_BYTE *)(v7.QuadPart + 269) & 0x20) == 0 )
      {
        v265 = Login;
        goto LABEL_427;
      }
      v199 = *(const void **)(v7.QuadPart + 960);
      if ( v199 )
      {
        v69 = *(unsigned int *)(v7.QuadPart + 968);
      }
      else
      {
        v200 = *(_QWORD *)(v7.QuadPart + 192);
        v69 = 2 * (unsigned int)*(unsigned __int16 *)(v200 + 50);
        v199 = (const void *)(v200 + *(unsigned __int16 *)(v200 + 48));
      }
      v394 = v199;
      v319 = v69;
      if ( dword_103095910 && (dword_103095910 != (_DWORD)v69 || memcmp_0(qword_103095810, v199, (unsigned int)v69)) )
      {
        v265 = Login;
        goto LABEL_427;
      }
      v351 = *(__int16 *)(v7.QuadPart + 16);
      v69 = qword_102ECFB00;
      if ( _InterlockedCompareExchange((volatile signed __int32 *)(qword_102ECFB00 + 11748), v351, 0) )
      {
        Login = v317;
        v265 = v317;
        goto LABEL_427;
      }
    }
    if ( (*(_BYTE *)(v7.QuadPart + 269) & 0x20) != 0 )
    {
      v201 = **(_QWORD **)(*(_QWORD *)(v7.QuadPart + 104) + 264LL);
      if ( !(v273 ? (*(__int64 (**)(void))(v201 + 72))() : (*(unsigned int (**)(void))v201)()) )
        goto LABEL_444;
    }
    if ( (*(_BYTE *)(qword_102ECFB00 + 48) & 0x20) != 0 )
    {
      v203 = GetMasterDbId();
      LOBYTE(v264) = 0;
      LOBYTE(v259) = 1;
      if ( !(unsigned __int8)ISECManager::AccessCheck(
                               0,
                               v203,
                               0,
                               24,
                               1,
                               v259,
                               0,
                               0,
                               30,
                               0,
                               0,
                               0,
                               0,
                               -1,
                               0,
                               0,
                               0,
                               v264,
                               0,
                               0,
                               0,
                               0,
                               0) )
      {
        ex_callprint(6005, 14, 1);
        Login = 18451;
        v265 = 18451;
        goto LABEL_321;
      }
    }
    if ( (*((_BYTE *)qword_102ECFB10 + 450) & 0x40) != 0 )
    {
      v204 = GetMasterDbId();
      LOBYTE(v261) = 0;
      LOBYTE(v260) = 1;
      if ( !(unsigned __int8)ISECManager::CheckPermRule(1413567059, 0, 0, v204, 0, 0, -1, 0, v260, v261, 0, 0) )
      {
LABEL_444:
        Login = 18451;
        v265 = 18451;
        goto LABEL_321;
      }
    }
    v65 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)(v7.QuadPart + 104) + 264LL) + 128LL))(*(_QWORD *)(*(_QWORD *)(v7.QuadPart + 104) + 264LL));
    v353 = v65;
    if ( v274 )
    {
      v66 = v547 == v65;
    }
    else
    {
      if ( v65 )
        goto LABEL_614;
      v66 = v547 == 0;
    }
    if ( v66 )
    {
      if ( (*(_BYTE *)(v7.QuadPart + 270) & 4) == 0 )
      {
        v67 = *(_QWORD *)(*(_QWORD *)(v7.QuadPart + 104) + 264LL);
        v469 = NtCurrentTeb()->ThreadLocalStoragePointer;
        v470 = (struct ImpliedLoginInfo **)(v469[SystemThread_TlsIndex] + SystemThread_TlsOffset);
        v471 = *v470;
        v306 = v471;
        LOWORD(v266) = *(_WORD *)(*((_QWORD *)v471 + 10) + 8LL);
        if ( !(*(unsigned int (__fastcall **)(__int64, _QWORD, __int64, _QWORD))(*(_QWORD *)v67 + 288LL))(
                v67,
                (unsigned __int16)v266,
                1,
                0) )
        {
          v542 = 15;
          goto LABEL_331;
        }
      }
LABEL_107:
      IssueLoginSuccessReport((struct CSession *)v7.QuadPart, v271);
      if ( (*(_DWORD *)(v7.QuadPart + 400) & 0x4000000) != 0 )
      {
        if ( *((_DWORD *)s_pServerConf + 2) != 3 )
        {
          Login = 18493;
          v265 = 18493;
          goto LABEL_321;
        }
        v205 = (const struct CSession *)*(unsigned int *)(qword_102ECFB00 + 14548);
        v354 = (int)v205;
        if ( (_DWORD)v205 )
        {
          Login = 18494;
          v265 = 18494;
          goto LABEL_321;
        }
        if ( *(_WORD *)(*(_QWORD *)(v7.QuadPart + 192) + 84LL) )
        {
          Login = 18495;
          v265 = 18495;
          goto LABEL_321;
        }
        v265 = 0;
        Login = LSpawnUserInstance(v205, v314);
        v265 = Login;
        if ( Login )
          goto LABEL_321;
      }
      v355 = *(_DWORD *)(GetXdbServerGlobals(v68) + 8308);
      if ( !v355 && *(_WORD *)(*(_QWORD *)(v7.QuadPart + 192) + 84LL) && !(unsigned int)FAttachDb(v636, v551, 0) )
      {
        v206 = 0;
        v330 = 0;
        v207 = *(_QWORD *)(v7.QuadPart + 192);
        if ( v207 )
        {
          v206 = 2 * *(unsigned __int16 *)(v207 + 70);
          v330 = v206;
        }
        Login = 1832;
        v69 = 15350;
        if ( !v206 )
          Login = 15350;
        v265 = Login;
        goto LABEL_427;
      }
      if ( !LoginUseDbHelper::FDetermineSessionDb(
              (LoginUseDbHelper *)&si128,
              v636,
              v551[0],
              0,
              0,
              (enum ELoginFailedState *)&v542,
              v312,
              v540) )
      {
        Login = si128.m128i_i32[0];
        if ( !HIDWORD(v593) )
          goto LABEL_651;
        v208 = si128.m128i_i32[0];
        if ( v591 != 1 )
          v208 = si128.m128i_u16[0];
        if ( v208 )
        {
LABEL_651:
          if ( LoginUseDbHelper::IsHaDrError((LoginUseDbHelper *)&si128) )
          {
            if ( v217 == 1 )
            {
              v274 = Login;
            }
            else
            {
              Login = (unsigned __int16)Login;
              v274 = (unsigned __int16)Login;
            }
          }
          else
          {
            Login = 18456;
            v274 = 18456;
          }
        }
        else
        {
          Login = 0;
          v274 = 0;
        }
        v265 = Login;
        if ( (*(_BYTE *)(v7.QuadPart + 270) & 4) != 0 )
        {
          v277 = (struct CUEnvTransient *)0x8000000001LL;
          if ( (qword_102F21DB4 & 0x80u) != 0LL )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
            XeCloudPkg::login_substep_failure::login_substep_failure((XeCloudPkg::login_substep_failure *)v619);
            v209 = si128.m128i_i32[0];
            if ( v591 != 1 )
              v209 = si128.m128i_u16[0];
            v621 = v209;
            v622 = si128.m128i_i32[3];
            v623 = 0;
            v624 = 0;
            v422 = *(_OWORD *)((char *)v271 + 28);
            v210 = v620 + 2;
            v472 = v620 + 2;
            v620[2] = &v422;
            *((_DWORD *)v210 + 2) = 16;
            *((_WORD *)v210 + 6) = 4;
            *((_WORD *)v210 + 7) = 0;
            v211 = v620 + 4;
            v473 = v620 + 4;
            v620[4] = L"useDbhelper.FDetermineSessionDb failed";
            *((_DWORD *)v211 + 2) = 76;
            *((_WORD *)v211 + 6) = 5;
            *((_WORD *)v211 + 7) = 0;
            v212 = GetXdbServerGlobals(5);
            v214 = -1;
            do
              ++v214;
            while ( *(_WORD *)(v212 + 2 * v214) );
            v474 = GetXdbServerGlobals(v213);
            v215 = v620 + 6;
            v475 = v620 + 6;
            v620[6] = v474;
            *((_DWORD *)v215 + 2) = 2 * v214;
            *((_WORD *)v215 + 6) = 6;
            *((_WORD *)v215 + 7) = 0;
            LODWORD(v215) = (unsigned int)v593 >> 1;
            v216 = v620 + 8;
            v476 = v620 + 8;
            v620[8] = &v592;
            *((_DWORD *)v216 + 2) = 2 * (_DWORD)v215;
            *((_WORD *)v216 + 6) = 7;
            *((_WORD *)v216 + 7) = 0;
            XeCloudPkg::login_substep_failure::Publish((XeCloudPkg::login_substep_failure *)v619);
          }
        }
        if ( Login )
        {
          if ( v273 )
          {
            if ( LoginUseDbHelper::IsHaDrError((LoginUseDbHelper *)&si128) )
            {
              v542 = 125;
              Login = 40613;
              v265 = 40613;
              goto LABEL_321;
            }
            goto LABEL_427;
          }
          if ( Login != 952 )
          {
LABEL_427:
            if ( !Login )
            {
LABEL_171:
              if ( v552 && !Login )
              {
                if ( *(_DWORD *)(qword_102ECFB00 + 14504)
                  && (*(_BYTE *)(GetXdbServerGlobals(v69) + 12009) || *(_BYTE *)(GetXdbServerGlobals(v69) + 12008))
                  && (v69 = *(unsigned __int8 *)(GetXdbServerGlobals(v69) + 12004), (v289 = v69) == 0)
                  && byte_102EDCA63
                  || (v290 = *(_BYTE *)(GetXdbServerGlobals(v69) + 12004)) != 0 && byte_102EDCA62 )
                {
                  LODWORD(v278) = 0;
                  v532 = NtCurrentTeb()->ThreadLocalStoragePointer;
                  v533 = (__int64 *)(v532[SystemThread_TlsIndex] + SystemThread_TlsOffset);
                  v534 = *v533;
                  v535 = *(CSession **)(v534 + 72);
                  CSession::GetSesLoginNameSidDbIdThreadSafe(
                    v535,
                    v639,
                    0x100u,
                    (unsigned int *)&v271,
                    v635,
                    0x55u,
                    (unsigned int *)&v278,
                    0);
                  UpdateFederatedAADPrincipalUsernameIfRequired(
                    (unsigned int)v635,
                    (_DWORD)v278,
                    (unsigned int)v639,
                    (_DWORD)v271,
                    (__int64)v279);
                }
              }
              if ( v308 )
              {
                if ( v270 < 0 )
                {
                  if ( *(_QWORD *)v308 )
                    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v308 + 32LL))(*(_QWORD *)v308);
                }
                else
                {
                  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v308 + 24LL))(*(_QWORD *)v308);
                }
              }
              v536 = v308;
              if ( v308 )
              {
                v252 = *(void (__fastcall ****)(_QWORD, __int64))v308;
                v537 = v252;
                if ( v252 )
                  (**v252)(v252, 1);
                operator delete(v308, 8u);
              }
              AutoInstallMsqlXact::~AutoInstallMsqlXact((AutoInstallMsqlXact *)v417);
              operator delete[]((void *)v552);
              ExcHandler::~ExcHandler((ExcHandler *)v594);
              v96 = v334;
              v97 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                  + SystemThread_TlsOffset;
              v98 = *(struct Worker **)(v97 + 256);
              if ( !v98 )
              {
                SystemThread::MakeMiniSOSThread(0);
                v98 = *(struct Worker **)(v97 + 256);
              }
              if ( *((_DWORD *)v98 + 139) )
                ExceptionPostCatchActions(v98);
              v629 = 0;
              if ( v270 < 0 && (*(_BYTE *)(qword_102ECFB00 + 48) & 1) != 0 )
                _InterlockedCompareExchange(
                  (volatile signed __int32 *)(qword_102ECFB00 + 11748),
                  0,
                  *(__int16 *)(v7.QuadPart + 16));
              if ( *(_WORD *)(*(_QWORD *)(*(_QWORD *)(SystemThread_TlsOffset
                                                    + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                      + SystemThread_TlsIndex))
                                        + 80LL)
                            + 8LL) )
                g_dbtableFactory[6](
                  *(unsigned __int16 *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                + SystemThread_TlsIndex)
                                                              + SystemThread_TlsOffset)
                                                  + 80LL)
                                      + 8LL),
                  14);
              if ( (WORD2(qword_102EDC9FC) & 0x400) != 0 )
              {
                v597 = 0x10000;
                v598 = 0;
                v599 = v602;
                v600 = &v603;
                v604 = 0;
                v601 = 0;
                v605 = 0;
                v602[0] = &v606;
                v602[1] = 9;
                if ( v311
                  && ((QueryPerformanceCounter(&v327), v327.QuadPart >= (unsigned __int64)v557.QuadPart)
                    ? (v253 = v327.QuadPart - v557.QuadPart)
                    : (v253 = 0),
                      Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart) )
                {
                  if ( v253 == -1 )
                    v254 = -1;
                  else
                    v254 = (unsigned __int64)(1000000 * v253)
                         / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
                }
                else
                {
                  v254 = 0;
                }
                v606 = v254;
                v607 = v550 == 0;
                XeSqlPkg::security_authentication_perf_login::Publish((XeSqlPkg::security_authentication_perf_login *)v596);
              }
              v99 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                  + SystemThread_TlsOffset;
              v100 = *(_QWORD *)(v99 + 256);
              if ( !v100 )
              {
                SystemThread::MakeMiniSOSThread(0);
                v100 = *(_QWORD *)(v99 + 256);
              }
              *(_QWORD *)(v100 + 3208) = v96;
              v625 = &CAutoSetXLvlIntCtxtImplNoException::`vftable';
              if ( v626 )
              {
                v626 = 0;
                v101 = (__int64 *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                 + SystemThread_TlsOffset);
                v102 = *v101;
                CExecLvlIntCtxt::ExitBatch(*(CExecLvlIntCtxt **)(*v101 + 128));
                *(_QWORD *)(v102 + 128) = 0;
              }
              CExecLvlIntCtxt::~CExecLvlIntCtxt((CExecLvlIntCtxt *)v627);
              v625 = &XactAccessor::`vftable';
              if ( v339 )
              {
                SEParams::UninstallFromTLS(v339);
                v339 = 0;
              }
              SEParams::~SEParams((SEParams *)v595);
              if ( (v281 & 1) != 0 )
              {
                v103 = v280;
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v280 + 32LL))(v280);
                if ( _InterlockedExchangeAdd(v103 + 35, 0xFFFFFFFF) == 1 )
                {
                  v255 = *((_QWORD *)v280 + 1);
                  (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)v280 + 40LL))(v280, 1);
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v255 + 16LL))(v255);
                }
                v280 = 0;
                v281 &= ~1u;
              }
              CAutoSetupCXCtxtSingleThread::~CAutoSetupCXCtxtSingleThread((CAutoSetupCXCtxtSingleThread *)v628);
              v104 = v336;
              if ( (_QWORD)v336 )
              {
                v256 = *(CConnection **)(v336 + 480);
                if ( v256 )
                  CConnection::Release(v256);
                *(_QWORD *)(v104 + 480) = 0;
              }
              v105 = *((_QWORD *)&v336 + 1);
              if ( *((_QWORD *)&v336 + 1) )
              {
                *(_QWORD *)(*((_QWORD *)&v336 + 1) + 8LL) = 0;
                v257 = *(ExecutionContext **)(v105 + 48);
                if ( v257 )
                {
                  ExecutionContext::CleanupAndDelete(v257, 1);
                  *(_QWORD *)(v105 + 48) = 0;
                }
                *(_QWORD *)(v105 + 40) = 0;
              }
              ITaskProxy::SetCurrentTaskProxy(0);
              return (unsigned int)v270;
            }
LABEL_321:
            if ( byte_102EDCADA )
            {
              v424 = *(_OWORD *)((char *)v271 + 28);
              AuditLoginXdb(&v540, Login, v542, &v424);
            }
            v152 = (unsigned int)CConnection::PNetConn(v278);
            LoginError(Login, (_DWORD)v271, v152, v542, (__int64)&si128);
            v270 = Login | 0x80000000;
            goto LABEL_171;
          }
        }
        else if ( byte_102EDCB21
               && (*(_BYTE *)(v7.QuadPart + 270) & 4) != 0
               && LoginUseDbHelper::IsHaDrError((LoginUseDbHelper *)&si128) )
        {
          v542 = 125;
          Login = 40613;
          v265 = 40613;
          goto LABEL_321;
        }
        goto LABEL_331;
      }
      v70 = v540;
      if ( byte_102EDCB3B )
      {
        if ( !v540 )
          goto LABEL_113;
        v218 = *(_QWORD *)(qword_102ECFB00 + 32);
        v477 = v218;
        switch ( v540 )
        {
          case 0x7FFCu:
            v219 = *(_QWORD *)(v218 + 104);
            break;
          case 0x7FFDu:
            v219 = *(_QWORD *)(v218 + 112);
            break;
          case 0x7FFFu:
            v219 = *(_QWORD *)(v218 + 88);
            break;
          default:
            if ( v540 > *(_DWORD *)(v218 + 76) )
              goto LABEL_498;
            v219 = *(_QWORD *)(*(_QWORD *)(v218 + 40) + 8LL * (int)(v540 - 1));
            break;
        }
        v332 = v219;
        if ( !v219 )
          goto LABEL_498;
        v301 = *(_BYTE *)(v219 + 628);
        if ( v301 && (*(_BYTE *)(v7.QuadPart + 270) & 4) != 0 )
        {
          if ( !*(_DWORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8) + 1028) && !v63 )
          {
            Login = 40852;
            v265 = 40852;
            v542 = 131;
            goto LABEL_321;
          }
          v70 = v540;
        }
      }
      if ( !v70 )
        goto LABEL_113;
      v220 = *(_QWORD *)(qword_102ECFB00 + 32);
      v478 = v220;
      switch ( v70 )
      {
        case 0x7FFCu:
          v221 = *(_QWORD *)(v220 + 104);
          goto LABEL_513;
        case 0x7FFDu:
          v221 = *(_QWORD *)(v220 + 112);
          goto LABEL_513;
        case 0x7FFFu:
          v221 = *(_QWORD *)(v220 + 88);
          goto LABEL_513;
      }
      if ( v70 <= *(_DWORD *)(v220 + 76) )
      {
        v221 = *(_QWORD *)(*(_QWORD *)(v220 + 40) + 8LL * (int)(v70 - 1));
LABEL_513:
        v333 = v221;
        if ( !v221 )
        {
          v265 = 18456;
          v542 = 126;
          goto LABEL_332;
        }
        if ( *(_BYTE *)(v221 + 629) )
        {
          if ( (*(_BYTE *)(v7.QuadPart + 270) & 4) != 0 )
          {
            Login = 40613;
            v265 = 40613;
            v542 = 143;
            goto LABEL_321;
          }
        }
        else if ( (*(_BYTE *)(v7.QuadPart + 270) & 4) != 0 )
        {
          v222 = *(_QWORD *)(v221 + 4624);
          if ( v222 )
          {
            if ( *(_BYTE *)(v222 + 8273) )
            {
              v316 = (CDbAndSetOpts *)0x800000012LL;
              if ( (dword_102EDCA28 & 8) != 0 )
              {
                v609 = 0;
                v610 = 0;
                v611 = 0;
                v612 = 0;
                v613 = &v615;
                v616 = 0;
                v617 = 0;
                v614 = 0;
                v618 = 0;
                XeSqlPkg::login_request_to_page_server::Publish((XeSqlPkg::login_request_to_page_server *)v608);
              }
              Login = 40613;
              v265 = 40613;
              v542 = 168;
              goto LABEL_321;
            }
          }
        }
LABEL_113:
        if ( (unsigned int)FDetermineSessionLang(v637, v554, 0) )
        {
          v71 = *(_DWORD *)CDefaultCollation::PDCServer();
          v356 = v71;
          if ( FUTF8Collation(v71) )
          {
            v72 = v314;
          }
          else
          {
            v318 = 0;
            v479 = (_DWORD *)CDefaultCollation::PDCServer();
            LOWORD(v547) = (*v479 & 0x1000) == 0;
            v302 = CSIDFromCID(v71);
            v318 = getcssoname(v302, 1001, v638, 256);
            v72 = v314;
            LOWORD(v258) = v318;
            (*(void (__fastcall **)(struct CConnectionOutput *, int *, __int64, wchar_t *, int))(*(_QWORD *)v314 + 144LL))(
              v314,
              &v547,
              2,
              v638,
              v258);
          }
          v73 = 0;
          v329 = 0;
          v74 = 0;
          v328 = 0;
          v480 = (unsigned int *)CDefaultCollation::PDCServer();
          v357 = LCIDFromCID(*v480);
          if ( !_ultow_s(v357, Buffer, 0x10u, 10) )
          {
            v73 = wcsnlen(Buffer, 0xFu);
            v329 = v73;
          }
          v481 = (int *)CDefaultCollation::PDCServer();
          v358 = *v481;
          v75 = (v358 & 0x1000) != 0;
          v275 = v75;
          if ( (v358 & 0x2000) != 0 )
          {
            v75 |= 2u;
            v275 = v75;
          }
          if ( (v358 & 0x4000) != 0 )
          {
            v75 |= 0x10000u;
            v275 = v75;
          }
          if ( (v358 & 0x8000) != 0 )
          {
            v75 |= 0x20000u;
            v275 = v75;
          }
          if ( (v358 & 0x200) != 0 )
          {
            v75 |= 8u;
            v275 = v75;
          }
          if ( !_ultow_s(v75, Source, 0x10u, 10) )
          {
            v74 = wcsnlen(Source, 0xFu);
            v328 = v74;
          }
          (*(void (__fastcall **)(struct CConnectionOutput *, wchar_t *, _QWORD))(*(_QWORD *)v72 + 160LL))(
            v72,
            Buffer,
            (unsigned int)(2 * v73));
          (*(void (__fastcall **)(struct CConnectionOutput *, wchar_t *, _QWORD))(*(_QWORD *)v72 + 168LL))(
            v72,
            Source,
            (unsigned int)(2 * v74));
          if ( (*(_BYTE *)(v7.QuadPart + 403) & 1) == 0 )
          {
LABEL_129:
            CSession::RecordLogin((CSession *)v7.QuadPart);
            v483 = NtCurrentTeb()->ThreadLocalStoragePointer;
            v484 = v483[SystemThread_TlsIndex] + SystemThread_TlsOffset;
            v485 = *(CDiagnostics **)(v484 + 80);
            CDiagnostics::RecordLogin(v485);
            v76 = *(_DWORD *)(v7.QuadPart + 400);
            v486 = NtCurrentTeb()->ThreadLocalStoragePointer;
            v487 = (struct ImpliedLoginInfo **)(v486[SystemThread_TlsIndex] + SystemThread_TlsOffset);
            v488 = *v487;
            v306 = v488;
            v303 = *(_WORD *)(v7.QuadPart + 184) >= 6u;
            v77 = v303;
            v78 = (*(__int64 (__fastcall **)(struct IServerConfiguration *))(*(_QWORD *)s_pServerConf + 504LL))(s_pServerConf);
            CDbAndSetOpts::InitAllOptions(v316, (v76 & 0x100200) != 0, v77, v79, *(_WORD *)(v78 + 126) > 0);
            if ( byte_102EDCBBC && (*(_BYTE *)(v7.QuadPart + 270) & 4) != 0 )
            {
              v267 = 1;
              v80 = v277;
            }
            else
            {
              v267 = 0;
              v80 = v277;
              *((_WORD *)v80 + 136) = SECurDbLockRef::GetCookieForBaseDbAndCloseDb((struct CUEnvTransient *)((char *)v277 + 274));
            }
            *(_BYTE *)(v7.QuadPart + 266) = 0;
            v81 = v312;
            if ( v312 && *(_BYTE *)v312 )
              goto LABEL_160;
            v489 = NtCurrentTeb()->ThreadLocalStoragePointer;
            v490 = v489[SystemThread_TlsIndex] + SystemThread_TlsOffset;
            v491 = *(_QWORD *)(v490 + 80);
            *(_DWORD *)(v491 + 1000) |= 8u;
            v359 = Base_PublicGlobals::sm_invariantTscAvailable;
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&v396);
              v82 = (CSbTransportMgr *)v396.QuadPart;
            }
            else
            {
              v397 = MEMORY[0x7FFE0008];
              v82 = MEMORY[0x7FFE0008];
            }
            v398 = v82;
            CNetConnection::GetLock(*(CNetConnection **)(v8 + 16));
            v83 = (_QWORD *)(v8 + 648);
            *(_QWORD *)(v8 + 648) = v82;
            *(_DWORD *)(v8 + 664) = 1;
            v492 = *(_QWORD *)(v8 + 16);
            v84 = *(_QWORD **)(v492 + 392);
            v493 = v84;
            v304 = SOS_PublicGlobals::sm_SpinlockStatSnapshot;
            if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
            {
              v230 = rand();
              if ( v230 == 5 * (v230 / 5) )
                Spinlock<114,16,258>::UpdateStatSnapshot();
            }
            *v84 = 0;
            if ( !FExecuteLogonTriggers((struct CSession *)v7.QuadPart, v271, 0) )
            {
              v542 = 1;
              v265 = 17892;
              v494 = NtCurrentTeb()->ThreadLocalStoragePointer;
              v495 = v494[SystemThread_TlsIndex] + SystemThread_TlsOffset;
              v496 = *(_QWORD *)(v495 + 80);
              *(_DWORD *)(v496 + 1000) &= ~8u;
              LODWORD(v315) = Base_PublicGlobals::sm_invariantTscAvailable;
              if ( Base_PublicGlobals::sm_invariantTscAvailable )
              {
                QueryPerformanceCounter(&v399);
                v231 = (CSbTransportMgr *)v399.QuadPart;
              }
              else
              {
                v231 = MEMORY[0x7FFE0008];
                v400 = MEMORY[0x7FFE0008];
              }
              v401 = v231;
              v402 = v231;
              CNetConnection::GetLock(*(CNetConnection **)(v8 + 16));
              v497 = v8 + 648;
              if ( *(_DWORD *)(v8 + 664) )
              {
                if ( (unsigned __int64)v402 > *v83 )
                {
                  v277 = (CSbTransportMgr *)((char *)v402 - *v83);
                  v498 = v277;
                  v499 = v8 + 656;
                  *(_QWORD *)(v8 + 656) += v277;
                }
                *(_DWORD *)(v8 + 664) = 0;
              }
              v500 = *(_QWORD *)(v8 + 16);
              v232 = *(_QWORD **)(v500 + 392);
              v501 = v232;
              v305 = SOS_PublicGlobals::sm_SpinlockStatSnapshot;
              if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
              {
                v233 = rand();
                if ( v233 == 5 * (v233 / 5) )
                  Spinlock<114,16,258>::UpdateStatSnapshot();
              }
              *v232 = 0;
              Login = v265;
              goto LABEL_321;
            }
            v360 = Base_PublicGlobals::sm_invariantTscAvailable;
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&v403);
              v85 = (CSbTransportMgr *)v403.QuadPart;
            }
            else
            {
              v85 = MEMORY[0x7FFE0008];
              v404 = MEMORY[0x7FFE0008];
            }
            v405 = v85;
            v406 = v85;
            CNetConnection::GetLock(*(CNetConnection **)(v8 + 16));
            v502 = v8 + 648;
            if ( *(_DWORD *)(v8 + 664) )
            {
              if ( (unsigned __int64)v406 > *v83 )
              {
                v277 = (CSbTransportMgr *)((char *)v406 - *v83);
                v503 = v277;
                v504 = v8 + 656;
                *(_QWORD *)(v8 + 656) += v277;
              }
              *(_DWORD *)(v8 + 664) = 0;
            }
            v505 = *(_QWORD *)(v8 + 16);
            v86 = *(_QWORD **)(v505 + 392);
            v506 = v86;
            v282 = SOS_PublicGlobals::sm_SpinlockStatSnapshot;
            if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
            {
              v234 = rand();
              if ( v234 == 5 * (v234 / 5) )
                Spinlock<114,16,258>::UpdateStatSnapshot();
            }
            *v86 = 0;
            v361 = Base_PublicGlobals::sm_invariantTscAvailable;
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&v407);
              v87 = (CSbTransportMgr *)v407.QuadPart;
            }
            else
            {
              v408 = MEMORY[0x7FFE0008];
              v87 = MEMORY[0x7FFE0008];
            }
            v409 = v87;
            CNetConnection::GetLock(*(CNetConnection **)(v8 + 16));
            v88 = (_QWORD *)(v8 + 672);
            *(_QWORD *)(v8 + 672) = v87;
            *(_DWORD *)(v8 + 688) = 1;
            v507 = *(_QWORD *)(v8 + 16);
            v89 = *(_QWORD **)(v507 + 392);
            v508 = v89;
            v283 = SOS_PublicGlobals::sm_SpinlockStatSnapshot;
            if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
            {
              v235 = rand();
              if ( v235 == 5 * (v235 / 5) )
                Spinlock<114,16,258>::UpdateStatSnapshot();
            }
            *v89 = 0;
            ExecuteClassifier();
            v362 = Base_PublicGlobals::sm_invariantTscAvailable;
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&v410);
              v90 = (CSbTransportMgr *)v410.QuadPart;
            }
            else
            {
              v90 = MEMORY[0x7FFE0008];
              v411 = MEMORY[0x7FFE0008];
            }
            v412 = v90;
            v413 = v90;
            CNetConnection::GetLock(*(CNetConnection **)(v8 + 16));
            v509 = v8 + 672;
            if ( *(_DWORD *)(v8 + 688) )
            {
              if ( (unsigned __int64)v413 > *v88 )
              {
                v277 = (CSbTransportMgr *)((char *)v413 - *v88);
                v510 = v277;
                v511 = v8 + 680;
                *(_QWORD *)(v8 + 680) += v277;
              }
              *(_DWORD *)(v8 + 688) = 0;
            }
            v512 = *(_QWORD *)(v8 + 16);
            v91 = *(_QWORD **)(v512 + 392);
            v513 = v91;
            v284 = SOS_PublicGlobals::sm_SpinlockStatSnapshot;
            if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
            {
              v236 = rand();
              if ( v236 == 5 * (v236 / 5) )
                Spinlock<114,16,258>::UpdateStatSnapshot();
            }
            *v91 = 0;
            v363 = Base_PublicGlobals::sm_invariantTscAvailable;
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&v414);
              v92 = (CSbTransportMgr *)v414.QuadPart;
            }
            else
            {
              v415 = MEMORY[0x7FFE0008];
              v92 = MEMORY[0x7FFE0008];
            }
            v416 = v92;
            CNetConnection::GetLock(*(CNetConnection **)(v8 + 16));
            *(_QWORD *)(v8 + 720) = v92;
            *(_DWORD *)(v8 + 736) = 1;
            v514 = *(_QWORD *)(v8 + 16);
            v93 = *(_QWORD **)(v514 + 392);
            v515 = v93;
            v285 = SOS_PublicGlobals::sm_SpinlockStatSnapshot;
            if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
            {
              v237 = rand();
              if ( v237 == 5 * (v237 / 5) )
                Spinlock<114,16,258>::UpdateStatSnapshot();
            }
            *v93 = 0;
            v516 = NtCurrentTeb()->ThreadLocalStoragePointer;
            v517 = v516[SystemThread_TlsIndex] + SystemThread_TlsOffset;
            v518 = *(_QWORD *)(v517 + 80);
            *(_DWORD *)(v518 + 1000) &= ~8u;
            if ( (*(_BYTE *)(v7.QuadPart + 272) & 0x20) == 0 )
            {
LABEL_159:
              v81 = v312;
LABEL_160:
              if ( v267 )
                *((_WORD *)v80 + 136) = SECurDbLockRef::GetCookieForBaseDbAndCloseDb((struct CUEnvTransient *)((char *)v80 + 274));
              v94 = ((__int64 (__fastcall *)(_QWORD))CSession::AccountForNewSessionRequest)((LARGE_INTEGER)v7.QuadPart);
              LODWORD(v309) = v94;
              if ( !v94 )
              {
                if ( !*(_BYTE *)v81 )
                {
                  v95 = (struct CNetConnection *)(*(__int64 (__fastcall **)(struct CBatch *))(*(_QWORD *)v315 + 72LL))(v315);
                  StartOrStopTdsForwarder((struct CSession *)v7.QuadPart, v80, v95, 0);
                }
                if ( (*(_BYTE *)(v7.QuadPart + 270) & 4) != 0 )
                {
                  v251 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v7.QuadPart + 96) + 16LL))(*(_QWORD *)(v7.QuadPart + 96));
                  v531 = v251;
                  if ( v251 )
                  {
                    v69 = *(_QWORD *)(v251 + 688);
                    if ( v69 )
                    {
                      if ( !*(_DWORD *)(v251 + 1088) )
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v69 + 48LL))(v69);
                    }
                  }
                }
                Login = v265;
                if ( !v265 )
                {
                  if ( byte_102EDCACF )
                    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)(v7.QuadPart + 104) + 264LL) + 464LL))(*(_QWORD *)(*(_QWORD *)(v7.QuadPart + 104) + 264LL));
                  if ( byte_102EDCADA )
                  {
                    v423 = *(_OWORD *)((char *)v271 + 28);
                    AuditLoginXdb(&v540, 0, v542, &v423);
                  }
                  goto LABEL_171;
                }
                goto LABEL_321;
              }
              v542 = 1;
              if ( v94 == 0x80000000 )
              {
                Login = 10928;
                v265 = 10928;
                goto LABEL_321;
              }
              if ( v94 == -2113929216 )
              {
                Login = 10936;
                v265 = 10936;
                goto LABEL_321;
              }
              Login = v265;
              goto LABEL_427;
            }
            v364 = Base_PublicGlobals::sm_invariantTscAvailable;
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&v365);
              v238 = (CSbTransportMgr *)v365.QuadPart;
            }
            else
            {
              v366 = MEMORY[0x7FFE0008];
              v238 = MEMORY[0x7FFE0008];
            }
            v367 = v238;
            CNetConnection::GetLock(*(CNetConnection **)(v8 + 16));
            v239 = (_QWORD *)(v8 + 696);
            *(_QWORD *)(v8 + 696) = v238;
            *(_DWORD *)(v8 + 712) = 1;
            v519 = *(_QWORD *)(v8 + 16);
            v240 = *(_QWORD **)(v519 + 392);
            v520 = v240;
            v286 = SOS_PublicGlobals::sm_SpinlockStatSnapshot;
            if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
            {
              v241 = rand();
              if ( v241 == 5 * (v241 / 5) )
                Spinlock<114,16,258>::UpdateStatSnapshot();
            }
            *v240 = 0;
            if ( !v267 )
            {
              v277 = (struct CUEnvTransient *)v7.QuadPart;
              v242 = *(_BYTE *)(v7.QuadPart + 270);
              if ( (v242 & 4) != 0 )
              {
                v243 = v242 & 0xFB;
                *(_BYTE *)(v7.QuadPart + 270) = v243;
                *(_BYTE *)(v7.QuadPart + 271) &= ~1u;
                v244 = *(_BYTE *)(v7.QuadPart + 271);
                *(_DWORD *)(v7.QuadPart + 404) = 2;
                *(_BYTE *)(v7.QuadPart + 270) = v243 | 4;
                v244 |= 1u;
                *(_BYTE *)(v7.QuadPart + 271) = v244;
                *(_BYTE *)(v7.QuadPart + 271) = v244 | 1;
                *(_DWORD *)(v7.QuadPart + 404) = 1;
              }
              else
              {
                v277 = 0;
              }
            }
            if ( CSession::FRecoverSessionStateFromTDS((CSession *)v7.QuadPart, 0, (enum ELoginFailedState *)&v542) )
            {
              LODWORD(v314) = Base_PublicGlobals::sm_invariantTscAvailable;
              if ( Base_PublicGlobals::sm_invariantTscAvailable )
              {
                QueryPerformanceCounter(&v373);
                v248 = (CSbTransportMgr *)v373.QuadPart;
              }
              else
              {
                v248 = MEMORY[0x7FFE0008];
                v374 = MEMORY[0x7FFE0008];
              }
              v387 = v248;
              v372 = v248;
              CNetConnection::GetLock(*(CNetConnection **)(v8 + 16));
              v526 = v8 + 696;
              if ( *(_DWORD *)(v8 + 712) )
              {
                if ( (unsigned __int64)v372 > *v239 )
                {
                  v277 = (CSbTransportMgr *)((char *)v372 - *v239);
                  v527 = v277;
                  v528 = v8 + 704;
                  *(_QWORD *)(v8 + 704) += v277;
                }
                *(_DWORD *)(v8 + 712) = 0;
              }
              v529 = *(_QWORD *)(v8 + 16);
              v249 = *(_QWORD **)(v529 + 392);
              v530 = v249;
              v288 = SOS_PublicGlobals::sm_SpinlockStatSnapshot;
              if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
              {
                v250 = rand();
                if ( v250 == 5 * (v250 / 5) )
                  Spinlock<114,16,258>::UpdateStatSnapshot();
              }
              *v249 = 0;
              goto LABEL_159;
            }
            LODWORD(v312) = Base_PublicGlobals::sm_invariantTscAvailable;
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&v368);
              v245 = (CSbTransportMgr *)v368.QuadPart;
            }
            else
            {
              v245 = MEMORY[0x7FFE0008];
              v369 = MEMORY[0x7FFE0008];
            }
            v370 = v245;
            v371 = v245;
            CNetConnection::GetLock(*(CNetConnection **)(v8 + 16));
            v521 = v8 + 696;
            if ( *(_DWORD *)(v8 + 712) )
            {
              if ( (unsigned __int64)v371 > *v239 )
              {
                v277 = (CSbTransportMgr *)((char *)v371 - *v239);
                v522 = v277;
                v523 = v8 + 704;
                *(_QWORD *)(v8 + 704) += v277;
              }
              *(_DWORD *)(v8 + 712) = 0;
            }
            v524 = *(_QWORD *)(v8 + 16);
            v246 = *(_QWORD **)(v524 + 392);
            v525 = v246;
            v287 = SOS_PublicGlobals::sm_SpinlockStatSnapshot;
            if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
            {
              v247 = rand();
              if ( v247 == 5 * (v247 / 5) )
                Spinlock<114,16,258>::UpdateStatSnapshot();
            }
            *v246 = 0;
            goto LABEL_331;
          }
          if ( v273 )
          {
            v542 = 18;
            Login = 40620;
            v265 = 40620;
            goto LABEL_321;
          }
          if ( !v550 && v553 )
          {
            v223 = 0;
            v324 = 0;
            v224 = 0;
            v395 = 0;
            v482 = *(_QWORD *)(v7.QuadPart + 216);
            v225 = v482;
            v337 = 0;
            v338 = 0;
            if ( v482 )
            {
              v337 = v482;
              v338 = 0;
              if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v482 + 24LL))(v482) )
              {
                v542 = 19;
                Login = 18456;
                v265 = 18456;
                CAutoEraseClearMemory::~CAutoEraseClearMemory((CAutoEraseClearMemory *)&v337);
                goto LABEL_321;
              }
              v223 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v225 + 64LL))(v225);
              v324 = v223;
              v224 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v225 + 56LL))(v225);
              v395 = v224;
            }
            CSession::GetUserSid((CSession *)v7.QuadPart, v634, 0x55u, &v310);
            v226 = GetMasterDbId();
            v323 = v226;
            v227 = *(_QWORD *)(v7.QuadPart + 104);
            if ( v227 )
            {
              v228 = *(_QWORD *)(v227 + 264);
              if ( v228 )
              {
                if ( (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v228 + 232LL))(v228, 1) )
                {
                  v229 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(*(_QWORD *)(v7.QuadPart + 104)
                                                                                  + 264LL)
                                                                    + 232LL))(
                           *(_QWORD *)(*(_QWORD *)(v7.QuadPart + 104) + 264LL),
                           1);
                  v226 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v229 + 16LL))(v229);
                  v323 = v226;
                }
              }
            }
            Login = ChangePassword(v279, v634, v310, v224, v223, v226);
            v265 = Login;
            if ( Login )
            {
              v542 = 57;
              CAutoEraseClearMemory::~CAutoEraseClearMemory((CAutoEraseClearMemory *)&v337);
              goto LABEL_427;
            }
            CAutoEraseClearMemory::~CAutoEraseClearMemory((CAutoEraseClearMemory *)&v337);
            goto LABEL_129;
          }
          v542 = 18;
        }
        else
        {
          v542 = 17;
        }
LABEL_331:
        v265 = 18456;
LABEL_332:
        Login = 18456;
        goto LABEL_321;
      }
LABEL_498:
      v265 = 18456;
      v542 = 126;
      goto LABEL_332;
    }
LABEL_614:
    v542 = 173;
    goto LABEL_331;
  }
  if ( !(unsigned int)IsContainedAGEnabledInstance() )
    goto LABEL_52;
  v143 = 0;
  v322 = 0;
  v144 = *(_QWORD *)(v7.QuadPart + 192);
  if ( v144 )
  {
    v143 = 2 * *(unsigned __int16 *)(v144 + 70);
    v322 = v143;
    v145 = (const wchar_t *)(v144 + *(unsigned __int16 *)(v144 + 68));
  }
  else
  {
    v145 = 0;
  }
  v381 = v145;
  v545 = 0;
  v546[0] = 0;
  ContainedAGSystemDbsId = HadrRuntimeCallbacks::GetContainedAGSystemDbsId(&v555, &v545, v546);
  v147 = ContainedAGSystemDbsId;
  v292 = ContainedAGSystemDbsId;
  if ( !v145 || !v143 )
    goto LABEL_314;
  if ( !ContainedAGSystemDbsId )
    goto LABEL_317;
  if ( *(_BYTE *)(qword_102ECFB00 + 48768) && *(_BYTE *)(qword_102ECFB00 + 48772) )
    goto LABEL_315;
  v148 = v143 >> 1;
  v375 = CompareStringWEnglishNoCase(1u, 0, v145, v143 >> 1, L"master", (unsigned __int64)(int)dword_102F1BB98 >> 1);
  if ( v375 == 2
    || (v376 = CompareStringWEnglishNoCase(1u, 0, v145, v148, L"tempdb", (unsigned __int64)dword_102F1BB9C >> 1),
        v376 == 2)
    || (v377 = CompareStringWEnglishNoCase(1u, 0, v145, v148, L"msdb", (unsigned __int64)(int)dword_102F1BBA4 >> 1),
        v377 == 2)
    || (v549 = 0,
        v548[0] = 0,
        v589 = (__int128)*HadrRuntimeCallbacks::GetContainedOrSystemAGId(&v539, v145, v143, &v549, v548),
        v589 == *(_OWORD *)&v555) )
  {
LABEL_314:
    if ( v147 )
    {
LABEL_315:
      v41 = v555;
      *(_WORD *)(v7.QuadPart + 4928) = v545;
      *(_WORD *)(v7.QuadPart + 4930) = v546[0];
LABEL_316:
      v8 = v309;
      goto LABEL_51;
    }
LABEL_317:
    *(_BYTE *)(v7.QuadPart + 270) |= 0x20u;
    v41 = Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
    *(_WORD *)(v7.QuadPart + 4928) = 1;
    *(_WORD *)(v7.QuadPart + 4930) = 0;
    goto LABEL_316;
  }
  v265 = 18456;
  v542 = 38;
  v149 = (unsigned int)CConnection::PNetConn(v278);
  LoginError(18456, (_DWORD)v271, v149, 38, (__int64)&si128);
  v270 = -2147465192;
  operator delete[]((void *)v552);
  ExcHandler::~ExcHandler((ExcHandler *)v594);
  v429 = NtCurrentTeb()->ThreadLocalStoragePointer;
  v150 = v429[SystemThread_TlsIndex] + SystemThread_TlsOffset;
  v430 = v150;
  v151 = *(_QWORD *)(v150 + 256);
  v279 = (struct IMemObj *)v151;
  if ( !v151 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v151 = *(_QWORD *)(v150 + 256);
    v279 = (struct IMemObj *)v151;
  }
  *(_QWORD *)(v151 + 3208) = v334;
  CAutoSetXLvlIntCtxtImplNoException::~CAutoSetXLvlIntCtxtImplNoException((CAutoSetXLvlIntCtxtImplNoException *)&v625);
  AutoInstallParams::~AutoInstallParams((AutoInstallParams *)&v339);
  SEParams::~SEParams((SEParams *)v595);
  AutoResumeMsqlXactManager::~AutoResumeMsqlXactManager((AutoResumeMsqlXactManager *)&v280);
  CAutoSetupCXCtxtSingleThread::~CAutoSetupCXCtxtSingleThread((CAutoSetupCXCtxtSingleThread *)v628);
  CAutoLoginInit::~CAutoLoginInit((CAutoLoginInit *)&v336);
  return 2147502104LL;
}

```

## disassembly

```asm
0x100555e20  push    rbx
0x100555e22  push    rsi
0x100555e23  push    rdi
0x100555e24  push    r12
0x100555e26  push    r13
0x100555e28  push    r14
0x100555e2a  push    r15
0x100555e2c  mov     eax, 2DC0h
0x100555e31  call    _alloca_probe
0x100555e36  sub     rsp, rax
0x100555e39  mov     [rsp+2DF8h+var_2930], 0FFFFFFFFFFFFFFFEh
0x100555e45  movaps  [rsp+2DF8h+var_48], xmm6
0x100555e4d  mov     rax, cs:__security_cookie
0x100555e54  xor     rax, rsp
0x100555e57  mov     [rsp+2DF8h+var_58], rax
0x100555e5f  jmp     loc_100549FD2
0x100549fd2  mov     [rsp+2DF8h+var_2D28], r9
0x100549fda  mov     rdi, r8
0x100549fdd  mov     [rsp+2DF8h+var_2D00], r8
0x100549fe5  mov     rbx, rdx
0x100549fe8  mov     [rsp+2DF8h+var_2C78], rdx
0x100549ff0  mov     [rsp+2DF8h+var_2CF8], rcx
0x100549ff8  mov     [rsp+2DF8h+var_2BD0], rcx
0x10054a000  mov     rax, [rsp+2DF8h+arg_20]
0x10054a008  mov     [rsp+2DF8h+var_2C90], rax
0x10054a010  xor     r15d, r15d
0x10054a013  mov     [rsp+2DF8h+var_2C94], r15d
0x10054a01b  lea     r13d, [r15+1]
0x10054a01f  test    dword ptr cs:qword_102EDC9FC+4, 400h
0x10054a029  jnz     loc_100F27CAD
0x10054a02f  mov     rax, [rdi+18h]
0x10054a033  mov     [rsp+2DF8h+var_2C80], rax
0x10054a03b  mov     [rsp+2DF8h+var_2D2C], r15d
0x10054a043  mov     r14, [rbx+18h]
0x10054a047  mov     qword ptr [rsp+2DF8h+var_2C40], r14
0x10054a04f  mov     [rsp+2DF8h+var_2D38], r15d
0x10054a057  mov     [rsp+2DF8h+var_2548], r15d
0x10054a05f  mov     [rsp+2DF8h+var_2D2E], r15b
0x10054a067  mov     dword ptr [rsp+2DF8h+var_2544], r15d
0x10054a06f  mov     dword ptr [rsp+2DF8h+var_2530+4], r15d
0x10054a077  mov     [rsp+2DF8h+var_2D1C], r15d
0x10054a07f  mov     [rsp+2DF8h+var_2C88], r15d
0x10054a087  mov     [rsp+2DF8h+var_2CB8], r15
0x10054a08f  mov     [rsp+2DF8h+var_2C98], r15d
0x10054a097  mov     r12, [r14+60h]
0x10054a09b  mov     [rsp+2DF8h+var_2CA0], r12
0x10054a0a3  movzx   eax, byte ptr [r12+31h]
0x10054a0a9  test    al, 1
0x10054a0ab  jz      short loc_10054A0BB
0x10054a0ad  or      byte ptr [r14+110h], 10h
0x10054a0b5  movzx   eax, byte ptr [r12+31h]
0x10054a0bb  test    al, 2
0x10054a0bd  jnz     loc_100F27CCA
0x10054a0c3  mov     [rsp+2DF8h+var_2568], r13d
0x10054a0cb  mov     [rsp+2DF8h+var_22A0], r15
0x10054a0d3  movdqa  xmm0, cs:__xmm@00000000ffffffffffffffff00000000
0x10054a0db  movdqa  [rsp+2DF8h+var_23B8], xmm0
0x10054a0e4  mov     [rsp+2DF8h+var_23A8], r15d
0x10054a0ec  mov     [rsp+2DF8h+var_23A4], r15w
0x10054a0f5  mov     [rsp+2DF8h+var_2D20], r15d
0x10054a0fd  mov     [rsp+2DF8h+var_2D10], r15d
0x10054a105  mov     rax, cs:qword_102ECFB00
0x10054a10c  cmp     [rax+38A8h], r15d
0x10054a113  jnz     loc_100F27CD8
0x10054a119  mov     ebx, r15d
0x10054a11c  mov     [rsp+2DF8h+var_2D18], ebx
0x10054a123  cmp     dword ptr [r12+3DCh], 2
0x10054a12c  jz      loc_100F27CEE
0x10054a132  mov     eax, r15d
0x10054a135  mov     [rsp+2DF8h+var_2554], eax
0x10054a13c  test    ebx, ebx
0x10054a13e  jnz     loc_100F27D0A
0x10054a144  mov     ebx, r15d
0x10054a147  mov     [rsp+2DF8h+var_2D34], ebx
0x10054a14e  call    cs:__imp_GetXdbServerGlobals
0x10054a154  cmp     [rax+2074h], r15d
0x10054a15b  jnz     loc_100F27D1B
0x10054a161  call    cs:__imp_GetXdbServerGlobals
0x10054a167  cmp     [rax+2EC8h], r15d
0x10054a16e  jnz     loc_100F27F9E
0x10054a174  mov     rax, cs:qword_102ECFB00
0x10054a17b  cmp     [rax+38A8h], r15d
0x10054a182  jnz     loc_100F27FED
0x10054a188  mov     ebx, [rsp+2DF8h+var_2D34]
0x10054a18f  xor     r8d, r8d; bool
0x10054a192  mov     rdx, r12; struct CPhysicalConnection *
0x10054a195  mov     rcx, r14; struct CSession *
0x10054a198  call    ?CanConnectionBeImpliedAuthInXdbOrLinux@ImpliedAuthenticationManager@@SA_NPEBVCSession@@PEBVCPhysicalConnection@@_N@Z; ImpliedAuthenticationManager::CanConnectionBeImpliedAuthInXdbOrLinux(CSession const *,CPhysicalConnection const *,bool)
0x10054a19d  test    al, al
0x10054a19f  jnz     loc_100F28149
0x10054a1a5  mov     rax, cs:qword_102ECFB10
0x10054a1ac  test    byte ptr [rax+430h], 40h
0x10054a1b3  jnz     loc_100F28381
0x10054a1b9  mov     r8, gs:58h
0x10054a1c2  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10054a1c9  mov     ecx, [rax]
0x10054a1cb  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10054a1d2  mov     edx, [rax]
0x10054a1d4  add     rdx, [r8+rcx*8]
0x10054a1d8  mov     rax, [rdx]
0x10054a1db  test    rax, rax
0x10054a1de  jnz     loc_100F2834D
0x10054a1e4  call    ?IsReplicatedMasterEnabled@@YAHXZ; IsReplicatedMasterEnabled(void)
0x10054a1e9  test    eax, eax
0x10054a1eb  jnz     loc_100F28373
0x10054a1f1  xorps   xmm0, xmm0
0x10054a1f4  movdqu  [rsp+2DF8h+var_2C00], xmm0
0x10054a1fd  mov     rsi, [rsp+2DF8h+var_2D28]
0x10054a205  movups  xmm6, xmmword ptr [rsi+1Ch]
0x10054a209  mov     qword ptr [rsp+2DF8h+var_2C00], r14
0x10054a211  mov     rdi, [rsp+2DF8h+var_2D00]
0x10054a219  mov     qword ptr [rsp+2DF8h+var_2C00+8], rdi
0x10054a221  mov     [rdi+8], r14
0x10054a225  mov     [r14+1E0h], rdi
0x10054a22c  lock inc dword ptr [rdi+4Ch]
0x10054a230  lea     rcx, [r14+1F8h]; struct ITaskProxy *
0x10054a237  call    ?SetCurrentTaskProxy@ITaskProxy@@SAXPEAV1@@Z; ITaskProxy::SetCurrentTaskProxy(ITaskProxy *)
0x10054a23c  mov     rdx, [rsp+2DF8h+var_2CF8]; struct IMemObj *
0x10054a244  mov     rcx, rdi; this
0x10054a247  call    ?FInitMainEc@CConnection@@QEAAHPEAVIMemObj@@@Z; CConnection::FInitMainEc(IMemObj *)
0x10054a24c  test    eax, eax
0x10054a24e  jz      loc_100F283FE
0x10054a254  call    ?PCreateInstanceNoX@CDiagnostics@@SAPEAV1@XZ; CDiagnostics::PCreateInstanceNoX(void)
0x10054a259  mov     rbx, rax
0x10054a25c  mov     [rsp+2DF8h+var_2928], rax
0x10054a264  test    rax, rax
0x10054a267  jz      loc_100F283FE
0x10054a26d  mov     [rdi+28h], rbx
0x10054a271  mov     rcx, r14; this
0x10054a274  call    ?FInitForNewConnection@CSession@@QEAA_NXZ; CSession::FInitForNewConnection(void)
0x10054a279  test    al, al
0x10054a27b  jz      loc_100F283DE
0x10054a281  mov     rcx, r14; struct CSession *
0x10054a284  call    ?FAddSession@CSessionMgr@@SA_NPEAVCSession@@@Z; CSessionMgr::FAddSession(CSession *)
0x10054a289  test    al, al
0x10054a28b  jz      loc_100F283DE
0x10054a291  mov     rcx, [r14+60h]
0x10054a295  test    rcx, rcx
0x10054a298  jz      short loc_10054A2E9
0x10054a29a  mov     rax, [rcx]
0x10054a29d  call    qword ptr [rax+10h]
0x10054a2a0  test    rax, rax
0x10054a2a3  jz      short loc_10054A2E9
0x10054a2a5  mov     rcx, [r14+60h]
0x10054a2a9  movzx   edi, word ptr [r14+10h]
0x10054a2ae  mov     rax, [rcx]
0x10054a2b1  call    qword ptr [rax+10h]
0x10054a2b4  mov     [rax+2ACh], di
0x10054a2bb  mov     rcx, [rax+1C0h]
0x10054a2c2  test    rcx, rcx
0x10054a2c5  jz      short loc_10054A2E1
0x10054a2c7  mov     [rsp+2DF8h+var_2CCC], di
0x10054a2cf  lea     r8, [rsp+2DF8h+var_2CCC]
0x10054a2d7  mov     edx, 1Ch
0x10054a2dc  call    SNISetInfo
0x10054a2e1  mov     rdi, [rsp+2DF8h+var_2D00]
0x10054a2e9  movdqa  [rsp+2DF8h+var_29A8], xmm6
0x10054a2f2  mov     [rsp+2DF8h+var_2DD8], rsi
0x10054a2f7  lea     r9, [rsp+2DF8h+var_29A8]
0x10054a2ff  mov     r8d, r13d
0x10054a302  mov     rdx, r14
0x10054a305  mov     rcx, rbx
0x10054a308  call    ?InitMainThread@CDiagnostics@@QEAAXPEAVCSession@@W4thread_type@@U_GUID@@PEAVSNI_Conn@@@Z; CDiagnostics::InitMainThread(CSession *,thread_type,_GUID,SNI_Conn *)
0x10054a30d  mov     rcx, rbx; struct CDiagThreadSafe *
0x10054a310  call    ?Add@CDiagManager@@SAXPEAVCDiagThreadSafe@@@Z; CDiagManager::Add(CDiagThreadSafe *)
0x10054a315  xorps   xmm0, xmm0
0x10054a318  movdqu  [rsp+2DF8h+var_2C00], xmm0
0x10054a321  mov     eax, 0FFFFFFFFh
0x10054a326  lock xadd [rbx+18h], eax
0x10054a32b  cmp     eax, 1
0x10054a32e  jz      loc_100F28445
0x10054a334  mov     r9, rdi; struct CConnection *
0x10054a337  mov     r8, r14; struct CSession *
0x10054a33a  mov     rdx, [rsp+2DF8h+var_2C78]; struct CBatch *
0x10054a342  lea     rcx, [rsp+2DF8h+var_17A8]; this
0x10054a34a  call    ??0CAutoSetupCXCtxtSingleThread@@QEAA@PEAVCBatch@@PEAVCSession@@PEAVCConnection@@@Z; CAutoSetupCXCtxtSingleThread::CAutoSetupCXCtxtSingleThread(CBatch *,CSession *,CConnection *)
0x10054a34f  nop
0x10054a350  mov     rdx, gs:58h
0x10054a359  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10054a360  mov     ecx, [rax]
0x10054a362  lea     r9, ds:0[rcx*8]
0x10054a36a  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10054a371  mov     r8d, [rax]
0x10054a374  mov     rax, [r9+rdx]
0x10054a378  mov     rcx, [r8+rax]
0x10054a37c  mov     rax, [rcx+78h]
0x10054a380  mov     [rsp+2DF8h+var_2D08], rax
0x10054a388  mov     rax, gs:58h
0x10054a391  mov     rcx, [rax+r9]
0x10054a395  mov     rax, [rcx+r8]
0x10054a399  mov     rcx, [rax+40h]
0x10054a39d  mov     rax, [rcx]
0x10054a3a0  mov     [rsp+2DF8h+var_2C70], rax
0x10054a3a8  mov     rbx, r15
0x10054a3ab  mov     [rsp+2DF8h+var_2CF0], rbx
0x10054a3b3  mov     edi, r15d
0x10054a3b6  mov     [rsp+2DF8h+var_2CE8], r15d
0x10054a3be  mov     rsi, [r14+288h]
0x10054a3c5  mov     rax, [rsi]
0x10054a3c8  xor     edx, edx
0x10054a3ca  mov     rcx, rsi
0x10054a3cd  call    qword ptr [rax+18h]
0x10054a3d0  test    al, al
0x10054a3d2  jz      short loc_10054A3F1
0x10054a3d4  lock inc dword ptr [rsi+8Ch]
0x10054a3db  mov     rbx, rsi
0x10054a3de  mov     [rsp+2DF8h+var_2CF0], rbx
0x10054a3e6  mov     edi, r13d
0x10054a3e9  mov     [rsp+2DF8h+var_2CE8], r13d
0x10054a3f1  test    byte ptr [rsp+2DF8h+var_2CE8], 1
0x10054a3f9  jz      loc_100F28458
0x10054a3ff  lea     rcx, [rsp+2DF8h+var_2268]
0x10054a407  call    cs:__imp_??0SEParams@@QEAA@XZ; SEParams::SEParams(void)
0x10054a40d  nop
0x10054a40e  mov     r8, gs:58h
0x10054a417  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10054a41e  mov     ecx, [rax]
0x10054a420  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10054a427  mov     edx, [rax]
0x10054a429  add     rdx, [r8+rcx*8]
0x10054a42d  mov     rbx, [rdx+50h]
0x10054a431  mov     rcx, [rsp+2DF8h+var_2CF0]
0x10054a439  mov     rax, [rcx]
0x10054a43c  call    qword ptr [rax]
0x10054a43e  mov     rdi, rax
0x10054a441  add     rbx, 100h
0x10054a448  mov     rax, [rsp+2DF8h+var_2C70]
0x10054a450  movzx   ecx, byte ptr [rax+4Ch]; unsigned __int8
0x10054a454  call    ?getSessionIsolationLevel@@YA?AW4ISOLATIONLEVEL@@E@Z; getSessionIsolationLevel(uchar)
0x10054a459  mov     r8d, eax
0x10054a45c  mov     dword ptr [rsp+2DF8h+var_2DC8], r15d
0x10054a461  mov     [rsp+2DF8h+var_2DD0], rbx
0x10054a466  mov     [rsp+2DF8h+var_2DD8], rdi
0x10054a46b  xor     r9d, r9d
0x10054a46e  mov     edx, 0FFFFFFFFh
0x10054a473  lea     rcx, [rsp+2DF8h+var_2268]
0x10054a47b  call    cs:__imp_?Init@SEParams@@QEAAXIW4ISOLATIONLEVEL@@PEAVISecurityContext@@PEAVXactWorkspace@@PEAVSEExecutionStatistics@@I@Z; SEParams::Init(uint,ISOLATIONLEVEL,ISecurityContext *,XactWorkspace *,SEExecutionStatistics *,uint)
0x10054a481  mov     [rsp+2DF8h+var_2BD8], r15
0x10054a489  lea     rdx, [rsp+2DF8h+var_2268]; struct SEParams *
0x10054a491  lea     rcx, [rsp+2DF8h+var_2BE0]; this
0x10054a499  call    ?Install@AutoInstallParams@@QEAAXPEAVSEParams@@@Z; AutoInstallParams::Install(SEParams *)
0x10054a49e  cmp     [rsp+2DF8h+var_2BD8], 0
0x10054a4a7  jnz     loc_100F284BD
0x10054a4ad  mov     r8, [rsp+2DF8h+var_2C78]; struct CBatch *
0x10054a4b5  mov     rdx, r14; struct CSession *
0x10054a4b8  lea     rcx, [rsp+2DF8h+var_1AB8]; this
0x10054a4c0  call    ??0CAutoSetXLvlIntCtxtImplNoException@@QEAA@PEAVCSession@@PEAVCBatch@@@Z; CAutoSetXLvlIntCtxtImplNoException::CAutoSetXLvlIntCtxtImplNoException(CSession *,CBatch *)
0x10054a4c5  nop
0x10054a4c6  mov     [rsp+2DF8h+var_2578], r15d
0x10054a4ce  mov     rdx, gs:58h
0x10054a4d7  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10054a4de  mov     ecx, [rax]
0x10054a4e0  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10054a4e7  mov     ebx, [rax]
0x10054a4e9  add     rbx, [rdx+rcx*8]
0x10054a4ed  mov     rcx, [rbx+100h]
0x10054a4f4  test    rcx, rcx
0x10054a4f7  jz      loc_100F284ED
0x10054a4fd  mov     rdx, [rcx+0C88h]
0x10054a504  mov     [rsp+2DF8h+var_2C10], rdx
0x10054a50c  mov     rax, cs:__imp_?ex_trans_cexcept@@YAXIPEAU_EXCEPTION_POINTERS@@@Z; ex_trans_cexcept(uint,_EXCEPTION_POINTERS *)
0x10054a513  mov     [rcx+0C88h], rax
0x10054a51a  mov     [rsp+2DF8h+var_2920], rdx
0x10054a522  xor     edx, edx; unsigned __int16
0x10054a524  mov     [rsp+2DF8h+var_2DD0], r15; struct Worker *
0x10054a529  mov     rax, cs:__imp_?hdl_prntbackout@@YAHHHHHPEAD@Z; hdl_prntbackout(int,int,int,int,char *)
0x10054a530  mov     [rsp+2DF8h+var_2DD8], rax; int (*)(int, int, int, int, char *)
0x10054a535  xor     r9d, r9d; unsigned __int8
0x10054a538  xor     r8d, r8d; unsigned __int8
0x10054a53b  lea     rcx, [rsp+2DF8h+var_2298]; this
0x10054a543  call    ??0ExcHandler@@QEAA@GEEP6AHHHHHPEAD@ZPEAVWorker@@@Z; ExcHandler::ExcHandler(ushort,uchar,uchar,int (*)(int,int,int,int,char *),Worker *)
0x10054a548  nop
0x10054a549  nop     dword ptr [rax+00000000h]
0x10054a550  mov     [rsp+2DF8h+var_2538], r15
0x10054a558  mov     dword ptr [rsp+2DF8h+var_2518], r15d
0x10054a560  call    ?IsContainedAGEnabledInstance@@YAHXZ; IsContainedAGEnabledInstance(void)
0x10054a565  test    eax, eax
0x10054a567  jz      loc_10054A6BD
0x10054a56d  lea     rdx, [rsp+2DF8h+var_2528]; retstr
0x10054a575  mov     rcx, r14; this
0x10054a578  call    ?GetHadronAgId@CSession@@QEAA?AU_GUID@@XZ; CSession::GetHadronAgId(void)
0x10054a57d  mov     rax, qword ptr [rsp+2DF8h+var_2528.Data1]
0x10054a585  cmp     rax, qword ptr cs:?sm_val@?$Zero@ULocaleEntry@?$XE_StaticPackage@$0L@@@@@2ULocaleEntry@?$XE_StaticPackage@$0L@@@B.Data1; XE_StaticPackage<11>::LocaleEntry const Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val ...
0x10054a58c  jnz     loc_100F28544
0x10054a592  mov     rax, qword ptr [rsp+2DF8h+var_2528.Data4]
0x10054a59a  cmp     rax, qword ptr cs:?sm_val@?$Zero@ULocaleEntry@?$XE_StaticPackage@$0L@@@@@2ULocaleEntry@?$XE_StaticPackage@$0L@@@B.Data4; XE_StaticPackage<11>::LocaleEntry const Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val ...
0x10054a5a1  jnz     loc_100F28544
0x10054a5a7  mov     edi, r15d
0x10054a5aa  mov     [rsp+2DF8h+var_2C58], r15d
0x10054a5b2  mov     rax, [r14+0C0h]
0x10054a5b9  test    rax, rax
0x10054a5bc  jz      loc_100F28500
0x10054a5c2  movzx   edi, word ptr [rax+46h]
0x10054a5c6  add     edi, edi
0x10054a5c8  mov     [rsp+2DF8h+var_2C58], edi
0x10054a5cf  movzx   ebx, word ptr [rax+44h]
0x10054a5d3  add     rbx, rax
0x10054a5d6  jmp     short loc_10054A5D9
0x10054a5d9  mov     [rsp+2DF8h+var_2AF0], rbx
0x10054a5e1  mov     [rsp+2DF8h+var_2564], r15w
  ... truncated ...
```
