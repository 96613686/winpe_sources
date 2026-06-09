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
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rcx
  int v17; // ebx
  __int64 v18; // rax
  struct SNI_Conn *v19; // rsi
  __int128 v20; // xmm6
  CConnection *v21; // rdi
  struct CDiagnostics *v22; // rax
  volatile signed __int32 *v23; // rbx
  __int64 v24; // rcx
  __int16 v25; // di
  __int64 v26; // rax
  __int64 v27; // rcx
  __int64 v28; // r9
  volatile signed __int32 *v29; // rbx
  char v30; // di
  volatile signed __int32 *v31; // rsi
  __int64 v32; // rbx
  struct XactWorkspace *v33; // rdi
  enum ISOLATIONLEVEL SessionIsolationLevel; // eax
  __int64 v35; // rbx
  __int64 v36; // rcx
  __int64 v37; // rdx
  __int64 v38; // rdx
  __int64 v39; // rcx
  int v40; // edi
  __int64 v41; // rax
  const wchar_t *v42; // rbx
  GUID v43; // xmm1
  GUID v44; // xmm0
  __int64 v45; // rcx
  int v46; // esi
  __int64 v47; // rbx
  unsigned __int16 MasterDbId; // ax
  CSbTransportMgr *QuadPart; // rbx
  __int64 v50; // rdx
  _QWORD *v51; // rbx
  __int64 v52; // rcx
  __int64 v53; // rcx
  struct IMemObj *v54; // rdi
  __int64 v55; // rdx
  __int64 v56; // rcx
  unsigned int Login; // esi
  __int64 v58; // rbx
  int v59; // edx
  char v60; // cl
  char v61; // bl
  unsigned int v62; // r13d
  __int64 v63; // rax
  const wchar_t *v64; // r12
  __int64 v65; // rcx
  __int64 v66; // rcx
  void *v67; // rbx
  CSbTransportMgr *v68; // rax
  _QWORD *v69; // rdx
  _QWORD *v70; // rbx
  int v71; // ebx
  int v72; // ecx
  int v73; // eax
  bool v74; // zf
  __int64 v75; // rcx
  __int64 v76; // rdx
  __int64 v77; // rcx
  unsigned __int64 v78; // rdx
  __int64 v79; // rcx
  unsigned int v80; // edx
  __int64 v81; // rcx
  unsigned int v82; // ebx
  __int64 v83; // rcx
  struct CConnectionOutput *v84; // rsi
  int v85; // edi
  int v86; // ebx
  __int64 v87; // rcx
  unsigned int v88; // ecx
  int v89; // edi
  bool v90; // bl
  __int64 v91; // rax
  __int16 v92; // r9
  struct CUEnvTransient *v93; // rsi
  struct CRoutingEnvChangeInfo *v94; // rbx
  CSbTransportMgr *v95; // rbx
  _QWORD *v96; // rdi
  _QWORD *v97; // rbx
  CSbTransportMgr *v98; // rax
  _QWORD *v99; // rbx
  CSbTransportMgr *v100; // rbx
  _QWORD *v101; // rdi
  _QWORD *v102; // rbx
  CSbTransportMgr *v103; // rax
  _QWORD *v104; // rbx
  CSbTransportMgr *v105; // rbx
  _QWORD *v106; // rbx
  int v107; // eax
  struct CNetConnection *v108; // rax
  __int64 v109; // r12
  __int64 v110; // rbx
  struct Worker *v111; // rcx
  __int64 v112; // rbx
  __int64 v113; // rax
  __int64 *v114; // rdx
  __int64 v115; // rbx
  volatile signed __int32 *v116; // rbx
  __int64 v117; // rbx
  __int64 v118; // rbx
  unsigned int v120; // ebx
  __int64 v121; // rax
  const wchar_t *v122; // rdi
  __int64 v123; // rsi
  __int64 v124; // rdx
  __int64 v125; // rcx
  int v126; // ecx
  __int64 v127; // rcx
  __int64 v128; // rdx
  __int64 XdbServerGlobals; // rax
  __int64 v130; // rax
  struct CSessionTraceFlags *v131; // rcx
  __int64 v132; // rcx
  __int64 v133; // rdx
  char v134; // al
  char v135; // cl
  __int64 v136; // rdx
  __int64 v137; // rcx
  __int64 v138; // rdx
  struct CSessionTraceFlags *v139; // rcx
  __int64 v140; // rdx
  struct CSessionTraceFlags *v141; // rcx
  char v142; // al
  char v143; // cl
  struct IMemObj *v144; // rdx
  struct _GUID *v145; // rcx
  DWORD LengthSid; // eax
  struct ImpliedLoginInfo *ImpliedLoginInfoFromCertificate; // rax
  char v148; // al
  __int64 v149; // rcx
  __int64 v150; // rdx
  __int64 v151; // rax
  int v152; // ecx
  __int64 v153; // rax
  ImpliedAuthenticationManager *v154; // rcx
  struct CSessionTraceFlags *v155; // rcx
  __int64 v156; // rax
  const wchar_t *v157; // r8
  CConnection *v158; // rcx
  ExecutionContext *v159; // rcx
  __int64 v160; // rbx
  unsigned int v161; // edi
  __int64 v162; // rax
  const wchar_t *v163; // rbx
  bool ContainedAGSystemDbsId; // al
  bool v165; // r12
  unsigned int v166; // esi
  unsigned int v167; // eax
  __int64 v168; // rbx
  __int64 v169; // rax
  unsigned int v170; // eax
  __int64 v171; // rbx
  unsigned __int16 ReplicatedMasterDbId; // ax
  __int64 v173; // rax
  int v174; // r8d
  __int64 v175; // rax
  signed int v176; // edi
  const wchar_t *v177; // rbx
  CDefaultCollation *v178; // rax
  _QWORD *v179; // rax
  AutoReadOnlyXact *v180; // rbx
  __int64 v181; // rax
  void *v182; // rbx
  unsigned __int16 v183; // ax
  __int64 v184; // rax
  __int64 v185; // rbx
  unsigned int v186; // edi
  const wchar_t *v187; // rbx
  __int64 v188; // rcx
  CDefaultCollation *v189; // rax
  char v190; // al
  __int64 v191; // rax
  __int64 v192; // rdx
  const wchar_t *v193; // rbx
  int v194; // edi
  const wchar_t *v195; // rdx
  __int64 v196; // rax
  __int64 v197; // rax
  char v198; // al
  __int64 v199; // rax
  unsigned int v200; // edi
  CDefaultCollation *v201; // rax
  __int64 v202; // rcx
  unsigned int v203; // edi
  CDefaultCollation *v204; // rax
  void *v205; // rbx
  void *v206; // rcx
  unsigned int v207; // edi
  CDefaultCollation *v208; // rax
  __int64 v209; // rcx
  unsigned int v210; // edi
  CDefaultCollation *v211; // rax
  __int64 v212; // rdx
  __int64 v213; // rcx
  __int64 v214; // rbx
  const wchar_t *v215; // rax
  __int64 v216; // rdx
  struct SNI_Conn *v217; // r12
  unsigned int v218; // eax
  int v219; // eax
  int v220; // r8d
  char v221; // al
  __int64 v222; // rax
  __int64 v223; // rax
  unsigned __int16 v225; // ax
  unsigned __int16 v226; // ax
  const struct CSession *v227; // rcx
  int v228; // eax
  __int64 v229; // rcx
  __int32 v230; // eax
  __int64 v231; // rdx
  __int32 v232; // eax
  _QWORD *v233; // rax
  _QWORD *v234; // rax
  __int64 v235; // rax
  __int64 v236; // rdx
  __int64 v237; // rcx
  __int64 v238; // rdi
  _QWORD *v239; // rcx
  _QWORD *v240; // rdx
  int v241; // r8d
  __int64 v242; // r8
  __int64 v243; // r8
  __int64 v244; // r8
  __int64 v245; // rdx
  __int64 v246; // rax
  unsigned int v247; // edi
  const wchar_t *v248; // rsi
  __int64 v249; // rbx
  unsigned int v250; // ebx
  __int64 v251; // rcx
  __int64 v252; // rcx
  __int64 v253; // rax
  int v254; // r8d
  CSbTransportMgr *v255; // rax
  _QWORD *v256; // rbx
  int v257; // r8d
  int v258; // r8d
  int v259; // r8d
  int v260; // r8d
  int v261; // r8d
  CSbTransportMgr *v262; // rbx
  _QWORD *v263; // rdi
  _QWORD *v264; // rbx
  int v265; // r8d
  char v266; // cl
  char v267; // cl
  char v268; // al
  CSbTransportMgr *v269; // rax
  _QWORD *v270; // rbx
  int v271; // r8d
  CSbTransportMgr *v272; // rax
  _QWORD *v273; // rbx
  int v274; // r8d
  __int64 v275; // rax
  void (__fastcall ***v276)(_QWORD, __int64); // rcx
  LONGLONG v277; // rax
  unsigned __int64 v278; // rax
  __int64 v279; // rbx
  CConnection *v280; // rcx
  ExecutionContext *v281; // rcx
  int v282; // [rsp+20h] [rbp-2DD8h]
  int v283; // [rsp+28h] [rbp-2DD0h]
  int v284; // [rsp+40h] [rbp-2DB8h]
  int v285; // [rsp+48h] [rbp-2DB0h]
  __int64 v286; // [rsp+58h] [rbp-2DA0h]
  __int64 v287; // [rsp+70h] [rbp-2D88h]
  int v288; // [rsp+88h] [rbp-2D70h]
  int v289; // [rsp+C0h] [rbp-2D38h] BYREF
  int v290; // [rsp+C4h] [rbp-2D34h]
  char v291; // [rsp+C8h] [rbp-2D30h]
  char v292; // [rsp+C9h] [rbp-2D2Fh]
  char v293; // [rsp+CAh] [rbp-2D2Eh]
  signed int v294; // [rsp+CCh] [rbp-2D2Ch]
  struct SNI_Conn *v295; // [rsp+D0h] [rbp-2D28h] BYREF
  int v296; // [rsp+D8h] [rbp-2D20h]
  int v297; // [rsp+DCh] [rbp-2D1Ch]
  int v298; // [rsp+E0h] [rbp-2D18h]
  unsigned int v299; // [rsp+E4h] [rbp-2D14h]
  int v300; // [rsp+E8h] [rbp-2D10h]
  struct CUEnvTransient *v301; // [rsp+F0h] [rbp-2D08h]
  CConnection *v302; // [rsp+F8h] [rbp-2D00h] BYREF
  struct IMemObj *v303; // [rsp+100h] [rbp-2CF8h]
  volatile signed __int32 *v304; // [rsp+108h] [rbp-2CF0h] BYREF
  int v305; // [rsp+110h] [rbp-2CE8h]
  bool v306; // [rsp+118h] [rbp-2CE0h]
  bool v307; // [rsp+119h] [rbp-2CDFh]
  bool v308; // [rsp+11Ah] [rbp-2CDEh]
  bool v309; // [rsp+11Bh] [rbp-2CDDh]
  bool v310; // [rsp+11Ch] [rbp-2CDCh]
  bool v311; // [rsp+11Dh] [rbp-2CDBh]
  bool v312; // [rsp+11Eh] [rbp-2CDAh]
  char v313; // [rsp+11Fh] [rbp-2CD9h]
  char v314; // [rsp+120h] [rbp-2CD8h]
  bool v316; // [rsp+122h] [rbp-2CD6h]
  int v317; // [rsp+124h] [rbp-2CD4h]
  bool v318; // [rsp+128h] [rbp-2CD0h]
  __int16 v319; // [rsp+12Ch] [rbp-2CCCh] BYREF
  bool v320; // [rsp+130h] [rbp-2CC8h]
  char v321; // [rsp+131h] [rbp-2CC7h]
  char v322; // [rsp+132h] [rbp-2CC6h]
  char v323; // [rsp+133h] [rbp-2CC5h]
  bool v324; // [rsp+134h] [rbp-2CC4h]
  char v325; // [rsp+135h] [rbp-2CC3h]
  unsigned __int8 v326; // [rsp+136h] [rbp-2CC2h]
  bool v327; // [rsp+137h] [rbp-2CC1h]
  bool v328; // [rsp+138h] [rbp-2CC0h]
  bool v329; // [rsp+139h] [rbp-2CBFh]
  struct ImpliedLoginInfo *v330; // [rsp+140h] [rbp-2CB8h]
  wchar_t *v331; // [rsp+148h] [rbp-2CB0h]
  AutoReadOnlyXact *v332; // [rsp+150h] [rbp-2CA8h] BYREF
  __int64 v333; // [rsp+158h] [rbp-2CA0h]
  unsigned int v334; // [rsp+160h] [rbp-2C98h] BYREF
  int v335; // [rsp+164h] [rbp-2C94h]
  struct CRoutingEnvChangeInfo *v336; // [rsp+168h] [rbp-2C90h]
  int v337; // [rsp+170h] [rbp-2C88h]
  struct CConnectionOutput *v338; // [rsp+178h] [rbp-2C80h]
  struct CBatch *v339; // [rsp+180h] [rbp-2C78h]
  CDbAndSetOpts *v340; // [rsp+188h] [rbp-2C70h]
  unsigned int v341; // [rsp+190h] [rbp-2C68h]
  int v342; // [rsp+194h] [rbp-2C64h]
  int v343; // [rsp+198h] [rbp-2C60h]
  unsigned int v344; // [rsp+19Ch] [rbp-2C5Ch] BYREF
  int v345; // [rsp+1A0h] [rbp-2C58h]
  unsigned int v346; // [rsp+1A4h] [rbp-2C54h]
  unsigned int v347; // [rsp+1A8h] [rbp-2C50h]
  unsigned int v348; // [rsp+1ACh] [rbp-2C4Ch]
  int v349; // [rsp+1B0h] [rbp-2C48h]
  unsigned int v350; // [rsp+1B4h] [rbp-2C44h]
  LARGE_INTEGER v351; // [rsp+1B8h] [rbp-2C40h] BYREF
  int v352; // [rsp+1C0h] [rbp-2C38h]
  int v353; // [rsp+1C4h] [rbp-2C34h]
  int v354; // [rsp+1C8h] [rbp-2C30h]
  wchar_t *v355; // [rsp+1D0h] [rbp-2C28h]
  __int64 v356; // [rsp+1D8h] [rbp-2C20h]
  __int64 v357; // [rsp+1E0h] [rbp-2C18h]
  __int64 v358; // [rsp+1E8h] [rbp-2C10h]
  signed int v359; // [rsp+1F0h] [rbp-2C08h]
  __int128 v360; // [rsp+1F8h] [rbp-2C00h] BYREF
  __int64 v361; // [rsp+208h] [rbp-2BF0h] BYREF
  int v362; // [rsp+210h] [rbp-2BE8h]
  SEParams *v363; // [rsp+218h] [rbp-2BE0h] BYREF
  __int64 v364; // [rsp+220h] [rbp-2BD8h]
  struct IMemObj *v365; // [rsp+228h] [rbp-2BD0h]
  int v366; // [rsp+230h] [rbp-2BC8h]
  int v367; // [rsp+234h] [rbp-2BC4h]
  unsigned int v368; // [rsp+238h] [rbp-2BC0h]
  int v369; // [rsp+23Ch] [rbp-2BBCh]
  unsigned int v370; // [rsp+240h] [rbp-2BB8h]
  int v371; // [rsp+244h] [rbp-2BB4h]
  unsigned int v372; // [rsp+248h] [rbp-2BB0h]
  int v373; // [rsp+24Ch] [rbp-2BACh]
  int v374; // [rsp+250h] [rbp-2BA8h]
  int v375; // [rsp+258h] [rbp-2BA0h]
  int v377; // [rsp+264h] [rbp-2B94h]
  int v378; // [rsp+268h] [rbp-2B90h]
  int v379; // [rsp+26Ch] [rbp-2B8Ch]
  unsigned int v380; // [rsp+270h] [rbp-2B88h]
  unsigned int v381; // [rsp+274h] [rbp-2B84h]
  int v382; // [rsp+278h] [rbp-2B80h]
  int v383; // [rsp+280h] [rbp-2B78h]
  int v384; // [rsp+284h] [rbp-2B74h]
  int v385; // [rsp+288h] [rbp-2B70h]
  int v386; // [rsp+28Ch] [rbp-2B6Ch]
  int v387; // [rsp+290h] [rbp-2B68h]
  int v388; // [rsp+294h] [rbp-2B64h]
  LARGE_INTEGER v389; // [rsp+298h] [rbp-2B60h] BYREF
  CSbTransportMgr *v390; // [rsp+2A0h] [rbp-2B58h]
  CSbTransportMgr *v391; // [rsp+2A8h] [rbp-2B50h]
  LARGE_INTEGER v392; // [rsp+2B0h] [rbp-2B48h] BYREF
  CSbTransportMgr *v393; // [rsp+2B8h] [rbp-2B40h]
  CSbTransportMgr *v394; // [rsp+2C0h] [rbp-2B38h]
  CSbTransportMgr *v395; // [rsp+2C8h] [rbp-2B30h]
  CSbTransportMgr *v396; // [rsp+2D0h] [rbp-2B28h]
  LARGE_INTEGER v397; // [rsp+2D8h] [rbp-2B20h] BYREF
  CSbTransportMgr *v398; // [rsp+2E0h] [rbp-2B18h]
  int v399; // [rsp+2E8h] [rbp-2B10h]
  int v400; // [rsp+2ECh] [rbp-2B0Ch]
  int v401; // [rsp+2F0h] [rbp-2B08h]
  int v402; // [rsp+2F8h] [rbp-2B00h]
  int v403; // [rsp+300h] [rbp-2AF8h]
  const wchar_t *v404; // [rsp+308h] [rbp-2AF0h]
  const wchar_t *v405; // [rsp+310h] [rbp-2AE8h]
  LARGE_INTEGER PerformanceCount; // [rsp+318h] [rbp-2AE0h] BYREF
  CSbTransportMgr *v407; // [rsp+320h] [rbp-2AD8h]
  CSbTransportMgr *v408; // [rsp+328h] [rbp-2AD0h]
  const wchar_t *v409; // [rsp+330h] [rbp-2AC8h]
  _QWORD *v410; // [rsp+338h] [rbp-2AC0h]
  CSbTransportMgr *v411; // [rsp+340h] [rbp-2AB8h]
  const wchar_t *v412; // [rsp+348h] [rbp-2AB0h]
  const wchar_t *v413; // [rsp+350h] [rbp-2AA8h]
  LARGE_INTEGER v414; // [rsp+358h] [rbp-2AA0h] BYREF
  CSbTransportMgr *v415; // [rsp+360h] [rbp-2A98h]
  CSbTransportMgr *v416; // [rsp+368h] [rbp-2A90h]
  CSbTransportMgr *v417; // [rsp+370h] [rbp-2A88h]
  unsigned __int64 v418; // [rsp+378h] [rbp-2A80h]
  const wchar_t *v419; // [rsp+380h] [rbp-2A78h]
  LARGE_INTEGER v420; // [rsp+388h] [rbp-2A70h] BYREF
  CSbTransportMgr *v421; // [rsp+390h] [rbp-2A68h]
  CSbTransportMgr *v422; // [rsp+398h] [rbp-2A60h]
  LARGE_INTEGER v423; // [rsp+3A0h] [rbp-2A58h] BYREF
  CSbTransportMgr *v424; // [rsp+3A8h] [rbp-2A50h]
  CSbTransportMgr *v425; // [rsp+3B0h] [rbp-2A48h]
  CSbTransportMgr *v426; // [rsp+3B8h] [rbp-2A40h]
  LARGE_INTEGER v427; // [rsp+3C0h] [rbp-2A38h] BYREF
  CSbTransportMgr *v428; // [rsp+3C8h] [rbp-2A30h]
  CSbTransportMgr *v429; // [rsp+3D0h] [rbp-2A28h]
  CSbTransportMgr *v430; // [rsp+3D8h] [rbp-2A20h]
  LARGE_INTEGER v431; // [rsp+3E0h] [rbp-2A18h] BYREF
  CSbTransportMgr *v432; // [rsp+3E8h] [rbp-2A10h]
  CSbTransportMgr *v433; // [rsp+3F0h] [rbp-2A08h]
  LARGE_INTEGER v434; // [rsp+3F8h] [rbp-2A00h] BYREF
  CSbTransportMgr *v435; // [rsp+400h] [rbp-29F8h]
  CSbTransportMgr *v436; // [rsp+408h] [rbp-29F0h]
  CSbTransportMgr *v437; // [rsp+410h] [rbp-29E8h]
  LARGE_INTEGER v438; // [rsp+418h] [rbp-29E0h] BYREF
  CSbTransportMgr *v439; // [rsp+420h] [rbp-29D8h]
  CSbTransportMgr *v440; // [rsp+428h] [rbp-29D0h]
  _OWORD v441[2]; // [rsp+430h] [rbp-29C8h] BYREF
  __int128 v442; // [rsp+450h] [rbp-29A8h] BYREF
  struct _GUID v443; // [rsp+460h] [rbp-2998h] BYREF
  struct _GUID v444; // [rsp+470h] [rbp-2988h] BYREF
  struct _GUID v445; // [rsp+480h] [rbp-2978h] BYREF
  __int128 v446; // [rsp+490h] [rbp-2968h] BYREF
  __int128 v447; // [rsp+4A0h] [rbp-2958h] BYREF
  __int128 v448; // [rsp+4B0h] [rbp-2948h] BYREF
  __int64 v449; // [rsp+4C0h] [rbp-2938h]
  __int64 v450; // [rsp+4C8h] [rbp-2930h]
  struct CDiagnostics *v451; // [rsp+4D0h] [rbp-2928h]
  __int64 v452; // [rsp+4D8h] [rbp-2920h]
  _QWORD *v453; // [rsp+4E0h] [rbp-2918h]
  __int64 v454; // [rsp+4E8h] [rbp-2910h]
  __int64 v455; // [rsp+4F0h] [rbp-2908h]
  __int64 v456; // [rsp+4F8h] [rbp-2900h]
  __int64 v457; // [rsp+500h] [rbp-28F8h]
  __int64 v458; // [rsp+508h] [rbp-28F0h]
  __int64 v459; // [rsp+510h] [rbp-28E8h]
  _QWORD *v460; // [rsp+518h] [rbp-28E0h]
  _QWORD *v461; // [rsp+520h] [rbp-28D8h]
  __int64 v462; // [rsp+528h] [rbp-28D0h]
  void *v463; // [rsp+530h] [rbp-28C8h]
  __int64 v464; // [rsp+538h] [rbp-28C0h]
  _QWORD *ThreadLocalStoragePointer; // [rsp+540h] [rbp-28B8h]
  __int64 *v466; // [rsp+548h] [rbp-28B0h]
  __int64 v467; // [rsp+550h] [rbp-28A8h]
  __int64 v468; // [rsp+558h] [rbp-28A0h]
  __int64 v469; // [rsp+560h] [rbp-2898h]
  __int64 v470; // [rsp+568h] [rbp-2890h]
  const wchar_t *v471; // [rsp+570h] [rbp-2888h]
  __int64 v472; // [rsp+578h] [rbp-2880h]
  const wchar_t *v473; // [rsp+580h] [rbp-2878h]
  const wchar_t *v474; // [rsp+588h] [rbp-2870h]
  __int64 v475; // [rsp+590h] [rbp-2868h]
  void *v476; // [rsp+598h] [rbp-2860h]
  const wchar_t *v477; // [rsp+5A0h] [rbp-2858h]
  const wchar_t *v478; // [rsp+5A8h] [rbp-2850h]
  __int64 v479; // [rsp+5B0h] [rbp-2848h]
  void *v480; // [rsp+5B8h] [rbp-2840h]
  __int64 v481; // [rsp+5C0h] [rbp-2838h]
  const wchar_t *v482; // [rsp+5C8h] [rbp-2830h]
  __int64 v483; // [rsp+5D0h] [rbp-2828h]
  void *v484; // [rsp+5D8h] [rbp-2820h]
  __int64 v485; // [rsp+5E0h] [rbp-2818h]
  struct ImpliedLoginInfo *v486; // [rsp+5E8h] [rbp-2810h]
  __int64 v487; // [rsp+5F0h] [rbp-2808h]
  __int64 v488; // [rsp+5F8h] [rbp-2800h]
  _QWORD *v489; // [rsp+600h] [rbp-27F8h]
  _QWORD *v490; // [rsp+608h] [rbp-27F0h]
  struct ImpliedLoginInfo **v491; // [rsp+610h] [rbp-27E8h]
  struct ImpliedLoginInfo *v492; // [rsp+618h] [rbp-27E0h]
  _QWORD *v493; // [rsp+620h] [rbp-27D8h]
  struct ImpliedLoginInfo **v494; // [rsp+628h] [rbp-27D0h]
  struct ImpliedLoginInfo *v495; // [rsp+630h] [rbp-27C8h]
  _QWORD *v496; // [rsp+638h] [rbp-27C0h]
  _QWORD *v497; // [rsp+640h] [rbp-27B8h]
  __int64 v498; // [rsp+648h] [rbp-27B0h]
  _QWORD *v499; // [rsp+650h] [rbp-27A8h]
  _QWORD *v500; // [rsp+658h] [rbp-27A0h]
  __int64 v501; // [rsp+660h] [rbp-2798h]
  __int64 v502; // [rsp+668h] [rbp-2790h]
  _DWORD *v503; // [rsp+670h] [rbp-2788h]
  unsigned int *v504; // [rsp+678h] [rbp-2780h]
  int *v505; // [rsp+680h] [rbp-2778h]
  __int64 v506; // [rsp+688h] [rbp-2770h]
  _QWORD *v507; // [rsp+690h] [rbp-2768h]
  __int64 v508; // [rsp+698h] [rbp-2760h]
  CDiagnostics *v509; // [rsp+6A0h] [rbp-2758h]
  _QWORD *v510; // [rsp+6A8h] [rbp-2750h]
  struct ImpliedLoginInfo **v511; // [rsp+6B0h] [rbp-2748h]
  struct ImpliedLoginInfo *v512; // [rsp+6B8h] [rbp-2740h]
  _QWORD *v513; // [rsp+6C0h] [rbp-2738h]
  __int64 v514; // [rsp+6C8h] [rbp-2730h]
  __int64 v515; // [rsp+6D0h] [rbp-2728h]
  __int64 v516; // [rsp+6D8h] [rbp-2720h]
  _QWORD *v517; // [rsp+6E0h] [rbp-2718h]
  _QWORD *v518; // [rsp+6E8h] [rbp-2710h]
  __int64 v519; // [rsp+6F0h] [rbp-2708h]
  __int64 v520; // [rsp+6F8h] [rbp-2700h]
  __int64 v521; // [rsp+700h] [rbp-26F8h]
  struct CUEnvTransient *v522; // [rsp+708h] [rbp-26F0h]
  __int64 v523; // [rsp+710h] [rbp-26E8h]
  __int64 v524; // [rsp+718h] [rbp-26E0h]
  _QWORD *v525; // [rsp+720h] [rbp-26D8h]
  __int64 v526; // [rsp+728h] [rbp-26D0h]
  struct CUEnvTransient *v527; // [rsp+730h] [rbp-26C8h]
  __int64 v528; // [rsp+738h] [rbp-26C0h]
  __int64 v529; // [rsp+740h] [rbp-26B8h]
  _QWORD *v530; // [rsp+748h] [rbp-26B0h]
  __int64 v531; // [rsp+750h] [rbp-26A8h]
  _QWORD *v532; // [rsp+758h] [rbp-26A0h]
  __int64 v533; // [rsp+760h] [rbp-2698h]
  struct CUEnvTransient *v534; // [rsp+768h] [rbp-2690h]
  __int64 v535; // [rsp+770h] [rbp-2688h]
  __int64 v536; // [rsp+778h] [rbp-2680h]
  _QWORD *v537; // [rsp+780h] [rbp-2678h]
  __int64 v538; // [rsp+788h] [rbp-2670h]
  _QWORD *v539; // [rsp+790h] [rbp-2668h]
  _QWORD *v540; // [rsp+798h] [rbp-2660h]
  __int64 v541; // [rsp+7A0h] [rbp-2658h]
  __int64 v542; // [rsp+7A8h] [rbp-2650h]
  __int64 v543; // [rsp+7B0h] [rbp-2648h]
  _QWORD *v544; // [rsp+7B8h] [rbp-2640h]
  __int64 v545; // [rsp+7C0h] [rbp-2638h]
  struct CUEnvTransient *v546; // [rsp+7C8h] [rbp-2630h]
  __int64 v547; // [rsp+7D0h] [rbp-2628h]
  __int64 v548; // [rsp+7D8h] [rbp-2620h]
  _QWORD *v549; // [rsp+7E0h] [rbp-2618h]
  __int64 v550; // [rsp+7E8h] [rbp-2610h]
  struct CUEnvTransient *v551; // [rsp+7F0h] [rbp-2608h]
  __int64 v552; // [rsp+7F8h] [rbp-2600h]
  __int64 v553; // [rsp+800h] [rbp-25F8h]
  _QWORD *v554; // [rsp+808h] [rbp-25F0h]
  __int64 v555; // [rsp+810h] [rbp-25E8h]
  _QWORD *v556; // [rsp+818h] [rbp-25E0h]
  __int64 *v557; // [rsp+820h] [rbp-25D8h]
  __int64 v558; // [rsp+828h] [rbp-25D0h]
  CSession *v559; // [rsp+830h] [rbp-25C8h]
  AutoReadOnlyXact *v560; // [rsp+838h] [rbp-25C0h]
  void (__fastcall ***v561)(_QWORD, __int64); // [rsp+840h] [rbp-25B8h]
  struct _GUID v562[2]; // [rsp+850h] [rbp-25A8h] BYREF
  struct _GUID v563; // [rsp+870h] [rbp-2588h] BYREF
  unsigned int v564; // [rsp+880h] [rbp-2578h] BYREF
  __int64 v565; // [rsp+888h] [rbp-2570h] BYREF
  unsigned int v566; // [rsp+890h] [rbp-2568h] BYREF
  unsigned __int16 v567; // [rsp+894h] [rbp-2564h] BYREF
  unsigned __int16 v568[2]; // [rsp+898h] [rbp-2560h] BYREF
  unsigned __int16 v569; // [rsp+89Ch] [rbp-255Ch] BYREF
  unsigned __int16 v570[2]; // [rsp+8A0h] [rbp-2558h] BYREF
  int v571; // [rsp+8A4h] [rbp-2554h] BYREF
  unsigned __int16 v572[2]; // [rsp+8A8h] [rbp-2550h] BYREF
  unsigned __int16 v573; // [rsp+8ACh] [rbp-254Ch] BYREF
  int v574; // [rsp+8B0h] [rbp-2548h] BYREF
  int v575[3]; // [rsp+8B4h] [rbp-2544h] BYREF
  __int64 v576; // [rsp+8C0h] [rbp-2538h] BYREF
  int v577; // [rsp+8C8h] [rbp-2530h] BYREF
  int v578; // [rsp+8CCh] [rbp-252Ch] BYREF
  struct _GUID v579; // [rsp+8D0h] [rbp-2528h] BYREF
  unsigned __int8 v580[8]; // [rsp+8E0h] [rbp-2518h] BYREF
  LARGE_INTEGER v581; // [rsp+8E8h] [rbp-2510h] BYREF
  int v582; // [rsp+8F0h] [rbp-2508h] BYREF
  int v583; // [rsp+8F4h] [rbp-2504h]
  __int16 v584; // [rsp+8F8h] [rbp-2500h]
  int v585; // [rsp+8FCh] [rbp-24FCh]
  __int16 v586; // [rsp+900h] [rbp-24F8h]
  int v587; // [rsp+904h] [rbp-24F4h]
  __int128 v588; // [rsp+908h] [rbp-24F0h]
  __int128 v589; // [rsp+918h] [rbp-24E0h]
  __int128 v590; // [rsp+928h] [rbp-24D0h]
  __int16 v591; // [rsp+938h] [rbp-24C0h]
  int v592; // [rsp+93Ch] [rbp-24BCh]
  __int128 v593; // [rsp+940h] [rbp-24B8h]
  __int128 v594; // [rsp+950h] [rbp-24A8h]
  __int128 v595; // [rsp+960h] [rbp-2498h]
  __int128 v596; // [rsp+970h] [rbp-2488h]
  __int128 v597; // [rsp+980h] [rbp-2478h]
  __int128 v598; // [rsp+990h] [rbp-2468h]
  __int16 v599; // [rsp+9A0h] [rbp-2458h]
  int v600; // [rsp+9A4h] [rbp-2454h]
  char v601; // [rsp+9A8h] [rbp-2450h]
  __int64 v602; // [rsp+9ACh] [rbp-244Ch]
  __int128 v603; // [rsp+9B4h] [rbp-2444h]
  __int128 v604; // [rsp+9C4h] [rbp-2434h]
  __int16 v605; // [rsp+9D4h] [rbp-2424h]
  int v606; // [rsp+9D8h] [rbp-2420h]
  char v607; // [rsp+9DCh] [rbp-241Ch]
  char v608; // [rsp+9DDh] [rbp-241Bh]
  int v609; // [rsp+9E0h] [rbp-2418h]
  int v610; // [rsp+9E4h] [rbp-2414h]
  char v611; // [rsp+9E8h] [rbp-2410h]
  struct _GUID v612; // [rsp+9F0h] [rbp-2408h] BYREF
  __int128 v613; // [rsp+A10h] [rbp-23E8h]
  __m128i si128; // [rsp+A40h] [rbp-23B8h] BYREF
  int v615; // [rsp+A50h] [rbp-23A8h]
  __int16 v616; // [rsp+A54h] [rbp-23A4h] BYREF
  __int64 v617; // [rsp+B58h] [rbp-22A0h]
  _BYTE v618[48]; // [rsp+B60h] [rbp-2298h] BYREF
  _BYTE v619[80]; // [rsp+B90h] [rbp-2268h] BYREF
  char v620[8]; // [rsp+BE0h] [rbp-2218h] BYREF
  int v621; // [rsp+BE8h] [rbp-2210h]
  int v622; // [rsp+BF0h] [rbp-2208h]
  _QWORD *v623; // [rsp+BF8h] [rbp-2200h]
  char *v624; // [rsp+C00h] [rbp-21F8h]
  __int64 v625; // [rsp+C08h] [rbp-21F0h]
  _QWORD v626[2]; // [rsp+C10h] [rbp-21E8h] BYREF
  char v627; // [rsp+C20h] [rbp-21D8h] BYREF
  __int64 v628; // [rsp+E30h] [rbp-1FC8h]
  __int64 v629; // [rsp+E38h] [rbp-1FC0h]
  unsigned __int64 v630; // [rsp+E40h] [rbp-1FB8h] BYREF
  bool v631; // [rsp+E48h] [rbp-1FB0h]
  char v632[8]; // [rsp+E50h] [rbp-1FA8h] BYREF
  __int16 v633; // [rsp+E58h] [rbp-1FA0h]
  __int16 v634; // [rsp+E5Ah] [rbp-1F9Eh]
  int v635; // [rsp+E60h] [rbp-1F98h]
  __int64 v636; // [rsp+E68h] [rbp-1F90h]
  char *v637; // [rsp+E70h] [rbp-1F88h]
  __int64 v638; // [rsp+E78h] [rbp-1F80h]
  char v639; // [rsp+E80h] [rbp-1F78h] BYREF
  int v640; // [rsp+10A0h] [rbp-1D58h]
  int v641; // [rsp+10A4h] [rbp-1D54h]
  __int64 v642; // [rsp+10A8h] [rbp-1D50h]
  _BYTE v643[24]; // [rsp+10B0h] [rbp-1D48h] BYREF
  _QWORD *v644; // [rsp+10C8h] [rbp-1D30h]
  __int32 v645; // [rsp+1310h] [rbp-1AE8h]
  __int32 v646; // [rsp+1314h] [rbp-1AE4h]
  char v647; // [rsp+1318h] [rbp-1AE0h]
  char v648; // [rsp+1319h] [rbp-1ADFh]
  void **v649; // [rsp+1340h] [rbp-1AB8h] BYREF
  char v650; // [rsp+1348h] [rbp-1AB0h]
  char v651[768]; // [rsp+1350h] [rbp-1AA8h] BYREF
  _BYTE v652[4496]; // [rsp+1650h] [rbp-17A8h] BYREF
  __int64 v653; // [rsp+27E0h] [rbp-618h]
  _OWORD pSid[4]; // [rsp+2850h] [rbp-5A8h] BYREF
  int v655; // [rsp+2890h] [rbp-568h]
  wchar_t Buffer[16]; // [rsp+28A0h] [rbp-558h] BYREF
  wchar_t Source[16]; // [rsp+28C0h] [rbp-538h] BYREF
  unsigned __int8 v658[96]; // [rsp+28E0h] [rbp-518h] BYREF
  unsigned __int8 v659[96]; // [rsp+2940h] [rbp-4B8h] BYREF
  wchar_t v660[128]; // [rsp+29A0h] [rbp-458h] BYREF
  wchar_t v661[128]; // [rsp+2AA0h] [rbp-358h] BYREF
  wchar_t v662[128]; // [rsp+2BA0h] [rbp-258h] BYREF
  wchar_t v663[128]; // [rsp+2CA0h] [rbp-158h] BYREF

  v450 = -2;
  v295 = a4;
  v302 = (CConnection *)a3;
  v6 = a2;
  v339 = a2;
  v303 = a1;
  v365 = a1;
  v336 = a5;
  v335 = 0;
  if ( (WORD2(qword_102EDC9FC) & 0x400) != 0 )
  {
    v335 = 1;
    QueryPerformanceCounter(&v581);
  }
  v338 = a3[3];
  v294 = 0;
  v7 = *(LARGE_INTEGER *)((char *)v6 + 24);
  v351 = v7;
  v289 = 0;
  v574 = 0;
  v293 = 0;
  v575[0] = 0;
  v578 = 0;
  v297 = 0;
  v337 = 0;
  v330 = 0;
  v334 = 0;
  v8 = *(_QWORD *)(v7.QuadPart + 96);
  v333 = v8;
  v9 = *(_BYTE *)(v8 + 49);
  if ( (v9 & 1) != 0 )
  {
    *(_BYTE *)(v7.QuadPart + 272) |= 0x10u;
    v9 = *(_BYTE *)(v8 + 49);
  }
  if ( (v9 & 2) != 0 )
    *(_BYTE *)(v7.QuadPart + 272) |= 0x20u;
  v566 = 1;
  v617 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v615 = 0;
  v616 = 0;
  v296 = 0;
  v300 = 0;
  if ( !*(_DWORD *)(qword_102ECFB00 + 14504) || (v10 = 1, !byte_102EDCEA9) )
    v10 = 0;
  v298 = v10;
  if ( *(_DWORD *)(v8 + 988) != 2
    || (LOBYTE(a2) = 2, v74 = CPhysicalConnection::GetFeatureExtension(v8, a2) == 0, v11 = 1, v74) )
  {
    v11 = 0;
  }
  v571 = v11;
  if ( !v10 || (v12 = 1, !v11) )
    v12 = 0;
  v290 = v12;
  if ( !*(_DWORD *)(GetXdbServerGlobals(a1, a2) + 8308) )
  {
    if ( *(_DWORD *)(GetXdbServerGlobals(v14, v13) + 11976) )
    {
      v134 = *(_BYTE *)(v7.QuadPart + 270) | 0x10;
      *(_BYTE *)(v7.QuadPart + 270) = v134;
      v135 = *(_BYTE *)(v7.QuadPart + 271) | 2;
      *(_BYTE *)(v7.QuadPart + 271) = v135;
      if ( *(_DWORD *)(v8 + 968) != 5 || v12 )
      {
        *(_BYTE *)(v7.QuadPart + 270) = v134 | 2;
        *(_BYTE *)(v7.QuadPart + 271) = v135 & 0xFD;
      }
      goto LABEL_16;
    }
    if ( *(_DWORD *)(qword_102ECFB00 + 14504)
      && (*(_BYTE *)(GetXdbServerGlobals(v16, v15) + 12009) || *(_BYTE *)(GetXdbServerGlobals(v137, v136) + 12008))
      && !*(_BYTE *)(GetXdbServerGlobals(v137, v136) + 12004) )
    {
      if ( !*(_DWORD *)(qword_102ECFB00 + 14504)
        && (*((char *)qword_102ECFB10 + 1533) < 0
         || (v139 = (struct CSessionTraceFlags *)SystemThread_TlsIndex,
             v138 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                  + SystemThread_TlsOffset,
             *(_QWORD *)v138)
         && (v139 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v138 + 56LL)) != 0
         && CSessionTraceFlags::CheckSessionTraceInternal(v139, 0x2FEFu))
        || *(_BYTE *)(GetXdbServerGlobals(v139, v138) + 12005) )
      {
        *(_BYTE *)(v7.QuadPart + 270) |= 8u;
      }
      if ( !*(_DWORD *)(qword_102ECFB00 + 14504)
        || !*(_BYTE *)(GetXdbServerGlobals(v139, v138) + 12009)
        || (v140 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                 + SystemThread_TlsOffset,
            *(_QWORD *)v140)
        && (v141 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v140 + 56LL)) != 0
        && CSessionTraceFlags::CheckSessionTraceInternal(v141, 0x3275u) )
      {
        v143 = *(_BYTE *)(v7.QuadPart + 270);
      }
      else
      {
        v142 = *(_BYTE *)(v7.QuadPart + 270) | 0x80;
        *(_BYTE *)(v7.QuadPart + 270) = v142;
        v143 = v142;
        if ( *(_DWORD *)(v8 + 968) == 5 && !v12 )
        {
          *(_BYTE *)(v7.QuadPart + 270) = v142 | 0x40;
          goto LABEL_16;
        }
      }
      *(_BYTE *)(v7.QuadPart + 270) = v143 | 2;
      goto LABEL_16;
    }
    goto LABEL_16;
  }
  v120 = 0;
  v121 = *(_QWORD *)(v7.QuadPart + 192);
  if ( v121 )
  {
    v120 = 2 * *(unsigned __int16 *)(v121 + 70);
    v122 = (const wchar_t *)(v121 + *(unsigned __int16 *)(v121 + 68));
  }
  else
  {
    v122 = 0;
  }
  v123 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  v126 = *(_DWORD *)(GetXdbServerGlobals(v125, v124) + 8196);
  v296 = v126;
  if ( *(_DWORD *)(v8 + 988) <= 1u )
  {
    if ( *(_DWORD *)(*(_QWORD *)(v123 + 520) + 20LL) )
    {
      *(_DWORD *)(v7.QuadPart + 404) = 1;
      v300 = v126;
      goto LABEL_16;
    }
    if ( v126 )
    {
LABEL_16:
      v17 = v290;
      goto LABEL_17;
    }
    *(_BYTE *)(v7.QuadPart + 270) |= 4u;
    *(_BYTE *)(v7.QuadPart + 271) |= 1u;
    v127 = (unsigned __int8)-*((_BYTE *)qword_102EF3550 + 453);
    v128 = *(_BYTE *)(v7.QuadPart + 271) & 0xF7;
    *(_BYTE *)(v7.QuadPart + 271) = v128 | (*((_BYTE *)qword_102EF3550 + 453) != 0 ? 8 : 0);
    v297 = 1;
    *(_DWORD *)(v7.QuadPart + 404) = 1;
    XdbServerGlobals = GetXdbServerGlobals(v127, v128);
    v17 = v290;
    goto LABEL_207;
  }
  if ( !FPDWFeaturesExposed()
    || (*(_DWORD *)(v7.QuadPart + 400) & 0x8000) != 0
    || *(_DWORD *)(*(_QWORD *)(v123 + 520) + 20LL) )
  {
    if ( v296
      && FPDWFeaturesExposed()
      && v120 > 4
      && !wcsncmp(v122, L"b-", 2u)
      && *(_DWORD *)(*(_QWORD *)(v123 + 520) + 20LL) )
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
    || (v130 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                         + SystemThread_TlsOffset)) != 0
    && (v131 = **(struct CSessionTraceFlags ***)(v130 + 56)) != 0
    && CSessionTraceFlags::CheckSessionTraceInternal(v131, 0x2562u) )
  {
    v17 = v290;
    goto LABEL_221;
  }
  v17 = v290;
  if ( v290 )
  {
LABEL_221:
    *(_BYTE *)(v7.QuadPart + 270) |= 2u;
    goto LABEL_17;
  }
  *(_BYTE *)(v7.QuadPart + 270) |= 4u;
  *(_BYTE *)(v7.QuadPart + 271) |= 1u;
  v132 = (unsigned __int8)-*((_BYTE *)qword_102EF3550 + 453);
  v133 = *(_BYTE *)(v7.QuadPart + 271) & 0xF7;
  *(_BYTE *)(v7.QuadPart + 271) = v133 | (*((_BYTE *)qword_102EF3550 + 453) != 0 ? 8 : 0);
  v297 = 1;
  *(_DWORD *)(v7.QuadPart + 404) = 1;
  XdbServerGlobals = GetXdbServerGlobals(v132, v133);
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
    v153 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v7.QuadPart + 96) + 16LL))(*(_QWORD *)(v7.QuadPart + 96));
    ImpliedLoginInfoFromCertificate = ImpliedAuthenticationManager::GetImpliedLoginInfoFromCertificate(
                                        v154,
                                        *(const struct _CERT_CONTEXT **)(v153 + 1032));
    v330 = ImpliedLoginInfoFromCertificate;
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
      v294 = 0;
      goto LABEL_18;
    }
    memset(pSid, 0, sizeof(pSid));
    v655 = 0;
    v344 = 68;
    if ( GetAppContainerSidFromSNIConnection(v145, v144, v295, (unsigned __int8 *)pSid, &v344) >= 0 )
    {
      LengthSid = GetLengthSid(pSid);
      ImpliedLoginInfoFromCertificate = ImpliedAuthenticationManager::GetImpliedLoginInfo(
                                          g_impliedAuthenticationManager,
                                          (unsigned __int8 *)pSid,
                                          LengthSid);
      v330 = ImpliedLoginInfoFromCertificate;
    }
    else
    {
LABEL_271:
      ImpliedLoginInfoFromCertificate = 0;
    }
  }
  v294 = 0;
  if ( ImpliedLoginInfoFromCertificate )
  {
    v337 = 1;
    v148 = *(_BYTE *)(v7.QuadPart + 270);
    v294 = 0;
    if ( (v148 & 0x10) == 0 )
    {
      *(_BYTE *)(v7.QuadPart + 270) = v148 | 4;
      *(_BYTE *)(v7.QuadPart + 271) |= 1u;
      v149 = (unsigned __int8)-*((_BYTE *)qword_102EF3550 + 453);
      v150 = *(_BYTE *)(v7.QuadPart + 271) & 0xF7;
      *(_BYTE *)(v7.QuadPart + 271) = v150 | (*((_BYTE *)qword_102EF3550 + 453) != 0 ? 8 : 0);
      v151 = GetXdbServerGlobals(v149, v150);
      v152 = 3;
      if ( *(_DWORD *)(v151 + 8308) )
        v152 = 1;
      *(_DWORD *)(v7.QuadPart + 404) = v152;
      v300 = v296;
      goto LABEL_265;
    }
  }
