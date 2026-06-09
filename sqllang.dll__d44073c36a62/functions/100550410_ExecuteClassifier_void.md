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
  __int64 v1; // r14
  __int64 v2; // rcx
  unsigned __int64 v3; // r12
  unsigned int v4; // ebx
  bool v5; // di
  __int64 v6; // rcx
  char v7; // r13
  unsigned __int16 MasterDbId; // r15
  __int64 v9; // rcx
  __int64 v10; // rdi
  struct SOS_ResourceGroup *v11; // rdx
  __int64 DACGroup; // rax
  __int64 v13; // rdx
  signed __int32 v14; // eax
  __int64 v15; // rax
  __int64 v16; // rbx
  __int64 v17; // rax
  __int64 v18; // rdi
  __int64 v19; // rbx
  _QWORD *ThreadLocalStoragePointer; // rdx
  __int64 v21; // rcx
  const wchar_t *v22; // r15
  struct DBTABLE *v23; // r8
  DataVirtualizationResource *v24; // rax
  int v25; // eax
  const wchar_t *v26; // rcx
  int v27; // edx
  const wchar_t *v28; // r15
  __int64 v29; // rax
  const wchar_t *v30; // rcx
  unsigned int v31; // eax
  __int64 v32; // rax
  __int64 v33; // r13
  __int64 v34; // rax
  __int64 v35; // r15
  __int64 v36; // r13
  __int64 v37; // rcx
  SloInfo *Slo; // rax
  char v39; // cl
  __int64 v40; // rdi
  __int64 v41; // rcx
  void ***v42; // rdx
  bool v43; // zf
  __int64 v44; // rax
  DBTABLE *v45; // r15
  __int64 v46; // rdi
  __int64 v47; // rax
  __int64 v48; // rdi
  __int64 v49; // rcx
  struct CSQLObject *ObjectByDbAndObjId; // rdi
  wchar_t *v51; // r13
  struct SOS_ResourceGroup *v52; // rdx
  __int64 v53; // rcx
  SOS_ResourceGroup *v54; // rdi
  __int64 v55; // rdx
  __int64 v56; // rdi
  struct Worker *v57; // rcx
  int v58; // eax
  __int64 v59; // rcx
  __int64 v60; // rdi
  struct SOS_ResourceGroup *v61; // rdx
  struct SOS_ResourceGroup *v62; // rdi
  __int32 v63; // eax
  __int32 v64; // edx
  __int64 v65; // rdi
  CSbTransportMgr *QuadPart; // rcx
  unsigned __int64 v67; // rax
  unsigned __int64 v68; // rcx
  __int64 v69; // r9
  __int64 v70; // rax
  int v71; // ecx
  unsigned int v72; // ecx
  SloInfo *v73; // r15
  __crt_locale_pointers *DefaultLocale; // rax
  struct SOS_ResourceGroup *PrimaryGroup; // rax
  void *v76; // rdi
  int v77; // r13d
  unsigned int v78; // edx
  int v79; // r15d
  int DuplicatedUserConnections; // eax
  __int64 v81; // rdx
  SOS_ResourceGroup *v82; // rdi
  SOS_ResourceGroup *v83; // rcx
  __int64 v84; // rcx
  __int64 v85; // rcx
  int (*v86)(int, int, int, int, char *); // [rsp+20h] [rbp-7F8h]
  struct Worker *v87; // [rsp+28h] [rbp-7F0h]
  char v88; // [rsp+50h] [rbp-7C8h]
  struct SOS_ResourceGroup *DWGroup; // [rsp+58h] [rbp-7C0h] BYREF
  char v90; // [rsp+60h] [rbp-7B8h]
  struct SOS_ResourceGroup *v91; // [rsp+68h] [rbp-7B0h] BYREF
  unsigned __int16 v92; // [rsp+70h] [rbp-7A8h]
  int v93; // [rsp+74h] [rbp-7A4h]
  char v94; // [rsp+78h] [rbp-7A0h]
  unsigned __int8 v95; // [rsp+80h] [rbp-798h]
  unsigned __int16 v96; // [rsp+84h] [rbp-794h]
  int v97; // [rsp+88h] [rbp-790h] BYREF
  __int64 v98; // [rsp+90h] [rbp-788h]
  int v99; // [rsp+98h] [rbp-780h]
  int v100; // [rsp+9Ch] [rbp-77Ch]
  unsigned int v101; // [rsp+A0h] [rbp-778h]
  __int64 v103; // [rsp+A8h] [rbp-770h]
  int v104; // [rsp+B0h] [rbp-768h]
  void *Source; // [rsp+B8h] [rbp-760h]
  int v106; // [rsp+C0h] [rbp-758h] BYREF
  int v107; // [rsp+C4h] [rbp-754h] BYREF
  int v108; // [rsp+C8h] [rbp-750h]
  __int128 v109; // [rsp+D0h] [rbp-748h]
  struct CSQLObject *v110; // [rsp+E0h] [rbp-738h]
  __int64 v111; // [rsp+E8h] [rbp-730h]
  __int64 v112; // [rsp+F0h] [rbp-728h]
  __int64 v113; // [rsp+F8h] [rbp-720h]
  void **v114; // [rsp+100h] [rbp-718h] BYREF
  _BYTE v115[2]; // [rsp+108h] [rbp-710h] BYREF
  __int16 v116; // [rsp+10Ah] [rbp-70Eh]
  wchar_t *String1; // [rsp+110h] [rbp-708h] BYREF
  __int64 v118; // [rsp+118h] [rbp-700h]
  int v119; // [rsp+120h] [rbp-6F8h]
  __int128 v120; // [rsp+128h] [rbp-6F0h] BYREF
  __int128 v121; // [rsp+138h] [rbp-6E0h]
  __int128 v122; // [rsp+150h] [rbp-6C8h]
  __int128 v123; // [rsp+160h] [rbp-6B8h]
  int v124; // [rsp+170h] [rbp-6A8h]
  int v125; // [rsp+174h] [rbp-6A4h]
  unsigned int v126; // [rsp+178h] [rbp-6A0h]
  unsigned int v127; // [rsp+180h] [rbp-698h]
  int v128; // [rsp+184h] [rbp-694h]
  int v129; // [rsp+188h] [rbp-690h]
  BOOL v130; // [rsp+190h] [rbp-688h]
  __int64 v132; // [rsp+1A0h] [rbp-678h]
  __int64 v133; // [rsp+1A8h] [rbp-670h]
  struct SOS_ResourceGroup *v134; // [rsp+1B0h] [rbp-668h]
  __int64 v135; // [rsp+1B8h] [rbp-660h]
  __int64 v136; // [rsp+1C0h] [rbp-658h]
  SOS_ResourceManager *v137; // [rsp+1C8h] [rbp-650h]
  __int64 v138; // [rsp+1D0h] [rbp-648h]
  LARGE_INTEGER PerformanceCount; // [rsp+1D8h] [rbp-640h] BYREF
  _QWORD *v140; // [rsp+1E0h] [rbp-638h]
  int v141; // [rsp+1E8h] [rbp-630h]
  void **v142; // [rsp+1F0h] [rbp-628h] BYREF
  void ***v143; // [rsp+1F8h] [rbp-620h]
  int v144; // [rsp+200h] [rbp-618h]
  __int64 v145; // [rsp+208h] [rbp-610h]
  __int64 v146; // [rsp+210h] [rbp-608h]
  int v147; // [rsp+218h] [rbp-600h]
  int v148; // [rsp+21Ch] [rbp-5FCh]
  __int64 v149; // [rsp+220h] [rbp-5F8h] BYREF
  char v150; // [rsp+228h] [rbp-5F0h]
  __int64 v151; // [rsp+230h] [rbp-5E8h]
  char v152; // [rsp+240h] [rbp-5D8h]
  char v153; // [rsp+248h] [rbp-5D0h]
  __int128 v154; // [rsp+250h] [rbp-5C8h] BYREF
  __int64 v155; // [rsp+260h] [rbp-5B8h]
  int v156; // [rsp+268h] [rbp-5B0h]
  int v157; // [rsp+26Ch] [rbp-5ACh]
  int v158; // [rsp+270h] [rbp-5A8h]
  int v159; // [rsp+274h] [rbp-5A4h]
  int v160; // [rsp+278h] [rbp-5A0h]
  __int64 v161; // [rsp+280h] [rbp-598h]
  int v162; // [rsp+288h] [rbp-590h]
  __int16 v163; // [rsp+28Ch] [rbp-58Ch]
  int v164; // [rsp+290h] [rbp-588h]
  int v165; // [rsp+294h] [rbp-584h]
  char v166; // [rsp+298h] [rbp-580h]
  __int64 v167; // [rsp+2A0h] [rbp-578h]
  int v168; // [rsp+2A8h] [rbp-570h]
  __int16 v169; // [rsp+2ACh] [rbp-56Ch]
  __int128 v170; // [rsp+2B0h] [rbp-568h]
  int v171; // [rsp+2C0h] [rbp-558h]
  __int16 v172; // [rsp+2C4h] [rbp-554h]
  __int16 v173; // [rsp+2C6h] [rbp-552h]
  __int16 v174; // [rsp+2C8h] [rbp-550h]
  int v175; // [rsp+2CCh] [rbp-54Ch]
  char v176; // [rsp+2D0h] [rbp-548h]
  __m128i v177; // [rsp+2E0h] [rbp-538h] BYREF
  int v178; // [rsp+2F0h] [rbp-528h]
  __int64 v179; // [rsp+2F8h] [rbp-520h]
  __int64 v180; // [rsp+300h] [rbp-518h]
  _QWORD *v181; // [rsp+308h] [rbp-510h]
  _QWORD *v182; // [rsp+310h] [rbp-508h]
  _QWORD *v183; // [rsp+318h] [rbp-500h]
  __int64 v184; // [rsp+320h] [rbp-4F8h]
  __int64 v185; // [rsp+328h] [rbp-4F0h]
  _QWORD *v186; // [rsp+330h] [rbp-4E8h]
  _QWORD *v187; // [rsp+338h] [rbp-4E0h]
  _QWORD *v188; // [rsp+340h] [rbp-4D8h]
  __int64 v189; // [rsp+348h] [rbp-4D0h]
  __int64 v190; // [rsp+350h] [rbp-4C8h]
  __int64 v191; // [rsp+358h] [rbp-4C0h]
  __int128 *v192; // [rsp+360h] [rbp-4B8h]
  _BYTE *v193; // [rsp+368h] [rbp-4B0h]
  wchar_t **p_String1; // [rsp+370h] [rbp-4A8h]
  _BYTE *v195; // [rsp+378h] [rbp-4A0h]
  _QWORD *v196; // [rsp+380h] [rbp-498h]
  __int64 v197; // [rsp+388h] [rbp-490h]
  __int64 v198; // [rsp+390h] [rbp-488h]
  __int128 *v199; // [rsp+398h] [rbp-480h]
  _QWORD *v200; // [rsp+3A0h] [rbp-478h]
  __int64 v201; // [rsp+3A8h] [rbp-470h]
  struct IMemObj *v202; // [rsp+3B0h] [rbp-468h]
  struct CSQLObject *v203; // [rsp+3B8h] [rbp-460h]
  struct CSQLObject *v204; // [rsp+3C0h] [rbp-458h]
  __int128 *v205; // [rsp+3C8h] [rbp-450h]
  SloInfo *v206; // [rsp+3D0h] [rbp-448h]
  struct CSQLObject *v207; // [rsp+3D8h] [rbp-440h]
  struct SOS_ResourceGroup *v208; // [rsp+3E0h] [rbp-438h]
  SOS_ResourceGroup *v209; // [rsp+3E8h] [rbp-430h]
  struct SOS_ResourceGroup *v210; // [rsp+3F0h] [rbp-428h]
  __int64 v211; // [rsp+3F8h] [rbp-420h]
  __int64 v212; // [rsp+400h] [rbp-418h]
  SOS_ResourceGroup *v213; // [rsp+408h] [rbp-410h]
  __int64 v214; // [rsp+410h] [rbp-408h]
  __int64 v215; // [rsp+418h] [rbp-400h]
  __int64 v216; // [rsp+420h] [rbp-3F8h]
  __int64 v217; // [rsp+428h] [rbp-3F0h]
  _QWORD v218[5]; // [rsp+430h] [rbp-3E8h] BYREF
  _QWORD *v219; // [rsp+458h] [rbp-3C0h]
  __int64 v220; // [rsp+460h] [rbp-3B8h]
  __int64 v221; // [rsp+468h] [rbp-3B0h]
  _BYTE v222[48]; // [rsp+470h] [rbp-3A8h] BYREF
  __m128i si128; // [rsp+4A0h] [rbp-378h] BYREF
  int v224; // [rsp+4B0h] [rbp-368h]
  unsigned __int16 v225; // [rsp+4B4h] [rbp-364h]
  int v226; // [rsp+4B8h] [rbp-360h]
  char v227; // [rsp+4BCh] [rbp-35Ch]
  unsigned int v228; // [rsp+4C0h] [rbp-358h]
  char Destination[268]; // [rsp+4C4h] [rbp-354h] BYREF
  _BYTE v230[272]; // [rsp+5D0h] [rbp-248h] BYREF
  wchar_t v231[136]; // [rsp+6E0h] [rbp-138h] BYREF

  v214 = -2;
  v0 = (SOS_ResourceManager *)SOS_PublicGlobals::sm_ResourceManager;
  v137 = (SOS_ResourceManager *)SOS_PublicGlobals::sm_ResourceManager;
  if ( SOS_PublicGlobals::sm_isResourceManagerEnabled )
  {
    v1 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                               + SystemThread_TlsOffset)
                   + 72LL);
    v138 = v1;
    if ( (*(_BYTE *)(v1 + 269) & 0x20) == 0 )
    {
      if ( *(_DWORD *)(GetXdbServerGlobals(SystemThread_TlsIndex) + 11976)
        && *((_BYTE *)qword_102EF3550 + 743)
        && (v17 = ((__int64 (__fastcall *)(_QWORD))g_dbtableFactory[4])(*(unsigned __int16 *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset + 80LL)
                                                                                            + 600LL))) != 0 )
      {
        v18 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                        + SystemThread_TlsOffset
                        + 80LL);
        v19 = *(_QWORD *)(v17 + 4664);
        v2 = *(_QWORD *)(v18 + 1064);
        v3 = -1;
        if ( v2 && _InterlockedExchangeAdd((volatile signed __int32 *)(v2 + 8), 0xFFFFFFFF) == 1 && v2 != -8 )
          (**(void (__fastcall ***)(__int64, __int64))v2)(v2, 1);
        *(_QWORD *)(v18 + 1064) = v19;
        if ( v19 )
          _InterlockedIncrement((volatile signed __int32 *)(v19 + 8));
      }
      else
      {
        v3 = -1;
      }
      v4 = 0;
      DWGroup = 0;
      v5 = 1;
      v88 = 0;
      if ( (*(_DWORD *)(qword_102ECFB00 + 14504)
         && (*(_BYTE *)(GetXdbServerGlobals(v2) + 12009) || *(_BYTE *)(GetXdbServerGlobals(v2) + 12008))
         && !*(_BYTE *)(GetXdbServerGlobals(v2) + 12004)
         || *(_BYTE *)(GetXdbServerGlobals(v2) + 12004))
        && *((_BYTE *)qword_102EF3550 + 1585) )
      {
        DWGroup = (struct SOS_ResourceGroup *)SloInfo::GetDWGroup();
        v5 = DWGroup == 0;
      }
      if ( *((_BYTE *)qword_102EF3550 + 1634) )
      {
        if ( (*(_BYTE *)(v1 + 270) & 0x40) != 0 )
        {
          DWGroup = (struct SOS_ResourceGroup *)SloInfo::GetVDWFrontendGroup();
          if ( DWGroup )
          {
            v5 = 0;
            v7 = 0;
            goto LABEL_12;
          }
        }
      }
      if ( !v5
        || !*(_DWORD *)(GetXdbServerGlobals(v2) + 8308)
        && (!*(_DWORD *)(GetXdbServerGlobals(v6) + 11976)
         || (*(_BYTE *)(v1 + 270) & 2) == 0 && *((_BYTE *)qword_102EF3550 + 743)) )
      {
        goto LABEL_11;
      }
      if ( FPDWFeaturesExposed() )
      {
        v22 = *(const wchar_t **)(v1 + 960);
        if ( !v22 )
          v22 = (const wchar_t *)(*(_QWORD *)(v1 + 192) + *(unsigned __int16 *)(*(_QWORD *)(v1 + 192) + 48LL));
        v23 = 0;
        if ( *((_BYTE *)qword_102EF3550 + 718) || (*((_BYTE *)qword_102ECFB10 + 1432) & 0x20) != 0 )
        {
          ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
          if ( *(_WORD *)(*(_QWORD *)(ThreadLocalStoragePointer[SystemThread_TlsIndex] + SystemThread_TlsOffset + 80LL)
                        + 600LL) )
          {
            _mm_lfence();
            v23 = (struct DBTABLE *)((__int64 (*)(void))g_dbtableFactory[4])();
          }
        }
        DWGroup = ParsePDWResourceGroup(v22, (int)ThreadLocalStoragePointer, v23);
        if ( DWGroup )
        {
          v5 = 0;
          v7 = 0;
          goto LABEL_12;
        }
      }
      if ( (*(_BYTE *)(v1 + 270) & 4) == 0 )
      {
        if ( *(_DWORD *)(GetXdbServerGlobals(v21) + 11976) )
        {
          v24 = qword_102EF3550;
          if ( !*((_BYTE *)qword_102EF3550 + 742) || (*(_BYTE *)(v1 + 270) & 2) == 0 )
          {
LABEL_77:
            if ( *((_BYTE *)v24 + 1342) )
            {
              v30 = *(const wchar_t **)(v1 + 960);
              if ( v30 )
              {
                v31 = *(_DWORD *)(v1 + 968);
LABEL_80:
                if ( v31 >= 0x16 && wcsstr(v30, L"SQLExternalMonitoring") )
                {
                  do
                    v25 = SOS_ResourceManager::LookupGroup(
                            SOS_PublicGlobals::sm_ResourceManager,
                            L"SQLExternalMonitoringGroup",
                            SOS_PublicGlobals::sm_ResourceManager,
                            &DWGroup);
                  while ( v25 == 0x80000000 );
LABEL_67:
                  if ( v25 )
                    DWGroup = (struct SOS_ResourceGroup *)((char *)&SOS_PublicGlobals::sm_ResourceManager + 112);
                  goto LABEL_69;
                }
                goto LABEL_85;
              }
              v32 = *(_QWORD *)(v1 + 192);
              v30 = (const wchar_t *)(v32 + *(unsigned __int16 *)(v32 + 48));
              v31 = 2 * *(unsigned __int16 *)(v32 + 50);
              if ( v30 )
                goto LABEL_80;
            }
LABEL_85:
            v33 = *(unsigned __int16 *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                    + SystemThread_TlsIndex)
                                                  + SystemThread_TlsOffset
                                                  + 80LL)
                                      + 600LL);
            v34 = ((__int64 (__fastcall *)(__int64))g_dbtableFactory[4])(v33);
            v35 = v34;
            if ( v34
              && !FSystemDatabase((const wchar_t *)(v34 + 936), *(_DWORD *)(v34 + 928), v33, 1)
              && (unsigned int)(v33 - 32764) > 2 )
            {
              v103 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                               + SystemThread_TlsOffset
                               + 80LL);
              v36 = *(_QWORD *)(v35 + 4664);
              v37 = *(_QWORD *)(v103 + 1064);
              if ( v37 && _InterlockedExchangeAdd((volatile signed __int32 *)(v37 + 8), 0xFFFFFFFF) == 1 && v37 != -8 )
                (**(void (__fastcall ***)(__int64, __int64))v37)(v37, 1);
              *(_QWORD *)(v103 + 1064) = v36;
              if ( v36 )
                _InterlockedIncrement((volatile signed __int32 *)(v36 + 8));
              if ( DBTABLE::GetSlo((DBTABLE *)v35) )
              {
                Slo = DBTABLE::GetSlo((DBTABLE *)v35);
                DWGroup = SloInfo::GetPrimaryGroup(Slo);
                if ( !DBTABLE::IsWorkloadIsolationEnabled((DBTABLE *)v35)
                  || !*(_DWORD *)(v35 + 4676)
                  || *((_BYTE *)qword_102EF3550 + 560) && DBTABLE::IsReadableSecondary((DBTABLE *)v35, 0) )
                {
                  if ( !DWGroup )
                  {
LABEL_69:
                    v5 = 0;
                    v7 = 0;
                    goto LABEL_12;
                  }
                  *((_DWORD *)DWGroup + 198) = COpenConnections::GetDuplicatedUserConnections(qword_102EF3DA8);
                  v5 = 0;
                  v7 = 0;
                }
                else
                {
                  v7 = 1;
                  v88 = 1;
                }
LABEL_12:
                if ( !DWGroup )
                  DWGroup = (struct SOS_ResourceGroup *)((char *)&SOS_PublicGlobals::sm_ResourceManager + 112);
                if ( v7 )
                  MasterDbId = *(_WORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                      + SystemThread_TlsIndex)
                                                    + SystemThread_TlsOffset
                                                    + 80LL)
                                        + 600LL);
                else
                  MasterDbId = GetMasterDbId();
                v92 = MasterDbId;
                LODWORD(v98) = MasterDbId;
                v103 = ((__int64 (__fastcall *)(_QWORD))g_dbtableFactory[4])(MasterDbId);
                v93 = *(_DWORD *)(v103 + 4676);
                if ( !v93 || !v5 )
                {
                  v9 = *(_QWORD *)(v1 + 104);
                  v10 = *(_QWORD *)(v9 + 712);
                  *(_QWORD *)(v9 + 712) = DWGroup;
                  if ( v10 )
                  {
                    if ( *(_DWORD *)(v10 + 164) >= 3u )
                    {
                      _InterlockedDecrement((volatile signed __int32 *)(v10 + 64));
                      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v10 + 40), 0xFFFFFFFF) == 1 )
                      {
                        if ( *(_QWORD *)(v10 + 24) )
                          TList<GroupList,SOS_ResourceGroup,16,TListSLock>::RemoveElem(*(_QWORD *)(v10 + 32), v10);
                        SOS_ResourceGroup::Destroy((SOS_ResourceGroup *)v10);
                      }
                    }
                  }
                  v11 = DWGroup;
                  DWGroup = 0;
                  SOS_ResourceManager::BindCurrentTaskToGroup(SOS_PublicGlobals::sm_ResourceManager, v11);
                  goto LABEL_20;
                }
                v112 = v1;
                v39 = *(_BYTE *)(v1 + 270);
                if ( (v39 & 4) != 0 )
                {
                  *(_BYTE *)(v1 + 270) = v39 & 0xFB;
                  *(_BYTE *)(v1 + 271) &= ~1u;
                  *(_DWORD *)(v1 + 404) = 2;
                }
                else
                {
                  v112 = 0;
                }
                v40 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                + SystemThread_TlsOffset);
                v111 = v40;
                v91 = 0;
                si128 = _mm_load_si128((const __m128i *)&_xmm);
                v224 = 0;
                v225 = MasterDbId;
                v226 = 0;
                v227 = 0;
                v228 = 0;
                v90 = 0;
                try
                {
                  ExcHandler::ExcHandler(
                    (ExcHandler *)v222,
                    0,
                    0,
                    0,
                    (int (*)(int, int, int, int, char *))MSQLErrorHandlerFunc,
                    0);
                  v143 = 0;
                  v144 = 0;
                  v145 = 0;
                  v146 = 0;
                  v147 = 0;
                  v148 = 0;
                  v218[2] = &v149;
                  v149 = 0;
                  v150 = 1;
                  v151 = 0;
                  v152 = 1;
                  v142 = &CSysTaskConnOut::`vftable';
                  v153 = 0;
                  v41 = *(_QWORD *)(v40 + 112);
                  v218[3] = v41;
                  v122 = 0;
                  v123 = 0;
                  v218[4] = &v142;
                  v42 = *(void ****)(v41 + 24);
                  if ( v42 != &v142 )
                  {
                    *(_QWORD *)&v122 = v41;
                    *((_QWORD *)&v122 + 1) = v42;
                    *(_QWORD *)&v123 = v143;
                    *((_QWORD *)&v123 + 1) = &v142;
                    v143 = v42;
                    *(_QWORD *)(v41 + 24) = &v142;
                  }
                  v124 = 88;
                  v219 = NtCurrentTeb()->ThreadLocalStoragePointer;
                  v220 = v219[SystemThread_TlsIndex] + SystemThread_TlsOffset;
                  v221 = v220;
                  v179 = *(_QWORD *)(v220 + 80);
                  v180 = v179;
                  v96 = *(_WORD *)(v179 + 600);
                  v97 = 0;
                  if ( v7 )
                  {
                    CAutoDb::FUse((CAutoDb *)&v97, MasterDbId, 0, 1, 1, 0);
                  }
                  else
                  {
                    DBMgr::OpenDB(*(_QWORD *)(qword_102ECFB00 + 32), 0, MasterDbId, 3, 1, 64);
                    v90 = 1;
                  }
                  v106 = 0;
                  v107 = 0;
                  v109 = 0;
                  v108 = 1;
                  v125 = 88;
                  v181 = NtCurrentTeb()->ThreadLocalStoragePointer;
                  v182 = (_QWORD *)(v181[SystemThread_TlsIndex] + SystemThread_TlsOffset);
                  v183 = v182;
                  v184 = *v182;
                  v185 = v184;
                  v113 = v184;
                  *(_QWORD *)&v109 = *(_QWORD *)(v184 + 144);
                  v141 = 88;
                  v186 = NtCurrentTeb()->ThreadLocalStoragePointer;
                  v187 = (_QWORD *)(v186[SystemThread_TlsIndex] + SystemThread_TlsOffset);
                  v188 = v187;
                  v189 = *v187;
                  v190 = v189;
                  v113 = v189;
                  v130 = *(_BYTE *)(v189 + 152) != 0;
                  v43 = (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)v109 + 464LL))(v109) == 0;
                  v44 = *(_QWORD *)v109;
                  if ( v43 )
                  {
                    (*(void (__fastcall **)(_QWORD, const wchar_t *, __int64))(v44 + 8))(v109, L"RG Classifier", 26);
                    v106 = 2;
                  }
                  else
                  {
                    (*(void (__fastcall **)(_QWORD, __int64, __int64, int *))(v44 + 232))(v109, 1, 1, &v107);
                    v108 = 1;
                    v106 = 4;
                  }
                  v100 = 0;
                  LODWORD(v113) = 3;
                  do
                  {
                    v99 = 0;
                    v104 = SOS_PublicGlobals::sm_ResourceManager;
                    v45 = (DBTABLE *)v103;
                    v191 = v103 + 4676;
                    v93 = *(_DWORD *)(v103 + 4676);
                    if ( !v93 )
                      break;
                    CClassifierTraceEvent::PreEvent((CClassifierTraceEvent *)&si128, v93);
                    v114 = &CAutoClearXVariant::`vftable';
                    v192 = &v120;
                    v120 = CTypeInfo::tiSSWName1;
                    v121 = xmmword_10305ADF0;
                    LOBYTE(v120) = _mm_cvtsi128_si32(CTypeInfo::tiSSWName1);
                    v94 = v120;
                    v193 = v115;
                    v116 = 0;
                    v115[0] = 3;
                    v115[1] = v120;
                    p_String1 = &String1;
                    String1 = 0;
                    v118 = 0;
                    v119 = 0;
                    memset_0(v230, 0, 0x102u);
                    v195 = v115;
                    String1 = (wchar_t *)v230;
                    v118 = 258;
                    v129 = 88;
                    v196 = NtCurrentTeb()->ThreadLocalStoragePointer;
                    v46 = v196[SystemThread_TlsIndex] + SystemThread_TlsOffset;
                    v197 = v46;
                    v47 = *(_QWORD *)(v46 + 256);
                    v132 = v47;
                    if ( !v47 )
                    {
                      SystemThread::MakeMiniSOSThread(0);
                      v47 = *(_QWORD *)(v46 + 256);
                      v132 = v47;
                    }
                    v198 = *(_QWORD *)(v47 + 1000);
                    v199 = &v154;
                    v154 = 0;
                    v155 = 0;
                    v156 = 0;
                    v157 = 0;
                    v158 = 0;
                    v159 = 0;
                    v160 = 0;
                    v161 = v198;
                    v162 = 1;
                    v163 = 0;
                    v164 = 0;
                    v165 = 0;
                    v166 = 0;
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
                    CParamExchange::InitForNonRpc((CParamExchange *)&v154, 0, 4u);
                    CParamExchange::InsertRetParam(
                      (CParamExchange *)&v154,
                      (struct CXVariant *)v115,
                      0,
                      0,
                      4u,
                      (const struct CTypeInfo *)&CTypeInfo::tiSSWName1);
                    v128 = 88;
                    v200 = NtCurrentTeb()->ThreadLocalStoragePointer;
                    v48 = v200[SystemThread_TlsIndex] + SystemThread_TlsOffset;
                    v201 = v48;
                    v49 = *(_QWORD *)(v48 + 256);
                    v133 = v49;
                    if ( !v49 )
                    {
                      SystemThread::MakeMiniSOSThread(0);
                      v49 = *(_QWORD *)(v48 + 256);
                      v133 = v49;
                    }
                    v202 = *(struct IMemObj **)(v49 + 1000);
                    ObjectByDbAndObjId = CSQLObject::CCreateObjectByDbAndObjId::CreateObjectByDbAndObjId(
                                           v202,
                                           v98,
                                           v93,
                                           20038);
                    v110 = ObjectByDbAndObjId;
                    v203 = ObjectByDbAndObjId;
                    v204 = ObjectByDbAndObjId;
                    *((_BYTE *)ObjectByDbAndObjId + 584) = 2;
                    (*(void (__fastcall **)(struct CSQLObject *, __int64, __int128 *, _QWORD))(*(_QWORD *)ObjectByDbAndObjId
                                                                                             + 152LL))(
                      ObjectByDbAndObjId,
                      v111,
                      &v154,
                      0);
                    v51 = String1;
                    Source = String1;
                    if ( v115[0] == 3 )
                    {
                      (*(void (__fastcall **)(struct CSQLObject *, __int64))(*(_QWORD *)ObjectByDbAndObjId + 136LL))(
                        ObjectByDbAndObjId,
                        1);
                      CParamExchange::~CParamExchange((CParamExchange *)&v154);
                      CAutoClearXVariant::~CAutoClearXVariant(&v114);
LABEL_121:
                      v7 = v88;
                      break;
                    }
                    v205 = &v120;
                    if ( (_WORD)v121 == 0xFFFF
                      || (v95 = *((_BYTE *)&xsm_rgOrdFromXvt + (unsigned __int8)v120),
                          v71 = (unsigned __int16)v121,
                          *((_BYTE *)&CTypeInfo::sxm_rgfIsLargeObject + v95)) )
                    {
                      v71 = 0xFFFF;
                    }
                    v72 = v71 - 2;
                    v127 = v72;
                    if ( (unsigned int)v118 <= v72 )
                      v72 = v118;
                    v101 = v72;
                    String1[(unsigned __int64)v72 >> 1] = 0;
                    if ( v88 )
                    {
                      v73 = DBTABLE::GetSlo(v45);
                      v206 = v73;
                      if ( v73 )
                      {
                        DefaultLocale = GetDefaultLocale();
                        if ( !_wcsicmp_l(v51, L"default", DefaultLocale) )
                        {
                          PrimaryGroup = SloInfo::GetPrimaryGroup(v73);
                          v91 = PrimaryGroup;
                          Source = (char *)PrimaryGroup + 260;
                          goto LABEL_193;
                        }
                        SloInfo::GetDbScopedResourceGroupName(v73, v51, v231, 0x81u);
                        Source = v231;
                      }
                    }
                    PrimaryGroup = v91;
LABEL_193:
                    if ( PrimaryGroup )
                    {
                      v77 = v99;
                      goto LABEL_207;
                    }
                    v76 = Source;
                    v77 = SOS_ResourceManager::LookupGroup(SOS_PublicGlobals::sm_ResourceManager, Source, v104, &v91);
                    v99 = v77;
                    if ( !v77 )
                    {
                      ObjectByDbAndObjId = v110;
LABEL_207:
                      v228 = 0;
                      goto LABEL_200;
                    }
                    v126 = v101 >> 1;
                    v78 = 128;
                    if ( v101 >> 1 < 0x80 )
                      v78 = v101 >> 1;
                    v228 = v78;
                    if ( v78 )
                      memcpy_s(Destination, 0x100u, v76, 2LL * v78);
                    ObjectByDbAndObjId = v110;
LABEL_200:
                    v79 = ++v100;
                    v207 = ObjectByDbAndObjId;
                    (*(void (__fastcall **)(struct CSQLObject *, __int64))(*(_QWORD *)ObjectByDbAndObjId + 136LL))(
                      ObjectByDbAndObjId,
                      1);
                    CParamExchange::~CParamExchange((CParamExchange *)&v154);
                    CAutoClearXVariant::~CAutoClearXVariant(&v114);
                    if ( v77 != 0x80000000 )
                      goto LABEL_121;
                    v7 = v88;
                  }
                  while ( !v88 || v79 < 3 );
                  v52 = v91;
                  if ( !v7 )
                    goto LABEL_125;
                  if ( v91 )
                    goto LABEL_126;
                  v52 = DWGroup;
                  v208 = DWGroup;
                  DWGroup = 0;
                  v91 = v208;
