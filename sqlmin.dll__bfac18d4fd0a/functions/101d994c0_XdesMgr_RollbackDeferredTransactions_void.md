# XdesMgr::RollbackDeferredTransactions(void)

- ea: `0x101d994c0`
- end: `0x101d9aefe`
- name: `?RollbackDeferredTransactions@XdesMgr@@QEAAXXZ`
- size: `6718`
- prototype: `void __fastcall(XdesMgr *__hidden this)`
- caller_count: `1`
- callee_count: `30`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x101cf1a20`

## callees

- `0x100401380`
- `0x1004013f0`
- `0x100401490`
- `0x100402000`
- `0x100402620`
- `0x10042ec20`
- `0x1004888d0`
- `0x1005b4980`
- `0x10063dc00`
- `0x100640310`
- `0x100640360`
- `0x100642260`
- `0x100643010`
- `0x100690890`
- `0x1006ae9a0`
- `0x1006aeb50`
- `0x1006aed00`
- `0x100aa4360`
- `0x1011538d0`
- `0x10163fd00`
- `0x101cdbd10`
- `0x101cdbea0`
- `0x101d0ba60`
- `0x101d32380`
- `0x101d35670`
- `0x101d8e130`
- `0x101d986a0`
- `0x101d994c0`
- `0x101d9fd70`
- `0x1023aecb0`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x101d9978d`
- `KERNEL32!QueryPerformanceCounter` at `0x101d997cc`
- `KERNEL32!QueryPerformanceCounter` at `0x101d9978d`
- `KERNEL32!QueryPerformanceCounter` at `0x101d997cc`
- `ole32!StringFromGUID2` at `0x101d9a5a3`
- `ole32!StringFromGUID2` at `0x101d9a714`
- `ole32!StringFromGUID2` at `0x101d9a5a3`
- `ole32!StringFromGUID2` at `0x101d9a714`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x101d9a54d`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x101d998b4`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x101d9ad02`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x101d99723`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101d99779`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101d997b8`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x101d99a1c`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x101d99a41`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x101d99a65`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x101d99b68`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x101d99b8c`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x101d99bce`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x101d99ccb`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x101d99cef`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x101d9a5e1`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x101d9ad46`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x101d9acfa`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x101d9acfa`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101d99b2e`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101d99c91`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101d99b2e`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101d99c91`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d995b2`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d99f9a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d9a398`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d995b2`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d99f9a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d9a398`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d99ee9`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d99f42`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d9a301`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d9a866`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d99ee9`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d99f42`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d9a301`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d9a866`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d9a472`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d9a4ec`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d9a672`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d9a6ec`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d9a472`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d9a4ec`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d9a672`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101d9a6ec`
- `sqldk!SystemThread_TlsIndex` at `0x101d99567`
- `sqldk!SystemThread_TlsIndex` at `0x101d995c8`
- `sqldk!SystemThread_TlsIndex` at `0x101d99747`
- `sqldk!SystemThread_TlsIndex` at `0x101d99931`
- `sqldk!SystemThread_TlsIndex` at `0x101d99aad`
- `sqldk!SystemThread_TlsIndex` at `0x101d99c10`
- `sqldk!SystemThread_TlsIndex` at `0x101d9a42b`
- `sqldk!SystemThread_TlsIndex` at `0x101d9a4a5`
- `sqldk!SystemThread_TlsIndex` at `0x101d9a62b`
- `sqldk!SystemThread_TlsIndex` at `0x101d9a6a5`
- `sqldk!SystemThread_TlsIndex` at `0x101d9acc2`
- `sqldk!SystemThread_TlsOffset` at `0x101d99570`
- `sqldk!SystemThread_TlsOffset` at `0x101d995d1`
- `sqldk!SystemThread_TlsOffset` at `0x101d99750`
- `sqldk!SystemThread_TlsOffset` at `0x101d9993a`
- `sqldk!SystemThread_TlsOffset` at `0x101d99ab6`
- `sqldk!SystemThread_TlsOffset` at `0x101d99c19`
- `sqldk!SystemThread_TlsOffset` at `0x101d9a434`
- `sqldk!SystemThread_TlsOffset` at `0x101d9a4ae`
- `sqldk!SystemThread_TlsOffset` at `0x101d9a634`
- `sqldk!SystemThread_TlsOffset` at `0x101d9a6ae`
- `sqldk!SystemThread_TlsOffset` at `0x101d9accb`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101d995ec`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101d99adf`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101d99c42`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101d9ace4`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101d995ec`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101d99adf`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101d99c42`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101d9ace4`
- `sqldk!??_V@YAXPEAX@Z` at `0x101d99b46`
- `sqldk!??_V@YAXPEAX@Z` at `0x101d99ca9`
- `sqldk!??_V@YAXPEAX@Z` at `0x101d9abe4`
- `sqldk!??_V@YAXPEAX@Z` at `0x101d9ad84`
- `sqldk!??_V@YAXPEAX@Z` at `0x101d9ad93`
- `sqldk!??_V@YAXPEAX@Z` at `0x101d99b46`
- `sqldk!??_V@YAXPEAX@Z` at `0x101d99ca9`
- `sqldk!??_V@YAXPEAX@Z` at `0x101d9abe4`
- `sqldk!??_V@YAXPEAX@Z` at `0x101d9ad84`
- `sqldk!??_V@YAXPEAX@Z` at `0x101d9ad93`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x101d998c0`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x101d9ad0e`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x101d998c0`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x101d9ad0e`
- `api-ms-win-crt-string-l1-1-0!wcscpy_s` at `0x101d99ba8`
- `api-ms-win-crt-string-l1-1-0!wcscpy_s` at `0x101d99d0b`
- `api-ms-win-crt-string-l1-1-0!wcscpy_s` at `0x101d99ba8`
- `api-ms-win-crt-string-l1-1-0!wcscpy_s` at `0x101d99d0b`
- `sqllang!?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ` at `0x101d9999f`
- `sqllang!?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ` at `0x101d9a31e`
- `sqllang!?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ` at `0x101d9a99c`
- `sqllang!?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ` at `0x101d9999f`
- `sqllang!?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ` at `0x101d9a31e`
- `sqllang!?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ` at `0x101d9a99c`

## string_xrefs