LABEL_18:
  if ( (*((_BYTE *)qword_102ECFB10 + 1072) & 0x40) != 0
    || (v18 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                        + SystemThread_TlsOffset)) != 0
    && (v155 = **(struct CSessionTraceFlags ***)(v18 + 56)) != 0
    && CSessionTraceFlags::CheckSessionTraceInternal(v155, 0x2186u)
    || (unsigned int)IsReplicatedMasterEnabled() && (*(_BYTE *)(v7.QuadPart + 270) & 2) != 0 )
  {
    if ( (v156 = *(_QWORD *)(v7.QuadPart + 192)) != 0
      && (v157 = (const wchar_t *)(v156 + *(unsigned __int16 *)(v156 + 68)), *(_WORD *)(v156 + 70))
      && v157
      && CompareStringWEnglishNoCase(1u, 0, v157, *(unsigned __int16 *)(v156 + 70), L"PHYSMASTER", 10) == 2
      || v17 )
    {
      *(_BYTE *)(v7.QuadPart + 270) |= 0x20u;
    }
  }
  v360 = 0;
  v19 = v295;
  v20 = *(_OWORD *)((char *)v295 + 28);
  *(LARGE_INTEGER *)&v360 = v7;
  v21 = v302;
  *((_QWORD *)&v360 + 1) = v302;
  *((LARGE_INTEGER *)v302 + 1) = v7;
  *(_QWORD *)(v7.QuadPart + 480) = v21;
  _InterlockedIncrement((volatile signed __int32 *)v21 + 19);
  ITaskProxy::SetCurrentTaskProxy((struct ITaskProxy *)(v7.QuadPart + 504));
  if ( !(unsigned int)CConnection::FInitMainEc(v21, v303) )
    goto LABEL_284;
  v22 = CDiagnostics::PCreateInstanceNoX();
  v23 = (volatile signed __int32 *)v22;
  v451 = v22;
  if ( !v22 )
    goto LABEL_284;
  *((_QWORD *)v21 + 5) = v22;
  if ( !CSession::FInitForNewConnection((CSession *)v7.QuadPart)
    || !CSessionMgr::FAddSession((struct CSession *)v7.QuadPart) )
  {
    if ( _InterlockedExchangeAdd(v23 + 6, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)v23 + 40LL))(v23, 1);