LABEL_125:
                  if ( v52 )
                  {
LABEL_126:
                    if ( *((_DWORD *)v52 + 39) == 1 )
                    {
                      v134 = v52;
                      if ( *((_DWORD *)v52 + 41) >= 3u )
                      {
                        _InterlockedDecrement((volatile signed __int32 *)v52 + 16);
                        v53 = (__int64)v134 + 16;
                        v135 = (__int64)v134 + 16;
                        if ( !_InterlockedDecrement((volatile signed __int32 *)v134 + 10) )
                        {
                          if ( *(_QWORD *)(v135 + 8) )
                          {
                            v54 = (SOS_ResourceGroup *)(v53 - 16);
                            if ( !v53 )
                              v54 = 0;
                            v209 = v54;
                            TList<GroupList,SOS_ResourceGroup,16,TListSLock>::RemoveElem(*(_QWORD *)(v135 + 16), v54);
                            SOS_ResourceGroup::Destroy(v54);
                            v91 = 0;
                            goto LABEL_133;
                          }
                          if ( v53 )
                          {
                            SOS_ResourceGroup::Destroy((SOS_ResourceGroup *)(v53 - 16));
                            v91 = 0;
                            goto LABEL_133;
                          }
                          SOS_ResourceGroup::Destroy(0);
                        }
                      }
                      v91 = 0;
                      goto LABEL_133;
                    }
                    if ( v52 == (struct SOS_ResourceGroup *)((char *)&SOS_PublicGlobals::sm_ResourceManager + 112) )
                    {
                      v52 = DWGroup;
                      v210 = DWGroup;
                      DWGroup = 0;
                      v91 = v210;
                    }
                    if ( v7 )
                    {
                      DuplicatedUserConnections = COpenConnections::GetDuplicatedUserConnections(qword_102EF3DA8);
                      *((_DWORD *)v91 + 198) = DuplicatedUserConnections;
                      v52 = v91;
                    }
                    SOS_ResourceManager::BindCurrentTaskToGroup(SOS_PublicGlobals::sm_ResourceManager, v52);
                    v211 = *(_QWORD *)(v1 + 104);
                    v212 = *(_QWORD *)(v211 + 712);
                    v81 = v212;
                    *(_QWORD *)(v211 + 712) = v91;
                    if ( v81 )
                    {
                      if ( *(_DWORD *)(v81 + 164) >= 3u )
                      {
                        _InterlockedDecrement((volatile signed __int32 *)(v81 + 64));
                        v136 = v81 + 16;
                        if ( !_InterlockedDecrement((volatile signed __int32 *)(v81 + 40)) )
                        {
                          if ( *(_QWORD *)(v136 + 8) )
                          {
                            v82 = (SOS_ResourceGroup *)v81;
                            if ( v81 == -16 )
                              v82 = 0;
                            v213 = v82;
                            TList<GroupList,SOS_ResourceGroup,16,TListSLock>::RemoveElem(*(_QWORD *)(v136 + 16), v82);
                            v83 = v82;
                          }
                          else
                          {
                            v83 = 0;
                            if ( v81 != -16 )
                              v83 = (SOS_ResourceGroup *)v81;
                          }
                          SOS_ResourceGroup::Destroy(v83);
                        }
                      }
                    }
                  }