- `0x101d9a5c3`: `committed`
- `0x101d9aa59`: `Deferred Rollback`
- `0x101d9aaf0`: `Deferred Rollback`
- `0x101d9a38d`: `rollbackXdes->m_dtcInfo != NULL`
- `0x101d995a8`: `pCurrentTaskProxy`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
void __fastcall XdesMgr::RollbackDeferredTransactions(XdesMgr *this)
{
  unsigned int *v1; // r12
  int v2; // r14d
  __int64 v3; // rdx
  __int64 v4; // rbx
  __int64 v5; // rdx
  int v6; // ecx
  void **v7; // r9
  void **v8; // r8
  void **v9; // rdx
  signed __int64 UniqueThread_low; // rsi
  volatile signed __int64 *v11; // rsi
  __int64 v12; // r14
  __int64 v13; // r8
  DirtyPageMgr *QuadPart; // rbx
  signed __int64 v15; // rdx
  DirtyPageMgr *v16; // rax
  signed __int64 v17; // rdx
  char *v18; // rbx
  XdesMgr *v19; // rcx
  int v20; // r8d
  XdesRMFull *v21; // rsi
  unsigned int v22; // eax
  __int64 v23; // rdx
  __int64 v24; // rcx
  unsigned int XactOutcome; // r14d
  unsigned __int8 **v26; // rax
  __int64 v27; // rax
  __int64 v28; // rcx
  __int64 v29; // rbx
  __int64 v30; // rcx
  struct IMemObj *v31; // rcx
  rsize_t v32; // rsi
  unsigned __int64 v33; // rax
  wchar_t *v34; // r14
  __int64 v35; // rbx
  const wchar_t *v36; // rax
  __int64 v37; // rax
  __int64 v38; // rcx
  __int64 v39; // rbx
  __int64 v40; // rcx
  struct IMemObj *v41; // rcx
  rsize_t v42; // rbx
  unsigned __int64 v43; // rax
  void *v44; // rsi
  __int64 v45; // r14
  const wchar_t *v46; // rax
  __int64 v47; // rcx
  __int64 v48; // rax
  bool v49; // r15
  __int64 v50; // r13
  wchar_t *v51; // r12
  __int64 v52; // rbx
  __int64 v53; // rdx
  __int64 v54; // rcx
  _QWORD *v55; // rbx
  struct CDTCState *DTCStateByDbId; // rax
  struct CDTCState *v57; // r13
  __int64 v58; // rax
  GUID *v59; // r9
  __int64 v60; // rax
  struct CSessionTraceFlags *v61; // rcx
  __int64 v62; // rax
  struct CSessionTraceFlags *v63; // rcx
  char v64; // r15
  __int64 v65; // rcx
  const wchar_t *v66; // rbx
  __int64 v67; // rax
  __int64 v68; // rax
  struct CSessionTraceFlags *v69; // rcx
  __int64 v70; // rax
  struct CSessionTraceFlags *v71; // rcx
  __int64 v72; // rcx
  __int64 v73; // rcx
  __int64 v74; // rcx
  __int64 v75; // rcx
  char v76; // r10
  __int64 v77; // rcx
  __int64 v78; // rcx
  int v79; // eax
  char v80; // al
  bool v81; // bl
  __int64 v82; // rcx
  void ***v83; // r14
  struct IndexErrorTable *v84; // rbx
  const struct LSN *v85; // rax
  CDTCState *v86; // rbx
  __int64 v87; // rbx
  struct Worker *v88; // rcx
  int v89; // r8d
  __int64 v90; // rcx
  bool v91; // r9
  int v92; // ecx
  unsigned __int8 **v93; // [rsp+20h] [rbp-1478h]
  unsigned __int8 **v94; // [rsp+20h] [rbp-1478h]
  unsigned int v95; // [rsp+44h] [rbp-1454h]
  XdesRMFull *v96; // [rsp+48h] [rbp-1450h]
  unsigned int v97; // [rsp+50h] [rbp-1448h] BYREF
  int v98; // [rsp+54h] [rbp-1444h] BYREF
  __int16 v99; // [rsp+58h] [rbp-1440h]
  char v100; // [rsp+5Ch] [rbp-143Ch]
  bool v101; // [rsp+5Dh] [rbp-143Bh]
  int v102; // [rsp+60h] [rbp-1438h]
  int v103; // [rsp+64h] [rbp-1434h]
  GUID *rguid; // [rsp+68h] [rbp-1430h]
  int v105; // [rsp+70h] [rbp-1428h] BYREF
  int v106; // [rsp+74h] [rbp-1424h] BYREF
  int v107; // [rsp+78h] [rbp-1420h]
  struct CDTCState *v108; // [rsp+80h] [rbp-1418h]
  volatile signed __int64 *v109; // [rsp+88h] [rbp-1410h]
  int v110; // [rsp+90h] [rbp-1408h]
  __int64 v111; // [rsp+98h] [rbp-1400h]
  XdesMgr *v112; // [rsp+A0h] [rbp-13F8h]
  __int64 v113; // [rsp+A8h] [rbp-13F0h]
  __int16 v114; // [rsp+B0h] [rbp-13E8h]
  unsigned __int16 v115; // [rsp+B2h] [rbp-13E6h]
  int v116; // [rsp+B4h] [rbp-13E4h] BYREF
  unsigned int SizeInWords; // [rsp+B8h] [rbp-13E0h]
  int SizeInWords_4; // [rsp+BCh] [rbp-13DCh] BYREF
  int v119; // [rsp+C0h] [rbp-13D8h] BYREF
  int v120; // [rsp+C4h] [rbp-13D4h] BYREF
  int v121; // [rsp+C8h] [rbp-13D0h] BYREF
  _DWORD v122[3]; // [rsp+CCh] [rbp-13CCh]
  wchar_t *v123; // [rsp+D8h] [rbp-13C0h]
  int v124; // [rsp+E0h] [rbp-13B8h] BYREF
  __int16 v125; // [rsp+E4h] [rbp-13B4h]
  int v126; // [rsp+F0h] [rbp-13A8h] BYREF
  __int16 v127; // [rsp+F4h] [rbp-13A4h]
  int v128; // [rsp+100h] [rbp-1398h] BYREF
  __int16 v129; // [rsp+104h] [rbp-1394h]
  void **v130; // [rsp+110h] [rbp-1388h] BYREF
  __int64 v131; // [rsp+118h] [rbp-1380h]
  unsigned int v132; // [rsp+120h] [rbp-1378h]
  __int64 v133; // [rsp+128h] [rbp-1370h]
  char v134; // [rsp+130h] [rbp-1368h]
  struct RecoveryUnit **v135; // [rsp+138h] [rbp-1360h]
  __int64 v136; // [rsp+140h] [rbp-1358h]
  XdesMgr *v137; // [rsp+148h] [rbp-1350h]
  __int64 v138; // [rsp+150h] [rbp-1348h]
  DeferredLockSpaceIdManager *v139; // [rsp+158h] [rbp-1340h]
  wchar_t *v140; // [rsp+160h] [rbp-1338h]
  void *v141; // [rsp+168h] [rbp-1330h]
  void **v142; // [rsp+170h] [rbp-1328h] BYREF
  __int64 v143; // [rsp+178h] [rbp-1320h]
  unsigned int v144; // [rsp+180h] [rbp-1318h]
  __int64 v145; // [rsp+188h] [rbp-1310h]
  char v146; // [rsp+190h] [rbp-1308h]
  int v147; // [rsp+198h] [rbp-1300h]
  __int64 v148; // [rsp+1A0h] [rbp-12F8h]
  void *v149; // [rsp+1A8h] [rbp-12F0h] BYREF
  int v150; // [rsp+1B0h] [rbp-12E8h]
  int v151; // [rsp+1B8h] [rbp-12E0h]
  __int64 v152; // [rsp+1C0h] [rbp-12D8h]
  __int64 v153; // [rsp+1C8h] [rbp-12D0h]
  int v154; // [rsp+1D0h] [rbp-12C8h] BYREF
  int v156; // [rsp+1D8h] [rbp-12C0h]
  LARGE_INTEGER PerformanceCount; // [rsp+1E0h] [rbp-12B8h] BYREF
  LARGE_INTEGER v159; // [rsp+1E8h] [rbp-12B0h] BYREF
  __int64 v160; // [rsp+1F0h] [rbp-12A8h]
  __int64 v161; // [rsp+1F8h] [rbp-12A0h]
  int v162; // [rsp+200h] [rbp-1298h]
  int v163; // [rsp+204h] [rbp-1294h]
  __int64 v164; // [rsp+208h] [rbp-1290h]
  int v165; // [rsp+210h] [rbp-1288h]
  int v166; // [rsp+214h] [rbp-1284h]
  int v167; // [rsp+218h] [rbp-1280h]
  int v168; // [rsp+21Ch] [rbp-127Ch]
  int v169; // [rsp+220h] [rbp-1278h]
  int v170; // [rsp+224h] [rbp-1274h]
  int v171; // [rsp+228h] [rbp-1270h]
  int v172; // [rsp+22Ch] [rbp-126Ch]
  int v173; // [rsp+230h] [rbp-1268h]
  int v174; // [rsp+234h] [rbp-1264h]
  int v175; // [rsp+238h] [rbp-1260h]
  int v176; // [rsp+23Ch] [rbp-125Ch]
  int v177; // [rsp+240h] [rbp-1258h]
  int v178; // [rsp+244h] [rbp-1254h]
  char *v180; // [rsp+250h] [rbp-1248h]
  unsigned int v181; // [rsp+258h] [rbp-1240h]
  int v182; // [rsp+260h] [rbp-1238h]
  int v183; // [rsp+268h] [rbp-1230h]
  int v184; // [rsp+26Ch] [rbp-122Ch]
  _DWORD v185[6]; // [rsp+270h] [rbp-1228h] BYREF
  __int64 v186; // [rsp+288h] [rbp-1210h]
  _QWORD *v187; // [rsp+290h] [rbp-1208h]
  __int64 v188; // [rsp+298h] [rbp-1200h]
  struct IMemObj *v189; // [rsp+2A0h] [rbp-11F8h]
  __int64 v190; // [rsp+2A8h] [rbp-11F0h]
  __int64 v191; // [rsp+2B0h] [rbp-11E8h]
  _QWORD *v192; // [rsp+2B8h] [rbp-11E0h]
  __int64 v193; // [rsp+2C0h] [rbp-11D8h]
  struct IMemObj *v194; // [rsp+2C8h] [rbp-11D0h]
  __int64 v195; // [rsp+2D0h] [rbp-11C8h]
  __int64 v196; // [rsp+2D8h] [rbp-11C0h]
  __int64 v197; // [rsp+2E0h] [rbp-11B8h]
  __int64 v198; // [rsp+2E8h] [rbp-11B0h]
  __int64 v199; // [rsp+2F0h] [rbp-11A8h]
  _QWORD *v200; // [rsp+2F8h] [rbp-11A0h]
  __int64 *v201; // [rsp+300h] [rbp-1198h]
  __int64 v202; // [rsp+308h] [rbp-1190h]
  struct CSessionTraceFlags *v203; // [rsp+310h] [rbp-1188h]
  _QWORD *v204; // [rsp+318h] [rbp-1180h]
  __int64 *v205; // [rsp+320h] [rbp-1178h]
  __int64 v206; // [rsp+328h] [rbp-1170h]
  struct CSessionTraceFlags *v207; // [rsp+330h] [rbp-1168h]
  __int64 v208; // [rsp+338h] [rbp-1160h]
  _QWORD *v209; // [rsp+340h] [rbp-1158h]
  __int64 *v210; // [rsp+348h] [rbp-1150h]
  __int64 v211; // [rsp+350h] [rbp-1148h]
  struct CSessionTraceFlags *v212; // [rsp+358h] [rbp-1140h]
  _QWORD *v213; // [rsp+360h] [rbp-1138h]
  __int64 *v214; // [rsp+368h] [rbp-1130h]
  __int64 v215; // [rsp+370h] [rbp-1128h]
  __int64 v216; // [rsp+378h] [rbp-1120h]
  __int64 v217; // [rsp+380h] [rbp-1118h]
  __int64 v218; // [rsp+388h] [rbp-1110h]
  __int64 v219; // [rsp+390h] [rbp-1108h]
  __int64 v220; // [rsp+398h] [rbp-1100h]
  __int64 v221; // [rsp+3A0h] [rbp-10F8h]
  __int64 v222; // [rsp+3A8h] [rbp-10F0h]
  __int64 v223; // [rsp+3B0h] [rbp-10E8h]
  __int64 v224; // [rsp+3B8h] [rbp-10E0h]
  __int64 v225; // [rsp+3C0h] [rbp-10D8h]
  __int64 v226; // [rsp+3C8h] [rbp-10D0h]
  __int64 v227; // [rsp+3D0h] [rbp-10C8h]
  void ***v228; // [rsp+3D8h] [rbp-10C0h]
  struct IMemObj *v229; // [rsp+3E0h] [rbp-10B8h]
  CDTCState *v230; // [rsp+3E8h] [rbp-10B0h]
  struct CSessionTraceFlags *v231; // [rsp+3F0h] [rbp-10A8h]
  _QWORD *ThreadLocalStoragePointer; // [rsp+3F8h] [rbp-10A0h]
  __int128 v233; // [rsp+400h] [rbp-1098h] BYREF
  _BYTE v234[16]; // [rsp+410h] [rbp-1088h] BYREF
  __int64 v235; // [rsp+420h] [rbp-1078h]
  __int64 v236; // [rsp+428h] [rbp-1070h]
  __int64 CurrentInstance; // [rsp+430h] [rbp-1068h]
  __int64 v238; // [rsp+438h] [rbp-1060h]
  _BYTE v239[48]; // [rsp+440h] [rbp-1058h] BYREF
  _BYTE v240[608]; // [rsp+470h] [rbp-1028h] BYREF
  int v241; // [rsp+6D0h] [rbp-DC8h]
  __int16 v242; // [rsp+6D4h] [rbp-DC4h]
  int v243; // [rsp+6D6h] [rbp-DC2h]
  __int16 v244; // [rsp+6DAh] [rbp-DBEh]
  bool v245; // [rsp+6DCh] [rbp-DBCh]
  __int16 v246; // [rsp+6DDh] [rbp-DBBh]
  __int16 v247; // [rsp+6DFh] [rbp-DB9h]
  char v248; // [rsp+6E1h] [rbp-DB7h]
  _BYTE v249[608]; // [rsp+700h] [rbp-D98h] BYREF
  int v250; // [rsp+960h] [rbp-B38h]
  __int16 v251; // [rsp+964h] [rbp-B34h]
  int v252; // [rsp+966h] [rbp-B32h]
  __int16 v253; // [rsp+96Ah] [rbp-B2Eh]
  bool v254; // [rsp+96Ch] [rbp-B2Ch]
  __int16 v255; // [rsp+96Dh] [rbp-B2Bh]
  __int16 v256; // [rsp+96Fh] [rbp-B29h]
  char v257; // [rsp+971h] [rbp-B27h]
  _BYTE v258[608]; // [rsp+990h] [rbp-B08h] BYREF
  int v259; // [rsp+BF0h] [rbp-8A8h]
  __int16 v260; // [rsp+BF4h] [rbp-8A4h]
  int v261; // [rsp+BF6h] [rbp-8A2h]
  __int16 v262; // [rsp+BFAh] [rbp-89Eh]
  bool v263; // [rsp+BFCh] [rbp-89Ch]
  __int16 v264; // [rsp+BFDh] [rbp-89Bh]
  __int16 v265; // [rsp+BFFh] [rbp-899h]
  char v266; // [rsp+C01h] [rbp-897h]
  _BYTE v267[608]; // [rsp+C20h] [rbp-878h] BYREF
  int v268; // [rsp+E80h] [rbp-618h]
  __int16 v269; // [rsp+E84h] [rbp-614h]
  int v270; // [rsp+E86h] [rbp-612h]
  __int16 v271; // [rsp+E8Ah] [rbp-60Eh]
  char v272; // [rsp+E8Ch] [rbp-60Ch]
  __int16 v273; // [rsp+E8Dh] [rbp-60Bh]
  __int16 v274; // [rsp+E8Fh] [rbp-609h]
  char v275; // [rsp+E91h] [rbp-607h]
  _BYTE v276[24]; // [rsp+EB0h] [rbp-5E8h] BYREF
  __int64 v277; // [rsp+EC8h] [rbp-5D0h]
  char v278; // [rsp+1110h] [rbp-388h]
  char v279; // [rsp+1111h] [rbp-387h]
  char v280; // [rsp+1112h] [rbp-386h]
  _BYTE v281[24]; // [rsp+1130h] [rbp-368h] BYREF
  __int64 v282; // [rsp+1148h] [rbp-350h]
  char v283; // [rsp+1390h] [rbp-108h]
  char v284; // [rsp+1391h] [rbp-107h]
  char v285; // [rsp+1392h] [rbp-106h]
  char v286[16]; // [rsp+13B0h] [rbp-E8h] BYREF
  OLECHAR sz[40]; // [rsp+13C0h] [rbp-D8h] BYREF
  OLECHAR v288[40]; // [rsp+1410h] [rbp-88h] BYREF

  v216 = -2;
  v1 = (unsigned int *)this;
  v112 = this;
  v135 = (struct RecoveryUnit **)this;
  v137 = this;
  v2 = 1;
  v103 = 0;
  v102 = 0;
  v97 = 0;
  v98 = 0;
  v99 = 0;
  v138 = 0;
  v109 = (volatile signed __int64 *)((char *)this + 8);
  v110 = 0;
  v3 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v139 = *(DeferredLockSpaceIdManager **)(*(_QWORD *)this + 9200LL);
  if ( !*(_QWORD *)(v3 + 24) )
    utassert_fail(1u, "pCurrentTaskProxy", "xdesmgr.cpp", 5075, 0);
  v147 = 0;
  v4 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v5 = *(_QWORD *)(v4 + 256);
  if ( !v5 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v5 = *(_QWORD *)(v4 + 256);
  }
  v148 = v5;
  v6 = *(_DWORD *)(v5 + 616);
  v147 = !(*(_BYTE *)(v5 + 616) & 1);
  *(_DWORD *)(v5 + 616) = v6 | 1;
LABEL_6:
  v7 = &SLogIterForward::`vftable';
  v8 = &SLogIterForward::`vftable';
  v9 = &LogIter::`vftable';
  while ( v2 )
  {
    v143 = 0;
    v144 = 5;
    v145 = 0;
    v146 = 0;
    v142 = &SLogIterForward::`vftable';
    v131 = 0;
    v132 = 5;
    v133 = 0;
    v134 = 0;
    v130 = &SLogIterForward::`vftable';
    v141 = 0;
    v140 = 0;
    UniqueThread_low = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
    if ( *(_DWORD *)v109 || _InterlockedCompareExchange64(v109, UniqueThread_low, 0) )
    {
      if ( (SOS_PublicGlobals::sm_osStats & 0x84) != 0x84 )
        goto LABEL_25;
      v12 = 0;
      v13 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      if ( v13 && *(_QWORD *)(v13 + 272) == v13 )
        v12 = *(_QWORD *)(v13 + 256);
      if ( v12 )
      {
        if ( Base_PublicGlobals::sm_invariantTscAvailable )
        {
          QueryPerformanceCounter(&PerformanceCount);
          QuadPart = (DirtyPageMgr *)PerformanceCount.QuadPart;
        }
        else
        {
          QuadPart = MEMORY[0x7FFE0008];
        }
        v15 = UniqueThread_low;
        v11 = v109;
        Spinlock<153,9,257>::SpinToAcquireWithExponentialBackoff(v109, v15);
        if ( Base_PublicGlobals::sm_invariantTscAvailable )
        {
          QueryPerformanceCounter(&v159);
          v16 = (DirtyPageMgr *)v159.QuadPart;
        }
        else
        {
          v16 = MEMORY[0x7FFE0008];
          v11 = v109;
        }
        if ( v16 < QuadPart )
          *(_QWORD *)(v12 + 3192) = *(_QWORD *)(v12 + 3192);
        else
          *(_QWORD *)(v12 + 3192) += v16 - QuadPart;
      }
      else
      {
LABEL_25:
        v17 = UniqueThread_low;
        v11 = v109;
        Spinlock<153,9,257>::SpinToAcquireWithExponentialBackoff(v109, v17);
      }
    }
    else
    {
      v11 = v109;
    }
    v110 = 1;
    v18 = 0;
    if ( v138 )
      v19 = *(XdesMgr **)(v138 + 8920);
    else
      v19 = (XdesMgr *)*((_QWORD *)v137 + 4);
    if ( v19 == (XdesMgr *)((char *)v137 + 24) )
      v19 = 0;
    v2 = 0;
    while ( 1 )
    {
      if ( v19 )
        v18 = (char *)v19 - 8912;
      v96 = (XdesRMFull *)v18;
      if ( !v18 )
      {
LABEL_190:
        if ( (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot )
        {
          v89 = rand();
          if ( v89 == 5 * (v89 / 5) )
            Spinlock<153,9,257>::UpdateStatSnapshot();
        }
        *v11 = 0;
        v110 = 0;
        goto LABEL_194;
      }
      if ( (*(unsigned int (__fastcall **)(char *, void **, void **, void **))(*(_QWORD *)v18 + 632LL))(v18, v9, v8, v7) )
        break;
      v19 = (XdesMgr *)*((_QWORD *)v18 + 1115);
      if ( v19 == (XdesMgr *)(v1 + 6) )
        goto LABEL_190;
      v18 = 0;
    }
    v107 = 1;
    v233 = *(_OWORD *)(v18 + 120);
    if ( (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot )
    {
      v20 = rand();
      if ( v20 == 5 * (v20 / 5) )
        Spinlock<153,9,257>::UpdateStatSnapshot();
    }
    *v11 = 0;
    v110 = 0;
    try
    {
      ExcHandler::ExcHandler(
        (ExcHandler *)v239,
        0,
        0,
        0,
        (int (*)(int, int, int, int, char *))hdl_recoveryThroughError,
        0);
      v180 = v18;
      ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
      v235 = ThreadLocalStoragePointer[SystemThread_TlsIndex] + SystemThread_TlsOffset;
      v236 = *(_QWORD *)(v235 + 24);
      v21 = (XdesRMFull *)v18;
      (*(void (__fastcall **)(char *))(*(_QWORD *)v18 + 880LL))(v18);
      v22 = (*(__int64 (__fastcall **)(XdesRMFull *))(*(_QWORD *)v21 + 896LL))(v21);
      XactOutcome = v22;
      v95 = v22;
      if ( dword_1031852C8 && v22 == 3 )
      {
        if ( dword_103184474
          || (CurrentInstance = CFeatureSwitchesLangSvc::GetCurrentInstance(v24, v23), *(_BYTE *)(CurrentInstance + 663))
          || byte_1031852E4
          || FUseDTCOnManagedInstance() )
        {
          v26 = (unsigned __int8 **)(v18 + 8984);
          if ( !*((_QWORD *)v18 + 1123) )
            goto LABEL_50;
        }
        else
        {
          v26 = (unsigned __int8 **)(v18 + 8984);
LABEL_50:
          XdesRMFull::GetPrepareInfo(
            (XdesRMFull *)v18,
            (struct FullPruId *)&v97,
            (struct XdesId *)&v98,
            (int *)v18 + 2248,
            v26,
            0,
            &v154,
            0);
          v136 = g_dbtableFactory[4]((unsigned __int16)v97);
          v114 = *(_WORD *)(*((_QWORD *)v18 + 6) + 1720LL);
          v113 = ((__int64 (*)(void))g_dbtableFactory[4])();
          v116 = 0;
          v27 = ((__int64 (__fastcall *)(__int64, int *))g_dbtableFactory[2])(v113, &v116);
          v238 = v27;
          v28 = -1;
          do
            ++v28;
          while ( *(_WORD *)(v27 + 2 * v28) );
          v186 = v28;
          SizeInWords = v28 + 1;
          v187 = NtCurrentTeb()->ThreadLocalStoragePointer;
          v29 = v187[SystemThread_TlsIndex] + SystemThread_TlsOffset;
          v188 = v29;
          v30 = *(_QWORD *)(v29 + 256);
          v160 = v30;
          if ( !v30 )
          {
            SystemThread::MakeMiniSOSThread(0);
            v30 = *(_QWORD *)(v29 + 256);
            v160 = v30;
          }
          v31 = *(struct IMemObj **)(v30 + 1000);
          v189 = v31;
          v32 = SizeInWords;
          v33 = 2LL * SizeInWords;
          if ( !is_mul_ok(SizeInWords, 2u) )
            v33 = -1;
          v34 = (wchar_t *)operator new[](v33, v31, "sql\\ntdbms\\storeng\\dfs\\trans\\xdesmgr.cpp", 5153, 5u);
          v123 = v34;
          if ( v34 )
            operator delete[](0);
          v140 = v34;
          v105 = 0;
          v35 = v113;
          ((void (__fastcall *)(__int64, int *))g_dbtableFactory[2])(v113, &v105);
          if ( v105 )
          {
            SizeInWords_4 = 0;
            v36 = (const wchar_t *)((__int64 (__fastcall *)(__int64, int *))g_dbtableFactory[2])(v35, &SizeInWords_4);
          }
          else
          {
            v36 = &word_10280BED8;
          }
          wcscpy_s(v34, v32, v36);
          if ( v136 )
          {
            v119 = 0;
            v37 = ((__int64 (__fastcall *)(__int64, int *))g_dbtableFactory[2])(v136, &v119);
            v190 = v37;
            v38 = -1;
            do
              ++v38;
            while ( *(_WORD *)(v37 + 2 * v38) );
            v191 = v38;
            v122[0] = v38 + 1;
            v192 = NtCurrentTeb()->ThreadLocalStoragePointer;
            v39 = v192[SystemThread_TlsIndex] + SystemThread_TlsOffset;
            v193 = v39;
            v40 = *(_QWORD *)(v39 + 256);
            v161 = v40;
            if ( !v40 )
            {
              SystemThread::MakeMiniSOSThread(0);
              v40 = *(_QWORD *)(v39 + 256);
              v161 = v40;
            }
            v41 = *(struct IMemObj **)(v40 + 1000);
            v194 = v41;
            v42 = v122[0];
            v43 = 2LL * v122[0];
            if ( !is_mul_ok(v122[0], 2u) )
              v43 = -1;
            v44 = operator new[](v43, v41, "sql\\ntdbms\\storeng\\dfs\\trans\\xdesmgr.cpp", 5159, 5u);
            *(_QWORD *)&v122[1] = v44;
            if ( v44 )
              operator delete[](0);
            v141 = v44;
            v106 = 0;
            v45 = v136;
            ((void (__fastcall *)(__int64, int *))g_dbtableFactory[2])(v136, &v106);
            if ( v106 )
            {
              v120 = 0;
              v46 = (const wchar_t *)((__int64 (__fastcall *)(__int64, int *))g_dbtableFactory[2])(v45, &v120);
            }
            else
            {
              v46 = &word_10280BED8;
            }
            wcscpy_s((wchar_t *)v44, v42, v46);
            v47 = *(_QWORD *)(v45 + 4624);
            if ( v47 )
            {
              v195 = *(_QWORD *)(v45 + 4624);
              v48 = *(_QWORD *)(v47 + 9216);
              if ( v48 )
                v49 = (*(_BYTE *)(v48 + 1464) & 1) != 0 && *(_DWORD *)(v48 + 36) == 3;
              else
                v49 = 0;
              v196 = v47;
              if ( v48 && (*(_BYTE *)(v48 + 1464) & 1) != 0 && *(_DWORD *)(v48 + 36) == 3 )
              {
                v21 = v96;
                v50 = v113;
                v51 = v123;
                goto LABEL_91;
              }
            }
            else
            {
              v49 = 0;
            }
            if ( byte_10316E726
              && dword_1031852C8
              && (v162 = 34, v163 = 0x100000, (qword_10317F744 & 0x10000000000000LL) != 0) )
            {
              v177 = 34;
              v178 = 0x100000;
              XeSqlPkg::resolve_xact_commit::resolve_xact_commit((XeSqlPkg::resolve_xact_commit *)v240);
              v21 = v96;
              v241 = *((_DWORD *)v96 + 10);
              v242 = *((_WORD *)v96 + 22);
              v243 = v98;
              v244 = v99;
              v245 = v49;
              v50 = v113;
              v246 = *(_WORD *)(v113 + 40);
              v247 = v97;
              v248 = 2;
              v51 = v123;
              XeSqlPkg::redo_page_lsn_inconsistency::Setphysical_db_id(
                (XeSqlPkg::redo_page_lsn_inconsistency *)v240,
                v123);
              XeSqlPkg::resolve_xact_commit::Setcoordinator_database_name(
                (XeSqlPkg::resolve_xact_commit *)v240,
                *(const wchar_t *const *)&v122[1]);
              XeSqlPkg::resolve_xact_defer::Publish((XeSqlPkg::resolve_xact_defer *)v240);
            }
            else
            {
              v21 = v96;
              v50 = v113;
              v51 = v123;
            }
            v124 = *((_DWORD *)v21 + 10);
            v125 = *((_WORD *)v21 + 22);
            LODWORD(v93) = *(_DWORD *)(v50 + 928);
            ex_raise(34, 63, 21, 3, v93, v50 + 936, &v124);
LABEL_91:
            v181 = HIWORD(v97);
            if ( HIWORD(v97) )
            {
              v52 = 0;
              v164 = 0;
              goto LABEL_95;
            }
            v52 = *(_QWORD *)(v45 + 4624);
            v164 = v52;
            if ( !v52 )
            {
LABEL_95:
              LODWORD(v93) = HIWORD(v97);
              ex_raise(9, 30, 21, 1, v93, v45 + 936);
            }
            XactOutcome = XdesMgr::GetXactOutcome(v52 + 6600, &v98);
            if ( XactOutcome == 1 )
            {
              if ( byte_10316E726 )
              {
                if ( dword_1031852C8 )
                {
                  v169 = 34;
                  v170 = 0x40000;
                  if ( (qword_10317F744 & 0x4000000000000LL) != 0 )
                  {
                    v171 = 34;
                    v172 = 0x40000;
                    XeSqlPkg::resolve_xact_commit::resolve_xact_commit((XeSqlPkg::resolve_xact_commit *)v258);
                    v259 = *((_DWORD *)v21 + 10);
                    v260 = *((_WORD *)v21 + 22);
                    v261 = v98;
                    v262 = v99;
                    v263 = v49;
                    v264 = *(_WORD *)(v50 + 40);
                    v265 = v97;
                    v266 = 2;
                    XeSqlPkg::redo_page_lsn_inconsistency::Setphysical_db_id(
                      (XeSqlPkg::redo_page_lsn_inconsistency *)v258,
                      v51);
                    XeSqlPkg::resolve_xact_commit::Setcoordinator_database_name(
                      (XeSqlPkg::resolve_xact_commit *)v258,
                      *(const wchar_t *const *)&v122[1]);
                    XeSqlPkg::resolve_xact_commit::Publish((XeSqlPkg::resolve_xact_commit *)v258);
                  }
                }
              }
              (*(void (__fastcall **)(XdesRMFull *, __int64))(*(_QWORD *)v21 + 912LL))(v21, 1);
              v1 = (unsigned int *)v112;
            }
            else if ( XactOutcome - 2 < 2 )
            {
              if ( byte_10316E726 )
              {
                if ( dword_1031852C8 )
                {
                  v165 = 34;
                  v166 = 0x80000;
                  if ( (qword_10317F744 & 0x8000000000000LL) != 0 )
                  {
                    v167 = 34;
                    v168 = 0x80000;
                    XeSqlPkg::resolve_xact_commit::resolve_xact_commit((XeSqlPkg::resolve_xact_commit *)v249);
                    v250 = *((_DWORD *)v21 + 10);
                    v251 = *((_WORD *)v21 + 22);
                    v252 = v98;
                    v253 = v99;
                    v254 = v49;
                    v255 = *(_WORD *)(v50 + 40);
                    v256 = v97;
                    v257 = 2;
                    XeSqlPkg::redo_page_lsn_inconsistency::Setphysical_db_id(
                      (XeSqlPkg::redo_page_lsn_inconsistency *)v249,
                      v51);
                    XeSqlPkg::resolve_xact_commit::Setcoordinator_database_name(
                      (XeSqlPkg::resolve_xact_commit *)v249,
                      *(const wchar_t *const *)&v122[1]);
                    XeSqlPkg::resolve_xact_rollback::Publish((XeSqlPkg::resolve_xact_rollback *)v249);
                  }
                }
              }
              (*(void (__fastcall **)(XdesRMFull *, __int64))(*(_QWORD *)v21 + 912LL))(v21, 2);
              v1 = (unsigned int *)v112;
            }
            else
            {
              utassert_fail(1u, "FALSE", "xdesmgr.cpp", 5224, "Invalid switch value");
              v1 = (unsigned int *)v112;
            }
          }
          else
          {
            if ( byte_10316E726
              && dword_1031852C8
              && (v173 = 34, v174 = 0x100000, (qword_10317F744 & 0x10000000000000LL) != 0) )
            {
              v175 = 34;
              v176 = 0x100000;
              XeSqlPkg::resolve_xact_commit::resolve_xact_commit((XeSqlPkg::resolve_xact_commit *)v267);
              v21 = v96;
              v268 = *((_DWORD *)v96 + 10);
              v269 = *((_WORD *)v96 + 22);
              v270 = v98;
              v271 = v99;
              v272 = 0;
              v273 = *(_WORD *)(v35 + 40);
              v274 = v97;
              v275 = 2;
              XeSqlPkg::redo_page_lsn_inconsistency::Setphysical_db_id(
                (XeSqlPkg::redo_page_lsn_inconsistency *)v267,
                v34);
              XeSqlPkg::resolve_xact_commit::Setcoordinator_database_name((XeSqlPkg::resolve_xact_commit *)v267, 0);
              XeSqlPkg::resolve_xact_defer::Publish((XeSqlPkg::resolve_xact_defer *)v267);
            }
            else
            {
              v21 = v96;
            }
            v126 = *((_DWORD *)v21 + 10);
            v127 = *((_WORD *)v21 + 22);
            LODWORD(v94) = *(_DWORD *)(v35 + 928);
            ex_raise(34, 63, 21, 4, v94, v35 + 936, &v126);
            XactOutcome = v95;
          }
        }
      }
      if ( !dword_103184474 )
      {
        if ( !dword_1031852C8 || (v197 = CFeatureSwitchesLangSvc::GetCurrentInstance(v24, v23), !*(_BYTE *)(v197 + 663)) )
        {
          if ( !byte_1031852E4 && !FUseDTCOnManagedInstance() )
            goto LABEL_165;
        }
      }
      XactOutcome = (*(__int64 (__fastcall **)(XdesRMFull *))(*(_QWORD *)v21 + 896LL))(v21);
      if ( XactOutcome != 3 )
        goto LABEL_165;
      v55 = (_QWORD *)((char *)v21 + 8984);
      if ( !*((_QWORD *)v21 + 1123) )
        utassert_fail(
          XactOutcome - 2,
          "rollbackXdes->m_dtcInfo != NULL",
          "xdesmgr.cpp",
          5251,
          "prepare log record dtc info can not be null at this time");
      rguid = 0;
      if ( dword_1031852C8 )
      {
        DTCStateByDbId = (struct CDTCState *)*((_QWORD *)v21 + 85);
      }
      else
      {
        v115 = *(_WORD *)(*((_QWORD *)v21 + 6) + 1720LL);
        DTCStateByDbId = GetDTCStateByDbId(v115);
      }
      v108 = DTCStateByDbId;
      v57 = DTCStateByDbId;
      v58 = *v55;
      if ( *((_DWORD *)v57 + 87) == 2 )
      {
        v198 = *v55;
        v59 = (GUID *)(v58 + 4);
        rguid = (GUID *)(v58 + 4);
        goto LABEL_137;
      }
      v199 = *v55;
      rguid = (GUID *)v58;
      if ( (qword_10317AD29 & 0x40000000000000LL) == 0 )
      {
        v200 = NtCurrentTeb()->ThreadLocalStoragePointer;
        v201 = (__int64 *)(v200[SystemThread_TlsIndex] + SystemThread_TlsOffset);
        v60 = *v201;
        v202 = v60;
        if ( v60 )
        {
          v61 = **(struct CSessionTraceFlags ***)(v60 + 56);
          v203 = v61;
          if ( v61 )
          {
            if ( CSessionTraceFlags::CheckSessionTraceInternal(v61, 0xD7Eu) )
              goto LABEL_160;
          }
        }
        if ( (qword_10317AD29 & 0x80000000000000LL) != 0 )
          goto LABEL_159;
        v204 = NtCurrentTeb()->ThreadLocalStoragePointer;
        v205 = (__int64 *)(v204[SystemThread_TlsIndex] + SystemThread_TlsOffset);
        v62 = *v205;
        v206 = v62;
        if ( v62 )
        {
          v63 = **(struct CSessionTraceFlags ***)(v62 + 56);
          v207 = v63;
          if ( v63 )
          {
            if ( CSessionTraceFlags::CheckSessionTraceInternal(v63, 0xD7Fu) )
              goto LABEL_159;
          }
        }
        v21 = v96;
        v59 = rguid;
LABEL_137:
        XactOutcome = CDTCState::ResolvePreparedXact(v108, *v55, *((unsigned int *)v21 + 2248), v59);
        if ( XactOutcome != 3 )
          goto LABEL_164;
        if ( dword_1031852C8 && *((_DWORD *)v57 + 87) != 2 )
        {
          v64 = *(_BYTE *)((*(__int64 (__fastcall **)(struct IServerConfiguration *))(*(_QWORD *)s_pServerConf + 504LL))(s_pServerConf)
                         + 241);
          v100 = v64;
          if ( v64 == 2 )
          {
            XactOutcome = 2;
            goto LABEL_144;
          }
          if ( v64 == 1 )
          {
            XactOutcome = 1;
LABEL_144:
            StringFromGUID2(rguid, sz, 39);
            v65 = *(_QWORD *)(*(_QWORD *)v1 + 1712LL);
            v208 = v65;
            v121 = 0;
            v66 = L"committed";
            if ( v64 == 2 )
              v66 = L"aborted";
            v67 = ((__int64 (__fastcall *)(__int64, int *))g_dbtableFactory[2])(v65, &v121);
            log_unlocalized_systemmetadata(
              L"The in-doubt transaction with UOW  %ls in the database '%ls' has been %ls as per the policy 'in-doubt xact resolution'\n",
              sz,
              v67,
              v66);
LABEL_162:
            v111 = 0x2000000000000018LL;
            if ( (qword_10317F720 & 0x20000000) != 0 )
            {
              XeSqlPkg::dtc_transaction_recovery::dtc_transaction_recovery((XeSqlPkg::dtc_transaction_recovery *)v281);
              v283 = *((_BYTE *)v57 + 348);
              v284 = XactOutcome;
              v285 = v76;
              v77 = v282 + 16;
              v219 = v282 + 16;
              *(_QWORD *)(v282 + 16) = rguid;
              *(_DWORD *)(v77 + 8) = 16;
              *(_WORD *)(v77 + 12) = 3;
              *(_WORD *)(v77 + 14) = 0;
              v78 = v282 + 32;
              v220 = v282 + 32;
              *(_QWORD *)(v282 + 32) = (char *)v108 + 112;
              *(_DWORD *)(v78 + 8) = 16;
              *(_WORD *)(v78 + 12) = 4;
              *(_WORD *)(v78 + 14) = 0;
              XeSqlPkg::dtc_transaction_recovery::Publish((XeSqlPkg::dtc_transaction_recovery *)v281);
            }
LABEL_164:
            (*(void (__fastcall **)(XdesRMFull *, _QWORD))(*(_QWORD *)v21 + 912LL))(v21, XactOutcome);
LABEL_165:
            if ( dword_103184474 )
              goto LABEL_171;
            v79 = dword_1031852C8;
            if ( dword_1031852C8 )
            {
              v221 = CFeatureSwitchesLangSvc::GetCurrentInstance(v54, v53);
              if ( !*(_BYTE *)(v221 + 663) )
              {
                v79 = dword_1031852C8;
                goto LABEL_169;
              }
LABEL_171:
              if ( XactOutcome != 1 )
              {
LABEL_172:
                v80 = (*(__int64 (__fastcall **)(XdesRMFull *))(*(_QWORD *)v21 + 136LL))(v21);
                v81 = v80 == 0;
                v101 = v80 == 0;
                v82 = *(_QWORD *)v137;
                if ( v80 )
                {
                  v225 = 17;
                  v111 = 0;
                  v226 = *(_QWORD *)(v82 + 1736);
                  v227 = 0;
                  v143 = v226;
                  v145 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD))(*(_QWORD *)v226 + 128LL))(
                           v82,
                           v144,
                           v226,
                           0);
                  (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v145 + 8LL))(v145, 0, 1);
                }
                else
                {
                  v222 = 17;
                  v111 = 0;
                  v223 = *(_QWORD *)(v82 + 1744);
                  v224 = 0;
                  v131 = v223;
                  v133 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD))(*(_QWORD *)v223 + 56LL))(
                           v82,
                           v132,
                           v223,
                           0);
                  (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v133 + 8LL))(v133, 0, 1);
                  (*(void (__fastcall **)(__int64, XdesRMFull *))(*(_QWORD *)v133 + 80LL))(v133, v21);
                }
                v83 = &v142;
                if ( v81 )
                  v83 = &v130;
                v228 = v83;
                v149 = 0;
                v150 = 0;
                v151 = 0;
                v152 = 0;
                v153 = 0;
                v229 = *(struct IMemObj **)(*(_QWORD *)(*(_QWORD *)v1 + 1712LL) + 688LL);
                IndexErrorTable::Init((IndexErrorTable *)&v149, 100, v229);
                v84 = (struct IndexErrorTable *)&v149;
                if ( !*(_BYTE *)(*(_QWORD *)v1 + 27257LL) )
                  v84 = 0;
                v85 = (const struct LSN *)(*(__int64 (__fastcall **)(XdesRMFull *, char *))(*(_QWORD *)v21 + 288LL))(
                                            v21,
                                            v286);
                XdesRMReadWrite::RollbackToLsn(
                  v21,
                  v85,
                  (struct LogIter *)v83,
                  v84,
                  (const struct AllocUnitId *)&x_MDAllocUnitIdBad);
                IndexErrorTable::Cleanup((IndexErrorTable *)&v149);
                if ( v149 )
                {
                  operator delete[](v149);
                  v149 = 0;
                  v150 = 0;
                }
              }
              (*(void (__fastcall **)(XdesRMFull *))(*(_QWORD *)v21 + 904LL))(v21);
              (*(void (__fastcall **)(XdesRMFull *, _QWORD))(*(_QWORD *)v21 + 880LL))(v21, 0);
              v180 = 0;
              v86 = (CDTCState *)*((_QWORD *)v21 + 85);
              v230 = v86;
              if ( FUseDTCOnManagedInstance() && *((_DWORD *)v86 + 87) != 2 && *((_QWORD *)v21 + 1123) )
                CDTCState::decrementRecoveryCount(v86);
              (*(void (__fastcall **)(XdesRMFull *, __int64))(*(_QWORD *)v21 + 760LL))(v21, 1);
              DeferredLockSpaceIdManager::RemoveLockSpaceId(v139, (const struct LockSpaceId *)&v233);
              ++v103;
              ExcHandler::~ExcHandler((ExcHandler *)v239);
              goto LABEL_216;
            }
LABEL_169:
            if ( byte_1031852E4 || v79 )
              goto LABEL_171;
            goto LABEL_172;
          }
        }
        if ( (qword_10317AD29 & 0x40000000000000LL) == 0 )
        {
          v209 = NtCurrentTeb()->ThreadLocalStoragePointer;
          v210 = (__int64 *)(v209[SystemThread_TlsIndex] + SystemThread_TlsOffset);
          v68 = *v210;
          v211 = v68;
          if ( !v68
            || (v69 = **(struct CSessionTraceFlags ***)(v68 + 56), (v212 = v69) == 0)
            || (v156 = CSessionTraceFlags::CheckSessionTraceInternal(v69, 0xD7Eu)) == 0 )
          {
            if ( (qword_10317AD29 & 0x80000000000000LL) == 0 )
            {
              v213 = NtCurrentTeb()->ThreadLocalStoragePointer;
              v214 = (__int64 *)(v213[SystemThread_TlsIndex] + SystemThread_TlsOffset);
              v70 = *v214;
              v215 = v70;
              if ( !v70
                || (v71 = **(struct CSessionTraceFlags ***)(v70 + 56), (v231 = v71) == 0)
                || (v182 = CSessionTraceFlags::CheckSessionTraceInternal(v71, 0xD7Fu)) == 0 )
              {
                if ( !StringFromGUID2(rguid, v288, 39) )
                {
                  LOBYTE(v72) = -41;
                  ex_raise_oom(v72);
                }
                log_unlocalized_systemmetadata(
                  L"SQL Server detected a DTC in-doubt transaction with UOW  %ls.Please resolve it following the guideline"
                   " for Troubleshooting DTC Transactions.\n",
                  v288);
                v183 = 24;
                v184 = 0x20000000;
                if ( (qword_10317F720 & 0x20000000) != 0 )
                {
                  XeSqlPkg::dtc_transaction_recovery::dtc_transaction_recovery((XeSqlPkg::dtc_transaction_recovery *)v276);
                  v278 = *((_BYTE *)v57 + 348);
                  v279 = 3;
                  v280 = 0;
                  v73 = v277 + 16;
                  v217 = v277 + 16;
                  *(_QWORD *)(v277 + 16) = rguid;
                  *(_DWORD *)(v73 + 8) = 16;
                  *(_WORD *)(v73 + 12) = 3;
                  *(_WORD *)(v73 + 14) = 0;
                  v74 = v277 + 32;
                  v218 = v277 + 32;
                  *(_QWORD *)(v277 + 32) = (char *)v108 + 112;
                  *(_DWORD *)(v74 + 8) = 16;
                  *(_WORD *)(v74 + 12) = 4;
                  *(_WORD *)(v74 + 14) = 0;
                  XeSqlPkg::dtc_transaction_recovery::Publish((XeSqlPkg::dtc_transaction_recovery *)v276);
                  v21 = v96;
                  v128 = *((_DWORD *)v96 + 10);
                  v129 = *((_WORD *)v96 + 22);
                  v75 = *(_QWORD *)(*(_QWORD *)v1 + 1712LL);
                  LODWORD(v93) = *(_DWORD *)(v75 + 928);
                  ex_raise(34, 37, 21, 4, v93, v75 + 936, &v128);
                }
                goto LABEL_164;
              }
            }
LABEL_159:
            XactOutcome = 1;
            v21 = v96;
            goto LABEL_162;
          }
LABEL_160:
          v21 = v96;
        }
      }
      XactOutcome = 2;
      goto LABEL_162;
    }
    catch ( SQLError v185 )
    {
      try
      {
        ExceptionBackout::ExceptionBackout((ExceptionBackout *)v234, (const struct SQLError *)v185);
        if ( v185[4] == 1 )
          v92 = v185[0];
        else
          v92 = LOWORD(v185[0]);
        RecoveryMgr::CheckAndMarkDeferrableEnclaveError(v92, *v135, *(unsigned __int16 *)(MEMORY[0x30] + 1720LL), v91);
        ++v102;
        v138 = 0;
        ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v234);
      }
      catch ( ShortStackException )
      {
      }
      v1 = (unsigned int *)v135;
      v112 = (XdesMgr *)v135;
    }
LABEL_216:
    v2 = v107;
    v87 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v88 = *(struct Worker **)(v87 + 256);
    if ( !v88 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v88 = *(struct Worker **)(v87 + 256);
    }
    if ( *((_DWORD *)v88 + 139) )
      ExceptionPostCatchActions(v88);
LABEL_194:
    if ( CommonGlobalState::m_PerfCountersEnabled )
      PerfmonManager::SetInstanceCounterValue(
        (PerfmonManager *)&ResourceStr,
        5u,
        0x50u,
        v1[4],
        *(unsigned __int16 *)(*(_QWORD *)v1 + 1720LL));
    operator delete[](v140);
    operator delete[](v141);
    v130 = &SLogIterForward::`vftable';
    if ( v133 )
    {
      (**(void (__fastcall ***)(__int64, __int64))v133)(v133, 1);
      v133 = 0;
    }
    v142 = &SLogIterForward::`vftable';
    v9 = &LogIter::`vftable';
    v8 = &SLogIterForward::`vftable';
    v7 = &SLogIterForward::`vftable';
    if ( v145 )
    {
      (**(void (__fastcall ***)(__int64, __int64, void **, void **))v145)(
        v145,
        1,
        &SLogIterForward::`vftable',
        &SLogIterForward::`vftable');
      v145 = 0;
      goto LABEL_6;
    }
  }
  if ( !v102 )
  {
    *(_BYTE *)(*(_QWORD *)v1 + 7378LL) = 0;
    v90 = *(_QWORD *)v1;
    if ( !*(_BYTE *)(*(_QWORD *)v1 + 6872LL)
      && !*(_QWORD *)(v90 + 6880)
      && !*(_BYTE *)(*(_QWORD *)(v90 + 6600) + 7378LL) )
    {
      *(_BYTE *)(v90 + 6872) = 1;
    }
  }
  if ( v103 > 0 )
  {
    ex_callprint(3407, 10, 2);
    if ( *(_BYTE *)(*(_QWORD *)v1 + 7390LL) )
      DeferredAllocUnitDrop::ScanDroppedAllocUnitsAfterRecovery(*(struct RecoveryUnit **)v1, 0, 1);
  }
  *(_DWORD *)(v148 + 616) &= ~v147;
}