LABEL_284:
    v158 = *(CConnection **)(v7.QuadPart + 480);
    if ( v158 )
      CConnection::Release(v158);
    *(_QWORD *)(v7.QuadPart + 480) = 0;
    *((_QWORD *)v21 + 1) = 0;
    v159 = (ExecutionContext *)*((_QWORD *)v21 + 6);
    if ( v159 )
    {
      ExecutionContext::CleanupAndDelete(v159, 1);
      *((_QWORD *)v21 + 6) = 0;
    }
    *((_QWORD *)v21 + 5) = 0;
    goto LABEL_289;
  }
  v24 = *(_QWORD *)(v7.QuadPart + 96);
  if ( v24 && (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24) )
  {
    v25 = *(_WORD *)(v7.QuadPart + 16);
    v26 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v7.QuadPart + 96) + 16LL))(*(_QWORD *)(v7.QuadPart + 96));
    *(_WORD *)(v26 + 684) = v25;
    v27 = *(_QWORD *)(v26 + 448);
    if ( v27 )
    {
      v319 = v25;
      SNISetInfo(v27, 28, &v319);
    }
    v21 = v302;
  }
  v442 = v20;
  ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))CDiagnostics::InitMainThread)(
    v23,
    (LARGE_INTEGER)v7.QuadPart,
    1,
    &v442,
    v19);
  CDiagManager::Add((struct CDiagThreadSafe *)v23);
  v360 = 0;
  if ( _InterlockedExchangeAdd(v23 + 6, 0xFFFFFFFF) == 1 )
    (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)v23 + 40LL))(v23, 1);
  CAutoSetupCXCtxtSingleThread::CAutoSetupCXCtxtSingleThread(
    (CAutoSetupCXCtxtSingleThread *)v652,
    v339,
    (struct CSession *)v7.QuadPart,
    v21);
  v28 = 8LL * SystemThread_TlsIndex;
  v301 = *(struct CUEnvTransient **)(*(_QWORD *)(SystemThread_TlsOffset
                                               + *(_QWORD *)((char *)NtCurrentTeb()->ThreadLocalStoragePointer + v28))
                                   + 120LL);
  v340 = **(CDbAndSetOpts ***)(*(_QWORD *)(*(_QWORD *)((char *)NtCurrentTeb()->ThreadLocalStoragePointer + v28)
                                         + SystemThread_TlsOffset)
                             + 64LL);
  v29 = 0;
  v304 = 0;
  v30 = 0;
  v305 = 0;
  v31 = *(volatile signed __int32 **)(v7.QuadPart + 648);
  if ( (*(unsigned __int8 (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)v31 + 24LL))(v31, 0) )
  {
    _InterlockedIncrement(v31 + 35);
    v29 = v31;
    v304 = v31;
    v30 = 1;
    v305 = 1;
  }
  if ( (v305 & 1) == 0 )
  {
    if ( (v30 & 1) != 0 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v29 + 32LL))(v29);
      if ( _InterlockedExchangeAdd(v29 + 35, 0xFFFFFFFF) == 1 )
      {
        v160 = *((_QWORD *)v304 + 1);
        (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)v304 + 40LL))(v304, 1);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v160 + 16LL))(v160);
      }
      v304 = 0;
      v305 &= ~1u;
    }
    CAutoSetupCXCtxtSingleThread::~CAutoSetupCXCtxtSingleThread((CAutoSetupCXCtxtSingleThread *)v652);
