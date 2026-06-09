# ExecuteClassifier(void)

- ea: `0x100550410`
- end: `0x100550611`
- name: `?ExecuteClassifier@@YAXXZ`
- size: `513`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `21`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x100555e20`
- `0x100f2eaf0`

## callees

- `0x100401070`
- `0x1004012d0`
- `0x100401340`
- `0x100401433`
- `0x100403080`
- `0x100409b70`
- `0x100409cb0`
- `0x10040aaa0`
- `0x1004223e0`
- `0x100550410`
- `0x100550620`
- `0x1007639d0`
- `0x1007a7020`
- `0x100de61c0`
- `0x100de64b0`
- `0x100de6a80`
- `0x100de8400`
- `0x100f7d190`
- `0x10118fba0`
- `0x10118fe70`
- `0x101e88ac0`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x100de7d44`
- `KERNEL32!QueryPerformanceCounter` at `0x100de7d44`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x100550574`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x100de6cce`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x100de6e84`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x100de705c`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x100de7afb`
- `sqldk!?sm_isResourceManagerEnabled@SOS_PublicGlobals@@2HA` at `0x10055045c`
- `sqldk!?sm_ResourceManager@SOS_PublicGlobals@@2VSOS_ResourceManager@@A` at `0x10055044d`
- `sqldk!?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A` at `0x100de8237`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100de7d2c`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100de822b`
- `sqldk!?LookupGroup@SOS_ResourceManager@@QEAA?AW4SOS_RESULT@@PEB_W_JPEAPEAVSOS_ResourceGroup@@@Z` at `0x100de6f22`
- `sqldk!?LookupGroup@SOS_ResourceManager@@QEAA?AW4SOS_RESULT@@PEB_W_JPEAPEAVSOS_ResourceGroup@@@Z` at `0x100de6f7e`
- `sqldk!?LookupGroup@SOS_ResourceManager@@QEAA?AW4SOS_RESULT@@PEB_W_JPEAPEAVSOS_ResourceGroup@@@Z` at `0x100de7002`
- `sqldk!?LookupGroup@SOS_ResourceManager@@QEAA?AW4SOS_RESULT@@PEB_W_JPEAPEAVSOS_ResourceGroup@@@Z` at `0x100de7f92`
- `sqldk!?LookupGroup@SOS_ResourceManager@@QEAA?AW4SOS_RESULT@@PEB_W_JPEAPEAVSOS_ResourceGroup@@@Z` at `0x100de6f22`
- `sqldk!?LookupGroup@SOS_ResourceManager@@QEAA?AW4SOS_RESULT@@PEB_W_JPEAPEAVSOS_ResourceGroup@@@Z` at `0x100de6f7e`
- `sqldk!?LookupGroup@SOS_ResourceManager@@QEAA?AW4SOS_RESULT@@PEB_W_JPEAPEAVSOS_ResourceGroup@@@Z` at `0x100de7002`
- `sqldk!?LookupGroup@SOS_ResourceManager@@QEAA?AW4SOS_RESULT@@PEB_W_JPEAPEAVSOS_ResourceGroup@@@Z` at `0x100de7f92`
- `sqldk!?BindCurrentTaskToGroup@SOS_ResourceManager@@QEAAXPEAVSOS_ResourceGroup@@@Z` at `0x1005505ce`
- `sqldk!?BindCurrentTaskToGroup@SOS_ResourceManager@@QEAAXPEAVSOS_ResourceGroup@@@Z` at `0x100de7c7e`
- `sqldk!?BindCurrentTaskToGroup@SOS_ResourceManager@@QEAAXPEAVSOS_ResourceGroup@@@Z` at `0x100de813d`
- `sqldk!?BindCurrentTaskToGroup@SOS_ResourceManager@@QEAAXPEAVSOS_ResourceGroup@@@Z` at `0x1005505ce`
- `sqldk!?BindCurrentTaskToGroup@SOS_ResourceManager@@QEAAXPEAVSOS_ResourceGroup@@@Z` at `0x100de7c7e`
- `sqldk!?BindCurrentTaskToGroup@SOS_ResourceManager@@QEAAXPEAVSOS_ResourceGroup@@@Z` at `0x100de813d`
- `sqldk!?Destroy@SOS_ResourceGroup@@QEAAXXZ` at `0x100de6c7d`
- `sqldk!?Destroy@SOS_ResourceGroup@@QEAAXXZ` at `0x100de7a79`
- `sqldk!?Destroy@SOS_ResourceGroup@@QEAAXXZ` at `0x100de7c6b`
- `sqldk!?Destroy@SOS_ResourceGroup@@QEAAXXZ` at `0x100de7cbe`
- `sqldk!?Destroy@SOS_ResourceGroup@@QEAAXXZ` at `0x100de80d6`
- `sqldk!?Destroy@SOS_ResourceGroup@@QEAAXXZ` at `0x100de80e9`
- `sqldk!?Destroy@SOS_ResourceGroup@@QEAAXXZ` at `0x100de81de`
- `sqldk!?Destroy@SOS_ResourceGroup@@QEAAXXZ` at `0x100de8299`
- `sqldk!?Destroy@SOS_ResourceGroup@@QEAAXXZ` at `0x100de6c7d`
- `sqldk!?Destroy@SOS_ResourceGroup@@QEAAXXZ` at `0x100de7a79`
- `sqldk!?Destroy@SOS_ResourceGroup@@QEAAXXZ` at `0x100de7c6b`
- `sqldk!?Destroy@SOS_ResourceGroup@@QEAAXXZ` at `0x100de7cbe`
- `sqldk!?Destroy@SOS_ResourceGroup@@QEAAXXZ` at `0x100de80d6`
- `sqldk!?Destroy@SOS_ResourceGroup@@QEAAXXZ` at `0x100de80e9`
- `sqldk!?Destroy@SOS_ResourceGroup@@QEAAXXZ` at `0x100de81de`
- `sqldk!?Destroy@SOS_ResourceGroup@@QEAAXXZ` at `0x100de8299`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100de7f2d`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100de7f2d`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x100de7bf1`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x100de7bf1`
- `sqldk!SystemThread_TlsIndex` at `0x100550475`
- `sqldk!SystemThread_TlsIndex` at `0x100de6cad`
- `sqldk!SystemThread_TlsIndex` at `0x100de6cea`
- `sqldk!SystemThread_TlsIndex` at `0x100de6e5b`
- `sqldk!SystemThread_TlsIndex` at `0x100de7037`
- `sqldk!SystemThread_TlsIndex` at `0x100de70ac`
- `sqldk!SystemThread_TlsIndex` at `0x100de71bf`
- `sqldk!SystemThread_TlsIndex` at `0x100de7232`
- `sqldk!SystemThread_TlsIndex` at `0x100de7401`
- `sqldk!SystemThread_TlsIndex` at `0x100de74db`
- `sqldk!SystemThread_TlsIndex` at `0x100de7547`
- `sqldk!SystemThread_TlsIndex` at `0x100de7744`
- `sqldk!SystemThread_TlsIndex` at `0x100de78c1`
- `sqldk!SystemThread_TlsIndex` at `0x100de7b17`
- `sqldk!SystemThread_TlsIndex` at `0x100de7bb9`
- `sqldk!SystemThread_TlsIndex` at `0x100de7d12`
- `sqldk!SystemThread_TlsOffset` at `0x10055047e`
- `sqldk!SystemThread_TlsOffset` at `0x100de6cb6`
- `sqldk!SystemThread_TlsOffset` at `0x100de6cf3`
- `sqldk!SystemThread_TlsOffset` at `0x100de6e64`
- `sqldk!SystemThread_TlsOffset` at `0x100de7040`
- `sqldk!SystemThread_TlsOffset` at `0x100de70b5`
- `sqldk!SystemThread_TlsOffset` at `0x100de71c8`
- `sqldk!SystemThread_TlsOffset` at `0x100de723b`
- `sqldk!SystemThread_TlsOffset` at `0x100de740a`
- `sqldk!SystemThread_TlsOffset` at `0x100de74e4`
- `sqldk!SystemThread_TlsOffset` at `0x100de7550`
- `sqldk!SystemThread_TlsOffset` at `0x100de774d`
- `sqldk!SystemThread_TlsOffset` at `0x100de78ca`
- `sqldk!SystemThread_TlsOffset` at `0x100de7b20`
- `sqldk!SystemThread_TlsOffset` at `0x100de7bc2`
- `sqldk!SystemThread_TlsOffset` at `0x100de7d1b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100de7778`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100de78f3`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100de7bdb`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100de7778`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100de78f3`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100de7bdb`
- `sqlTsEs!??1CAutoClearXVariant@@UEAA@XZ` at `0x100de79b6`
- `sqlTsEs!??1CAutoClearXVariant@@UEAA@XZ` at `0x100de8038`
- `sqlTsEs!??1CAutoClearXVariant@@UEAA@XZ` at `0x100de79b6`
- `sqlTsEs!??1CAutoClearXVariant@@UEAA@XZ` at `0x100de8038`
- `VCRUNTIME140!wcsstr` at `0x100de6fdb`
- `VCRUNTIME140!wcsstr` at `0x100de6fdb`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp_l` at `0x100de7f40`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp_l` at `0x100de7f40`
- `sqlmin!?FSystemDatabase@@YA_NPEB_WKK_N@Z` at `0x100de7085`
- `sqlmin!?FSystemDatabase@@YA_NPEB_WKK_N@Z` at `0x100de7085`
- `sqlmin!?GetDACGroup@SloInfo@@SAPEAVSOS_ResourceGroup@@XZ` at `0x100de6bcc`
- `sqlmin!?GetDACGroup@SloInfo@@SAPEAVSOS_ResourceGroup@@XZ` at `0x100de6bcc`
- `sqlmin!?GetDWGroup@SloInfo@@SAPEAVSOS_ResourceGroup@@XZ` at `0x100de6d9f`
- `sqlmin!?GetDWGroup@SloInfo@@SAPEAVSOS_ResourceGroup@@XZ` at `0x100de6d9f`
- `sqlmin!?GetVDWFrontendGroup@SloInfo@@SAPEAVSOS_ResourceGroup@@XZ` at `0x100de6dc8`
- `sqlmin!?GetVDWFrontendGroup@SloInfo@@SAPEAVSOS_ResourceGroup@@XZ` at `0x100de6dc8`
- `sqlmin!?MapAppNameToWorkloadGroup@SloInfo@@SAPEB_WQEB_WH@Z` at `0x100de6f5e`
- `sqlmin!?MapAppNameToWorkloadGroup@SloInfo@@SAPEB_WQEB_WH@Z` at `0x100de6f5e`
- `sqlmin!?GetPrimaryGroup@SloInfo@@QEAAPEAVSOS_ResourceGroup@@XZ` at `0x100de7137`
- `sqlmin!?GetPrimaryGroup@SloInfo@@QEAAPEAVSOS_ResourceGroup@@XZ` at `0x100de7f51`
- `sqlmin!?GetPrimaryGroup@SloInfo@@QEAAPEAVSOS_ResourceGroup@@XZ` at `0x100de7137`
- `sqlmin!?GetPrimaryGroup@SloInfo@@QEAAPEAVSOS_ResourceGroup@@XZ` at `0x100de7f51`
- `sqlmin!?IsReadableSecondary@DBTABLE@@QEAA_N_N@Z` at `0x100de716f`
- `sqlmin!?IsReadableSecondary@DBTABLE@@QEAA_N_N@Z` at `0x100de716f`
- `sqlmin!?OpenDB@DBMgr@@QEAAPEAVDBTABLE@@PEAVBaseXact@@KW4EDBRefType@@HK@Z` at `0x100de7481`
- `sqlmin!?OpenDB@DBMgr@@QEAAPEAVDBTABLE@@PEAVBaseXact@@KW4EDBRefType@@HK@Z` at `0x100de7481`
- `sqlmin!?GetDbScopedResourceGroupName@SloInfo@@QEAAJPEB_WPEA_W_K@Z` at `0x100de8089`
- `sqlmin!?GetDbScopedResourceGroupName@SloInfo@@QEAAJPEB_WPEA_W_K@Z` at `0x100de8089`
- `sqlmin!?CloseDB@DBMgr@@QEAAXVContextHandle@@KW4EDBRefType@@@Z` at `0x100de7abf`
- `sqlmin!?CloseDB@DBMgr@@QEAAXVContextHandle@@KW4EDBRefType@@@Z` at `0x100de7abf`
- `sqlmin!?IsWorkloadIsolationEnabled@DBTABLE@@QEAA_NXZ` at `0x100de7145`
- `sqlmin!?IsWorkloadIsolationEnabled@DBTABLE@@QEAA_NXZ` at `0x100de7145`
- `sqlmin!?GetSlo@DBTABLE@@QEAAPEAVSloInfo@@XZ` at `0x100de711c`
- `sqlmin!?GetSlo@DBTABLE@@QEAAPEAVSloInfo@@XZ` at `0x100de712e`
- `sqlmin!?GetSlo@DBTABLE@@QEAAPEAVSloInfo@@XZ` at `0x100de7f13`
- `sqlmin!?GetSlo@DBTABLE@@QEAAPEAVSloInfo@@XZ` at `0x100de711c`
- `sqlmin!?GetSlo@DBTABLE@@QEAAPEAVSloInfo@@XZ` at `0x100de712e`
- `sqlmin!?GetSlo@DBTABLE@@QEAAPEAVSloInfo@@XZ` at `0x100de7f13`
- `sqlmin!?GetMasterDbId@@YAGXZ` at `0x100550557`
- `sqlmin!?GetMasterDbId@@YAGXZ` at `0x100550557`
- `sqlmin!GetXdbServerGlobals` at `0x1005504a8`
- `sqlmin!GetXdbServerGlobals` at `0x1005504e5`
- `sqlmin!GetXdbServerGlobals` at `0x100550511`
- `sqlmin!GetXdbServerGlobals` at `0x100550524`
- `sqlmin!GetXdbServerGlobals` at `0x100de6d58`
- `sqlmin!GetXdbServerGlobals` at `0x100de6d66`
- `sqlmin!GetXdbServerGlobals` at `0x100de6d78`
- `sqlmin!GetXdbServerGlobals` at `0x100de6ebd`
- `sqlmin!GetXdbServerGlobals` at `0x1005504a8`
- `sqlmin!GetXdbServerGlobals` at `0x1005504e5`
- `sqlmin!GetXdbServerGlobals` at `0x100550511`
- `sqlmin!GetXdbServerGlobals` at `0x100550524`
- `sqlmin!GetXdbServerGlobals` at `0x100de6d58`
- `sqlmin!GetXdbServerGlobals` at `0x100de6d66`
- `sqlmin!GetXdbServerGlobals` at `0x100de6d78`
- `sqlmin!GetXdbServerGlobals` at `0x100de6ebd`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
void ExecuteClassifier(void)
{
  SOS_ResourceManager *v0; // rsi
  _QWORD *ThreadLocalStoragePointer; // rdx
  __int64 v2; // r14
  __int64 v3; // rdx
  __int64 v4; // rcx
  unsigned __int64 v5; // r12
  unsigned int v6; // ebx
  bool v7; // di
  __int64 v8; // rdx
  __int64 v9; // rcx
  char v10; // r13
  unsigned __int16 MasterDbId; // r15
  __int64 v12; // rcx
  __int64 v13; // rdi
  struct SOS_ResourceGroup *v14; // rdx
  __int64 DACGroup; // rax
  __int64 v16; // rdx
  signed __int32 v17; // eax
  __int64 v18; // rax
  __int64 v19; // rbx
  __int64 v20; // rax
  __int64 v21; // rdi
  __int64 v22; // rbx
  _QWORD *v23; // rdx
  __int64 v24; // rcx
  const wchar_t *v25; // r15
  struct DBTABLE *v26; // r8
  DataVirtualizationResource *v27; // rax
  int v28; // eax
  const wchar_t *v29; // rcx
  int v30; // edx
  const wchar_t *v31; // r15
  __int64 v32; // rax
  const wchar_t *v33; // rcx
  unsigned int v34; // eax
  __int64 v35; // rax
  __int64 v36; // r13
  __int64 v37; // rax
  __int64 v38; // r15
  __int64 v39; // r13
  __int64 v40; // rcx
  SloInfo *Slo; // rax
  char v42; // cl
  __int64 v43; // rdi
  __int64 v44; // rcx
  void ***v45; // rdx
  bool v46; // zf
  __int64 v47; // rax
  DBTABLE *v48; // r15
  __int64 v49; // rdi
  __int64 v50; // rax
  __int64 v51; // rdi
  __int64 v52; // rcx
  struct CSQLObject *ObjectByDbAndObjId; // rdi
  wchar_t *v54; // r13
  struct SOS_ResourceGroup *v55; // rdx
  __int64 v56; // rcx
  SOS_ResourceGroup *v57; // rdi
  __int64 v58; // rdx
  __int64 v59; // rdi
  struct Worker *v60; // rcx
  int v61; // eax
  __int64 v62; // rcx
  __int64 v63; // rdi
  struct SOS_ResourceGroup *v64; // rdx
  struct SOS_ResourceGroup *v65; // rdi
  __int32 v66; // eax
  __int32 v67; // edx
  __int64 v68; // rdi
  CSbTransportMgr *QuadPart; // rcx
  unsigned __int64 v70; // rax
  unsigned __int64 v71; // rcx
  __int64 v72; // r9
  __int64 v73; // rax
  int v74; // ecx
  unsigned int v75; // ecx
  SloInfo *v76; // r15
  __crt_locale_pointers *DefaultLocale; // rax
  struct SOS_ResourceGroup *PrimaryGroup; // rax
  void *v79; // rdi
  int v80; // r13d
  unsigned int v81; // edx
  int v82; // r15d
  int DuplicatedUserConnections; // eax
  __int64 v84; // rdx
  SOS_ResourceGroup *v85; // rdi
  SOS_ResourceGroup *v86; // rcx
  __int64 v87; // rdx
  __int64 v88; // rcx
  __int64 v89; // rcx
  int (*v90)(int, int, int, int, char *); // [rsp+20h] [rbp-7F8h]
  struct Worker *v91; // [rsp+28h] [rbp-7F0h]
  char v92; // [rsp+50h] [rbp-7C8h]
  struct SOS_ResourceGroup *DWGroup; // [rsp+58h] [rbp-7C0h] BYREF
  char v94; // [rsp+60h] [rbp-7B8h]
  struct SOS_ResourceGroup *v95; // [rsp+68h] [rbp-7B0h] BYREF
  unsigned __int16 v96; // [rsp+70h] [rbp-7A8h]
  int v97; // [rsp+74h] [rbp-7A4h]
  char v98; // [rsp+78h] [rbp-7A0h]
  unsigned __int8 v99; // [rsp+80h] [rbp-798h]
  unsigned __int16 v100; // [rsp+84h] [rbp-794h]
  int v101; // [rsp+88h] [rbp-790h] BYREF
  __int64 v102; // [rsp+90h] [rbp-788h]
  int v103; // [rsp+98h] [rbp-780h]
  int v104; // [rsp+9Ch] [rbp-77Ch]
  unsigned int v105; // [rsp+A0h] [rbp-778h]
  __int64 v107; // [rsp+A8h] [rbp-770h]
  int v108; // [rsp+B0h] [rbp-768h]
  void *Source; // [rsp+B8h] [rbp-760h]
  int v110; // [rsp+C0h] [rbp-758h] BYREF
  int v111; // [rsp+C4h] [rbp-754h] BYREF
  int v112; // [rsp+C8h] [rbp-750h]
  __int128 v113; // [rsp+D0h] [rbp-748h]
  struct CSQLObject *v114; // [rsp+E0h] [rbp-738h]
  __int64 v115; // [rsp+E8h] [rbp-730h]
  __int64 v116; // [rsp+F0h] [rbp-728h]
  __int64 v117; // [rsp+F8h] [rbp-720h]
  void **v118; // [rsp+100h] [rbp-718h] BYREF
  _BYTE v119[2]; // [rsp+108h] [rbp-710h] BYREF
  __int16 v120; // [rsp+10Ah] [rbp-70Eh]
  wchar_t *String1; // [rsp+110h] [rbp-708h] BYREF
  __int64 v122; // [rsp+118h] [rbp-700h]
  int v123; // [rsp+120h] [rbp-6F8h]
  __int128 v124; // [rsp+128h] [rbp-6F0h] BYREF
  __int128 v125; // [rsp+138h] [rbp-6E0h]
  __int128 v126; // [rsp+150h] [rbp-6C8h]
  __int128 v127; // [rsp+160h] [rbp-6B8h]
  int v128; // [rsp+170h] [rbp-6A8h]
  int v129; // [rsp+174h] [rbp-6A4h]
  unsigned int v130; // [rsp+178h] [rbp-6A0h]
  unsigned int v131; // [rsp+180h] [rbp-698h]
  int v132; // [rsp+184h] [rbp-694h]
  int v133; // [rsp+188h] [rbp-690h]
  BOOL v134; // [rsp+190h] [rbp-688h]
  __int64 v136; // [rsp+1A0h] [rbp-678h]
  __int64 v137; // [rsp+1A8h] [rbp-670h]
  struct SOS_ResourceGroup *v138; // [rsp+1B0h] [rbp-668h]
  __int64 v139; // [rsp+1B8h] [rbp-660h]
  __int64 v140; // [rsp+1C0h] [rbp-658h]
  SOS_ResourceManager *v141; // [rsp+1C8h] [rbp-650h]
  __int64 v142; // [rsp+1D0h] [rbp-648h]
  LARGE_INTEGER PerformanceCount; // [rsp+1D8h] [rbp-640h] BYREF
  _QWORD *v144; // [rsp+1E0h] [rbp-638h]
  int v145; // [rsp+1E8h] [rbp-630h]
  void **v146; // [rsp+1F0h] [rbp-628h] BYREF
  void ***v147; // [rsp+1F8h] [rbp-620h]
  int v148; // [rsp+200h] [rbp-618h]
  __int64 v149; // [rsp+208h] [rbp-610h]
  __int64 v150; // [rsp+210h] [rbp-608h]
  int v151; // [rsp+218h] [rbp-600h]
  int v152; // [rsp+21Ch] [rbp-5FCh]
  __int64 v153; // [rsp+220h] [rbp-5F8h] BYREF
  char v154; // [rsp+228h] [rbp-5F0h]
  __int64 v155; // [rsp+230h] [rbp-5E8h]
  char v156; // [rsp+240h] [rbp-5D8h]
  char v157; // [rsp+248h] [rbp-5D0h]
  __int128 v158; // [rsp+250h] [rbp-5C8h] BYREF
  __int64 v159; // [rsp+260h] [rbp-5B8h]
  int v160; // [rsp+268h] [rbp-5B0h]
  int v161; // [rsp+26Ch] [rbp-5ACh]
  int v162; // [rsp+270h] [rbp-5A8h]
  int v163; // [rsp+274h] [rbp-5A4h]
  int v164; // [rsp+278h] [rbp-5A0h]
  __int64 v165; // [rsp+280h] [rbp-598h]
  int v166; // [rsp+288h] [rbp-590h]
  __int16 v167; // [rsp+28Ch] [rbp-58Ch]
  int v168; // [rsp+290h] [rbp-588h]
  int v169; // [rsp+294h] [rbp-584h]
  char v170; // [rsp+298h] [rbp-580h]
  __int64 v171; // [rsp+2A0h] [rbp-578h]
  int v172; // [rsp+2A8h] [rbp-570h]
  __int16 v173; // [rsp+2ACh] [rbp-56Ch]
  __int128 v174; // [rsp+2B0h] [rbp-568h]
  int v175; // [rsp+2C0h] [rbp-558h]
  __int16 v176; // [rsp+2C4h] [rbp-554h]
  __int16 v177; // [rsp+2C6h] [rbp-552h]
  __int16 v178; // [rsp+2C8h] [rbp-550h]
  int v179; // [rsp+2CCh] [rbp-54Ch]
  char v180; // [rsp+2D0h] [rbp-548h]
  __m128i v181; // [rsp+2E0h] [rbp-538h] BYREF
  int v182; // [rsp+2F0h] [rbp-528h]
  __int64 v183; // [rsp+2F8h] [rbp-520h]
  __int64 v184; // [rsp+300h] [rbp-518h]
  _QWORD *v185; // [rsp+308h] [rbp-510h]
  _QWORD *v186; // [rsp+310h] [rbp-508h]
  _QWORD *v187; // [rsp+318h] [rbp-500h]
  __int64 v188; // [rsp+320h] [rbp-4F8h]
  __int64 v189; // [rsp+328h] [rbp-4F0h]
  _QWORD *v190; // [rsp+330h] [rbp-4E8h]
  _QWORD *v191; // [rsp+338h] [rbp-4E0h]
  _QWORD *v192; // [rsp+340h] [rbp-4D8h]
  __int64 v193; // [rsp+348h] [rbp-4D0h]
  __int64 v194; // [rsp+350h] [rbp-4C8h]
  __int64 v195; // [rsp+358h] [rbp-4C0h]
  __int128 *v196; // [rsp+360h] [rbp-4B8h]
  _BYTE *v197; // [rsp+368h] [rbp-4B0h]
  wchar_t **p_String1; // [rsp+370h] [rbp-4A8h]
  _BYTE *v199; // [rsp+378h] [rbp-4A0h]
  _QWORD *v200; // [rsp+380h] [rbp-498h]
  __int64 v201; // [rsp+388h] [rbp-490h]
  __int64 v202; // [rsp+390h] [rbp-488h]
  __int128 *v203; // [rsp+398h] [rbp-480h]
  _QWORD *v204; // [rsp+3A0h] [rbp-478h]
  __int64 v205; // [rsp+3A8h] [rbp-470h]
  struct IMemObj *v206; // [rsp+3B0h] [rbp-468h]
  struct CSQLObject *v207; // [rsp+3B8h] [rbp-460h]
  struct CSQLObject *v208; // [rsp+3C0h] [rbp-458h]
  __int128 *v209; // [rsp+3C8h] [rbp-450h]
  SloInfo *v210; // [rsp+3D0h] [rbp-448h]
  struct CSQLObject *v211; // [rsp+3D8h] [rbp-440h]
  struct SOS_ResourceGroup *v212; // [rsp+3E0h] [rbp-438h]
  SOS_ResourceGroup *v213; // [rsp+3E8h] [rbp-430h]
  struct SOS_ResourceGroup *v214; // [rsp+3F0h] [rbp-428h]
  __int64 v215; // [rsp+3F8h] [rbp-420h]
  __int64 v216; // [rsp+400h] [rbp-418h]
  SOS_ResourceGroup *v217; // [rsp+408h] [rbp-410h]
  __int64 v218; // [rsp+410h] [rbp-408h]
  __int64 v219; // [rsp+418h] [rbp-400h]
  __int64 v220; // [rsp+420h] [rbp-3F8h]
  __int64 v221; // [rsp+428h] [rbp-3F0h]
  _QWORD v222[5]; // [rsp+430h] [rbp-3E8h] BYREF
  _QWORD *v223; // [rsp+458h] [rbp-3C0h]
  __int64 v224; // [rsp+460h] [rbp-3B8h]
  __int64 v225; // [rsp+468h] [rbp-3B0h]
  _BYTE v226[48]; // [rsp+470h] [rbp-3A8h] BYREF
  __m128i si128; // [rsp+4A0h] [rbp-378h] BYREF
  int v228; // [rsp+4B0h] [rbp-368h]
  unsigned __int16 v229; // [rsp+4B4h] [rbp-364h]
  int v230; // [rsp+4B8h] [rbp-360h]
  char v231; // [rsp+4BCh] [rbp-35Ch]
  unsigned int v232; // [rsp+4C0h] [rbp-358h]
  char Destination[268]; // [rsp+4C4h] [rbp-354h] BYREF
  _BYTE v234[272]; // [rsp+5D0h] [rbp-248h] BYREF
  wchar_t v235[136]; // [rsp+6E0h] [rbp-138h] BYREF

  v218 = -2;
  v0 = (SOS_ResourceManager *)SOS_PublicGlobals::sm_ResourceManager;
  v141 = (SOS_ResourceManager *)SOS_PublicGlobals::sm_ResourceManager;
  if ( SOS_PublicGlobals::sm_isResourceManagerEnabled )
  {
    ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
    v2 = *(_QWORD *)(*(_QWORD *)(ThreadLocalStoragePointer[SystemThread_TlsIndex] + SystemThread_TlsOffset) + 72LL);
    v142 = v2;
    if ( (*(_BYTE *)(v2 + 269) & 0x20) == 0 )
    {
      if ( *(_DWORD *)(GetXdbServerGlobals(SystemThread_TlsIndex, ThreadLocalStoragePointer) + 11976)
        && *((_BYTE *)qword_102EF3550 + 743)
        && (v20 = g_dbtableFactory[4](*(unsigned __int16 *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                        + SystemThread_TlsIndex)
                                                                      + SystemThread_TlsOffset
                                                                      + 80LL)
                                                          + 600LL))) != 0 )
      {
        v3 = SystemThread_TlsIndex;
        v21 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                        + SystemThread_TlsOffset
                        + 80LL);
        v22 = *(_QWORD *)(v20 + 4664);
        v4 = *(_QWORD *)(v21 + 1064);
        v5 = -1;
        if ( v4 )
        {
          v3 = v4 + 8;
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 8), 0xFFFFFFFF) == 1 && v4 != -8 )
            (**(void (__fastcall ***)(__int64, __int64))v4)(v4, 1);
        }
        *(_QWORD *)(v21 + 1064) = v22;
        if ( v22 )
          _InterlockedIncrement((volatile signed __int32 *)(v22 + 8));
      }
      else
      {
        v5 = -1;
      }
      v6 = 0;
      DWGroup = 0;
      v7 = 1;
      v92 = 0;
      if ( (*(_DWORD *)(qword_102ECFB00 + 14504)
         && (*(_BYTE *)(GetXdbServerGlobals(v4, v3) + 12009) || *(_BYTE *)(GetXdbServerGlobals(v4, v3) + 12008))
         && !*(_BYTE *)(GetXdbServerGlobals(v4, v3) + 12004)
         || *(_BYTE *)(GetXdbServerGlobals(v4, v3) + 12004))
        && *((_BYTE *)qword_102EF3550 + 1585) )
      {
        DWGroup = (struct SOS_ResourceGroup *)SloInfo::GetDWGroup();
        v7 = DWGroup == 0;
      }
      if ( *((_BYTE *)qword_102EF3550 + 1634) )
      {
        if ( (*(_BYTE *)(v2 + 270) & 0x40) != 0 )
        {
          DWGroup = (struct SOS_ResourceGroup *)SloInfo::GetVDWFrontendGroup();
          if ( DWGroup )
          {
            v7 = 0;
            v10 = 0;
            goto LABEL_12;
          }
        }
      }
      if ( !v7
        || !*(_DWORD *)(GetXdbServerGlobals(v4, v3) + 8308)
        && (!*(_DWORD *)(GetXdbServerGlobals(v9, v8) + 11976)
         || (*(_BYTE *)(v2 + 270) & 2) == 0 && *((_BYTE *)qword_102EF3550 + 743)) )
      {
        goto LABEL_11;
      }
      if ( FPDWFeaturesExposed() )
      {
        v25 = *(const wchar_t **)(v2 + 960);
        if ( !v25 )
          v25 = (const wchar_t *)(*(_QWORD *)(v2 + 192) + *(unsigned __int16 *)(*(_QWORD *)(v2 + 192) + 48LL));
        v26 = 0;
        if ( *((_BYTE *)qword_102EF3550 + 718) || (*((_BYTE *)qword_102ECFB10 + 1432) & 0x20) != 0 )
        {
          v23 = NtCurrentTeb()->ThreadLocalStoragePointer;
          if ( *(_WORD *)(*(_QWORD *)(v23[SystemThread_TlsIndex] + SystemThread_TlsOffset + 80LL) + 600LL) )
          {
            _mm_lfence();
            v26 = (struct DBTABLE *)((__int64 (*)(void))g_dbtableFactory[4])();
          }
        }
        DWGroup = ParsePDWResourceGroup(v25, (int)v23, v26);
        if ( DWGroup )
        {
          v7 = 0;
          v10 = 0;
          goto LABEL_12;
        }
      }
      if ( (*(_BYTE *)(v2 + 270) & 4) == 0 )
      {
        if ( *(_DWORD *)(GetXdbServerGlobals(v24, v23) + 11976) )
        {
          v27 = qword_102EF3550;
          if ( !*((_BYTE *)qword_102EF3550 + 742) || (*(_BYTE *)(v2 + 270) & 2) == 0 )
          {
LABEL_77:
            if ( *((_BYTE *)v27 + 1342) )
            {
              v33 = *(const wchar_t **)(v2 + 960);
              if ( v33 )
              {
                v34 = *(_DWORD *)(v2 + 968);
LABEL_80:
                if ( v34 >= 0x16 && wcsstr(v33, L"SQLExternalMonitoring") )
                {
                  do
                    v28 = SOS_ResourceManager::LookupGroup(
                            SOS_PublicGlobals::sm_ResourceManager,
                            L"SQLExternalMonitoringGroup",
                            SOS_PublicGlobals::sm_ResourceManager,
                            &DWGroup);
                  while ( v28 == 0x80000000 );
LABEL_67:
                  if ( v28 )
                    DWGroup = (struct SOS_ResourceGroup *)((char *)&SOS_PublicGlobals::sm_ResourceManager + 112);
                  goto LABEL_69;
                }
                goto LABEL_85;
              }
              v35 = *(_QWORD *)(v2 + 192);
              v33 = (const wchar_t *)(v35 + *(unsigned __int16 *)(v35 + 48));
              v34 = 2 * *(unsigned __int16 *)(v35 + 50);
              if ( v33 )
                goto LABEL_80;
            }
LABEL_85:
            v36 = *(unsigned __int16 *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                    + SystemThread_TlsIndex)
                                                  + SystemThread_TlsOffset
                                                  + 80LL)
                                      + 600LL);
            v37 = g_dbtableFactory[4](v36);
            v38 = v37;
            if ( v37
              && !FSystemDatabase((const wchar_t *)(v37 + 936), *(_DWORD *)(v37 + 928), v36, 1)
              && (unsigned int)(v36 - 32764) > 2 )
            {
              v107 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                               + SystemThread_TlsOffset
                               + 80LL);
              v39 = *(_QWORD *)(v38 + 4664);
              v40 = *(_QWORD *)(v107 + 1064);
              if ( v40 && _InterlockedExchangeAdd((volatile signed __int32 *)(v40 + 8), 0xFFFFFFFF) == 1 && v40 != -8 )
                (**(void (__fastcall ***)(__int64, __int64))v40)(v40, 1);
              *(_QWORD *)(v107 + 1064) = v39;
              if ( v39 )
                _InterlockedIncrement((volatile signed __int32 *)(v39 + 8));
              if ( DBTABLE::GetSlo((DBTABLE *)v38) )
              {
                Slo = DBTABLE::GetSlo((DBTABLE *)v38);
                DWGroup = SloInfo::GetPrimaryGroup(Slo);
                if ( !DBTABLE::IsWorkloadIsolationEnabled((DBTABLE *)v38)
                  || !*(_DWORD *)(v38 + 4676)
                  || *((_BYTE *)qword_102EF3550 + 560) && DBTABLE::IsReadableSecondary((DBTABLE *)v38, 0) )
                {
                  if ( !DWGroup )
                  {
LABEL_69:
                    v7 = 0;
                    v10 = 0;
                    goto LABEL_12;
                  }
                  *((_DWORD *)DWGroup + 198) = COpenConnections::GetDuplicatedUserConnections(qword_102EF3DA8);
                  v7 = 0;
                  v10 = 0;
                }
                else
                {
                  v10 = 1;
                  v92 = 1;
                }
LABEL_12:
                if ( !DWGroup )
                  DWGroup = (struct SOS_ResourceGroup *)((char *)&SOS_PublicGlobals::sm_ResourceManager + 112);
                if ( v10 )
                  MasterDbId = *(_WORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                      + SystemThread_TlsIndex)
                                                    + SystemThread_TlsOffset
                                                    + 80LL)
                                        + 600LL);
                else
                  MasterDbId = GetMasterDbId();
                v96 = MasterDbId;
                LODWORD(v102) = MasterDbId;
                v107 = g_dbtableFactory[4](MasterDbId);
                v97 = *(_DWORD *)(v107 + 4676);
                if ( !v97 || !v7 )
                {
                  v12 = *(_QWORD *)(v2 + 104);
                  v13 = *(_QWORD *)(v12 + 712);
                  *(_QWORD *)(v12 + 712) = DWGroup;
                  if ( v13 )
                  {
                    if ( *(_DWORD *)(v13 + 164) >= 3u )
                    {
                      _InterlockedDecrement((volatile signed __int32 *)(v13 + 64));
                      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v13 + 40), 0xFFFFFFFF) == 1 )
                      {
                        if ( *(_QWORD *)(v13 + 24) )
                          TList<GroupList,SOS_ResourceGroup,16,TListSLock>::RemoveElem(*(_QWORD *)(v13 + 32), v13);
                        SOS_ResourceGroup::Destroy((SOS_ResourceGroup *)v13);
                      }
                    }
                  }
                  v14 = DWGroup;
                  DWGroup = 0;
                  SOS_ResourceManager::BindCurrentTaskToGroup(SOS_PublicGlobals::sm_ResourceManager, v14);
                  goto LABEL_20;
                }
                v116 = v2;
                v42 = *(_BYTE *)(v2 + 270);
                if ( (v42 & 4) != 0 )
                {
                  *(_BYTE *)(v2 + 270) = v42 & 0xFB;
                  *(_BYTE *)(v2 + 271) &= ~1u;
                  *(_DWORD *)(v2 + 404) = 2;
                }
                else
                {
                  v116 = 0;
                }
                v43 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                + SystemThread_TlsOffset);
                v115 = v43;
                v95 = 0;
                si128 = _mm_load_si128((const __m128i *)&_xmm);
                v228 = 0;
                v229 = MasterDbId;
                v230 = 0;
                v231 = 0;
                v232 = 0;
                v94 = 0;
                try
                {
                  ExcHandler::ExcHandler(
                    (ExcHandler *)v226,
                    0,
                    0,
                    0,
                    (int (*)(int, int, int, int, char *))MSQLErrorHandlerFunc,
                    0);
                  v147 = 0;
                  v148 = 0;
                  v149 = 0;
                  v150 = 0;
                  v151 = 0;
                  v152 = 0;
                  v222[2] = &v153;
                  v153 = 0;
                  v154 = 1;
                  v155 = 0;
                  v156 = 1;
                  v146 = &CSysTaskConnOut::`vftable';
                  v157 = 0;
                  v44 = *(_QWORD *)(v43 + 112);
                  v222[3] = v44;
                  v126 = 0;
                  v127 = 0;
                  v222[4] = &v146;
                  v45 = *(void ****)(v44 + 24);
                  if ( v45 != &v146 )
                  {
                    *(_QWORD *)&v126 = v44;
                    *((_QWORD *)&v126 + 1) = v45;
                    *(_QWORD *)&v127 = v147;
                    *((_QWORD *)&v127 + 1) = &v146;
                    v147 = v45;
                    *(_QWORD *)(v44 + 24) = &v146;
                  }
                  v128 = 88;
                  v223 = NtCurrentTeb()->ThreadLocalStoragePointer;
                  v224 = v223[SystemThread_TlsIndex] + SystemThread_TlsOffset;
                  v225 = v224;
                  v183 = *(_QWORD *)(v224 + 80);
                  v184 = v183;
                  v100 = *(_WORD *)(v183 + 600);
                  v101 = 0;
                  if ( v10 )
                  {
                    CAutoDb::FUse((CAutoDb *)&v101, MasterDbId, 0, 1, 1, 0);
                  }
                  else
                  {
                    DBMgr::OpenDB(*(_QWORD *)(qword_102ECFB00 + 32), 0, MasterDbId, 3, 1, 64);
                    v94 = 1;
                  }
                  v110 = 0;
                  v111 = 0;
                  v113 = 0;
                  v112 = 1;
                  v129 = 88;
                  v185 = NtCurrentTeb()->ThreadLocalStoragePointer;
                  v186 = (_QWORD *)(v185[SystemThread_TlsIndex] + SystemThread_TlsOffset);
                  v187 = v186;
                  v188 = *v186;
                  v189 = v188;
                  v117 = v188;
                  *(_QWORD *)&v113 = *(_QWORD *)(v188 + 144);
                  v145 = 88;
                  v190 = NtCurrentTeb()->ThreadLocalStoragePointer;
                  v191 = (_QWORD *)(v190[SystemThread_TlsIndex] + SystemThread_TlsOffset);
                  v192 = v191;
                  v193 = *v191;
                  v194 = v193;
                  v117 = v193;
                  v134 = *(_BYTE *)(v193 + 152) != 0;
                  v46 = (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)v113 + 464LL))(v113) == 0;
                  v47 = *(_QWORD *)v113;
                  if ( v46 )
                  {
                    (*(void (__fastcall **)(_QWORD, const wchar_t *, __int64))(v47 + 8))(v113, L"RG Classifier", 26);
                    v110 = 2;
                  }
                  else
                  {
                    (*(void (__fastcall **)(_QWORD, __int64, __int64, int *))(v47 + 232))(v113, 1, 1, &v111);
                    v112 = 1;
                    v110 = 4;
                  }
                  v104 = 0;
                  LODWORD(v117) = 3;
                  do
                  {
                    v103 = 0;
                    v108 = SOS_PublicGlobals::sm_ResourceManager;
                    v48 = (DBTABLE *)v107;
                    v195 = v107 + 4676;
                    v97 = *(_DWORD *)(v107 + 4676);
                    if ( !v97 )
                      break;
                    CClassifierTraceEvent::PreEvent((CClassifierTraceEvent *)&si128, v97);
                    v118 = &CAutoClearXVariant::`vftable';
                    v196 = &v124;
                    v124 = CTypeInfo::tiSSWName1;
                    v125 = xmmword_10305ADF0;
                    LOBYTE(v124) = _mm_cvtsi128_si32(CTypeInfo::tiSSWName1);
                    v98 = v124;
                    v197 = v119;
                    v120 = 0;
                    v119[0] = 3;
                    v119[1] = v124;
                    p_String1 = &String1;
                    String1 = 0;
                    v122 = 0;
                    v123 = 0;
                    memset_0(v234, 0, 0x102u);
                    v199 = v119;
                    String1 = (wchar_t *)v234;
                    v122 = 258;
                    v133 = 88;
                    v200 = NtCurrentTeb()->ThreadLocalStoragePointer;
                    v49 = v200[SystemThread_TlsIndex] + SystemThread_TlsOffset;
                    v201 = v49;
                    v50 = *(_QWORD *)(v49 + 256);
                    v136 = v50;
                    if ( !v50 )
                    {
                      SystemThread::MakeMiniSOSThread(0);
                      v50 = *(_QWORD *)(v49 + 256);
                      v136 = v50;
                    }
                    v202 = *(_QWORD *)(v50 + 1000);
                    v203 = &v158;
                    v158 = 0;
                    v159 = 0;
                    v160 = 0;
                    v161 = 0;
                    v162 = 0;
                    v163 = 0;
                    v164 = 0;
                    v165 = v202;
                    v166 = 1;
                    v167 = 0;
                    v168 = 0;
                    v169 = 0;
                    v170 = 0;
                    v171 = 0;
                    v172 = 0;
                    v173 = 0;
                    v174 = 0;
                    v175 = 0;
                    v176 = 0;
                    v177 = 0;
                    v178 = 0;
                    v179 = 0;
                    v180 = 0;
                    CParamExchange::InitForNonRpc((CParamExchange *)&v158, 0, 4u);
                    CParamExchange::InsertRetParam(
                      (CParamExchange *)&v158,
                      (struct CXVariant *)v119,
                      0,
                      0,
                      4u,
                      (const struct CTypeInfo *)&CTypeInfo::tiSSWName1);
                    v132 = 88;
                    v204 = NtCurrentTeb()->ThreadLocalStoragePointer;
                    v51 = v204[SystemThread_TlsIndex] + SystemThread_TlsOffset;
                    v205 = v51;
                    v52 = *(_QWORD *)(v51 + 256);
                    v137 = v52;
                    if ( !v52 )
                    {
                      SystemThread::MakeMiniSOSThread(0);
                      v52 = *(_QWORD *)(v51 + 256);
                      v137 = v52;
                    }
                    v206 = *(struct IMemObj **)(v52 + 1000);
                    ObjectByDbAndObjId = CSQLObject::CCreateObjectByDbAndObjId::CreateObjectByDbAndObjId(
                                           v206,
                                           v102,
                                           v97,
                                           20038);
                    v114 = ObjectByDbAndObjId;
                    v207 = ObjectByDbAndObjId;
                    v208 = ObjectByDbAndObjId;
                    *((_BYTE *)ObjectByDbAndObjId + 584) = 2;
                    (*(void (__fastcall **)(struct CSQLObject *, __int64, __int128 *, _QWORD))(*(_QWORD *)ObjectByDbAndObjId
                                                                                             + 152LL))(
                      ObjectByDbAndObjId,
                      v115,
                      &v158,
                      0);
                    v54 = String1;
                    Source = String1;
                    if ( v119[0] == 3 )
                    {
                      (*(void (__fastcall **)(struct CSQLObject *, __int64))(*(_QWORD *)ObjectByDbAndObjId + 136LL))(
                        ObjectByDbAndObjId,
                        1);
                      CParamExchange::~CParamExchange((CParamExchange *)&v158);
                      CAutoClearXVariant::~CAutoClearXVariant(&v118);
LABEL_121:
                      v10 = v92;
                      break;
                    }
                    v209 = &v124;
                    if ( (_WORD)v125 == 0xFFFF
                      || (v99 = *((_BYTE *)&xsm_rgOrdFromXvt + (unsigned __int8)v124),
                          v74 = (unsigned __int16)v125,
                          *((_BYTE *)&CTypeInfo::sxm_rgfIsLargeObject + v99)) )
                    {
                      v74 = 0xFFFF;
                    }
                    v75 = v74 - 2;
                    v131 = v75;
                    if ( (unsigned int)v122 <= v75 )
                      v75 = v122;
                    v105 = v75;
                    String1[(unsigned __int64)v75 >> 1] = 0;
                    if ( v92 )
                    {
                      v76 = DBTABLE::GetSlo(v48);
                      v210 = v76;
                      if ( v76 )
                      {
                        DefaultLocale = GetDefaultLocale();
                        if ( !_wcsicmp_l(v54, L"default", DefaultLocale) )
                        {
                          PrimaryGroup = SloInfo::GetPrimaryGroup(v76);
                          v95 = PrimaryGroup;
                          Source = (char *)PrimaryGroup + 260;
                          goto LABEL_193;
                        }
                        SloInfo::GetDbScopedResourceGroupName(v76, v54, v235, 0x81u);
                        Source = v235;
                      }
                    }
                    PrimaryGroup = v95;
LABEL_193:
                    if ( PrimaryGroup )
                    {
                      v80 = v103;
                      goto LABEL_207;
                    }
                    v79 = Source;
                    v80 = SOS_ResourceManager::LookupGroup(SOS_PublicGlobals::sm_ResourceManager, Source, v108, &v95);
                    v103 = v80;
                    if ( !v80 )
                    {
                      ObjectByDbAndObjId = v114;
LABEL_207:
                      v232 = 0;
                      goto LABEL_200;
                    }
                    v130 = v105 >> 1;
                    v81 = 128;
                    if ( v105 >> 1 < 0x80 )
                      v81 = v105 >> 1;
                    v232 = v81;
                    if ( v81 )
                      memcpy_s(Destination, 0x100u, v79, 2LL * v81);
                    ObjectByDbAndObjId = v114;
LABEL_200:
                    v82 = ++v104;
                    v211 = ObjectByDbAndObjId;
                    (*(void (__fastcall **)(struct CSQLObject *, __int64))(*(_QWORD *)ObjectByDbAndObjId + 136LL))(
                      ObjectByDbAndObjId,
                      1);
                    CParamExchange::~CParamExchange((CParamExchange *)&v158);
                    CAutoClearXVariant::~CAutoClearXVariant(&v118);
                    if ( v80 != 0x80000000 )
                      goto LABEL_121;
                    v10 = v92;
                  }
                  while ( !v92 || v82 < 3 );
                  v55 = v95;
                  if ( !v10 )
                    goto LABEL_125;
                  if ( v95 )
                    goto LABEL_126;
                  v55 = DWGroup;
                  v212 = DWGroup;
                  DWGroup = 0;
                  v95 = v212;