LABEL_133:
                  CAutoMsqlXact::CommitNestedXact((CAutoMsqlXact *)&v106, 0);
                  if ( !v7 )
                  {
                    v140 = 0;
                    DBMgr::CloseDB(*(_QWORD *)(qword_102ECFB00 + 32), 0, (unsigned int)v98, 3);
                  }
                  if ( v106 )
                    CAutoMsqlXact::RollbackNestedXact((CAutoMsqlXact *)&v106, 0);
                  if ( v97 )
                  {
                    v97 = 0;
                    g_dbtableFactory[6](0xFFFFFFFFLL, 16);
                  }
                  v140 = NtCurrentTeb()->ThreadLocalStoragePointer;
                  v215 = v140[SystemThread_TlsIndex] + SystemThread_TlsOffset;
                  v216 = *(_QWORD *)(v215 + 80);
                  *(_DWORD *)(v216 + 600) = v96;
                  v55 = v122;
                  if ( (_QWORD)v122 )
                  {
                    *(_QWORD *)(*(_QWORD *)(v122 + 24) + 8LL) = v123;
                    *(_QWORD *)(v55 + 24) = *((_QWORD *)&v122 + 1);
                    v122 = 0;
                    v123 = 0;
                  }
                  v142 = &CConnectionOutput::`vftable';
                  ExcHandler::~ExcHandler((ExcHandler *)v222);
                }
                catch ( SQLError v177 )
                {
                  try
                  {
                    ExceptionBackout::ExceptionBackout((ExceptionBackout *)v218, (const struct SQLError *)&v177);
                    si128 = v177;
                    v224 = v178;
                    if ( !v88 && (v90 || !*(_DWORD *)(GetXdbServerGlobals(v84) + 11976)) )
                    {
                      v98 = 0;
                      DBMgr::CloseDB(*(_QWORD *)(qword_102ECFB00 + 32), 0, v92, 3);
                    }
                    v85 = *(_QWORD *)(v111 + 128);
                    v217 = v85;
                    *(_BYTE *)(v85 + 296) = 0;
                    *(_DWORD *)(v85 + 76) &= ~0x2000000u;
                    ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v218);
                  }
                  catch ( ShortStackException )
                  {
                  }
                  v4 = 0;
                  v3 = -1;
                  v0 = v137;
                  v1 = v138;
                  v7 = v88;
                }
                v56 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                    + SystemThread_TlsOffset;
                v57 = *(struct Worker **)(v56 + 256);
                if ( !v57 )
                {
                  SystemThread::MakeMiniSOSThread(0);
                  v57 = *(struct Worker **)(v56 + 256);
                }
                if ( *((_DWORD *)v57 + 139) )
                  ExceptionPostCatchActions(v57);
                if ( !v91 )
                {
                  if ( v7 )
                  {
                    v58 = COpenConnections::GetDuplicatedUserConnections(qword_102EF3DA8);
                    *((_DWORD *)DWGroup + 198) = v58;
                  }
                  v59 = *(_QWORD *)(v1 + 104);
                  v60 = *(_QWORD *)(v59 + 712);
                  *(_QWORD *)(v59 + 712) = DWGroup;
                  if ( v60 )
                  {
                    if ( *(_DWORD *)(v60 + 164) >= 3u )
                    {
                      _InterlockedDecrement((volatile signed __int32 *)(v60 + 64));
                      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v60 + 40), 0xFFFFFFFF) == 1 )
                      {
                        if ( *(_QWORD *)(v60 + 24) )
                          TList<GroupList,SOS_ResourceGroup,16,TListSLock>::RemoveElem(*(_QWORD *)(v60 + 32), v60);
                        SOS_ResourceGroup::Destroy((SOS_ResourceGroup *)v60);
                      }
                    }
                  }
                  v61 = DWGroup;
                  DWGroup = 0;
                  SOS_ResourceManager::BindCurrentTaskToGroup(v0, v61);
                }
                v62 = DWGroup;
                if ( DWGroup )
                {
                  if ( *((_DWORD *)DWGroup + 41) >= 3u )
                  {
                    _InterlockedDecrement((volatile signed __int32 *)DWGroup + 16);
                    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v62 + 10, 0xFFFFFFFF) == 1 )
                    {
                      if ( *((_QWORD *)v62 + 3) )
                        TList<GroupList,SOS_ResourceGroup,16,TListSLock>::RemoveElem(*((_QWORD *)v62 + 4), v62);
                      SOS_ResourceGroup::Destroy(v62);
                    }
                  }
                  DWGroup = 0;
                }
                CClassifierTraceEvent::PostEvent((CClassifierTraceEvent *)&si128);
                v63 = si128.m128i_i32[0];
                v64 = si128.m128i_i32[0];
                if ( v224 != 1 )
                  v64 = si128.m128i_u16[0];
                if ( !v64 )
                  goto LABEL_179;
                if ( v224 != 1 )
                  v63 = si128.m128i_u16[0];
                if ( v63 == 3617 )
                {
LABEL_179:
                  v70 = v112;
                  if ( v112 )
                  {
                    *(_BYTE *)(v112 + 270) |= 4u;
                    *(_BYTE *)(v70 + 271) |= 1u;
                    *(_DWORD *)(v70 + 404) = 1;
                  }
LABEL_20:
                  SOS_AutoReleaseResourceGroup::UnhookAndRelease((SOS_AutoReleaseResourceGroup *)&DWGroup);
                  return;
                }
                v65 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
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
                v67 = *(_QWORD *)(v65 + 208);
                if ( (unsigned __int64)QuadPart < v67 )
                {
                  v68 = 0;
                }
                else
                {
                  v68 = (unsigned __int64)QuadPart - v67;
                  if ( v68 == -1 )
                  {
LABEL_173:
                    v69 = si128.m128i_u32[0];
                    if ( v224 != 1 )
                      v69 = si128.m128i_u16[0];
                    if ( v93 == *(_DWORD *)(v103 + 4676) )
                    {
                      v4 = 257;
                      if ( *(_DWORD *)(v103 + 4680) < 0x101u )
                        v4 = *(_DWORD *)(v103 + 4680);
                    }
                    LODWORD(v87) = *(__int16 *)(v65 + 72);
                    LODWORD(v86) = si128.m128i_i32[3];
                    scierrlog(0x2AE6u, 2LL * v4, v103 + 4684, v69, v86, v87, v3);
                    goto LABEL_179;
                  }
                }
                if ( Base_PublicGlobals::sm_invariantTscAvailable )
                  v3 = 1000 * v68 / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
                else
                  v3 = v68 / 0x2710;
                goto LABEL_173;
              }
            }
LABEL_11:
            v7 = 0;
            goto LABEL_12;
          }
        }
        if ( *(_DWORD *)(*(_QWORD *)((*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v1 + 96) + 16LL))(*(_QWORD *)(v1 + 96))
                                   + 520)
                       + 20LL) )
        {
          do
            v25 = SOS_ResourceManager::LookupGroup(
                    SOS_PublicGlobals::sm_ResourceManager,
                    L"XOdbcGroup",
                    SOS_PublicGlobals::sm_ResourceManager,
                    &DWGroup);
          while ( v25 == 0x80000000 );
          goto LABEL_67;
        }
        v26 = *(const wchar_t **)(v1 + 960);
        if ( v26 )
        {
          v27 = *(_DWORD *)(v1 + 968);
        }
        else
        {
          v29 = *(_QWORD *)(v1 + 192);
          v27 = 2 * *(unsigned __int16 *)(v29 + 50);
          v26 = (const wchar_t *)(v29 + *(unsigned __int16 *)(v29 + 48));
        }
        v28 = SloInfo::MapAppNameToWorkloadGroup(v26, v27);
        if ( v28 )
        {
          do
            v25 = SOS_ResourceManager::LookupGroup(
                    SOS_PublicGlobals::sm_ResourceManager,
                    v28,
                    SOS_PublicGlobals::sm_ResourceManager,
                    &DWGroup);
          while ( v25 == 0x80000000 );
          goto LABEL_67;
        }
      }
      v24 = qword_102EF3550;
      goto LABEL_77;
    }
    DACGroup = SloInfo::GetDACGroup();
    v13 = DACGroup;
    if ( DACGroup && (_UNKNOWN *)DACGroup != (_UNKNOWN *)((char *)&SOS_PublicGlobals::sm_ResourceManager + 3576) )
    {
      if ( *(_DWORD *)(DACGroup + 164) >= 3u )
      {
        v14 = *(_DWORD *)(DACGroup + 64);
        if ( v14 >= 0 )
        {
          while ( v14 != _InterlockedCompareExchange((volatile signed __int32 *)(v13 + 64), v14 + 1, v14) )
          {
            v14 = *(_DWORD *)(v13 + 64);
            if ( v14 < 0 )
              goto LABEL_27;
          }
          _InterlockedIncrement((volatile signed __int32 *)(v13 + 40));
        }
      }
LABEL_27:
      v15 = *(_QWORD *)(v1 + 104);
      v16 = *(_QWORD *)(v15 + 712);
      *(_QWORD *)(v15 + 712) = v13;
      if ( v16 )
      {
        if ( *(_DWORD *)(v16 + 164) >= 3u )
        {
          _InterlockedDecrement((volatile signed __int32 *)(v16 + 64));
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v16 + 40), 0xFFFFFFFF) == 1 )
          {
            if ( *(_QWORD *)(v16 + 24) )
              TList<GroupList,SOS_ResourceGroup,16,TListSLock>::RemoveElem(*(_QWORD *)(v16 + 32), v16);
            SOS_ResourceGroup::Destroy((SOS_ResourceGroup *)v16);
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