LABEL_289:
    ITaskProxy::SetCurrentTaskProxy(0);
    return 2147500037LL;
  }
  SEParams::SEParams((SEParams *)v619);
  v32 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                  + SystemThread_TlsOffset
                  + 80LL);
  v33 = (struct XactWorkspace *)(**(__int64 (__fastcall ***)(volatile signed __int32 *))v304)(v304);
  SessionIsolationLevel = getSessionIsolationLevel(*((_BYTE *)v340 + 76));
  SEParams::Init(
    (SEParams *)v619,
    0xFFFFFFFF,
    SessionIsolationLevel,
    0,
    v33,
    (struct SEExecutionStatistics *)(v32 + 256),
    0);
  v364 = 0;
  AutoInstallParams::Install((AutoInstallParams *)&v363, (struct SEParams *)v619);
  if ( v364 )
    utassert_fail(
      1u,
      "NULL == m_separamsPrev",
      "sephlpr.cpp",
      82,
      "SEParams is being installed more than once. Illegal usage.");
  CAutoSetXLvlIntCtxtImplNoException::CAutoSetXLvlIntCtxtImplNoException(
    (CAutoSetXLvlIntCtxtImplNoException *)&v649,
    (struct CSession *)v7.QuadPart,
    v339);
  v564 = 0;
  v35 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v36 = *(_QWORD *)(v35 + 256);
  if ( !v36 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v36 = *(_QWORD *)(v35 + 256);
  }
  v358 = *(_QWORD *)(v36 + 3208);
  v37 = v358;
  *(_QWORD *)(v36 + 3208) = ex_trans_cexcept;
  v452 = v37;
  ExcHandler::ExcHandler((ExcHandler *)v618, 0, 0, 0, (int (*)(int, int, int, int, char *))hdl_prntbackout, 0);
  v576 = 0;
  *(_DWORD *)v580 = 0;
  if ( !(unsigned int)IsContainedAGEnabledInstance() )
    goto LABEL_52;
  CSession::GetHadronAgId((CSession *)v7.QuadPart, &v579);
  if ( *(_QWORD *)&v579.Data1 == *(_QWORD *)&Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val.Data1
    && *(_QWORD *)v579.Data4 == *(_QWORD *)Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val.Data4 )
  {
    v40 = 0;
    v345 = 0;
    v41 = *(_QWORD *)(v7.QuadPart + 192);
    if ( v41 )
    {
      v40 = 2 * *(unsigned __int16 *)(v41 + 70);
      v345 = v40;
      v42 = (const wchar_t *)(v41 + *(unsigned __int16 *)(v41 + 68));
    }
    else
    {
      v42 = 0;
    }
    v404 = v42;
    v567 = 0;
    v568[0] = 0;
    v43 = Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
    v579 = Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
    if ( v42 && v40 )
    {
      if ( *(_BYTE *)(GetXdbServerGlobals(v39, v38) + 12004) )
      {
        v43 = v579;
      }
      else
      {
        v43 = *HadrRuntimeCallbacks::GetContainedOrSystemAGId(v562, v42, v40, &v567, v568);
        v562[1] = v43;
        v579 = v43;
      }
    }
    if ( *(_QWORD *)&v43.Data1 == *(_QWORD *)&Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val.Data1
      && _mm_srli_si128((__m128i)v43, 8).m128i_u64[0] == *(_QWORD *)Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val.Data4 )
    {
      *(_BYTE *)(v7.QuadPart + 270) |= 0x20u;
      v44 = Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
      *(_WORD *)(v7.QuadPart + 4928) = 1;
      *(_WORD *)(v7.QuadPart + 4930) = 0;
LABEL_51:
      *(GUID *)(v7.QuadPart + 4912) = v44;
      goto LABEL_52;
    }
    *(GUID *)(v7.QuadPart + 4912) = v43;
    *(_WORD *)(v7.QuadPart + 4928) = v567;
    *(_WORD *)(v7.QuadPart + 4930) = v568[0];
LABEL_52:
    v653 = *(_QWORD *)(*(_QWORD *)(v7.QuadPart + 648) + 16LL);
    v441[0] = 0;
    v332 = 0;
    AutoInstallMsqlXact::InstallXactForLogin(
      (AutoInstallMsqlXact *)v441,
      *(struct CMsqlXactManager **)(v7.QuadPart + 648));
    v318 = CommonGlobalState::m_PerfCountersEnabled;
    if ( CommonGlobalState::m_PerfCountersEnabled )
      PerfmonManager::IncrementCounterValue((PerfmonManager *)qword_102ECFB00, 3u, 0x10u, 1, 0);
    v45 = *(_QWORD *)(v7.QuadPart + 192);
    *(_DWORD *)(v7.QuadPart + 400) = *(_DWORD *)(v45 + 24);
    v46 = 2 * *(unsigned __int16 *)(v45 + 42);
    v296 = v46;
    v317 = v46;
    v331 = (wchar_t *)(v45 + *(unsigned __int16 *)(v45 + 40));
    v355 = v331;
    if ( !(unsigned int)IsReplicatedMasterEnabled() || CSession::FPhysicalMasterUsageForced((CSession *)v7.QuadPart) )
    {
      v47 = qword_102ECFB00;
      v457 = qword_102ECFB00;
      MasterDbId = GetMasterDbId();
      DBMgr::OpenDB(*(_QWORD *)(v47 + 32), 0, MasterDbId, 14, 1, 16448);
    }
    else
    {
      if ( !(unsigned __int8)StartupDependencies::IsCompleted(16) )
      {
        Login = 40613;
        v289 = 40613;
        v566 = 162;
        goto LABEL_321;
      }
      v171 = qword_102ECFB00;
      v455 = qword_102ECFB00;
      ReplicatedMasterDbId = GetReplicatedMasterDbId();
      v173 = DBMgr::OpenDB(*(_QWORD *)(v171 + 32), 0, ReplicatedMasterDbId, 14, 0, 16448);
      v456 = v173;
      if ( !v173 || *(_DWORD *)(*(_QWORD *)(v173 + 4624) + 1656LL) )
      {
        Login = 40613;
        v289 = 40613;
        v566 = 169;
        goto LABEL_321;
      }
    }
    v293 = 1;
    if ( (*(_BYTE *)(qword_102ECFB00 + 48) & 0x40) != 0 )
    {
      user_log(17142, 14, 0, 0x42F6u);
      v566 = 13;
      Login = 40613;
      if ( !v297 )
        Login = 18456;
      v289 = Login;
      goto LABEL_321;
    }
    if ( (*(_BYTE *)(v7.QuadPart + 402) & 0xFu) >= 2 )
    {
      v566 = 14;
      goto LABEL_331;
    }
    v402 = GetMasterDbId();
    v458 = ((__int64 (*)(void))g_dbtableFactory[4])();
    *(_DWORD *)(v7.QuadPart + 224) = *(_DWORD *)(v458 + 544);
    v403 = Base_PublicGlobals::sm_invariantTscAvailable;
    if ( Base_PublicGlobals::sm_invariantTscAvailable )
    {
      QueryPerformanceCounter(&PerformanceCount);
      QuadPart = (CSbTransportMgr *)PerformanceCount.QuadPart;
      v408 = (CSbTransportMgr *)PerformanceCount.QuadPart;
    }
    else
    {
      v407 = MEMORY[0x7FFE0008];
      QuadPart = MEMORY[0x7FFE0008];
      v408 = MEMORY[0x7FFE0008];
      v331 = v355;
      v46 = v317;
      v296 = v317;
    }
    CNetConnection::GetLock(*(CNetConnection **)(v8 + 16));
    *(_QWORD *)(v8 + 240) = QuadPart;
    *(_DWORD *)(v8 + 256) = 1;
    v459 = *(_QWORD *)(v8 + 16);
    v51 = *(_QWORD **)(v459 + 392);
    v460 = v51;
    v52 = SOS_PublicGlobals::sm_SpinlockStatSnapshot;
    v320 = SOS_PublicGlobals::sm_SpinlockStatSnapshot;
    if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
    {
      v174 = rand();
      v50 = (unsigned int)(v174 / 5);
      v52 = (unsigned int)(5 * v50);
      if ( v174 == (_DWORD)v52 )
        Spinlock<114,16,258>::UpdateStatSnapshot();
    }
    *v51 = 0;
    v53 = *(unsigned __int8 *)(GetXdbServerGlobals(v52, v50) + 12004);
    v321 = v53;
    if ( !(_BYTE)v53 )
      goto LABEL_62;
    v175 = *(_QWORD *)(v7.QuadPart + 192);
    if ( v175 )
    {
      v176 = 2 * *(unsigned __int16 *)(v175 + 70);
      v359 = v176;
      v177 = (const wchar_t *)(v175 + *(unsigned __int16 *)(v175 + 68));
    }
    else
    {
      v177 = 0;
      v176 = v359;
    }
    v409 = v177;
    if ( (*(_BYTE *)(v7.QuadPart + 270) & 4) != 0 )
    {
      v178 = (CDefaultCollation *)CDefaultCollation::PDCServer(v53);
      if ( CDefaultCollation::FEqIgnoreCaseW(v178, L"DwGen3TempDB", 0x18u, v177, v176)
        || FisFidoSysDbName(v177, (unsigned __int64)v176 >> 1) )
      {
        v566 = 179;
        goto LABEL_331;
      }
    }
    if ( FIsDwFidoDatabaseType(v177, v176) )
    {
      v366 = 3558;
      v54 = v303;
      v179 = operator new(8u, v303, "sql\\ntdbms\\msql\\ods\\login.cpp", 3558, 3u);
      v461 = v179;
      if ( v179 )
        *v179 = 0;
      else
        v179 = 0;
      v410 = v179;
      CAutoP<AutoReadOnlyXact>::operator=(&v332, v179);
      v180 = v332;
      AutoReadOnlyXact::BeginCompatibleXact(v332, L"login", 12, 0);
      if ( *(_QWORD *)v180 )
        v181 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v180 + 72LL))(*(_QWORD *)v180);
      else
        v181 = 0;
      v565 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v181 + 296LL))(v181);
      StartDwFidoScanTran(&v565, 0, 0);
    }
    else
    {
LABEL_62:
      v54 = v303;
    }
    if ( v337 )
    {
      LoadSecContextFromImpliedLoginInfo((struct CSession *)v7.QuadPart, v295, v330);
      Login = v289;
    }
    else
    {
      if ( !v297 )
      {
        *(_QWORD *)&v575[1] = 0;
        v577 = *(_BYTE *)(v7.QuadPart + 403) & 1;
        LOBYTE(v287) = *(_DWORD *)(v8 + 988) <= 1u;
        LODWORD(v286) = 0;
        Login = FindLogin(
                  (int)v295,
                  (int)v331,
                  v46,
                  (int)&v574,
                  (enum ELoginFailedState *)&v566,
                  (__int64)&v577,
                  0,
                  (__int64)v660,
                  (__int64)v575,
                  (__int64)v661,
                  (__int64)&v578,
                  v286,
                  0,
                  0,
                  v287,
                  (__int64)&v575[1],
                  (__int64)&v576,
                  (__int64)v580);
        v289 = Login;
        if ( !Login && (v56 = *(unsigned __int8 *)(GetXdbServerGlobals(v56, v55) + 12005), (v322 = v56) != 0) )
        {
          v58 = v576;
          if ( v576 )
          {
            v182 = *(void **)&v575[1];
            v462 = *(_QWORD *)&v575[1];
            if ( *(_QWORD *)&v575[1] )
            {
              v463 = *(void **)(*(_QWORD *)&v575[1] + 16LL);
              operator delete[](v463);
              operator delete(v182, Login + 24);
            }
            v71 = v300;
            goto LABEL_107;
          }
        }
        else
        {
          v58 = v576;
        }
        if ( byte_102EDCC61 || (*((_BYTE *)qword_102ECFB10 + 1559) & 8) != 0 )
        {
          v464 = v58;
          if ( !*(_DWORD *)(qword_102ECFB00 + 14504) )
          {
            GetMasterDbId();
            AuthenticateAgainstExtGovMD((_DWORD)v54, v59, (unsigned int)&v575[1], v58, (__int64)&v289, (__int64)&v566);
            Login = v289;
          }
          if ( *(_DWORD *)(GetXdbServerGlobals(v56, v55) + 11976) )
          {
            v183 = GetReplicatedMasterDbId();
            ManagedInstanceAuthenticateAgainstExtGovMD(v54, v183, &v575[1], v58, &v289, &v566);
            Login = v289;
          }
        }
        if ( byte_102F1BB90 || (*((_BYTE *)qword_102ECFB10 + 1743) & 0x40) != 0 )
        {
          ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
          v466 = (__int64 *)(ThreadLocalStoragePointer[SystemThread_TlsIndex] + SystemThread_TlsOffset);
          v467 = *v466;
          v468 = *(_QWORD *)(*(_QWORD *)(v467 + 120) + 264LL);
          v184 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v468 + 232LL))(v56, 1);
          v185 = v184;
          v469 = v184;
          if ( v184
            && (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v184 + 8LL))(v184) == 4
            && (v186 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v185 + 32LL))(v185, 1),
                v187 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v185 + 24LL))(v185, 1),
                v189 = (CDefaultCollation *)CDefaultCollation::PDCServer(v188),
                CDefaultCollation::FEqIgnoreCaseW(v189, v187, v186, L"##MS_BluemoonCertificate##", 0x34u)) )
          {
            *(_BYTE *)(v7.QuadPart + 270) |= 4u;
            v190 = *(_BYTE *)(v7.QuadPart + 270);
            *(_BYTE *)(v7.QuadPart + 271) |= 1u;
            *(_BYTE *)(v7.QuadPart + 270) = v190 | 8;
            v331 = v355;
            v296 = v317;
          }
          else
          {
            v331 = v355;
            v296 = v317;
          }
          Login = v289;
        }
        if ( *((_BYTE *)qword_102EF3550 + 655) )
        {
          v191 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
          v470 = v191;
          if ( *(_DWORD *)(qword_102ECFB00 + 14504) )
          {
            if ( *(_DWORD *)(v8 + 988) <= 1u && *(_DWORD *)(*(_QWORD *)(v191 + 520) + 20LL) )
            {
              v193 = *(const wchar_t **)(v7.QuadPart + 960);
              if ( v193 )
              {
                v194 = *(_DWORD *)(v7.QuadPart + 968);
              }
              else
              {
                v199 = *(_QWORD *)(v7.QuadPart + 192);
                v194 = 2 * *(unsigned __int16 *)(v199 + 50);
                v193 = (const wchar_t *)(v199 + *(unsigned __int16 *)(v199 + 48));
              }
              v412 = v193;
              v349 = v194;
              v195 = *(const wchar_t **)(GetXdbServerGlobals(qword_102ECFB00, v192) + 28360);
              v471 = v195;
              v196 = -1;
              do
                ++v196;
              while ( v195[v196] );
              v197 = 2 * v196;
              v472 = v197;
              if ( v194 == (_DWORD)v197 )
              {
                v367 = CompareStringWEnglishNoCase(
                         1u,
                         0,
                         v193,
                         (unsigned __int64)v194 >> 1,
                         v195,
                         (unsigned __int64)(int)v197 >> 1);
                if ( v367 == 2 )
                {
                  v198 = *(_BYTE *)(v7.QuadPart + 270);
                  if ( (v198 & 4) == 0 )
                  {
                    *(_BYTE *)(v7.QuadPart + 270) = v198 | 4;
                    *(_BYTE *)(v7.QuadPart + 271) |= 1u;
                  }
                }
              }
            }
          }
        }
        v323 = byte_102EDCDF0;
        v60 = *(_BYTE *)(v7.QuadPart + 270);
        v61 = v60 & 2;
        v292 = v60 & 2;
        if ( byte_102EDCDF0 && (v60 & 0x40) != 0 && !v61 && !Login )
        {
          v443 = *(struct _GUID *)((char *)v295 + 28);
          Login = AuthenticateLoginOnPolarisFrontend(
                    (struct CSession *)v7.QuadPart,
                    &v443,
                    v331,
                    v296,
                    v658,
                    (enum ELoginFailedState *)&v566);
          v289 = Login;
        }
        v62 = 0;
        v350 = 0;
        v63 = *(_QWORD *)(v7.QuadPart + 192);
        if ( v63 )
        {
          v62 = 2 * *(unsigned __int16 *)(v63 + 70);
          v350 = v62;
          v64 = (const wchar_t *)(v63 + *(unsigned __int16 *)(v63 + 68));
          v413 = v64;
        }
        else
        {
          v64 = 0;
          v413 = 0;
        }
        if ( (unsigned int)IsVDWFrontendInstance()
          && (*((_BYTE *)qword_102EF3550 + 1196) || IsSynapseSALEnabled())
          && !v61
          && !Login )
        {
          v200 = dword_102F1BBA4;
          v368 = dword_102F1BBA4;
          v473 = L"msdb";
          v201 = (CDefaultCollation *)CDefaultCollation::PDCServer(v65);
          if ( CDefaultCollation::FEqIgnoreCaseW(v201, v64, v62, L"msdb", v200) && byte_102EDCE0D
            || (v203 = dword_102F1BB9C,
                v369 = dword_102F1BB9C,
                v474 = L"tempdb",
                v204 = (CDefaultCollation *)CDefaultCollation::PDCServer(v202),
                CDefaultCollation::FEqIgnoreCaseW(v204, v64, v62, L"tempdb", v203))
            && byte_102EDCE0E )
          {
            Login = 18456;
            v289 = 18456;
            v566 = 193;
            v205 = *(void **)&v575[1];
            v475 = *(_QWORD *)&v575[1];
            if ( !*(_QWORD *)&v575[1] )
              goto LABEL_321;
            v206 = *(void **)(*(_QWORD *)&v575[1] + 16LL);
            v476 = v206;
LABEL_393:
            operator delete[](v206);
            operator delete(v205, 0x18u);
            goto LABEL_321;
          }
          v61 = v292;
        }
        if ( IsTridentSqlFrontendSession()
          && (byte_102EDCC88 || (*((_BYTE *)qword_102ECFB10 + 1519) & 0x40) != 0)
          && !v61 )
        {
          if ( !Login )
          {
            if ( byte_102EDCEFD )
            {
              v207 = dword_102F1BBA4;
              v370 = dword_102F1BBA4;
              v477 = L"msdb";
              v208 = (CDefaultCollation *)CDefaultCollation::PDCServer(v66);
              if ( CDefaultCollation::FEqIgnoreCaseW(v208, v64, v62, L"msdb", v207)
                || (v210 = dword_102F1BBA0,
                    v371 = dword_102F1BBA0,
                    v478 = L"model",
                    v211 = (CDefaultCollation *)CDefaultCollation::PDCServer(v209),
                    CDefaultCollation::FEqIgnoreCaseW(v211, v64, v62, L"model", v210)) )
              {
                Login = 18456;
                v289 = 18456;
                v566 = 193;
                v205 = *(void **)&v575[1];
                v479 = *(_QWORD *)&v575[1];
                if ( !*(_QWORD *)&v575[1] )
                  goto LABEL_321;
                v206 = *(void **)(*(_QWORD *)&v575[1] + 16LL);
                v480 = v206;
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
            v214 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v7.QuadPart + 96) + 16LL))(*(_QWORD *)(v7.QuadPart + 96));
            v481 = v214;
            if ( *(_DWORD *)(v214 + 1088) )
            {
              v215 = (const wchar_t *)GetXdbServerGlobals(v213, v212);
              v482 = v215;
              v216 = -1;
              do
                ++v216;
              while ( v215[v216] );
              v483 = 2 * v216;
              v582 = 0;
              v583 = 0;
              v584 = 0;
              v585 = 0;
              v586 = 0;
              v592 = 0;
              v600 = 0;
              v601 = 0;
              v602 = 0;
              v606 = 0;
              v607 = 0;
              v608 = 0;
              v609 = 0;
              v610 = 0;
              v611 = 0;
              v587 = 0;
              v588 = 0;
              v589 = 0;
              v590 = 0;
              v591 = 0;
              v593 = 0;
              v594 = 0;
              v595 = 0;
              v596 = 0;
              v597 = 0;
              v598 = 0;
              v599 = 0;
              v603 = 0;
              v604 = 0;
              v605 = 0;
              v217 = v295;
              v444 = *(struct _GUID *)((char *)v295 + 28);
              v218 = CCloudExtensions::PrivateEndpointsAccessLockdownCheck(
                       v215,
                       (unsigned __int16)(2 * v216),
                       &szPassword,
                       0,
                       (const wchar_t *)(v214 + 776),
                       *(_DWORD *)(v214 + 972),
                       &v444,
                       0,
                       (struct VnetPeerAddressInfo *)&v582,
                       (enum ELoginFailedState *)&v566);
              v372 = v218;
              if ( v218 )
              {
                Login = v218;
                v289 = v218;
              }
              else
              {
                *(_DWORD *)&v580[4] = v587;
                v219 = CNetConnection::SetEffectivePeerIPAddress((CNetConnection *)v214, &v580[4], 4u);
                v373 = v219;
                if ( v219 )
                {
                  v566 = 160;
                  v612 = *(struct _GUID *)((char *)v217 + 28);
                  XEventReportLoginSubstepFailureEvent(v219, 160, 0, 0, &v612, &szPassword, 0, &szPassword, 0);
                  Login = 40613;
                  v289 = 40613;
                }
              }
              v582 = 0;
              v583 = 0;
              v584 = 0;
              v585 = 0;
              v592 = 0;
              v600 = 0;
              v601 = 0;
              v606 = 0;
              v607 = 0;
              v587 = 0;
              v588 = 0;
              v589 = 0;
              v590 = 0;
              v591 = 0;
              v593 = 0;
              v594 = 0;
              v595 = 0;
              v596 = 0;
              v597 = 0;
              v598 = 0;
              v599 = 0;
              LODWORD(v602) = 0;
              v603 = 0;
              v604 = 0;
              v605 = 0;
            }
          }
        }
        v67 = *(void **)&v575[1];
        v449 = *(_QWORD *)&v575[1];
        if ( *(_QWORD *)&v575[1] )
        {
          v484 = *(void **)(*(_QWORD *)&v575[1] + 16LL);
          operator delete[](v484);
          operator delete(v67, 0x18u);
        }
        v8 = v333;
        goto LABEL_86;
      }
      Login = FindLoginXdb(
                v54,
                v295,
                (struct CSession *)v7.QuadPart,
                v331,
                v46,
                0,
                0,
                &v564,
                (enum ELoginFailedState *)&v566);
      v289 = Login;
      *(_DWORD *)(v7.QuadPart + 5076) = v564;
    }