LABEL_125:
                  if ( v55 )
                  {
LABEL_126:
                    if ( *((_DWORD *)v55 + 39) == 1 )
                    {
                      v138 = v55;
                      if ( *((_DWORD *)v55 + 41) >= 3u )
                      {
                        _InterlockedDecrement((volatile signed __int32 *)v55 + 16);
                        v56 = (__int64)v138 + 16;
                        v139 = (__int64)v138 + 16;
                        if ( !_InterlockedDecrement((volatile signed __int32 *)v138 + 10) )
                        {
                          if ( *(_QWORD *)(v139 + 8) )
                          {
                            v57 = (SOS_ResourceGroup *)(v56 - 16);
                            if ( !v56 )
                              v57 = 0;
                            v213 = v57;
                            TList<GroupList,SOS_ResourceGroup,16,TListSLock>::RemoveElem(*(_QWORD *)(v139 + 16), v57);
                            SOS_ResourceGroup::Destroy(v57);
                            v95 = 0;
                            goto LABEL_133;
                          }
                          if ( v56 )
                          {
                            SOS_ResourceGroup::Destroy((SOS_ResourceGroup *)(v56 - 16));
                            v95 = 0;
                            goto LABEL_133;
                          }
                          SOS_ResourceGroup::Destroy(0);
                        }
                      }
                      v95 = 0;
                      goto LABEL_133;
                    }
                    if ( v55 == (struct SOS_ResourceGroup *)((char *)&SOS_PublicGlobals::sm_ResourceManager + 112) )
                    {
                      v55 = DWGroup;
                      v214 = DWGroup;
                      DWGroup = 0;
                      v95 = v214;
                    }
                    if ( v10 )
                    {
                      DuplicatedUserConnections = COpenConnections::GetDuplicatedUserConnections(qword_102EF3DA8);
                      *((_DWORD *)v95 + 198) = DuplicatedUserConnections;
                      v55 = v95;
                    }
                    SOS_ResourceManager::BindCurrentTaskToGroup(SOS_PublicGlobals::sm_ResourceManager, v55);
                    v215 = *(_QWORD *)(v2 + 104);
                    v216 = *(_QWORD *)(v215 + 712);
                    v84 = v216;
                    *(_QWORD *)(v215 + 712) = v95;
                    if ( v84 )
                    {
                      if ( *(_DWORD *)(v84 + 164) >= 3u )
                      {
                        _InterlockedDecrement((volatile signed __int32 *)(v84 + 64));
                        v140 = v84 + 16;
                        if ( !_InterlockedDecrement((volatile signed __int32 *)(v84 + 40)) )
                        {
                          if ( *(_QWORD *)(v140 + 8) )
                          {
                            v85 = (SOS_ResourceGroup *)v84;
                            if ( v84 == -16 )
                              v85 = 0;
                            v217 = v85;
                            TList<GroupList,SOS_ResourceGroup,16,TListSLock>::RemoveElem(*(_QWORD *)(v140 + 16), v85);
                            v86 = v85;
                          }
                          else
                          {
                            v86 = 0;
                            if ( v84 != -16 )
                              v86 = (SOS_ResourceGroup *)v84;
                          }
                          SOS_ResourceGroup::Destroy(v86);
                        }
                      }
                    }
                  }