```

## disassembly

```asm
0x101d994c0  push    rdi
0x101d994c2  push    r12
0x101d994c4  push    r13
0x101d994c6  push    r14
0x101d994c8  push    r15
0x101d994ca  mov     eax, 1470h
0x101d994cf  call    _alloca_probe
0x101d994d4  sub     rsp, rax
0x101d994d7  mov     [rsp+1498h+var_1120], 0FFFFFFFFFFFFFFFEh
0x101d994e3  mov     [rsp+1498h+arg_8], rbx
0x101d994eb  mov     [rsp+1498h+arg_10], rsi
0x101d994f3  mov     rax, cs:__security_cookie
0x101d994fa  xor     rax, rsp
0x101d994fd  mov     [rsp+1498h+var_38], rax
0x101d99505  mov     r12, rcx
0x101d99508  mov     [rsp+1498h+var_13F8], rcx
0x101d99510  mov     [rsp+1498h+var_1360], rcx
0x101d99518  mov     [rsp+1498h+var_1350], rcx
0x101d99520  xor     edi, edi
0x101d99522  lea     r14d, [rdi+1]
0x101d99526  mov     [rsp+1498h+var_1434], edi
0x101d9952a  mov     [rsp+1498h+var_1438], edi
0x101d9952e  mov     [rsp+1498h+var_1448], edi
0x101d99532  mov     [rsp+1498h+var_1444], edi
0x101d99536  mov     [rsp+1498h+var_1440], di
0x101d9953b  mov     [rsp+1498h+var_1348], rdi
0x101d99543  mov     [rsp+1498h+var_1454], 3
0x101d9954b  lea     rax, [rcx+8]
0x101d9954f  mov     [rsp+1498h+var_1410], rax
0x101d99557  mov     [rsp+1498h+var_1408], edi
0x101d9955e  mov     r8, gs:58h
0x101d99567  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101d9956e  mov     ecx, [rax]
0x101d99570  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101d99577  mov     edx, [rax]
0x101d99579  add     rdx, [r8+rcx*8]
0x101d9957d  mov     rax, [r12]
0x101d99581  mov     rax, [rax+23F0h]
0x101d99588  mov     [rsp+1498h+var_1340], rax
0x101d99590  cmp     [rdx+18h], rdi
0x101d99594  jnz     short loc_101D995B8
0x101d99596  mov     [rsp+1498h+var_1478], rdi
0x101d9959b  mov     r9d, 13D3h
0x101d995a1  lea     r8, aXdesmgrCpp; "xdesmgr.cpp"
0x101d995a8  lea     rdx, aPcurrenttaskpr; "pCurrentTaskProxy"
0x101d995af  mov     ecx, r14d
0x101d995b2  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x101d995b8  mov     [rsp+1498h+var_1300], edi
0x101d995bf  mov     rdx, gs:58h
0x101d995c8  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101d995cf  mov     ecx, [rax]
0x101d995d1  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101d995d8  mov     ebx, [rax]
0x101d995da  add     rbx, [rdx+rcx*8]
0x101d995de  mov     rdx, [rbx+100h]
0x101d995e5  test    rdx, rdx
0x101d995e8  jnz     short loc_101D995F9
0x101d995ea  xor     ecx, ecx
0x101d995ec  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x101d995f2  mov     rdx, [rbx+100h]
0x101d995f9  mov     [rsp+1498h+var_12F8], rdx
0x101d99601  mov     ecx, [rdx+268h]
0x101d99607  mov     eax, ecx
0x101d99609  and     eax, 1
0x101d9960c  xor     eax, 1
0x101d9960f  mov     [rsp+1498h+var_1300], eax
0x101d99616  or      ecx, 1
0x101d99619  mov     [rdx+268h], ecx
0x101d9961f  mov     r15, 0FFFFFFFFFFFFFFFFh
0x101d99626  lea     r13d, [r15+5]
0x101d9962a  lea     r9, ??_7SLogIterForward@@6B@; const SLogIterForward::`vftable'
0x101d99631  lea     r8, ??_7SLogIterForward@@6B@; const SLogIterForward::`vftable'
0x101d99638  lea     rax, ??_7SLogIterForward@@6B@; const SLogIterForward::`vftable'
0x101d9963f  lea     rdx, ??_7LogIter@@6B@; const LogIter::`vftable'
0x101d99646  nop     word ptr [rax+rax+00000000h]
0x101d99650  lea     rcx, ??_7SLogIterForward@@6B@; const SLogIterForward::`vftable'
0x101d99657  test    r14d, r14d
0x101d9965a  jz      loc_101D9AE0D
0x101d99660  mov     [rsp+1498h+var_1328], rdx
0x101d99668  mov     [rsp+1498h+var_1328], rax
0x101d99670  mov     [rsp+1498h+var_1320], rdi
0x101d99678  mov     [rsp+1498h+var_1318], 5
0x101d99683  mov     [rsp+1498h+var_1310], rdi
0x101d9968b  mov     [rsp+1498h+var_1308], 0
0x101d99693  mov     [rsp+1498h+var_1328], r8
0x101d9969b  mov     [rsp+1498h+var_1388], rdx
0x101d996a3  mov     [rsp+1498h+var_1388], rcx
0x101d996ab  mov     [rsp+1498h+var_1380], rdi
0x101d996b3  mov     [rsp+1498h+var_1378], 5
0x101d996be  mov     [rsp+1498h+var_1370], rdi
0x101d996c6  mov     [rsp+1498h+var_1368], 0
0x101d996ce  mov     [rsp+1498h+var_1388], r9
0x101d996d6  mov     [rsp+1498h+var_1330], rdi
0x101d996de  mov     [rsp+1498h+var_1338], rdi
0x101d996e6  mov     eax, gs:48h
0x101d996ee  mov     esi, eax
0x101d996f0  mov     rax, [rsp+1498h+var_1410]
0x101d996f8  mov     ecx, [rax]
0x101d996fa  test    ecx, ecx
0x101d996fc  jnz     short loc_101D99723
0x101d996fe  mov     rcx, [rsp+1498h+var_1410]
0x101d99706  xor     eax, eax
0x101d99708  lock cmpxchg [rcx], rsi
0x101d9970d  mov     eax, edi
0x101d9970f  setz    al
0x101d99712  test    eax, eax
0x101d99714  jz      short loc_101D99723
0x101d99716  mov     rsi, [rsp+1498h+var_1410]
0x101d9971e  jmp     loc_101D9981C
0x101d99723  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x101d9972a  mov     ecx, [rax]
0x101d9972c  and     ecx, 84h
0x101d99732  cmp     cl, 84h
0x101d99735  jnz     loc_101D99809
0x101d9973b  mov     r14, rdi
0x101d9973e  mov     rdx, gs:58h
0x101d99747  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101d9974e  mov     ecx, [rax]
0x101d99750  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101d99757  mov     r8d, [rax]
0x101d9975a  add     r8, [rdx+rcx*8]
0x101d9975e  jz      short loc_101D99770
0x101d99760  cmp     [r8+110h], r8
0x101d99767  jnz     short loc_101D99770
0x101d99769  mov     r14, [r8+100h]
0x101d99770  test    r14, r14
0x101d99773  jz      loc_101D99809
0x101d99779  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x101d99780  cmp     dword ptr [rax], 0
0x101d99783  jz      short loc_101D9979D
0x101d99785  lea     rcx, [rsp+1498h+PerformanceCount]; lpPerformanceCount
0x101d9978d  call    cs:__imp_QueryPerformanceCounter
0x101d99793  mov     rbx, qword ptr [rsp+1498h+PerformanceCount]
0x101d9979b  jmp     short loc_101D997A5
0x101d9979d  mov     rbx, ds:7FFE0008h
0x101d997a5  mov     rdx, rsi
0x101d997a8  mov     rsi, [rsp+1498h+var_1410]
0x101d997b0  mov     rcx, rsi
0x101d997b3  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0JJ@$08$0BAB@@@AEAAX_K@Z; Spinlock<153,9,257>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x101d997b8  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x101d997bf  cmp     dword ptr [rax], 0
0x101d997c2  jz      short loc_101D997DC
0x101d997c4  lea     rcx, [rsp+1498h+var_12B0]; lpPerformanceCount
0x101d997cc  call    cs:__imp_QueryPerformanceCounter
0x101d997d2  mov     rax, qword ptr [rsp+1498h+var_12B0]
0x101d997da  jmp     short loc_101D997EC
0x101d997dc  mov     rax, ds:7FFE0008h
0x101d997e4  mov     rsi, [rsp+1498h+var_1410]
0x101d997ec  cmp     rax, rbx
0x101d997ef  jb      short loc_101D997FD
0x101d997f1  sub     rax, rbx
0x101d997f4  add     [r14+0C78h], rax
0x101d997fb  jmp     short loc_101D9981C
0x101d997fd  mov     rax, rdi
0x101d99800  add     [r14+0C78h], rax
0x101d99807  jmp     short loc_101D9981C
0x101d99809  mov     rdx, rsi
0x101d9980c  mov     rsi, [rsp+1498h+var_1410]
0x101d99814  mov     rcx, rsi
0x101d99817  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0JJ@$08$0BAB@@@AEAAX_K@Z; Spinlock<153,9,257>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x101d9981c  mov     [rsp+1498h+var_1408], 1
0x101d99827  mov     rax, [rsp+1498h+var_1350]
0x101d9982f  add     rax, 18h
0x101d99833  mov     rcx, [rsp+1498h+var_1348]
0x101d9983b  mov     rbx, rdi
0x101d9983e  test    rcx, rcx
0x101d99841  jz      short loc_101D9984C
0x101d99843  mov     rcx, [rcx+22D8h]
0x101d9984a  jmp     short loc_101D99850
0x101d9984c  mov     rcx, [rax+8]
0x101d99850  cmp     rcx, rax
0x101d99853  cmovz   rcx, rdi
0x101d99857  mov     r14d, edi
0x101d9985a  test    rcx, rcx
0x101d9985d  lea     rax, [rcx-22D0h]
0x101d99864  cmovnz  rbx, rax
0x101d99868  test    rbx, rbx
0x101d9986b  mov     [rsp+1498h+var_1450], rbx
0x101d99870  jz      loc_101D9AD02
0x101d99876  mov     rax, [rbx]
0x101d99879  mov     rcx, rbx
0x101d9987c  call    qword ptr [rax+278h]
0x101d99882  test    eax, eax
0x101d99884  jnz     short loc_101D998A0
0x101d99886  mov     rcx, [rbx+22D8h]
0x101d9988d  lea     rax, [r12+18h]
0x101d99892  cmp     rcx, rax
0x101d99895  jz      loc_101D9AD02
0x101d9989b  mov     rbx, rdi
0x101d9989e  jmp     short loc_101D9985A
0x101d998a0  mov     [rsp+1498h+var_1420], 1
0x101d998a8  movups  xmm0, xmmword ptr [rbx+78h]
0x101d998ac  movups  [rsp+1498h+var_1098], xmm0
0x101d998b4  mov     rax, cs:__imp_?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA; bool SOS_PublicGlobals::sm_SpinlockStatSnapshot
0x101d998bb  cmp     byte ptr [rax], 0
0x101d998be  jz      short loc_101D998E7
0x101d998c0  call    cs:__imp_rand
0x101d998c6  mov     r8d, eax
0x101d998c9  mov     eax, 66666667h
0x101d998ce  imul    r8d
0x101d998d1  sar     edx, 1
0x101d998d3  mov     ecx, edx
0x101d998d5  shr     ecx, 1Fh
0x101d998d8  add     edx, ecx
0x101d998da  lea     ecx, [rdx+rdx*4]
0x101d998dd  cmp     r8d, ecx
0x101d998e0  jnz     short loc_101D998E7
0x101d998e2  call    ?UpdateStatSnapshot@?$Spinlock@$0JJ@$08$0BAB@@@AEAAXXZ; Spinlock<153,9,257>::UpdateStatSnapshot(void)
0x101d998e7  mov     [rsi], rdi
0x101d998ea  mov     [rsp+1498h+var_1408], edi
0x101d998f1  xor     edx, edx; unsigned __int16
0x101d998f3  mov     [rsp+1498h+var_1470], rdi; struct Worker *
0x101d998f8  lea     rax, ?hdl_recoveryThroughError@@YAHHHHHPEAD@Z; hdl_recoveryThroughError(int,int,int,int,char *)
0x101d998ff  mov     [rsp+1498h+var_1478], rax; int (*)(int, int, int, int, char *)
0x101d99904  xor     r9d, r9d; unsigned __int8
0x101d99907  xor     r8d, r8d; unsigned __int8
0x101d9990a  lea     rcx, [rsp+1498h+var_1058]; this
0x101d99912  call    ??0ExcHandler@@QEAA@GEEP6AHHHHHPEAD@ZPEAVWorker@@@Z; ExcHandler::ExcHandler(ushort,uchar,uchar,int (*)(int,int,int,int,char *),Worker *)
0x101d99917  nop
0x101d99918  mov     [rsp+1498h+var_1248], rbx
0x101d99920  mov     r8, gs:58h
0x101d99929  mov     [rsp+1498h+var_10A0], r8
0x101d99931  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101d99938  mov     ecx, [rax]
0x101d9993a  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101d99941  mov     edx, [rax]
0x101d99943  add     rdx, [r8+rcx*8]
0x101d99947  mov     [rsp+1498h+var_1078], rdx
0x101d9994f  mov     rdx, [rdx+18h]
0x101d99953  mov     [rsp+1498h+var_1070], rdx
0x101d9995b  mov     rsi, [rsp+1498h+var_1450]
0x101d99960  mov     rax, [rsi]
0x101d99963  mov     rcx, rsi
0x101d99966  call    qword ptr [rax+370h]
0x101d9996c  nop
0x101d9996d  mov     rax, [rsi]
0x101d99970  mov     rcx, rsi
0x101d99973  call    qword ptr [rax+380h]
0x101d99979  mov     r14d, eax
0x101d9997c  mov     [rsp+1498h+var_1454], eax
0x101d99980  cmp     cs:dword_1031852C8, 0
0x101d99987  jz      loc_101D9A30C
0x101d9998d  cmp     eax, 3
0x101d99990  jnz     loc_101D9A30C
0x101d99996  cmp     cs:dword_103184474, 0
0x101d9999d  jnz     short loc_101D999D1
0x101d9999f  call    cs:__imp_?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ; CFeatureSwitchesLangSvc::GetCurrentInstance(void)
0x101d999a5  mov     [rsp+1498h+var_1068], rax
0x101d999ad  cmp     byte ptr [rax+297h], 0
0x101d999b4  jnz     short loc_101D999D1
0x101d999b6  cmp     cs:byte_1031852E4, 0
0x101d999bd  jnz     short loc_101D999D1
0x101d999bf  call    ?FUseDTCOnManagedInstance@@YA_NXZ; FUseDTCOnManagedInstance(void)
0x101d999c4  test    al, al
0x101d999c6  jnz     short loc_101D999D1
0x101d999c8  lea     rax, [rsi+2318h]
0x101d999cf  jmp     short loc_101D999E2
0x101d999d1  lea     rax, [rsi+2318h]
0x101d999d8  cmp     qword ptr [rax], 0
0x101d999dc  jnz     loc_101D9A30C
0x101d999e2  lea     r9, [rsi+2320h]; int *
0x101d999e9  mov     [rsp+1498h+var_1460], rdi; struct LedgerTransaction **
0x101d999ee  lea     rcx, [rsp+1498h+var_12C8]
0x101d999f6  mov     [rsp+1498h+var_1468], rcx; int *
0x101d999fb  mov     [rsp+1498h+var_1470], rdi; wchar_t *
0x101d99a00  mov     [rsp+1498h+var_1478], rax; unsigned __int8 **
0x101d99a05  lea     r8, [rsp+1498h+var_1444]; struct XdesId *
0x101d99a0a  lea     rdx, [rsp+1498h+var_1448]; struct FullPruId *
0x101d99a0f  mov     rcx, rsi; this
0x101d99a12  call    ?GetPrepareInfo@XdesRMFull@@QEAAXAEAVFullPruId@@AEAVXdesId@@AEAHPEAPEAEPEA_W2PEAPEAVLedgerTransaction@@@Z; XdesRMFull::GetPrepareInfo(FullPruId &,XdesId &,int &,uchar * *,wchar_t *,int &,LedgerTransaction * *)
0x101d99a17  movzx   ecx, word ptr [rsp+1498h+var_1448]
0x101d99a1c  mov     rax, cs:__imp_?g_dbtableFactory@@3UDBTableFactory@@A; DBTableFactory g_dbtableFactory
0x101d99a23  call    qword ptr [rax+20h]
0x101d99a26  mov     [rsp+1498h+var_1358], rax
0x101d99a2e  mov     rax, [rsi+30h]
0x101d99a32  movzx   ecx, word ptr [rax+6B8h]
0x101d99a39  mov     [rsp+1498h+var_13E8], cx
0x101d99a41  mov     rax, cs:__imp_?g_dbtableFactory@@3UDBTableFactory@@A; DBTableFactory g_dbtableFactory
0x101d99a48  call    qword ptr [rax+20h]
0x101d99a4b  mov     [rsp+1498h+var_13F0], rax
0x101d99a53  mov     [rsp+1498h+var_13E4], edi
0x101d99a5a  lea     rdx, [rsp+1498h+var_13E4]
0x101d99a62  mov     rcx, rax
0x101d99a65  mov     rax, cs:__imp_?g_dbtableFactory@@3UDBTableFactory@@A; DBTableFactory g_dbtableFactory
0x101d99a6c  call    qword ptr [rax+10h]
0x101d99a6f  mov     [rsp+1498h+var_1060], rax
0x101d99a77  mov     rcx, r15
0x101d99a7a  nop     word ptr [rax+rax+00h]
0x101d99a80  inc     rcx
0x101d99a83  cmp     word ptr [rax+rcx*2], 0
0x101d99a88  jnz     short loc_101D99A80
0x101d99a8a  mov     [rsp+1498h+var_1210], rcx
0x101d99a92  lea     eax, [rcx+1]
0x101d99a95  mov     dword ptr [rsp+1498h+SizeInWords], eax
0x101d99a9c  mov     rdx, gs:58h
0x101d99aa5  mov     [rsp+1498h+var_1208], rdx
0x101d99aad  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101d99ab4  mov     ecx, [rax]
0x101d99ab6  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101d99abd  mov     ebx, [rax]
  ... truncated ...
```