LABEL_86:
    v374 = Base_PublicGlobals::sm_invariantTscAvailable;
    if ( Base_PublicGlobals::sm_invariantTscAvailable )
    {
      QueryPerformanceCounter(&v414);
      v68 = (CSbTransportMgr *)v414.QuadPart;
      v416 = (CSbTransportMgr *)v414.QuadPart;
    }
    else
    {
      v68 = MEMORY[0x7FFE0008];
      v415 = MEMORY[0x7FFE0008];
      v416 = MEMORY[0x7FFE0008];
      Login = v289;
    }
    v417 = v68;
    CNetConnection::GetLock(*(CNetConnection **)(v8 + 16));
    v69 = (_QWORD *)(v8 + 240);
    v485 = v8 + 240;
    if ( *(_DWORD *)(v8 + 256) )
    {
      if ( (unsigned __int64)v417 > *v69 )
      {
        v330 = (CSbTransportMgr *)((char *)v417 - *v69);
        v486 = v330;
        v487 = v8 + 248;
        *(_QWORD *)(v8 + 248) += v330;
      }
      *(_DWORD *)(v8 + 256) = 0;
    }
    v488 = *(_QWORD *)(v8 + 16);
    v70 = *(_QWORD **)(v488 + 392);
    v489 = v70;
    v324 = SOS_PublicGlobals::sm_SpinlockStatSnapshot;
    if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
    {
      v220 = rand();
      if ( v220 == 5 * (v220 / 5) )
        Spinlock<114,16,258>::UpdateStatSnapshot();
    }
    *v70 = 0;
    if ( byte_102EDCEE7 && Login != 40613 && Login != 40969 && v566 != 165 )
    {
      v445 = *(struct _GUID *)((char *)v295 + 28);
      CheckIfTdAuditSessionExists((struct CSession *)v7.QuadPart, &v564, &v445);
    }
    if ( Login )
      goto LABEL_321;
    v71 = v300;
    if ( v300 )
    {
      *(_BYTE *)(v7.QuadPart + 270) |= 4u;
      *(_BYTE *)(v7.QuadPart + 271) |= 1u;
      v221 = *(_BYTE *)(v7.QuadPart + 271) & 0xF7 | (*((_BYTE *)qword_102EF3550 + 453) != 0 ? 8 : 0);
      *(_BYTE *)(v7.QuadPart + 271) = v221;
      v297 = 1;
      *(_BYTE *)(v7.QuadPart + 271) = v221 | 4;
      if ( !FPDWFeaturesExposed() )
      {
        Login = RebuildSdsLoginToken((struct CSession *)v7.QuadPart, &v564, (enum ELoginFailedState *)&v566);
        v289 = Login;
        if ( Login )
          goto LABEL_321;
      }
    }
    v490 = NtCurrentTeb()->ThreadLocalStoragePointer;
    v491 = (struct ImpliedLoginInfo **)(v490[SystemThread_TlsIndex] + SystemThread_TlsOffset);
    v492 = *v491;
    v330 = v492;
    ContextAccessor::UpdateSecurityInfo(*(_QWORD *)(*(_QWORD *)(v7.QuadPart + 104) + 264LL));
    v72 = *(_DWORD *)(qword_102ECFB00 + 48);
    if ( (v72 & 1) != 0 || (v72 & 0x2000) != 0 )
    {
      Login = 18401;
      if ( (*(_DWORD *)(qword_102ECFB00 + 48) & 1) != 0 )
        Login = 18461;
      v341 = Login;
      if ( !(***(unsigned int (__fastcall ****)(_QWORD))(*(_QWORD *)(v7.QuadPart + 104) + 264LL))(*(_QWORD *)(*(_QWORD *)(v7.QuadPart + 104) + 264LL)) )
      {
        v289 = Login;
        goto LABEL_427;
      }
      if ( (*(_DWORD *)(qword_102ECFB00 + 48) & 0x2000) != 0 && (*(_BYTE *)(v7.QuadPart + 269) & 0x20) == 0 )
      {
        v289 = Login;
        goto LABEL_427;
      }
      v78 = *(_QWORD *)(v7.QuadPart + 960);
      if ( v78 )
      {
        v79 = *(unsigned int *)(v7.QuadPart + 968);
      }
      else
      {
        v222 = *(_QWORD *)(v7.QuadPart + 192);
        v79 = 2 * (unsigned int)*(unsigned __int16 *)(v222 + 50);
        v78 = v222 + *(unsigned __int16 *)(v222 + 48);
      }
      v418 = v78;
      v343 = v79;
      if ( dword_103095910
        && (dword_103095910 != (_DWORD)v79 || memcmp_0(qword_103095810, (const void *)v78, (unsigned int)v79)) )
      {
        v289 = Login;
        goto LABEL_427;
      }
      v78 = (unsigned int)*(__int16 *)(v7.QuadPart + 16);
      v375 = v78;
      v79 = qword_102ECFB00;
      if ( _InterlockedCompareExchange((volatile signed __int32 *)(qword_102ECFB00 + 11748), v78, 0) )
      {
        Login = v341;
        v289 = v341;
        goto LABEL_427;
      }
    }
    if ( (*(_BYTE *)(v7.QuadPart + 269) & 0x20) != 0 )
    {
      v223 = **(_QWORD **)(*(_QWORD *)(v7.QuadPart + 104) + 264LL);
      if ( !(v297 ? (*(__int64 (**)(void))(v223 + 72))() : (*(unsigned int (**)(void))v223)()) )
        goto LABEL_444;
    }
    if ( (*(_BYTE *)(qword_102ECFB00 + 48) & 0x20) != 0 )
    {
      v225 = GetMasterDbId();
      LOBYTE(v288) = 0;
      LOBYTE(v283) = 1;
      if ( !(unsigned __int8)ISECManager::AccessCheck(
                               0,
                               v225,
                               0,
                               24,
                               1,
                               v283,
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
                               v288,
                               0,
                               0,
                               0,
                               0,
                               0) )
      {
        ex_callprint(6005, 14, 1);
        Login = 18451;
        v289 = 18451;
        goto LABEL_321;
      }
    }
    if ( (*((_BYTE *)qword_102ECFB10 + 450) & 0x40) != 0 )
    {
      v226 = GetMasterDbId();
      LOBYTE(v285) = 0;
      LOBYTE(v284) = 1;
      if ( !(unsigned __int8)ISECManager::CheckPermRule(1413567059, 0, 0, v226, 0, 0, -1, 0, v284, v285, 0, 0) )
      {
LABEL_444:
        Login = 18451;
        v289 = 18451;
        goto LABEL_321;
      }
    }
    v73 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)(v7.QuadPart + 104) + 264LL) + 128LL))(*(_QWORD *)(*(_QWORD *)(v7.QuadPart + 104) + 264LL));
    v377 = v73;
    if ( v298 )
    {
      v74 = v571 == v73;
    }
    else
    {
      if ( v73 )
        goto LABEL_614;
      v74 = v571 == 0;
    }
    if ( v74 )
    {
      if ( (*(_BYTE *)(v7.QuadPart + 270) & 4) == 0 )
      {
        v75 = *(_QWORD *)(*(_QWORD *)(v7.QuadPart + 104) + 264LL);
        v493 = NtCurrentTeb()->ThreadLocalStoragePointer;
        v494 = (struct ImpliedLoginInfo **)(v493[SystemThread_TlsIndex] + SystemThread_TlsOffset);
        v495 = *v494;
        v330 = v495;
        LOWORD(v290) = *(_WORD *)(*((_QWORD *)v495 + 10) + 8LL);
        if ( !(*(unsigned int (__fastcall **)(__int64, _QWORD, __int64, _QWORD))(*(_QWORD *)v75 + 288LL))(
                v75,
                (unsigned __int16)v290,
                1,
                0) )
        {
          v566 = 15;
          goto LABEL_331;
        }
      }
LABEL_107:
      IssueLoginSuccessReport((struct CSession *)v7.QuadPart, v295);
      if ( (*(_DWORD *)(v7.QuadPart + 400) & 0x4000000) != 0 )
      {
        if ( *((_DWORD *)s_pServerConf + 2) != 3 )
        {
          Login = 18493;
          v289 = 18493;
          goto LABEL_321;
        }
        v227 = (const struct CSession *)*(unsigned int *)(qword_102ECFB00 + 14548);
        v378 = (int)v227;
        if ( (_DWORD)v227 )
        {
          Login = 18494;
          v289 = 18494;
          goto LABEL_321;
        }
        if ( *(_WORD *)(*(_QWORD *)(v7.QuadPart + 192) + 84LL) )
        {
          Login = 18495;
          v289 = 18495;
          goto LABEL_321;
        }
        v289 = 0;
        Login = LSpawnUserInstance(v227, v338);
        v289 = Login;
        if ( Login )
          goto LABEL_321;
      }
      v379 = *(_DWORD *)(GetXdbServerGlobals(v77, v76) + 8308);
      if ( !v379 && *(_WORD *)(*(_QWORD *)(v7.QuadPart + 192) + 84LL) && !(unsigned int)FAttachDb(v660, v575, 0) )
      {
        v228 = 0;
        v354 = 0;
        v229 = *(_QWORD *)(v7.QuadPart + 192);
        if ( v229 )
        {
          v228 = 2 * *(unsigned __int16 *)(v229 + 70);
          v354 = v228;
        }
        Login = 1832;
        v79 = 15350;
        if ( !v228 )
          Login = 15350;
        v289 = Login;
        goto LABEL_427;
      }
      if ( !LoginUseDbHelper::FDetermineSessionDb(
              (LoginUseDbHelper *)&si128,
              v660,
              v575[0],
              0,
              0,
              (enum ELoginFailedState *)&v566,
              v336,
              v564) )
      {
        Login = si128.m128i_i32[0];
        if ( !HIDWORD(v617) )
          goto LABEL_651;
        v230 = si128.m128i_i32[0];
        if ( v615 != 1 )
          v230 = si128.m128i_u16[0];
        if ( v230 )
        {
LABEL_651:
          if ( LoginUseDbHelper::IsHaDrError((LoginUseDbHelper *)&si128) )
          {
            if ( v241 == 1 )
            {
              v298 = Login;
            }
            else
            {
              Login = (unsigned __int16)Login;
              v298 = (unsigned __int16)Login;
            }
          }
          else
          {
            Login = 18456;
            v298 = 18456;
          }
        }
        else
        {
          Login = 0;
          v298 = 0;
        }
        v289 = Login;
        if ( (*(_BYTE *)(v7.QuadPart + 270) & 4) != 0 )
        {
          v301 = (struct CUEnvTransient *)0x8000000001LL;
          if ( (qword_102F21DB4 & 0x80u) != 0LL )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
            XeCloudPkg::login_substep_failure::login_substep_failure((XeCloudPkg::login_substep_failure *)v643);
            v232 = si128.m128i_i32[0];
            if ( v615 != 1 )
              v232 = si128.m128i_u16[0];
            v645 = v232;
            v646 = si128.m128i_i32[3];
            v647 = 0;
            v648 = 0;
            v446 = *(_OWORD *)((char *)v295 + 28);
            v233 = v644 + 2;
            v496 = v644 + 2;
            v644[2] = &v446;
            *((_DWORD *)v233 + 2) = 16;
            *((_WORD *)v233 + 6) = 4;
            *((_WORD *)v233 + 7) = 0;
            v234 = v644 + 4;
            v497 = v644 + 4;
            v644[4] = L"useDbhelper.FDetermineSessionDb failed";
            *((_DWORD *)v234 + 2) = 76;
            *((_WORD *)v234 + 6) = 5;
            *((_WORD *)v234 + 7) = 0;
            v235 = GetXdbServerGlobals(5, v231);
            v238 = -1;
            do
              ++v238;
            while ( *(_WORD *)(v235 + 2 * v238) );
            v498 = GetXdbServerGlobals(v237, v236);
            v239 = v644 + 6;
            v499 = v644 + 6;
            v644[6] = v498;
            *((_DWORD *)v239 + 2) = 2 * v238;
            *((_WORD *)v239 + 6) = 6;
            *((_WORD *)v239 + 7) = 0;
            LODWORD(v239) = (unsigned int)v617 >> 1;
            v240 = v644 + 8;
            v500 = v644 + 8;
            v644[8] = &v616;
            *((_DWORD *)v240 + 2) = 2 * (_DWORD)v239;
            *((_WORD *)v240 + 6) = 7;
            *((_WORD *)v240 + 7) = 0;
            XeCloudPkg::login_substep_failure::Publish((XeCloudPkg::login_substep_failure *)v643);
          }
        }
        if ( Login )
        {
          if ( v297 )
          {
            if ( LoginUseDbHelper::IsHaDrError((LoginUseDbHelper *)&si128) )
            {
              v566 = 125;
              Login = 40613;
              v289 = 40613;
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
              if ( v576 && !Login )
              {
                if ( *(_DWORD *)(qword_102ECFB00 + 14504)
                  && (*(_BYTE *)(GetXdbServerGlobals(v79, v78) + 12009)
                   || *(_BYTE *)(GetXdbServerGlobals(v79, v78) + 12008))
                  && (v79 = *(unsigned __int8 *)(GetXdbServerGlobals(v79, v78) + 12004), (v313 = v79) == 0)
                  && byte_102EDCA63
                  || (v314 = *(_BYTE *)(GetXdbServerGlobals(v79, v78) + 12004)) != 0 && byte_102EDCA62 )
                {
                  LODWORD(v302) = 0;
                  v556 = NtCurrentTeb()->ThreadLocalStoragePointer;
                  v557 = (__int64 *)(v556[SystemThread_TlsIndex] + SystemThread_TlsOffset);
                  v558 = *v557;
                  v559 = *(CSession **)(v558 + 72);
                  CSession::GetSesLoginNameSidDbIdThreadSafe(
                    v559,
                    v663,
                    0x100u,
                    (unsigned int *)&v295,
                    v659,
                    0x55u,
                    (unsigned int *)&v302,
                    0);
                  UpdateFederatedAADPrincipalUsernameIfRequired(
                    (unsigned int)v659,
                    (_DWORD)v302,
                    (unsigned int)v663,
                    (_DWORD)v295,
                    (__int64)v303);
                }
              }
              if ( v332 )
              {
                if ( v294 < 0 )
                {
                  if ( *(_QWORD *)v332 )
                    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v332 + 32LL))(*(_QWORD *)v332);
                }
                else
                {
                  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v332 + 24LL))(*(_QWORD *)v332);
                }
              }
              v560 = v332;
              if ( v332 )
              {
                v276 = *(void (__fastcall ****)(_QWORD, __int64))v332;
                v561 = v276;
                if ( v276 )
                  (**v276)(v276, 1);
                operator delete(v332, 8u);
              }
              AutoInstallMsqlXact::~AutoInstallMsqlXact((AutoInstallMsqlXact *)v441);
              operator delete[]((void *)v576);
              ExcHandler::~ExcHandler((ExcHandler *)v618);
              v109 = v358;
              v110 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                   + SystemThread_TlsOffset;
              v111 = *(struct Worker **)(v110 + 256);
              if ( !v111 )
              {
                SystemThread::MakeMiniSOSThread(0);
                v111 = *(struct Worker **)(v110 + 256);
              }
              if ( *((_DWORD *)v111 + 139) )
                ExceptionPostCatchActions(v111);
              v653 = 0;
              if ( v294 < 0 && (*(_BYTE *)(qword_102ECFB00 + 48) & 1) != 0 )
                _InterlockedCompareExchange(
                  (volatile signed __int32 *)(qword_102ECFB00 + 11748),
                  0,
                  *(__int16 *)(v7.QuadPart + 16));
              if ( *(_WORD *)(*(_QWORD *)(*(_QWORD *)(SystemThread_TlsOffset
                                                    + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                      + SystemThread_TlsIndex))
                                        + 80LL)
                            + 8LL) )
                ((void (__fastcall *)(_QWORD, __int64))g_dbtableFactory[6])(
                  *(unsigned __int16 *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                + SystemThread_TlsIndex)
                                                              + SystemThread_TlsOffset)
                                                  + 80LL)
                                      + 8LL),
                  14);
              if ( (WORD2(qword_102EDC9FC) & 0x400) != 0 )
              {
                v621 = 0x10000;
                v622 = 0;
                v623 = v626;
                v624 = &v627;
                v628 = 0;
                v625 = 0;
                v629 = 0;
                v626[0] = &v630;
                v626[1] = 9;
                if ( v335
                  && ((QueryPerformanceCounter(&v351), v351.QuadPart >= (unsigned __int64)v581.QuadPart)
                    ? (v277 = v351.QuadPart - v581.QuadPart)
                    : (v277 = 0),
                      Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart) )
                {
                  if ( v277 == -1 )
                    v278 = -1;
                  else
                    v278 = (unsigned __int64)(1000000 * v277)
                         / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
                }
                else
                {
                  v278 = 0;
                }
                v630 = v278;
                v631 = v574 == 0;
                XeSqlPkg::security_authentication_perf_login::Publish((XeSqlPkg::security_authentication_perf_login *)v620);
              }
              v112 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                   + SystemThread_TlsOffset;
              v113 = *(_QWORD *)(v112 + 256);
              if ( !v113 )
              {
                SystemThread::MakeMiniSOSThread(0);
                v113 = *(_QWORD *)(v112 + 256);
              }
              *(_QWORD *)(v113 + 3208) = v109;
              v649 = &CAutoSetXLvlIntCtxtImplNoException::`vftable';
              if ( v650 )
              {
                v650 = 0;
                v114 = (__int64 *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                 + SystemThread_TlsOffset);
                v115 = *v114;
                CExecLvlIntCtxt::ExitBatch(*(CExecLvlIntCtxt **)(*v114 + 128));
                *(_QWORD *)(v115 + 128) = 0;
              }
              CExecLvlIntCtxt::~CExecLvlIntCtxt((CExecLvlIntCtxt *)v651);
              v649 = &XactAccessor::`vftable';
              if ( v363 )
              {
                SEParams::UninstallFromTLS(v363);
                v363 = 0;
              }
              SEParams::~SEParams((SEParams *)v619);
              if ( (v305 & 1) != 0 )
              {
                v116 = v304;
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v304 + 32LL))(v304);
                if ( _InterlockedExchangeAdd(v116 + 35, 0xFFFFFFFF) == 1 )
                {
                  v279 = *((_QWORD *)v304 + 1);
                  (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)v304 + 40LL))(v304, 1);
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v279 + 16LL))(v279);
                }
                v304 = 0;
                v305 &= ~1u;
              }
              CAutoSetupCXCtxtSingleThread::~CAutoSetupCXCtxtSingleThread((CAutoSetupCXCtxtSingleThread *)v652);
              v117 = v360;
              if ( (_QWORD)v360 )
              {
                v280 = *(CConnection **)(v360 + 480);
                if ( v280 )
                  CConnection::Release(v280);
                *(_QWORD *)(v117 + 480) = 0;
              }
              v118 = *((_QWORD *)&v360 + 1);
              if ( *((_QWORD *)&v360 + 1) )
              {
                *(_QWORD *)(*((_QWORD *)&v360 + 1) + 8LL) = 0;
                v281 = *(ExecutionContext **)(v118 + 48);
                if ( v281 )
                {
                  ExecutionContext::CleanupAndDelete(v281, 1);
                  *(_QWORD *)(v118 + 48) = 0;
                }
                *(_QWORD *)(v118 + 40) = 0;
              }
              ITaskProxy::SetCurrentTaskProxy(0);
              return (unsigned int)v294;
            }