LABEL_133:
                  CAutoMsqlXact::CommitNestedXact((CAutoMsqlXact *)&v110, 0);
                  if ( !v10 )
                  {
                    v144 = 0;
                    DBMgr::CloseDB(*(_QWORD *)(qword_102ECFB00 + 32), 0, (unsigned int)v102, 3);
                  }
                  if ( v110 )
                    CAutoMsqlXact::RollbackNestedXact((CAutoMsqlXact *)&v110, 0);
                  if ( v101 )
                  {
                    v101 = 0;
                    ((void (__fastcall *)(__int64, __int64))g_dbtableFactory[6])(0xFFFFFFFFLL, 16);
                  }
                  v144 = NtCurrentTeb()->ThreadLocalStoragePointer;
                  v219 = v144[SystemThread_TlsIndex] + SystemThread_TlsOffset;
                  v220 = *(_QWORD *)(v219 + 80);
                  *(_DWORD *)(v220 + 600) = v100;
                  v58 = v126;
                  if ( (_QWORD)v126 )
                  {
                    *(_QWORD *)(*(_QWORD *)(v126 + 24) + 8LL) = v127;
                    *(_QWORD *)(v58 + 24) = *((_QWORD *)&v126 + 1);
                    v126 = 0;
                    v127 = 0;
                  }
                  v146 = &CConnectionOutput::`vftable';
                  ExcHandler::~ExcHandler((ExcHandler *)v226);
                }
                catch ( SQLError v181 )
                {
                  try
                  {
                    ExceptionBackout::ExceptionBackout((ExceptionBackout *)v222, (const struct SQLError *)&v181);
                    si128 = v181;
                    v228 = v182;
                    if ( !v92 && (v94 || !*(_DWORD *)(GetXdbServerGlobals(v88, v87) + 11976)) )
                    {
                      v102 = 0;
                      DBMgr::CloseDB(*(_QWORD *)(qword_102ECFB00 + 32), 0, v96, 3);
                    }
                    v89 = *(_QWORD *)(v115 + 128);
                    v221 = v89;
                    *(_BYTE *)(v89 + 296) = 0;
                    *(_DWORD *)(v89 + 76) &= ~0x2000000u;
                    ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v222);
                  }
                  catch ( ShortStackException )
                  {
                  }
                  v6 = 0;
                  v5 = -1;
                  v0 = v141;
                  v2 = v142;
                  v10 = v92;
                }
                v59 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                    + SystemThread_TlsOffset;
                v60 = *(struct Worker **)(v59 + 256);
                if ( !v60 )
                {
                  SystemThread::MakeMiniSOSThread(0);
                  v60 = *(struct Worker **)(v59 + 256);
                }
                if ( *((_DWORD *)v60 + 139) )
                  ExceptionPostCatchActions(v60);
                if ( !v95 )
                {
                  if ( v10 )
                  {
                    v61 = COpenConnections::GetDuplicatedUserConnections(qword_102EF3DA8);
                    *((_DWORD *)DWGroup + 198) = v61;
                  }
                  v62 = *(_QWORD *)(v2 + 104);
                  v63 = *(_QWORD *)(v62 + 712);
                  *(_QWORD *)(v62 + 712) = DWGroup;
                  if ( v63 )
                  {
                    if ( *(_DWORD *)(v63 + 164) >= 3u )
                    {
                      _InterlockedDecrement((volatile signed __int32 *)(v63 + 64));
                      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v63 + 40), 0xFFFFFFFF) == 1 )
                      {
                        if ( *(_QWORD *)(v63 + 24) )
                          TList<GroupList,SOS_ResourceGroup,16,TListSLock>::RemoveElem(*(_QWORD *)(v63 + 32), v63);
                        SOS_ResourceGroup::Destroy((SOS_ResourceGroup *)v63);
                      }
                    }
                  }
                  v64 = DWGroup;
                  DWGroup = 0;
                  SOS_ResourceManager::BindCurrentTaskToGroup(v0, v64);
                }
                v65 = DWGroup;
                if ( DWGroup )
                {
                  if ( *((_DWORD *)DWGroup + 41) >= 3u )
                  {
                    _InterlockedDecrement((volatile signed __int32 *)DWGroup + 16);
                    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v65 + 10, 0xFFFFFFFF) == 1 )
                    {
                      if ( *((_QWORD *)v65 + 3) )
                        TList<GroupList,SOS_ResourceGroup,16,TListSLock>::RemoveElem(*((_QWORD *)v65 + 4), v65);
                      SOS_ResourceGroup::Destroy(v65);
                    }
                  }
                  DWGroup = 0;
                }
                CClassifierTraceEvent::PostEvent((CClassifierTraceEvent *)&si128);
                v66 = si128.m128i_i32[0];
                v67 = si128.m128i_i32[0];
                if ( v228 != 1 )
                  v67 = si128.m128i_u16[0];
                if ( !v67 )
                  goto LABEL_179;
                if ( v228 != 1 )
                  v66 = si128.m128i_u16[0];
                if ( v66 == 3617 )
                {
LABEL_179:
                  v73 = v116;
                  if ( v116 )
                  {
                    *(_BYTE *)(v116 + 270) |= 4u;
                    *(_BYTE *)(v73 + 271) |= 1u;
                    *(_DWORD *)(v73 + 404) = 1;
                  }
LABEL_20:
                  SOS_AutoReleaseResourceGroup::UnhookAndRelease((SOS_AutoReleaseResourceGroup *)&DWGroup);
                  return;
                }
                v68 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                + SystemThread_TlsOffset
                                + 80LL);
                if ( Base_PublicGlobals::sm_invariantTscAvailable )
                {
                  QueryPerformanceCounter(&PerformanceCount);
                  QuadPart = (CSbTransportMgr *)PerformanceCount.QuadPart;
                }
                else
                {
                  QuadPart = MEMORY[0x7FFE0008];
                }
                v70 = *(_QWORD *)(v68 + 208);
                if ( (unsigned __int64)QuadPart < v70 )
                {
                  v71 = 0;
                }
                else
                {
                  v71 = (unsigned __int64)QuadPart - v70;
                  if ( v71 == -1 )
                  {
LABEL_173:
                    v72 = si128.m128i_u32[0];
                    if ( v228 != 1 )
                      v72 = si128.m128i_u16[0];
                    if ( v97 == *(_DWORD *)(v107 + 4676) )
                    {
                      v6 = 257;
                      if ( *(_DWORD *)(v107 + 4680) < 0x101u )
                        v6 = *(_DWORD *)(v107 + 4680);
                    }
                    LODWORD(v91) = *(__int16 *)(v68 + 72);
                    LODWORD(v90) = si128.m128i_i32[3];
                    scierrlog(0x2AE6u, 2LL * v6, v107 + 4684, v72, v90, v91, v5);
                    goto LABEL_179;
                  }
                }
                if ( Base_PublicGlobals::sm_invariantTscAvailable )
                  v5 = 1000 * v71 / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
                else
                  v5 = v71 / 0x2710;
                goto LABEL_173;
              }
            }
LABEL_11:
            v10 = 0;
            goto LABEL_12;
          }
        }
        if ( *(_DWORD *)(*(_QWORD *)((*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v2 + 96) + 16LL))(*(_QWORD *)(v2 + 96))
                                   + 520)
                       + 20LL) )
        {
          do
            v28 = SOS_ResourceManager::LookupGroup(
                    SOS_PublicGlobals::sm_ResourceManager,
                    L"XOdbcGroup",
                    SOS_PublicGlobals::sm_ResourceManager,
                    &DWGroup);
          while ( v28 == 0x80000000 );
          goto LABEL_67;
        }
        v29 = *(const wchar_t **)(v2 + 960);
        if ( v29 )
        {
          v30 = *(_DWORD *)(v2 + 968);
        }
        else
        {
          v32 = *(_QWORD *)(v2 + 192);
          v30 = 2 * *(unsigned __int16 *)(v32 + 50);
          v29 = (const wchar_t *)(v32 + *(unsigned __int16 *)(v32 + 48));
        }
        v31 = SloInfo::MapAppNameToWorkloadGroup(v29, v30);
        if ( v31 )
        {
          do
            v28 = SOS_ResourceManager::LookupGroup(
                    SOS_PublicGlobals::sm_ResourceManager,
                    v31,
                    SOS_PublicGlobals::sm_ResourceManager,
                    &DWGroup);
          while ( v28 == 0x80000000 );
          goto LABEL_67;
        }
      }
      v27 = qword_102EF3550;
      goto LABEL_77;
    }
    DACGroup = SloInfo::GetDACGroup();
    v16 = DACGroup;
    if ( DACGroup && (_UNKNOWN *)DACGroup != (_UNKNOWN *)((char *)&SOS_PublicGlobals::sm_ResourceManager + 3576) )
    {
      if ( *(_DWORD *)(DACGroup + 164) >= 3u )
      {
        v17 = *(_DWORD *)(DACGroup + 64);
        if ( v17 >= 0 )
        {
          while ( v17 != _InterlockedCompareExchange((volatile signed __int32 *)(v16 + 64), v17 + 1, v17) )
          {
            v17 = *(_DWORD *)(v16 + 64);
            if ( v17 < 0 )
              goto LABEL_27;
          }
          _InterlockedIncrement((volatile signed __int32 *)(v16 + 40));
        }
      }
LABEL_27:
      v18 = *(_QWORD *)(v2 + 104);
      v19 = *(_QWORD *)(v18 + 712);
      *(_QWORD *)(v18 + 712) = v16;
      if ( v19 )
      {
        if ( *(_DWORD *)(v19 + 164) >= 3u )
        {
          _InterlockedDecrement((volatile signed __int32 *)(v19 + 64));
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v19 + 40), 0xFFFFFFFF) == 1 )
          {
            if ( *(_QWORD *)(v19 + 24) )
              TList<GroupList,SOS_ResourceGroup,16,TListSLock>::RemoveElem(*(_QWORD *)(v19 + 32), v19);
            SOS_ResourceGroup::Destroy((SOS_ResourceGroup *)v19);
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x100550410  mov     rax, rsp
0x100550413  push    r13
0x100550415  push    r14
0x100550417  push    r15
0x100550419  sub     rsp, 800h
0x100550420  mov     qword ptr [rax-408h], 0FFFFFFFFFFFFFFFEh
0x10055042b  mov     [rax+8], rbx
0x10055042f  mov     [rax+10h], rsi
0x100550433  mov     [rax+18h], rdi
0x100550437  mov     [rax+20h], r12
0x10055043b  mov     rax, cs:__security_cookie
0x100550442  xor     rax, rsp
0x100550445  mov     [rsp+818h+var_28], rax
0x10055044d  mov     rsi, cs:__imp_?sm_ResourceManager@SOS_PublicGlobals@@2VSOS_ResourceManager@@A; SOS_ResourceManager SOS_PublicGlobals::sm_ResourceManager
0x100550454  mov     [rsp+818h+var_650], rsi
0x10055045c  mov     rax, cs:__imp_?sm_isResourceManagerEnabled@SOS_PublicGlobals@@2HA; int SOS_PublicGlobals::sm_isResourceManagerEnabled
0x100550463  cmp     dword ptr [rax], 0
0x100550466  jz      loc_1005505DF
0x10055046c  mov     rdx, gs:58h
0x100550475  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10055047c  mov     ecx, [rax]
0x10055047e  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100550485  mov     eax, [rax]
0x100550487  add     rax, [rdx+rcx*8]
0x10055048b  mov     rax, [rax]
0x10055048e  mov     r14, [rax+48h]
0x100550492  mov     [rsp+818h+var_648], r14
0x10055049a  test    byte ptr [r14+10Dh], 20h
0x1005504a2  jnz     loc_100DE6BCC
0x1005504a8  call    cs:__imp_GetXdbServerGlobals
0x1005504ae  cmp     dword ptr [rax+2EC8h], 0
0x1005504b5  jnz     loc_100DE6C90
0x1005504bb  mov     r12, 0FFFFFFFFFFFFFFFFh
0x1005504c2  xor     ebx, ebx
0x1005504c4  mov     [rsp+818h+var_7C0], rbx
0x1005504c9  mov     dil, 1
0x1005504cc  xor     al, al
0x1005504ce  mov     [rsp+818h+var_7C8], al
0x1005504d2  mov     rax, cs:qword_102ECFB00
0x1005504d9  cmp     [rax+38A8h], ebx
0x1005504df  jnz     loc_100DE6D58
0x1005504e5  call    cs:__imp_GetXdbServerGlobals
0x1005504eb  cmp     byte ptr [rax+2EE4h], 0
0x1005504f2  jnz     loc_100DE6D8B
0x1005504f8  mov     rax, cs:qword_102EF3550
0x1005504ff  cmp     byte ptr [rax+662h], 0
0x100550506  jnz     loc_100DE6DBA
0x10055050c  test    dil, dil
0x10055050f  jz      short loc_100550537
0x100550511  call    cs:__imp_GetXdbServerGlobals
0x100550517  cmp     dword ptr [rax+2074h], 0
0x10055051e  jnz     loc_100DE6E07
0x100550524  call    cs:__imp_GetXdbServerGlobals
0x10055052a  cmp     dword ptr [rax+2EC8h], 0
0x100550531  jnz     loc_100DE6DE9
0x100550537  movzx   r13d, [rsp+818h+var_7C8]
0x10055053d  cmp     [rsp+818h+var_7C0], 0
0x100550543  jnz     short loc_10055054E
0x100550545  lea     rax, [rsi+70h]
0x100550549  mov     [rsp+818h+var_7C0], rax
0x10055054e  test    r13b, r13b
0x100550551  jnz     loc_100DE71B6
0x100550557  call    cs:__imp_?GetMasterDbId@@YAGXZ; GetMasterDbId(void)
0x10055055d  movzx   r15d, ax
0x100550561  mov     [rsp+818h+var_7A8], r15w
0x100550567  movzx   eax, r15w
0x10055056b  mov     dword ptr [rsp+818h+var_788], eax
0x100550572  mov     ecx, eax
0x100550574  mov     rdx, cs:__imp_?g_dbtableFactory@@3UDBTableFactory@@A; DBTableFactory g_dbtableFactory
0x10055057b  call    qword ptr [rdx+20h]
0x10055057e  mov     [rsp+818h+var_770], rax
0x100550586  mov     ecx, [rax+1244h]
0x10055058c  mov     [rsp+818h+var_7A4], ecx
0x100550590  test    ecx, ecx
0x100550592  jnz     loc_100DE71E7
0x100550598  mov     rcx, [r14+68h]
0x10055059c  mov     rdi, [rcx+2C8h]
0x1005505a3  mov     rax, [rsp+818h+var_7C0]
0x1005505a8  mov     [rcx+2C8h], rax
0x1005505af  test    rdi, rdi
0x1005505b2  jz      short loc_1005505C1
0x1005505b4  cmp     dword ptr [rdi+0A4h], 3
0x1005505bb  jnb     loc_100DE826F
0x1005505c1  mov     rdx, [rsp+818h+var_7C0]
0x1005505c6  mov     [rsp+818h+var_7C0], rbx
0x1005505cb  mov     rcx, rsi
0x1005505ce  call    cs:__imp_?BindCurrentTaskToGroup@SOS_ResourceManager@@QEAAXPEAVSOS_ResourceGroup@@@Z; SOS_ResourceManager::BindCurrentTaskToGroup(SOS_ResourceGroup *)
0x1005505d4  nop
0x1005505d5  lea     rcx, [rsp+818h+var_7C0]; this
0x1005505da  call    ?UnhookAndRelease@SOS_AutoReleaseResourceGroup@@QEAAXXZ; SOS_AutoReleaseResourceGroup::UnhookAndRelease(void)
0x1005505df  mov     rcx, [rsp+818h+var_28]
0x1005505e7  xor     rcx, rsp; StackCookie
0x1005505ea  call    __security_check_cookie
0x1005505ef  lea     r11, [rsp+818h+var_18]
0x1005505f7  mov     rbx, [r11+20h]
0x1005505fb  mov     rsi, [r11+28h]
0x1005505ff  mov     rdi, [r11+30h]
0x100550603  mov     r12, [r11+38h]
0x100550607  mov     rsp, r11
0x10055060a  pop     r15
0x10055060c  pop     r14
0x10055060e  pop     r13
0x100550610  retn
0x100de6bcc  call    cs:__imp_?GetDACGroup@SloInfo@@SAPEAVSOS_ResourceGroup@@XZ; SloInfo::GetDACGroup(void)
0x100de6bd2  mov     rdx, rax
0x100de6bd5  test    rax, rax
0x100de6bd8  jz      loc_1005505DF
0x100de6bde  lea     rcx, [rsi+0DF8h]
0x100de6be5  cmp     rax, rcx
0x100de6be8  jz      loc_1005505DF
0x100de6bee  cmp     dword ptr [rax+0A4h], 3
0x100de6bf5  jb      short loc_100DE6C24
0x100de6bf7  mov     eax, [rax+40h]
0x100de6bfa  test    eax, eax
0x100de6bfc  js      short loc_100DE6C24
0x100de6bfe  nop     word ptr [rax+rax]
0x100de6c03  nop     dword ptr [rax+00h]
0x100de6c07  nop     word ptr [rax+rax+00000000h]
0x100de6c10  lea     ecx, [rax+1]
0x100de6c13  lock cmpxchg [rdx+40h], ecx
0x100de6c18  jz      short loc_100DE6C89
0x100de6c1a  mov     eax, [rdx+40h]
0x100de6c1d  test    eax, eax
0x100de6c1f  jns     short loc_100DE6C10
0x100de6c21  jmp     short loc_100DE6C24
0x100de6c24  mov     rax, [r14+68h]
0x100de6c28  mov     rbx, [rax+2C8h]
0x100de6c2f  mov     [rax+2C8h], rdx
0x100de6c36  test    rbx, rbx
0x100de6c39  jz      loc_1005505DF
0x100de6c3f  cmp     dword ptr [rbx+0A4h], 3
0x100de6c46  jb      loc_1005505DF
0x100de6c4c  lock dec dword ptr [rbx+40h]
0x100de6c50  mov     r12, 0FFFFFFFFFFFFFFFFh
0x100de6c57  lock xadd [rbx+28h], r12d
0x100de6c5d  cmp     r12d, 1
0x100de6c61  jnz     loc_1005505DF
0x100de6c67  cmp     qword ptr [rbx+18h], 0
0x100de6c6c  jz      short loc_100DE6C7A
0x100de6c6e  mov     rdx, rbx
0x100de6c71  mov     rcx, [rbx+20h]
0x100de6c75  call    ?RemoveElem@?$TList@VGroupList@@VSOS_ResourceGroup@@$0BA@UTListSLock@@@@QEAAXPEAVSOS_ResourceGroup@@@Z; TList<GroupList,SOS_ResourceGroup,16,TListSLock>::RemoveElem(SOS_ResourceGroup *)
0x100de6c7a  mov     rcx, rbx
0x100de6c7d  call    cs:__imp_?Destroy@SOS_ResourceGroup@@QEAAXXZ; SOS_ResourceGroup::Destroy(void)
0x100de6c83  jmp     loc_1005505DF
0x100de6c89  lock inc dword ptr [rdx+28h]
0x100de6c8d  jmp     short loc_100DE6C24
0x100de6c90  mov     rax, cs:qword_102EF3550
0x100de6c97  cmp     byte ptr [rax+2E7h], 0
0x100de6c9e  jz      loc_1005504BB
0x100de6ca4  mov     rdx, gs:58h
0x100de6cad  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100de6cb4  mov     ecx, [rax]
0x100de6cb6  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100de6cbd  mov     eax, [rax]
0x100de6cbf  add     rax, [rdx+rcx*8]
0x100de6cc3  mov     rax, [rax+50h]
0x100de6cc7  movzx   ecx, word ptr [rax+258h]
0x100de6cce  mov     rax, cs:__imp_?g_dbtableFactory@@3UDBTableFactory@@A; DBTableFactory g_dbtableFactory
0x100de6cd5  call    qword ptr [rax+20h]
0x100de6cd8  test    rax, rax
0x100de6cdb  jz      loc_1005504BB
0x100de6ce1  mov     r9, gs:58h
0x100de6cea  mov     rcx, cs:__imp_SystemThread_TlsIndex
0x100de6cf1  mov     edx, [rcx]
0x100de6cf3  mov     rcx, cs:__imp_SystemThread_TlsOffset
0x100de6cfa  mov     r8d, [rcx]
0x100de6cfd  add     r8, [r9+rdx*8]
0x100de6d01  mov     rdi, [r8+50h]
0x100de6d05  mov     rbx, [rax+1238h]
0x100de6d0c  mov     rcx, [rdi+428h]
0x100de6d13  mov     r12, 0FFFFFFFFFFFFFFFFh
0x100de6d1a  test    rcx, rcx
0x100de6d1d  jz      short loc_100DE6D3E
0x100de6d1f  lea     rdx, [rcx+8]
0x100de6d23  mov     eax, r12d
0x100de6d26  lock xadd [rdx], eax
0x100de6d2a  cmp     eax, 1
0x100de6d2d  jnz     short loc_100DE6D3E
0x100de6d2f  test    rdx, rdx
0x100de6d32  jz      short loc_100DE6D3E
0x100de6d34  mov     rax, [rcx]
0x100de6d37  lea     edx, [r12+2]
0x100de6d3c  call    qword ptr [rax]
0x100de6d3e  mov     [rdi+428h], rbx
0x100de6d45  test    rbx, rbx
0x100de6d48  jz      loc_1005504C2
0x100de6d4e  lock inc dword ptr [rbx+8]
0x100de6d52  jmp     loc_1005504C2
0x100de6d58  call    cs:__imp_GetXdbServerGlobals
0x100de6d5e  cmp     [rax+2EE9h], bl
0x100de6d64  jnz     short loc_100DE6D78
0x100de6d66  call    cs:__imp_GetXdbServerGlobals
0x100de6d6c  cmp     [rax+2EE8h], bl
0x100de6d72  jz      loc_1005504E5
0x100de6d78  call    cs:__imp_GetXdbServerGlobals
0x100de6d7e  cmp     byte ptr [rax+2EE4h], 0
0x100de6d85  jnz     loc_1005504E5
0x100de6d8b  mov     rax, cs:qword_102EF3550
0x100de6d92  cmp     byte ptr [rax+631h], 0
0x100de6d99  jz      loc_1005504F8
0x100de6d9f  call    cs:__imp_?GetDWGroup@SloInfo@@SAPEAVSOS_ResourceGroup@@XZ; SloInfo::GetDWGroup(void)
0x100de6da5  mov     [rsp+818h+var_7C0], rax
0x100de6daa  movzx   edi, dil
0x100de6dae  test    rax, rax
0x100de6db1  cmovnz  edi, ebx
0x100de6db4  jmp     loc_1005504F8
0x100de6dba  test    byte ptr [r14+10Eh], 40h
0x100de6dc2  jz      loc_10055050C
0x100de6dc8  call    cs:__imp_?GetVDWFrontendGroup@SloInfo@@SAPEAVSOS_ResourceGroup@@XZ; SloInfo::GetVDWFrontendGroup(void)
0x100de6dce  mov     [rsp+818h+var_7C0], rax
0x100de6dd3  test    rax, rax
0x100de6dd6  jz      loc_10055050C
0x100de6ddc  xor     dil, dil
0x100de6ddf  movzx   r13d, dil
0x100de6de3  jmp     loc_10055053D
0x100de6de9  test    byte ptr [r14+10Eh], 2
0x100de6df1  jnz     short loc_100DE6E07
0x100de6df3  mov     rax, cs:qword_102EF3550
0x100de6dfa  cmp     byte ptr [rax+2E7h], 0
0x100de6e01  jnz     loc_100550537
0x100de6e07  call    ?FPDWFeaturesExposed@@YA_NXZ; FPDWFeaturesExposed(void)
0x100de6e0c  test    al, al
0x100de6e0e  jz      loc_100DE6EAF
0x100de6e14  mov     r15, [r14+3C0h]
0x100de6e1b  test    r15, r15
0x100de6e1e  jnz     short loc_100DE6E2F
0x100de6e20  mov     rax, [r14+0C0h]
0x100de6e27  movzx   r15d, word ptr [rax+30h]
0x100de6e2c  add     r15, rax
0x100de6e2f  mov     r8, rbx
0x100de6e32  mov     rax, cs:qword_102EF3550
0x100de6e39  cmp     [rax+2CEh], r8b
0x100de6e40  jnz     short loc_100DE6E52
0x100de6e42  mov     rax, cs:qword_102ECFB10
0x100de6e49  test    byte ptr [rax+598h], 20h
0x100de6e50  jz      short loc_100DE6E91
0x100de6e52  mov     rdx, gs:58h
0x100de6e5b  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100de6e62  mov     ecx, [rax]
0x100de6e64  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100de6e6b  mov     eax, [rax]
0x100de6e6d  add     rax, [rdx+rcx*8]
0x100de6e71  mov     rax, [rax+50h]
0x100de6e75  movzx   ecx, word ptr [rax+258h]
0x100de6e7c  test    cx, cx
0x100de6e7f  jz      short loc_100DE6E91
0x100de6e81  lfence
0x100de6e84  mov     rax, cs:__imp_?g_dbtableFactory@@3UDBTableFactory@@A; DBTableFactory g_dbtableFactory
0x100de6e8b  call    qword ptr [rax+20h]
0x100de6e8e  mov     r8, rax; struct DBTABLE *
0x100de6e91  mov     rcx, r15; String1
0x100de6e94  call    ?ParsePDWResourceGroup@@YAPEAVSOS_ResourceGroup@@PEB_WHPEAVDBTABLE@@@Z; ParsePDWResourceGroup(wchar_t const *,int,DBTABLE *)
0x100de6e99  mov     [rsp+818h+var_7C0], rax
0x100de6e9e  test    rax, rax
0x100de6ea1  jz      short loc_100DE6EAF
0x100de6ea3  xor     dil, dil
0x100de6ea6  movzx   r13d, dil
0x100de6eaa  jmp     loc_10055053D
0x100de6eaf  test    byte ptr [r14+10Eh], 4
0x100de6eb7  jnz     loc_100DE6FA5
0x100de6ebd  call    cs:__imp_GetXdbServerGlobals
0x100de6ec3  cmp     dword ptr [rax+2EC8h], 0
0x100de6eca  jz      short loc_100DE6EEE
0x100de6ecc  mov     rax, cs:qword_102EF3550
0x100de6ed3  cmp     byte ptr [rax+2E6h], 0
0x100de6eda  jz      loc_100DE6FAC
0x100de6ee0  test    byte ptr [r14+10Eh], 2
0x100de6ee8  jz      loc_100DE6FAC
0x100de6eee  mov     rcx, [r14+60h]
0x100de6ef2  mov     rax, [rcx]
0x100de6ef5  call    qword ptr [rax+10h]
0x100de6ef8  mov     rcx, [rax+208h]
0x100de6eff  cmp     dword ptr [rcx+14h], 0
0x100de6f03  jz      short loc_100DE6F48
0x100de6f05  nop     dword ptr [rax]
0x100de6f08  nop     dword ptr [rax+rax+00000000h]
0x100de6f10  movsxd  r8, dword ptr [rsi]
0x100de6f13  lea     r9, [rsp+818h+var_7C0]
0x100de6f18  lea     rdx, aXodbcgroup; "XOdbcGroup"
0x100de6f1f  mov     rcx, rsi
0x100de6f22  call    cs:__imp_?LookupGroup@SOS_ResourceManager@@QEAA?AW4SOS_RESULT@@PEB_W_JPEAPEAVSOS_ResourceGroup@@@Z; SOS_ResourceManager::LookupGroup(wchar_t const *,__int64,SOS_ResourceGroup * *)
0x100de6f28  cmp     eax, 80000000h
0x100de6f2d  jz      short loc_100DE6F10
0x100de6f2f  test    eax, eax
0x100de6f31  jz      short loc_100DE6F3C
0x100de6f33  lea     rax, [rsi+70h]
0x100de6f37  mov     [rsp+818h+var_7C0], rax
0x100de6f3c  xor     dil, dil
0x100de6f3f  movzx   r13d, dil
0x100de6f43  jmp     loc_10055053D
0x100de6f48  mov     rcx, [r14+3C0h]
0x100de6f4f  test    rcx, rcx
0x100de6f52  jz      short loc_100DE6F8E
0x100de6f54  mov     edx, [r14+3C8h]
0x100de6f5b  jmp     short loc_100DE6F5E
0x100de6f5e  call    cs:__imp_?MapAppNameToWorkloadGroup@SloInfo@@SAPEB_WQEB_WH@Z; SloInfo::MapAppNameToWorkloadGroup(wchar_t const * const,int)
0x100de6f64  mov     r15, rax
0x100de6f67  test    rax, rax
0x100de6f6a  jz      short loc_100DE6FA5
  ... truncated ...
```