LABEL_321:
            if ( byte_102EDCADA )
            {
              v448 = *(_OWORD *)((char *)v295 + 28);
              AuditLoginXdb(&v564, Login, v566, &v448);
            }
            v170 = (unsigned int)CConnection::PNetConn(v302);
            LoginError(Login, (_DWORD)v295, v170, v566, (__int64)&si128);
            v294 = Login | 0x80000000;
            goto LABEL_171;
          }
        }
        else if ( byte_102EDCB21
               && (*(_BYTE *)(v7.QuadPart + 270) & 4) != 0
               && LoginUseDbHelper::IsHaDrError((LoginUseDbHelper *)&si128) )
        {
          v566 = 125;
          Login = 40613;
          v289 = 40613;
          goto LABEL_321;
        }
        goto LABEL_331;
      }
      v80 = v564;
      if ( byte_102EDCB3B )
      {
        if ( !v564 )
          goto LABEL_113;
        v242 = *(_QWORD *)(qword_102ECFB00 + 32);
        v501 = v242;
        switch ( v564 )
        {
          case 0x7FFCu:
            v243 = *(_QWORD *)(v242 + 104);
            break;
          case 0x7FFDu:
            v243 = *(_QWORD *)(v242 + 112);
            break;
          case 0x7FFFu:
            v243 = *(_QWORD *)(v242 + 88);
            break;
          default:
            if ( v564 > *(_DWORD *)(v242 + 76) )
              goto LABEL_498;
            v243 = *(_QWORD *)(*(_QWORD *)(v242 + 40) + 8LL * (int)(v564 - 1));
            break;
        }
        v356 = v243;
        if ( !v243 )
          goto LABEL_498;
        v325 = *(_BYTE *)(v243 + 628);
        if ( v325 && (*(_BYTE *)(v7.QuadPart + 270) & 4) != 0 )
        {
          if ( !*(_DWORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8) + 1028) && !v71 )
          {
            Login = 40852;
            v289 = 40852;
            v566 = 131;
            goto LABEL_321;
          }
          v80 = v564;
        }
      }
      if ( !v80 )
        goto LABEL_113;
      v244 = *(_QWORD *)(qword_102ECFB00 + 32);
      v502 = v244;
      switch ( v80 )
      {
        case 0x7FFCu:
          v245 = *(_QWORD *)(v244 + 104);
          goto LABEL_513;
        case 0x7FFDu:
          v245 = *(_QWORD *)(v244 + 112);
          goto LABEL_513;
        case 0x7FFFu:
          v245 = *(_QWORD *)(v244 + 88);
          goto LABEL_513;
      }
      if ( v80 <= *(_DWORD *)(v244 + 76) )
      {
        v245 = *(_QWORD *)(*(_QWORD *)(v244 + 40) + 8LL * (int)(v80 - 1));
LABEL_513:
        v357 = v245;
        if ( !v245 )
        {
          v289 = 18456;
          v566 = 126;
          goto LABEL_332;
        }
        if ( *(_BYTE *)(v245 + 629) )
        {
          if ( (*(_BYTE *)(v7.QuadPart + 270) & 4) != 0 )
          {
            Login = 40613;
            v289 = 40613;
            v566 = 143;
            goto LABEL_321;
          }
        }
        else if ( (*(_BYTE *)(v7.QuadPart + 270) & 4) != 0 )
        {
          v246 = *(_QWORD *)(v245 + 4624);
          if ( v246 )
          {
            if ( *(_BYTE *)(v246 + 8273) )
            {
              v340 = (CDbAndSetOpts *)0x800000012LL;
              if ( (dword_102EDCA28 & 8) != 0 )
              {
                v633 = 0;
                v634 = 0;
                v635 = 0;
                v636 = 0;
                v637 = &v639;
                v640 = 0;
                v641 = 0;
                v638 = 0;
                v642 = 0;
                XeSqlPkg::login_request_to_page_server::Publish((XeSqlPkg::login_request_to_page_server *)v632);
              }
              Login = 40613;
              v289 = 40613;
              v566 = 168;
              goto LABEL_321;
            }
          }
        }
LABEL_113:
        if ( (unsigned int)FDetermineSessionLang(v661, v578, 0) )
        {
          v82 = *(_DWORD *)CDefaultCollation::PDCServer(v81);
          v380 = v82;
          if ( FUTF8Collation(v82) )
          {
            v84 = v338;
          }
          else
          {
            v342 = 0;
            v503 = (_DWORD *)CDefaultCollation::PDCServer(v83);
            LOWORD(v571) = (*v503 & 0x1000) == 0;
            v326 = CSIDFromCID(v82);
            v342 = getcssoname(v326, 1001, v662, 256);
            v84 = v338;
            LOWORD(v282) = v342;
            (*(void (__fastcall **)(struct CConnectionOutput *, int *, __int64, wchar_t *, int))(*(_QWORD *)v338 + 144LL))(
              v338,
              &v571,
              2,
              v662,
              v282);
          }
          v85 = 0;
          v353 = 0;
          v86 = 0;
          v352 = 0;
          v504 = (unsigned int *)CDefaultCollation::PDCServer(v83);
          v381 = LCIDFromCID(*v504);
          if ( !_ultow_s(v381, Buffer, 0x10u, 10) )
          {
            v85 = wcsnlen(Buffer, 0xFu);
            v353 = v85;
          }
          v505 = (int *)CDefaultCollation::PDCServer(v87);
          v382 = *v505;
          v88 = (v382 & 0x1000) != 0;
          v299 = v88;
          if ( (v382 & 0x2000) != 0 )
          {
            v88 |= 2u;
            v299 = v88;
          }
          if ( (v382 & 0x4000) != 0 )
          {
            v88 |= 0x10000u;
            v299 = v88;
          }
          if ( (v382 & 0x8000) != 0 )
          {
            v88 |= 0x20000u;
            v299 = v88;
          }
          if ( (v382 & 0x200) != 0 )
          {
            v88 |= 8u;
            v299 = v88;
          }
          if ( !_ultow_s(v88, Source, 0x10u, 10) )
          {
            v86 = wcsnlen(Source, 0xFu);
            v352 = v86;
          }
          (*(void (__fastcall **)(struct CConnectionOutput *, wchar_t *, _QWORD))(*(_QWORD *)v84 + 160LL))(
            v84,
            Buffer,
            (unsigned int)(2 * v85));
          (*(void (__fastcall **)(struct CConnectionOutput *, wchar_t *, _QWORD))(*(_QWORD *)v84 + 168LL))(
            v84,
            Source,
            (unsigned int)(2 * v86));
          if ( (*(_BYTE *)(v7.QuadPart + 403) & 1) == 0 )
          {
LABEL_129:
            CSession::RecordLogin((CSession *)v7.QuadPart);
            v507 = NtCurrentTeb()->ThreadLocalStoragePointer;
            v508 = v507[SystemThread_TlsIndex] + SystemThread_TlsOffset;
            v509 = *(CDiagnostics **)(v508 + 80);
            CDiagnostics::RecordLogin(v509);
            v89 = *(_DWORD *)(v7.QuadPart + 400);
            v510 = NtCurrentTeb()->ThreadLocalStoragePointer;
            v511 = (struct ImpliedLoginInfo **)(v510[SystemThread_TlsIndex] + SystemThread_TlsOffset);
            v512 = *v511;
            v330 = v512;
            v327 = *(_WORD *)(v7.QuadPart + 184) >= 6u;
            v90 = v327;
            v91 = (*(__int64 (__fastcall **)(struct IServerConfiguration *))(*(_QWORD *)s_pServerConf + 504LL))(s_pServerConf);
            CDbAndSetOpts::InitAllOptions(v340, (v89 & 0x100200) != 0, v90, v92, *(_WORD *)(v91 + 126) > 0);
            if ( byte_102EDCBBC && (*(_BYTE *)(v7.QuadPart + 270) & 4) != 0 )
            {
              v291 = 1;
              v93 = v301;
            }
            else
            {
              v291 = 0;
              v93 = v301;
              *((_WORD *)v93 + 136) = SECurDbLockRef::GetCookieForBaseDbAndCloseDb((struct CUEnvTransient *)((char *)v301 + 274));
            }
            *(_BYTE *)(v7.QuadPart + 266) = 0;
            v94 = v336;
            if ( v336 && *(_BYTE *)v336 )
              goto LABEL_160;
            v513 = NtCurrentTeb()->ThreadLocalStoragePointer;
            v514 = v513[SystemThread_TlsIndex] + SystemThread_TlsOffset;
            v515 = *(_QWORD *)(v514 + 80);
            *(_DWORD *)(v515 + 1000) |= 8u;
            v383 = Base_PublicGlobals::sm_invariantTscAvailable;
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&v420);
              v95 = (CSbTransportMgr *)v420.QuadPart;
            }
            else
            {
              v421 = MEMORY[0x7FFE0008];
              v95 = MEMORY[0x7FFE0008];
            }
            v422 = v95;
            CNetConnection::GetLock(*(CNetConnection **)(v8 + 16));
            v96 = (_QWORD *)(v8 + 648);
            *(_QWORD *)(v8 + 648) = v95;
            *(_DWORD *)(v8 + 664) = 1;
            v516 = *(_QWORD *)(v8 + 16);
            v97 = *(_QWORD **)(v516 + 392);
            v517 = v97;
            v328 = SOS_PublicGlobals::sm_SpinlockStatSnapshot;
            if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
            {
              v254 = rand();
              if ( v254 == 5 * (v254 / 5) )
                Spinlock<114,16,258>::UpdateStatSnapshot();
            }
            *v97 = 0;
            if ( !FExecuteLogonTriggers((struct CSession *)v7.QuadPart, v295, 0) )
            {
              v566 = 1;
              v289 = 17892;
              v518 = NtCurrentTeb()->ThreadLocalStoragePointer;
              v519 = v518[SystemThread_TlsIndex] + SystemThread_TlsOffset;
              v520 = *(_QWORD *)(v519 + 80);
              *(_DWORD *)(v520 + 1000) &= ~8u;
              LODWORD(v339) = Base_PublicGlobals::sm_invariantTscAvailable;
              if ( Base_PublicGlobals::sm_invariantTscAvailable )
              {
                QueryPerformanceCounter(&v423);
                v255 = (CSbTransportMgr *)v423.QuadPart;
              }
              else
              {
                v255 = MEMORY[0x7FFE0008];
                v424 = MEMORY[0x7FFE0008];
              }
              v425 = v255;
              v426 = v255;
              CNetConnection::GetLock(*(CNetConnection **)(v8 + 16));
              v521 = v8 + 648;
              if ( *(_DWORD *)(v8 + 664) )
              {
                if ( (unsigned __int64)v426 > *v96 )
                {
                  v301 = (CSbTransportMgr *)((char *)v426 - *v96);
                  v522 = v301;
                  v523 = v8 + 656;
                  *(_QWORD *)(v8 + 656) += v301;
                }
                *(_DWORD *)(v8 + 664) = 0;
              }
              v524 = *(_QWORD *)(v8 + 16);
              v256 = *(_QWORD **)(v524 + 392);
              v525 = v256;
              v329 = SOS_PublicGlobals::sm_SpinlockStatSnapshot;
              if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
              {
                v257 = rand();
                if ( v257 == 5 * (v257 / 5) )
                  Spinlock<114,16,258>::UpdateStatSnapshot();
              }
              *v256 = 0;
              Login = v289;
              goto LABEL_321;
            }
            v384 = Base_PublicGlobals::sm_invariantTscAvailable;
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&v427);
              v98 = (CSbTransportMgr *)v427.QuadPart;
            }
            else
            {
              v98 = MEMORY[0x7FFE0008];
              v428 = MEMORY[0x7FFE0008];
            }
            v429 = v98;
            v430 = v98;
            CNetConnection::GetLock(*(CNetConnection **)(v8 + 16));
            v526 = v8 + 648;
            if ( *(_DWORD *)(v8 + 664) )
            {
              if ( (unsigned __int64)v430 > *v96 )
              {
                v301 = (CSbTransportMgr *)((char *)v430 - *v96);
                v527 = v301;
                v528 = v8 + 656;
                *(_QWORD *)(v8 + 656) += v301;
              }
              *(_DWORD *)(v8 + 664) = 0;
            }
            v529 = *(_QWORD *)(v8 + 16);
            v99 = *(_QWORD **)(v529 + 392);
            v530 = v99;
            v306 = SOS_PublicGlobals::sm_SpinlockStatSnapshot;
            if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
            {
              v258 = rand();
              if ( v258 == 5 * (v258 / 5) )
                Spinlock<114,16,258>::UpdateStatSnapshot();
            }
            *v99 = 0;
            v385 = Base_PublicGlobals::sm_invariantTscAvailable;
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&v431);
              v100 = (CSbTransportMgr *)v431.QuadPart;
            }
            else
            {
              v432 = MEMORY[0x7FFE0008];
              v100 = MEMORY[0x7FFE0008];
            }
            v433 = v100;
            CNetConnection::GetLock(*(CNetConnection **)(v8 + 16));
            v101 = (_QWORD *)(v8 + 672);
            *(_QWORD *)(v8 + 672) = v100;
            *(_DWORD *)(v8 + 688) = 1;
            v531 = *(_QWORD *)(v8 + 16);
            v102 = *(_QWORD **)(v531 + 392);
            v532 = v102;
            v307 = SOS_PublicGlobals::sm_SpinlockStatSnapshot;
            if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
            {
              v259 = rand();
              if ( v259 == 5 * (v259 / 5) )
                Spinlock<114,16,258>::UpdateStatSnapshot();
            }
            *v102 = 0;
            ExecuteClassifier();
            v386 = Base_PublicGlobals::sm_invariantTscAvailable;
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&v434);
              v103 = (CSbTransportMgr *)v434.QuadPart;
            }
            else
            {
              v103 = MEMORY[0x7FFE0008];
              v435 = MEMORY[0x7FFE0008];
            }
            v436 = v103;
            v437 = v103;
            CNetConnection::GetLock(*(CNetConnection **)(v8 + 16));
            v533 = v8 + 672;
            if ( *(_DWORD *)(v8 + 688) )
            {
              if ( (unsigned __int64)v437 > *v101 )
              {
                v301 = (CSbTransportMgr *)((char *)v437 - *v101);
                v534 = v301;
                v535 = v8 + 680;
                *(_QWORD *)(v8 + 680) += v301;
              }
              *(_DWORD *)(v8 + 688) = 0;
            }
            v536 = *(_QWORD *)(v8 + 16);
            v104 = *(_QWORD **)(v536 + 392);
            v537 = v104;
            v308 = SOS_PublicGlobals::sm_SpinlockStatSnapshot;
            if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
            {
              v260 = rand();
              if ( v260 == 5 * (v260 / 5) )
                Spinlock<114,16,258>::UpdateStatSnapshot();
            }
            *v104 = 0;
            v387 = Base_PublicGlobals::sm_invariantTscAvailable;
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&v438);
              v105 = (CSbTransportMgr *)v438.QuadPart;
            }
            else
            {
              v439 = MEMORY[0x7FFE0008];
              v105 = MEMORY[0x7FFE0008];
            }
            v440 = v105;
            CNetConnection::GetLock(*(CNetConnection **)(v8 + 16));
            *(_QWORD *)(v8 + 720) = v105;
            *(_DWORD *)(v8 + 736) = 1;
            v538 = *(_QWORD *)(v8 + 16);
            v106 = *(_QWORD **)(v538 + 392);
            v539 = v106;
            v309 = SOS_PublicGlobals::sm_SpinlockStatSnapshot;
            if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
            {
              v261 = rand();
              if ( v261 == 5 * (v261 / 5) )
                Spinlock<114,16,258>::UpdateStatSnapshot();
            }
            *v106 = 0;
            v540 = NtCurrentTeb()->ThreadLocalStoragePointer;
            v541 = v540[SystemThread_TlsIndex] + SystemThread_TlsOffset;
            v542 = *(_QWORD *)(v541 + 80);
            *(_DWORD *)(v542 + 1000) &= ~8u;
            if ( (*(_BYTE *)(v7.QuadPart + 272) & 0x20) == 0 )
            {
LABEL_159:
              v94 = v336;
LABEL_160:
              if ( v291 )
                *((_WORD *)v93 + 136) = SECurDbLockRef::GetCookieForBaseDbAndCloseDb((struct CUEnvTransient *)((char *)v93 + 274));
              v107 = ((__int64 (__fastcall *)(_QWORD))CSession::AccountForNewSessionRequest)((LARGE_INTEGER)v7.QuadPart);
              LODWORD(v333) = v107;
              if ( !v107 )
              {
                if ( !*(_BYTE *)v94 )
                {
                  v108 = (struct CNetConnection *)(*(__int64 (__fastcall **)(struct CBatch *))(*(_QWORD *)v339 + 72LL))(v339);
                  StartOrStopTdsForwarder((struct CSession *)v7.QuadPart, v93, v108, 0);
                }
                if ( (*(_BYTE *)(v7.QuadPart + 270) & 4) != 0 )
                {
                  v275 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v7.QuadPart + 96) + 16LL))(*(_QWORD *)(v7.QuadPart + 96));
                  v555 = v275;
                  if ( v275 )
                  {
                    v79 = *(_QWORD *)(v275 + 688);
                    if ( v79 )
                    {
                      if ( !*(_DWORD *)(v275 + 1088) )
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v79 + 48LL))(v79);
                    }
                  }
                }
                Login = v289;
                if ( !v289 )
                {
                  if ( byte_102EDCACF )
                    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)(v7.QuadPart + 104) + 264LL) + 464LL))(*(_QWORD *)(*(_QWORD *)(v7.QuadPart + 104) + 264LL));
                  if ( byte_102EDCADA )
                  {
                    v447 = *(_OWORD *)((char *)v295 + 28);
                    AuditLoginXdb(&v564, 0, v566, &v447);
                  }
                  goto LABEL_171;
                }
                goto LABEL_321;
              }
              v566 = 1;
              if ( v107 == 0x80000000 )
              {
                Login = 10928;
                v289 = 10928;
                goto LABEL_321;
              }
              if ( v107 == -2113929216 )
              {
                Login = 10936;
                v289 = 10936;
                goto LABEL_321;
              }
              Login = v289;
              goto LABEL_427;
            }
            v388 = Base_PublicGlobals::sm_invariantTscAvailable;
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&v389);
              v262 = (CSbTransportMgr *)v389.QuadPart;
            }
            else
            {
              v390 = MEMORY[0x7FFE0008];
              v262 = MEMORY[0x7FFE0008];
            }
            v391 = v262;
            CNetConnection::GetLock(*(CNetConnection **)(v8 + 16));
            v263 = (_QWORD *)(v8 + 696);
            *(_QWORD *)(v8 + 696) = v262;
            *(_DWORD *)(v8 + 712) = 1;
            v543 = *(_QWORD *)(v8 + 16);
            v264 = *(_QWORD **)(v543 + 392);
            v544 = v264;
            v310 = SOS_PublicGlobals::sm_SpinlockStatSnapshot;
            if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
            {
              v265 = rand();
              if ( v265 == 5 * (v265 / 5) )
                Spinlock<114,16,258>::UpdateStatSnapshot();
            }
            *v264 = 0;
            if ( !v291 )
            {
              v301 = (struct CUEnvTransient *)v7.QuadPart;
              v266 = *(_BYTE *)(v7.QuadPart + 270);
              if ( (v266 & 4) != 0 )
              {
                v267 = v266 & 0xFB;
                *(_BYTE *)(v7.QuadPart + 270) = v267;
                *(_BYTE *)(v7.QuadPart + 271) &= ~1u;
                v268 = *(_BYTE *)(v7.QuadPart + 271);
                *(_DWORD *)(v7.QuadPart + 404) = 2;
                *(_BYTE *)(v7.QuadPart + 270) = v267 | 4;
                v268 |= 1u;
                *(_BYTE *)(v7.QuadPart + 271) = v268;
                *(_BYTE *)(v7.QuadPart + 271) = v268 | 1;
                *(_DWORD *)(v7.QuadPart + 404) = 1;
              }
              else
              {
                v301 = 0;
              }
            }
            if ( CSession::FRecoverSessionStateFromTDS((CSession *)v7.QuadPart, 0, (enum ELoginFailedState *)&v566) )
            {
              LODWORD(v338) = Base_PublicGlobals::sm_invariantTscAvailable;
              if ( Base_PublicGlobals::sm_invariantTscAvailable )
              {
                QueryPerformanceCounter(&v397);
                v272 = (CSbTransportMgr *)v397.QuadPart;
              }
              else
              {
                v272 = MEMORY[0x7FFE0008];
                v398 = MEMORY[0x7FFE0008];
              }
              v411 = v272;
              v396 = v272;
              CNetConnection::GetLock(*(CNetConnection **)(v8 + 16));
              v550 = v8 + 696;
              if ( *(_DWORD *)(v8 + 712) )
              {
                if ( (unsigned __int64)v396 > *v263 )
                {
                  v301 = (CSbTransportMgr *)((char *)v396 - *v263);
                  v551 = v301;
                  v552 = v8 + 704;
                  *(_QWORD *)(v8 + 704) += v301;
                }
                *(_DWORD *)(v8 + 712) = 0;
              }
              v553 = *(_QWORD *)(v8 + 16);
              v273 = *(_QWORD **)(v553 + 392);
              v554 = v273;
              v312 = SOS_PublicGlobals::sm_SpinlockStatSnapshot;
              if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
              {
                v274 = rand();
                if ( v274 == 5 * (v274 / 5) )
                  Spinlock<114,16,258>::UpdateStatSnapshot();
              }
              *v273 = 0;
              goto LABEL_159;
            }
            LODWORD(v336) = Base_PublicGlobals::sm_invariantTscAvailable;
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&v392);
              v269 = (CSbTransportMgr *)v392.QuadPart;
            }
            else
            {
              v269 = MEMORY[0x7FFE0008];
              v393 = MEMORY[0x7FFE0008];
            }
            v394 = v269;
            v395 = v269;
            CNetConnection::GetLock(*(CNetConnection **)(v8 + 16));
            v545 = v8 + 696;
            if ( *(_DWORD *)(v8 + 712) )
            {
              if ( (unsigned __int64)v395 > *v263 )
              {
                v301 = (CSbTransportMgr *)((char *)v395 - *v263);
                v546 = v301;
                v547 = v8 + 704;
                *(_QWORD *)(v8 + 704) += v301;
              }
              *(_DWORD *)(v8 + 712) = 0;
            }
            v548 = *(_QWORD *)(v8 + 16);
            v270 = *(_QWORD **)(v548 + 392);
            v549 = v270;
            v311 = SOS_PublicGlobals::sm_SpinlockStatSnapshot;
            if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
            {
              v271 = rand();
              if ( v271 == 5 * (v271 / 5) )
                Spinlock<114,16,258>::UpdateStatSnapshot();
            }
            *v270 = 0;
            goto LABEL_331;
          }
          if ( v297 )
          {
            v566 = 18;
            Login = 40620;
            v289 = 40620;
            goto LABEL_321;
          }
          if ( !v574 && v577 )
          {
            v247 = 0;
            v348 = 0;
            v248 = 0;
            v419 = 0;
            v506 = *(_QWORD *)(v7.QuadPart + 216);
            v249 = v506;
            v361 = 0;
            v362 = 0;
            if ( v506 )
            {
              v361 = v506;
              v362 = 0;
              if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v506 + 24LL))(v506) )
              {
                v566 = 19;
                Login = 18456;
                v289 = 18456;
                CAutoEraseClearMemory::~CAutoEraseClearMemory((CAutoEraseClearMemory *)&v361);
                goto LABEL_321;
              }
              v247 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v249 + 64LL))(v249);
              v348 = v247;
              v248 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v249 + 56LL))(v249);
              v419 = v248;
            }
            CSession::GetUserSid((CSession *)v7.QuadPart, v658, 0x55u, &v334);
            v250 = GetMasterDbId();
            v347 = v250;
            v251 = *(_QWORD *)(v7.QuadPart + 104);
            if ( v251 )
            {
              v252 = *(_QWORD *)(v251 + 264);
              if ( v252 )
              {
                if ( (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v252 + 232LL))(v252, 1) )
                {
                  v253 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(*(_QWORD *)(v7.QuadPart + 104)
                                                                                  + 264LL)
                                                                    + 232LL))(
                           *(_QWORD *)(*(_QWORD *)(v7.QuadPart + 104) + 264LL),
                           1);
                  v250 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v253 + 16LL))(v253);
                  v347 = v250;
                }
              }
            }
            Login = ChangePassword(v303, v658, v334, v248, v247, v250);
            v289 = Login;
            if ( Login )
            {
              v566 = 57;
              CAutoEraseClearMemory::~CAutoEraseClearMemory((CAutoEraseClearMemory *)&v361);
              goto LABEL_427;
            }
            CAutoEraseClearMemory::~CAutoEraseClearMemory((CAutoEraseClearMemory *)&v361);
            goto LABEL_129;
          }
          v566 = 18;
        }
        else
        {
          v566 = 17;
        }
LABEL_331:
        v289 = 18456;
LABEL_332:
        Login = 18456;
        goto LABEL_321;
      }
LABEL_498:
      v289 = 18456;
      v566 = 126;
      goto LABEL_332;
    }
LABEL_614:
    v566 = 173;
    goto LABEL_331;
  }
  if ( !(unsigned int)IsContainedAGEnabledInstance() )
    goto LABEL_52;
  v161 = 0;
  v346 = 0;
  v162 = *(_QWORD *)(v7.QuadPart + 192);
  if ( v162 )
  {
    v161 = 2 * *(unsigned __int16 *)(v162 + 70);
    v346 = v161;
    v163 = (const wchar_t *)(v162 + *(unsigned __int16 *)(v162 + 68));
  }
  else
  {
    v163 = 0;
  }
  v405 = v163;
  v569 = 0;
  v570[0] = 0;
  ContainedAGSystemDbsId = HadrRuntimeCallbacks::GetContainedAGSystemDbsId(&v579, &v569, v570);
  v165 = ContainedAGSystemDbsId;
  v316 = ContainedAGSystemDbsId;
  if ( !v163 || !v161 )
    goto LABEL_314;
  if ( !ContainedAGSystemDbsId )
    goto LABEL_317;
  if ( *(_BYTE *)(qword_102ECFB00 + 48768) && *(_BYTE *)(qword_102ECFB00 + 48772) )
    goto LABEL_315;
  v166 = v161 >> 1;
  v399 = CompareStringWEnglishNoCase(1u, 0, v163, v161 >> 1, L"master", (unsigned __int64)(int)dword_102F1BB98 >> 1);
  if ( v399 == 2
    || (v400 = CompareStringWEnglishNoCase(1u, 0, v163, v166, L"tempdb", (unsigned __int64)dword_102F1BB9C >> 1),
        v400 == 2)
    || (v401 = CompareStringWEnglishNoCase(1u, 0, v163, v166, L"msdb", (unsigned __int64)(int)dword_102F1BBA4 >> 1),
        v401 == 2)
    || (v573 = 0,
        v572[0] = 0,
        v613 = (__int128)*HadrRuntimeCallbacks::GetContainedOrSystemAGId(&v563, v163, v161, &v573, v572),
        v613 == *(_OWORD *)&v579) )
  {
LABEL_314:
    if ( v165 )
    {
LABEL_315:
      v44 = v579;
      *(_WORD *)(v7.QuadPart + 4928) = v569;
      *(_WORD *)(v7.QuadPart + 4930) = v570[0];
LABEL_316:
      v8 = v333;
      goto LABEL_51;
    }
LABEL_317:
    *(_BYTE *)(v7.QuadPart + 270) |= 0x20u;
    v44 = Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
    *(_WORD *)(v7.QuadPart + 4928) = 1;
    *(_WORD *)(v7.QuadPart + 4930) = 0;
    goto LABEL_316;
  }
  v289 = 18456;
  v566 = 38;
  v167 = (unsigned int)CConnection::PNetConn(v302);
  LoginError(18456, (_DWORD)v295, v167, 38, (__int64)&si128);
  v294 = -2147465192;
  operator delete[]((void *)v576);
  ExcHandler::~ExcHandler((ExcHandler *)v618);
  v453 = NtCurrentTeb()->ThreadLocalStoragePointer;
  v168 = v453[SystemThread_TlsIndex] + SystemThread_TlsOffset;
  v454 = v168;
  v169 = *(_QWORD *)(v168 + 256);
  v303 = (struct IMemObj *)v169;
  if ( !v169 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v169 = *(_QWORD *)(v168 + 256);
    v303 = (struct IMemObj *)v169;
  }
  *(_QWORD *)(v169 + 3208) = v358;
  CAutoSetXLvlIntCtxtImplNoException::~CAutoSetXLvlIntCtxtImplNoException((CAutoSetXLvlIntCtxtImplNoException *)&v649);
  AutoInstallParams::~AutoInstallParams((AutoInstallParams *)&v363);
  SEParams::~SEParams((SEParams *)v619);
  AutoResumeMsqlXactManager::~AutoResumeMsqlXactManager((AutoResumeMsqlXactManager *)&v304);
  CAutoSetupCXCtxtSingleThread::~CAutoSetupCXCtxtSingleThread((CAutoSetupCXCtxtSingleThread *)v652);
  CAutoLoginInit::~CAutoLoginInit((CAutoLoginInit *)&v360);
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
