# CAgentProtocolTalker::SyncServerUpdatesInternal(ISusSearchAttributeProvider *,CAgentProtocolTalkerContext *,CatScanContext *,ExtendedInfoScanContext *,CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>> const *,tagSystemSpec const *,CUpdateDeferralPolicyChecker const &,wchar_t const *,CUpdateDetectInfoList &,ulong,CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>> *,CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>> &,ulong *,ulong *,ulong *,bool *)

- ea: `0x18006a4a8`
- end: `0x18006cf0f`
- name: `?SyncServerUpdatesInternal@CAgentProtocolTalker@@AEAAJPEAUISusSearchAttributeProvider@@PEAVCAgentProtocolTalkerContext@@PEAVCatScanContext@@PEAUExtendedInfoScanContext@@PEBV?$CSusSortedArrayList@U_GUID@@V?$CSusSortedArrayListItemOpsBasic@U_GUID@@@@@@PEBUtagSystemSpec@@AEBVCUpdateDeferralPolicyChecker@@PEB_WAEAVCUpdateDetectInfoList@@KPEAV6@AEAV6@PEAKPEAKPEAKPEA_N@Z`
- size: `10855`
- prototype: ``
- caller_count: `1`
- callee_count: `62`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18007413c`

## callees

- `0x18000def4`
- `0x18001a774`
- `0x180022b0c`
- `0x180024670`
- `0x180024e34`
- `0x180032b70`
- `0x180033d90`
- `0x1800344f0`
- `0x1800358a8`
- `0x1800365e8`
- `0x18003b668`
- `0x18003b908`
- `0x18003b9c4`
- `0x18003baf4`
- `0x18005c9a4`
- `0x180060988`
- `0x1800634f8`
- `0x180064320`
- `0x1800645b8`
- `0x180064ec4`
- `0x180068600`
- `0x180068988`
- `0x180068cc4`
- `0x1800691dc`
- `0x1800693ec`
- `0x1800694cc`
- `0x180069770`
- `0x180069dbc`
- `0x180069fb0`
- `0x18006a4a8`
- `0x18006d128`
- `0x18006f7b0`
- `0x180072054`
- `0x180075a80`
- `0x180076820`
- `0x180076a80`
- `0x180076ca8`
- `0x1800783e0`
- `0x180078424`
- `0x180078680`
- `0x1800be4bc`
- `0x1800beb8c`
- `0x1800bec04`
- `0x1800bece0`
- `0x1800db980`
- `0x1800dc434`
- `0x1800dd080`
- `0x180113ae8`
- `0x180113b9c`
- `0x180113ca0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18006aaef`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18006ab82`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18006abfb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18006ae43`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18006b1c6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18006aaef`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18006ab82`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18006abfb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18006ae43`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18006b1c6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18006ab1f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18006abe2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18006ac2d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18006ae69`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18006b1f0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18006ab1f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18006abe2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18006ac2d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18006ae69`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18006b1f0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006aefe`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006af70`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006b03b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006b566`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006aefe`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006af70`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006b03b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006b566`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006aeef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006af61`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006b02c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006b557`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006aeef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006af61`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006b02c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006b557`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18006bf62`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18006bf62`
- `OLEAUT32!__imp_SysAllocString` at `0x18006acb4`
- `OLEAUT32!__imp_SysAllocString` at `0x18006ad2a`
- `OLEAUT32!__imp_SysAllocString` at `0x18006bdaf`
- `OLEAUT32!__imp_SysAllocString` at `0x18006acb4`
- `OLEAUT32!__imp_SysAllocString` at `0x18006ad2a`
- `OLEAUT32!__imp_SysAllocString` at `0x18006bdaf`
- `OLEAUT32!__imp_SysFreeString` at `0x18006a977`
- `OLEAUT32!__imp_SysFreeString` at `0x18006a984`
- `OLEAUT32!__imp_SysFreeString` at `0x18006c1ee`
- `OLEAUT32!__imp_SysFreeString` at `0x18006c249`
- `OLEAUT32!__imp_SysFreeString` at `0x18006c979`
- `OLEAUT32!__imp_SysFreeString` at `0x18006a977`
- `OLEAUT32!__imp_SysFreeString` at `0x18006a984`
- `OLEAUT32!__imp_SysFreeString` at `0x18006c1ee`
- `OLEAUT32!__imp_SysFreeString` at `0x18006c249`
- `OLEAUT32!__imp_SysFreeString` at `0x18006c979`
- `OLEAUT32!__imp_SysStringLen` at `0x18006bf35`
- `OLEAUT32!__imp_SysStringLen` at `0x18006bfc1`
- `OLEAUT32!__imp_SysStringLen` at `0x18006bf35`
- `OLEAUT32!__imp_SysStringLen` at `0x18006bfc1`

## string_xrefs

- `0x18006ba32`: `C:\__w\1\s\src\Client\Engine\Agent\ProtocolTalker.cpp`
- `0x18006bbae`: `C:\__w\1\s\src\Client\Engine\Agent\ProtocolTalker.cpp`
- `0x18006aaaf`: `Protocol Talker not inited`
- `0x18006ac37`: `GetSyncUpdatesSupportsTreatAppCategoryIdsAsInstalled`
- `0x18006b11c`: `AddSharedUpdatesToAppCatScanLists failed -- continuing`
- `0x18006b1fa`: `Could not read config property SupportUpdateDeploymentId from GetConfig sent by service.`
- `0x18006b30a`: `SyncUpdates adding %lu visited app categories`
- `0x18006cd2b`: `CAgentUpdateManager::DetectForUpdates failed`
- `0x18006ca27`: `GetAllValidAppCategoryIds returned no categories, bailing service sync`
- `0x18006cccb`: `PopulateDataStore to put cached drivers out of scope failed`
- `0x18006be4b`: `GetAllUserCompartments failed`
- `0x18006bf83`: `GetAllUserCompartments data unexpectedly large`
- `0x18006ca86`: `ProcessCoreMetadata did not return any update to be committed`
- `0x18006cb53`: `MetadataIntegrity::AgentHelper::VerifyMetadataSignatures`
- `0x18006c717`: `SyncUpdates - %lu bad out of %lu extended metadata signatures checked using %ls enforcement mode (raw mode: %ws).`
- `0x18006aa13`: `SyncUpdates round trips: %ld`
- `0x18006cd52`: `Sync of Updates`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
__int64 __fastcall CAgentProtocolTalker::SyncServerUpdatesInternal(
        CAgentProtocolTalker *a1,
        struct ISusSearchAttributeProvider *a2,
        CAgentProtocolTalkerContext *a3,
        CatScanContext *a4,
        __int64 a5,
        __int64 a6,
        CAgentProtocolTalker *a7,
        __int64 a8,
        OLECHAR *a9,
        CUpdateDetectInfoList *a10,
        __int64 a11,
        void *a12,
        __int64 a13,
        unsigned int *a14,
        _DWORD *a15,
        _DWORD *a16,
        bool *a17)
{
  bool v18; // zf
  _QWORD *v19; // r14
  _OWORD *v20; // rdi
  void (__fastcall ***v21)(_QWORD, __int64, _QWORD); // r12
  _QWORD *v22; // rsi
  struct CAppCatIdProvider *v23; // r15
  CSusService *v24; // r13
  int v25; // eax
  __int64 v26; // r9
  __int64 v27; // r8
  unsigned int *v28; // rdx
  signed int refreshed; // r13d
  unsigned int v30; // ebx
  _DWORD *v31; // rcx
  _DWORD *v32; // rax
  int v33; // eax
  void *v34; // rbx
  __int64 v35; // rcx
  RTL_SRWLOCK *v36; // rbx
  BOOL BooleanPropertyFromServerConfig; // r13d
  CAgentProtocolTalker *v38; // rcx
  unsigned __int8 v39; // al
  int v40; // ebx
  RTL_SRWLOCK *v41; // r13
  __int64 v42; // rdx
  __int64 v43; // r8
  const OLECHAR *v44; // rax
  bool v45; // al
  __int64 v46; // rdx
  const OLECHAR *v47; // rax
  const wchar_t *v48; // rbx
  const wchar_t *v49; // rcx
  int v50; // ebx
  CatScanContext *v51; // r8
  unsigned int v52; // ebx
  __int128 v53; // xmm6
  int v54; // eax
  HANDLE v55; // rax
  _OWORD *v56; // rax
  int v57; // eax
  HANDLE v58; // rax
  _QWORD *v59; // rax
  HANDLE ProcessHeap; // rax
  _QWORD *v61; // rax
  int v62; // eax
  __int64 RequestedAppCategoryIdList; // rax
  __int64 v64; // r13
  unsigned int v65; // r15d
  unsigned int v66; // ebx
  int v67; // ebx
  int v68; // r13d
  __int64 v69; // rdx
  int v70; // ebx
  void *v71; // r15
  CAgentProtocolTalkerContext *v72; // rbx
  int v73; // eax
  __int64 v74; // r13
  __int64 v75; // rax
  __int64 v76; // rbx
  __int64 v77; // rbx
  int v78; // eax
  int v79; // eax
  CSusService *v80; // rcx
  HANDLE v81; // rax
  _OWORD *v82; // rax
  _OWORD *v83; // rbx
  __int64 v84; // rdx
  __int64 v85; // rax
  int v86; // ebx
  CSusService *v87; // rbx
  unsigned int v88; // r9d
  int PerformDriverSync; // eax
  int v90; // ecx
  int v91; // ebx
  __int64 v92; // rdx
  int v93; // eax
  unsigned int v94; // ebx
  CAgentProtocolTalkerContext *v95; // r8
  unsigned int v96; // ebx
  unsigned int v97; // eax
  int v98; // eax
  int v99; // eax
  __int64 v100; // rdx
  __int64 v101; // r8
  __int64 v102; // r9
  CAgentProtocolTalkerContext *v103; // rbx
  int v104; // eax
  int v105; // eax
  unsigned int v106; // r13d
  int updated; // eax
  __int64 v108; // rdx
  CatScanContext *v109; // r13
  char v110; // al
  bool v111; // al
  __int64 v112; // rax
  int v113; // ecx
  __int64 v114; // rax
  int v115; // ecx
  int v116; // ebx
  __int64 v117; // rdx
  int v118; // eax
  int v119; // r9d
  UINT v120; // eax
  __int64 v121; // r9
  int v122; // ecx
  struct SusWsStructs::SusUpdateInfo *v123; // rax
  int v124; // eax
  int v125; // ecx
  __int64 v126; // rdx
  struct SusWsStructs::SusUpdateInfo *v127; // rax
  struct SusWsStructs::SusUpdateInfo *v128; // rdx
  int v129; // eax
  signed int v130; // ecx
  __int64 v131; // r13
  int v132; // r15d
  struct SusWsStructs::SusUpdateInfo *v133; // rbx
  __int64 v134; // r13
  int v135; // r15d
  struct SusWsStructs::SusUpdateInfo *v136; // rbx
  __int64 v137; // rax
  void *v138; // rbx
  __int64 v139; // rdx
  __int64 v140; // r11
  unsigned int v141; // r10d
  unsigned int v142; // r9d
  struct SusWsStructs::SusUpdateInfo *v143; // r13
  _DWORD *v144; // rbx
  _DWORD *v145; // rcx
  __int64 v146; // r8
  __int64 v147; // rdx
  unsigned int v148; // edx
  CSusService *v149; // r8
  struct SusWsStructs::SusUpdateInfo *v150; // r9
  struct SusWsStructs::SusUpdateInfo *v151; // r8
  __int64 v152; // rax
  __int64 v153; // rdx
  __int64 v154; // rcx
  struct SusWsStructs::SusExtendedUpdateInfo *v155; // rdx
  void *v156; // rax
  void *v157; // rbx
  __int64 v158; // rdx
  void *v159; // rcx
  void *v160; // rcx
  int v161; // r11d
  void *v162; // rdx
  const wchar_t *v163; // rax
  int lpString2; // [rsp+28h] [rbp-130h]
  int lpString2a; // [rsp+28h] [rbp-130h]
  int lpString2b; // [rsp+28h] [rbp-130h]
  int cchCount2; // [rsp+30h] [rbp-128h]
  struct SusWsStructs::SusUpdateInfo *v169; // [rsp+38h] [rbp-120h]
  void *v170; // [rsp+40h] [rbp-118h]
  void *v171; // [rsp+40h] [rbp-118h]
  void *v172; // [rsp+40h] [rbp-118h]
  struct SusWsStructs::SusExtendedUpdateInfo *v173; // [rsp+48h] [rbp-110h]
  struct SusWsStructs::SusExtendedUpdateInfo *v174; // [rsp+48h] [rbp-110h]
  __int64 v175; // [rsp+50h] [rbp-108h]
  __int64 v176; // [rsp+58h] [rbp-100h]
  wchar_t *v177; // [rsp+60h] [rbp-F8h]
  int v178[2]; // [rsp+68h] [rbp-F0h]
  __int64 v179; // [rsp+70h] [rbp-E8h]
  int v180[2]; // [rsp+78h] [rbp-E0h]
  __int64 v181; // [rsp+80h] [rbp-D8h]
  char *v182; // [rsp+88h] [rbp-D0h]
  __int64 v183; // [rsp+90h] [rbp-C8h]
  __int64 v184; // [rsp+98h] [rbp-C0h]
  __int64 v185; // [rsp+A0h] [rbp-B8h]
  CatScanContext *v186; // [rsp+A8h] [rbp-B0h]
  void ***v187; // [rsp+B0h] [rbp-A8h]
  void ***v188; // [rsp+B8h] [rbp-A0h]
  void ***v189; // [rsp+C0h] [rbp-98h]
  unsigned int v190; // [rsp+D8h] [rbp-80h]
  unsigned int v191; // [rsp+E8h] [rbp-70h] BYREF
  CAgentProtocolTalkerContext *v192; // [rsp+F0h] [rbp-68h]
  bool v193; // [rsp+F8h] [rbp-60h]
  int v194; // [rsp+FCh] [rbp-5Ch] BYREF
  BOOL v195; // [rsp+100h] [rbp-58h]
  CAgentProtocolTalker *v196; // [rsp+108h] [rbp-50h]
  int v197; // [rsp+110h] [rbp-48h]
  int v198; // [rsp+114h] [rbp-44h]
  int v199; // [rsp+118h] [rbp-40h]
  unsigned int v200; // [rsp+11Ch] [rbp-3Ch]
  CSusService *v201; // [rsp+120h] [rbp-38h]
  int v202; // [rsp+128h] [rbp-30h]
  unsigned int v203; // [rsp+12Ch] [rbp-2Ch] BYREF
  CSusService *v204; // [rsp+130h] [rbp-28h] BYREF
  int v205; // [rsp+138h] [rbp-20h]
  int v206; // [rsp+13Ch] [rbp-1Ch]
  unsigned int v207; // [rsp+140h] [rbp-18h]
  int v208; // [rsp+144h] [rbp-14h]
  int v209; // [rsp+148h] [rbp-10h]
  int v210; // [rsp+14Ch] [rbp-Ch]
  int v211; // [rsp+150h] [rbp-8h]
  int v212; // [rsp+154h] [rbp-4h]
  int v213; // [rsp+158h] [rbp+0h]
  CUpdateDetectInfoList *v214; // [rsp+160h] [rbp+8h]
  void *lpMem; // [rsp+168h] [rbp+10h]
  int v216; // [rsp+170h] [rbp+18h]
  BOOL v217; // [rsp+174h] [rbp+1Ch]
  struct ISusSearchAttributeProvider *v218; // [rsp+178h] [rbp+20h]
  int v219; // [rsp+180h] [rbp+28h]
  int v220; // [rsp+184h] [rbp+2Ch]
  int v221; // [rsp+188h] [rbp+30h]
  int v222; // [rsp+18Ch] [rbp+34h]
  int v223; // [rsp+190h] [rbp+38h]
  void *v224; // [rsp+198h] [rbp+40h]
  CatScanContext *v225; // [rsp+1A0h] [rbp+48h]
  void *v226; // [rsp+1A8h] [rbp+50h]
  void *v227; // [rsp+1B0h] [rbp+58h]
  void *v228; // [rsp+1B8h] [rbp+60h]
  void *v229; // [rsp+1C0h] [rbp+68h]
  int v230; // [rsp+1C8h] [rbp+70h]
  bool *v231; // [rsp+1D0h] [rbp+78h] BYREF
  int v232; // [rsp+1D8h] [rbp+80h]
  unsigned __int8 *v233; // [rsp+1E0h] [rbp+88h] BYREF
  struct CAppCatIdProvider *v234; // [rsp+1E8h] [rbp+90h] BYREF
  __int64 v235; // [rsp+1F0h] [rbp+98h]
  _DWORD *v236; // [rsp+1F8h] [rbp+A0h]
  __int64 v237; // [rsp+200h] [rbp+A8h]
  OLECHAR *psz; // [rsp+208h] [rbp+B0h]
  __int64 v239; // [rsp+210h] [rbp+B8h]
  _QWORD *v240; // [rsp+218h] [rbp+C0h]
  __int64 v241; // [rsp+220h] [rbp+C8h]
  __int64 v242; // [rsp+228h] [rbp+D0h]
  _QWORD *v243; // [rsp+230h] [rbp+D8h]
  void (__fastcall ***v244)(_QWORD, __int64, _QWORD); // [rsp+238h] [rbp+E0h]
  __int64 v245; // [rsp+240h] [rbp+E8h]
  _OWORD *v246; // [rsp+248h] [rbp+F0h]
  _QWORD *v247; // [rsp+250h] [rbp+F8h]
  _DWORD *v248; // [rsp+258h] [rbp+100h]
  _DWORD *v249; // [rsp+260h] [rbp+108h]
  void *v250; // [rsp+268h] [rbp+110h]
  __int64 v251; // [rsp+270h] [rbp+118h]
  CAgentProtocolTalker *v252; // [rsp+278h] [rbp+120h]
  __int128 v253; // [rsp+288h] [rbp+130h] BYREF
  int v254; // [rsp+298h] [rbp+140h]
  void *v255; // [rsp+2A0h] [rbp+148h]
  PSRWLOCK SRWLock; // [rsp+2A8h] [rbp+150h] BYREF
  void *v257; // [rsp+2B0h] [rbp+158h] BYREF
  __int64 v258; // [rsp+2B8h] [rbp+160h] BYREF
  __int64 v259; // [rsp+2C0h] [rbp+168h] BYREF
  void *v260; // [rsp+2C8h] [rbp+170h] BYREF
  struct SusWsStructs::SusUpdateInfo *v261[14]; // [rsp+2D8h] [rbp+180h] BYREF
  _OWORD v262[21]; // [rsp+348h] [rbp+1F0h] BYREF
  int v263; // [rsp+498h] [rbp+340h] BYREF
  unsigned int v264; // [rsp+49Ch] [rbp+344h] BYREF
  void **v265; // [rsp+4A0h] [rbp+348h] BYREF
  __int64 v266; // [rsp+4A8h] [rbp+350h]
  __int128 v267; // [rsp+4B0h] [rbp+358h]
  __int64 v268[2]; // [rsp+4C8h] [rbp+370h] BYREF
  __int64 v269; // [rsp+4D8h] [rbp+380h]
  int v270; // [rsp+4E8h] [rbp+390h] BYREF
  void *v271[2]; // [rsp+4F0h] [rbp+398h] BYREF
  __int64 v272; // [rsp+500h] [rbp+3A8h]
  void **v273; // [rsp+508h] [rbp+3B0h] BYREF
  void *v274; // [rsp+510h] [rbp+3B8h]
  __int128 v275; // [rsp+518h] [rbp+3C0h]
  void **v276; // [rsp+528h] [rbp+3D0h] BYREF
  void *v277; // [rsp+530h] [rbp+3D8h]
  __int128 v278; // [rsp+538h] [rbp+3E0h]
  void **v279; // [rsp+548h] [rbp+3F0h] BYREF
  void *v280; // [rsp+550h] [rbp+3F8h]
  __int128 v281; // [rsp+558h] [rbp+400h]
  void **v282; // [rsp+568h] [rbp+410h] BYREF
  void *v283; // [rsp+570h] [rbp+418h]
  __int128 v284; // [rsp+578h] [rbp+420h]
  void **v285; // [rsp+588h] [rbp+430h] BYREF
  void *v286; // [rsp+590h] [rbp+438h]
  __int128 v287; // [rsp+598h] [rbp+440h]
  void **v288; // [rsp+5A8h] [rbp+450h] BYREF
  __int64 v289; // [rsp+5B0h] [rbp+458h]
  __int64 v290; // [rsp+5B8h] [rbp+460h]
  __int64 v291[2]; // [rsp+5C0h] [rbp+468h] BYREF
  __int128 v292; // [rsp+5D0h] [rbp+478h]
  _QWORD v293[3]; // [rsp+5E0h] [rbp+488h] BYREF
  _DWORD v294[71]; // [rsp+5F8h] [rbp+4A0h] BYREF
  _QWORD v295[34]; // [rsp+718h] [rbp+5C0h] BYREF
  char v296[144]; // [rsp+828h] [rbp+6D0h] BYREF
  wchar_t v297[264]; // [rsp+8B8h] [rbp+760h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B30h] [rbp+9D8h]

  v225 = a4;
  v192 = a3;
  v218 = a2;
  v196 = a1;
  v235 = a5;
  v252 = a7;
  v239 = a6;
  v251 = a8;
  psz = a9;
  v214 = a10;
  v250 = a12;
  v245 = a13;
  v248 = a15;
  v249 = a16;
  v231 = a17;
  memset(v261, 0, sizeof(v261));
  memset(v262, 0, 0x148u);
  if ( !a7 || (v18 = *(_QWORD *)a7 == 0, v230 = 1, v18) )
    v230 = 0;
  v195 = 0;
  v217 = 0;
  v208 = 0;
  v221 = 0;
  v205 = 0;
  v219 = 0;
  v263 = 0;
  v232 = 0;
  v286 = 0;
  v287 = 0u;
  v285 = &CSusSortedArrayList<long,CSusSortedArrayListItemOpsBasic<long>>::`vftable';
  lpMem = 0;
  v198 = 0;
  v199 = 0;
  v274 = 0;
  v275 = 0u;
  v273 = &CSusSortedArrayList<long,CSusSortedArrayListItemOpsBasic<long>>::`vftable';
  v226 = 0;
  v200 = 0;
  v212 = 0;
  v283 = 0;
  v284 = 0u;
  v282 = &CSusSortedArrayList<long,CSusSortedArrayListItemOpsBasic<long>>::`vftable';
  v227 = 0;
  v222 = 0;
  v211 = 0;
  v277 = 0;
  v278 = 0u;
  v276 = &CSusSortedArrayList<long,CSusSortedArrayListItemOpsBasic<long>>::`vftable';
  v224 = 0;
  v197 = 0;
  v209 = 0;
  v280 = 0;
  v281 = 0u;
  v279 = &CSusSortedArrayList<long,CSusSortedArrayListItemOpsBasic<long>>::`vftable';
  v228 = 0;
  v223 = 0;
  v210 = 0;
  v291[1] = 0;
  v292 = 0u;
  v291[0] = (__int64)&CSusSortedArrayList<long,CSusSortedArrayListItemOpsBasic<long>>::`vftable';
  v229 = 0;
  v220 = 0;
  v213 = 0;
  v203 = 0;
  v233 = 0;
  v19 = 0;
  v247 = 0;
  v20 = 0;
  v246 = 0;
  v21 = 0;
  v244 = 0;
  v257 = 0;
  v264 = 0;
  v258 = 0;
  v259 = 0;
  v190 = 0;
  v22 = 0;
  v243 = 0;
  v240 = 0;
  v242 = 0;
  v23 = 0;
  v234 = 0;
  v293[1] = 0;
  v293[2] = 0;
  v293[0] = &CBSTRList::`vftable';
  v289 = 0;
  v290 = 0;
  v288 = &CBSTRList::`vftable';
  v271[0] = &CBSTRList::`vftable';
  v271[1] = 0;
  v272 = 0;
  v270 = 0;
  v260 = 0;
  v193 = 0;
  if ( !a3 || !*((_QWORD *)a3 + 78) )
  {
    CSusArrayList<wchar_t *,CSusArrayBSTRListItemOpDelete>::~CSusArrayList<wchar_t *,CSusArrayBSTRListItemOpDelete>(v271);
    CSusArrayList<wchar_t *,CSusArrayBSTRListItemOpDelete>::~CSusArrayList<wchar_t *,CSusArrayBSTRListItemOpDelete>(&v288);
    CSusArrayList<wchar_t *,CSusArrayBSTRListItemOpDelete>::~CSusArrayList<wchar_t *,CSusArrayBSTRListItemOpDelete>(v293);
    CSusArrayList<long,CSusSortedArrayListItemOpsBasic<long>>::~CSusArrayList<long,CSusSortedArrayListItemOpsBasic<long>>(v291);
    CSusArrayList<long,CSusSortedArrayListItemOpsBasic<long>>::~CSusArrayList<long,CSusSortedArrayListItemOpsBasic<long>>(&v279);
    CSusArrayList<long,CSusSortedArrayListItemOpsBasic<long>>::~CSusArrayList<long,CSusSortedArrayListItemOpsBasic<long>>(&v276);
    CSusArrayList<long,CSusSortedArrayListItemOpsBasic<long>>::~CSusArrayList<long,CSusSortedArrayListItemOpsBasic<long>>(&v282);
    CSusArrayList<long,CSusSortedArrayListItemOpsBasic<long>>::~CSusArrayList<long,CSusSortedArrayListItemOpsBasic<long>>(&v273);
    CSusArrayList<long,CSusSortedArrayListItemOpsBasic<long>>::~CSusArrayList<long,CSusSortedArrayListItemOpsBasic<long>>(&v285);
    return 2147500035LL;
  }
  v24 = (CSusService *)*((_QWORD *)a3 + 12);
  v201 = v24;
  memset(v295, 0, 0x108u);
  memset(v295, 0, 24);
  CDownloadSession::CDownloadSession((CDownloadSession *)&v295[3], *((const struct CCallerIdentity **)a3 + 5));
  v25 = CAgentProtocolTalkerContext::GetAndIncrementCorrelationVector(a3, v296);
  v27 = 0;
  if ( v25 < 0 )
    v296[0] = 0;
  v28 = a14;
  if ( !v218 || !a14 || (v31 = v248) == 0 || (v32 = v249) == 0 )
  {
    refreshed = -2147467261;
    v30 = 0;
    goto LABEL_19;
  }
  v27 = (__int64)v231;
  v26 = 0;
  if ( !v231 )
  {
    refreshed = -2147467261;
    v30 = 0;
    goto LABEL_19;
  }
  *a14 = 0;
  *v31 = 0;
  *v32 = 0;
  *(_BYTE *)v27 = 0;
  v33 = (***(__int64 (__fastcall ****)(_QWORD))a3)(*(_QWORD *)a3);
  v27 = 0;
  if ( v33 )
  {
    refreshed = -2145124341;
    goto LABEL_17;
  }
  if ( !*((_DWORD *)v196 + 18) )
  {
    refreshed = -2145124348;
    WUTrace(0, 0, 8, 3, -2145124348, L"Protocol Talker not inited");
    goto LABEL_43;
  }
  v36 = (RTL_SRWLOCK *)((char *)v24 + 40);
  SRWLock = v36;
  BooleanPropertyFromServerConfig = 0;
  AcquireSRWLockShared(v36);
  v194 = CSusService::ValidateServerConfigState(v201);
  if ( v194 >= 0 )
    BooleanPropertyFromServerConfig = CSusService::GetBooleanPropertyFromServerConfig(
                                        v201,
                                        L"SendClientPreferredLanguagesInSync",
                                        0);
  ReleaseSRWLockShared(v36);
  if ( v194 >= 0
    && BooleanPropertyFromServerConfig
    && CAgentProtocolTalker::GetUserPreferredLanguages(v38, (struct CBSTRList *)&v288) >= 0 )
  {
    *((_QWORD *)&v262[16] + 1) = v289;
    LODWORD(v262[16]) = HIDWORD(v290);
  }
  refreshed = CAgentProtocolTalker::RefreshPTState(v196, v192, 0, 1);
  v27 = 0;
  if ( refreshed < 0 )
    goto LABEL_17;
  AcquireSRWLockShared(v36);
  refreshed = CSusService::ValidateServerConfigState(v201);
  v241 = 0;
  if ( refreshed >= 0 )
  {
    if ( *((double *)v201 + 48) >= 4.0 )
      v39 = CSusService::GetBooleanPropertyFromServerConfig(v201, L"AllowDeadline", 0);
    else
      v39 = (*(__int64 (__fastcall **)(CSusService *))(*(_QWORD *)v201 + 24LL))(v201);
    v241 = v39;
  }
  ReleaseSRWLockShared(v36);
  v27 = 0;
  if ( refreshed < 0 )
    goto LABEL_17;
  v206 = 0;
  AcquireSRWLockShared(v36);
  v40 = CSusService::ValidateServerConfigState(v201);
  if ( v40 >= 0 )
    v206 = (*((_DWORD *)v201 + 124) >> 12) & 1;
  v41 = SRWLock;
  ReleaseSRWLockShared(SRWLock);
  if ( v40 < 0 )
  {
    WUTrace(0, 0, 8, 3, v40, L"GetSyncUpdatesSupportsTreatAppCategoryIdsAsInstalled");
    v206 = 0;
  }
  if ( (*(unsigned __int8 (__fastcall **)(CSusService *))(*(_QWORD *)v201 + 80LL))(v201) )
  {
    BYTE8(v262[18]) = (*(__int64 (__fastcall **)(struct ISusSearchAttributeProvider *, __int64, __int64, _QWORD))(*(_QWORD *)v218 + 16LL))(
                        v218,
                        v42,
                        v43,
                        0);
    v44 = (const OLECHAR *)(*(__int64 (__fastcall **)(struct ISusSearchAttributeProvider *))(*(_QWORD *)v218 + 88LL))(v218);
    v268[0] = (__int64)v44;
    if ( v44 )
    {
      *(_QWORD *)&v262[19] = SysAllocString(v44);
    }
    else
    {
      refreshed = CAgentProtocolTalkerContext::GetDeviceAttributes(v192, (wchar_t **)&v262[19]);
      v27 = 0;
      if ( refreshed < 0 )
        goto LABEL_17;
    }
    v45 = CSusService::SupportsURIEncodedAttributes(v201);
    refreshed = CAgentProtocolTalker::GetCallerAttributes(v218, v45, (wchar_t **)&v262[20]);
    v27 = 0;
    if ( refreshed < 0 )
      goto LABEL_17;
    v47 = (const OLECHAR *)(*(__int64 (__fastcall **)(struct ISusSearchAttributeProvider *, __int64, _QWORD))(*(_QWORD *)v218 + 96LL))(
                             v218,
                             v46,
                             0);
    *(_QWORD *)&v253 = v47;
    if ( v47 )
    {
      *((_QWORD *)&v262[19] + 1) = SysAllocString(v47);
    }
    else
    {
      refreshed = CAgentProtocolTalker::GetProductAttributes(v218, (wchar_t **)&v262[19] + 1);
      v27 = 0;
      if ( refreshed < 0 )
        goto LABEL_17;
    }
    v48 = L"CTAC";
    v49 = L"CTAC";
    if ( v268[0] )
      v49 = L"Caller";
    WUTrace(0, 0, 8, 4, 0, L"DeviceAttributes(%ws): %ws", v49, *(_QWORD *)&v262[19]);
    if ( (_QWORD)v253 )
      v48 = L"Caller";
    WUTrace(0, 0, 8, 4, 0, L"ProductAttributes(%ws): %ws", v48, *((_QWORD *)&v262[19] + 1));
    WUTrace(0, 0, 8, 4, 0, L"CallerAttributes: %ws", *(_QWORD *)&v262[20]);
    v41 = SRWLock;
  }
  if ( v235 && *(_DWORD *)v235 && *(_QWORD *)(v235 + 8) && *(_QWORD *)(v235 + 16) )
  {
    v50 = 0;
    AcquireSRWLockShared(v41);
    if ( (int)CSusService::ValidateServerConfigState(v201) >= 0 )
      v50 = (*((_DWORD *)v201 + 124) >> 13) & 1;
    ReleaseSRWLockShared(v41);
    if ( v50 )
      v219 = 1;
    else
      *(_DWORD *)v235 = 0;
  }
  v51 = v225;
  if ( !v225 || !*(_DWORD *)v225 || !*((_QWORD *)v225 + 1) )
  {
    ProcessHeap = GetProcessHeap();
    v61 = HeapAlloc(ProcessHeap, 0, 0x18u);
    v22 = v61;
    v243 = v61;
    v240 = v61;
    v27 = 0;
    if ( v61 )
    {
      *(_OWORD *)v61 = 0;
      *v61 = &CSusArrayList<_GUID,CSusArrayListItemOpNoop<_GUID>>::`vftable';
      v61[1] = 0;
      v61[2] = 0;
      v240 = v61;
      v242 = v239;
      goto LABEL_110;
    }
    v22 = 0;
    v240 = 0;
    goto LABEL_103;
  }
  v52 = 0;
  do
  {
    v53 = *(_OWORD *)(*((_QWORD *)v51 + 1) + 16LL * v52);
    v253 = v53;
    if ( *(_DWORD *)(*((_QWORD *)v51 + 3) + 4LL * v52) )
    {
      if ( v20 )
      {
LABEL_94:
        v57 = CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>>::AddUnsorted(v20, &v253);
        goto LABEL_99;
      }
      v263 = 1;
      v54 = v205;
      if ( *((_BYTE *)v51 + 32) )
        v54 = v206;
      v205 = v54;
      v55 = GetProcessHeap();
      v56 = HeapAlloc(v55, 0, 0x20u);
      v20 = v56;
      v268[0] = (__int64)v56;
      v27 = 0;
      if ( v56 )
      {
        *v56 = 0;
        v56[1] = 0;
        *((_QWORD *)v56 + 1) = 0;
        *((_QWORD *)v56 + 2) = 0;
        *(_QWORD *)v56 = &CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>>::`vftable';
        *((_DWORD *)v56 + 6) = 0;
        v246 = v56;
        goto LABEL_94;
      }
      v20 = 0;
      v246 = 0;
LABEL_103:
      refreshed = -2147024882;
      goto LABEL_17;
    }
    *(_OWORD *)v268 = 0;
    if ( !v19 )
    {
      v58 = GetProcessHeap();
      v59 = HeapAlloc(v58, 0, 0x18u);
      v19 = v59;
      v268[0] = (__int64)v59;
      v27 = 0;
      if ( !v59 )
      {
        v19 = 0;
        v247 = 0;
        goto LABEL_103;
      }
      *(_OWORD *)v59 = 0;
      *v59 = &CSusArrayList<RequestJobRange,CSusArrayListItemOpNoop<RequestJobRange>>::`vftable';
      v59[1] = 0;
      v59[2] = 0;
      v247 = v59;
    }
    *(_OWORD *)v268 = v53;
    v57 = (*(__int64 (__fastcall **)(_QWORD *, __int64 *, _QWORD))(*v19 + 8LL))(v19, v268, 0);
LABEL_99:
    v27 = 0;
    refreshed = v57;
    if ( v57 < 0 )
      goto LABEL_17;
    ++v52;
    v51 = v225;
  }
  while ( v52 < *(_DWORD *)v225 );
  if ( v20 )
  {
    refreshed = CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>>::Sort(v20);
    v27 = 0;
    if ( refreshed < 0 )
      goto LABEL_17;
  }
LABEL_110:
  if ( (*((_BYTE *)v192 + 48) & 2) != 0 )
  {
    refreshed = GetSizeAndPtrFromSID(*(PSID *)(*((_QWORD *)v192 + 5) + 88LL), &v203, &v233);
    v27 = 0;
    if ( refreshed < 0 )
    {
LABEL_17:
      v30 = 0;
      goto LABEL_18;
    }
  }
  refreshed = CSusService::CreateAppCatIdProvider(v201, &v234);
  v27 = 0;
  if ( refreshed < 0 )
    goto LABEL_416;
  if ( v263 )
  {
    v62 = CAgentProtocolTalker::AddSharedUpdatesToAppCatScanLists(v196, v203, v233, (char *)v192 + 8, v214, v291);
    if ( v62 < 0 )
      WUTrace(0, 0, 8, 3, v62, L"AddSharedUpdatesToAppCatScanLists failed -- continuing");
    if ( *((char *)v192 + 48) < 0 )
    {
      RequestedAppCategoryIdList = CAgentUpdateManager::InitializeAndGetRequestedAppCategoryIdList(
                                     *((_QWORD *)v196 + 3),
                                     (char *)v192 + 8,
                                     0);
      v64 = RequestedAppCategoryIdList;
      if ( RequestedAppCategoryIdList )
      {
        v65 = *(_DWORD *)(RequestedAppCategoryIdList + 20);
        v66 = 0;
        if ( v65 )
        {
          while ( 1 )
          {
            *(_OWORD *)v268 = *(_OWORD *)(*(_QWORD *)(v64 + 8) + 16LL * v66);
            if ( (unsigned int)CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>>::GetIndexOf(v20, v268) >= *((_DWORD *)v20 + 5) )
              break;
            if ( ++v66 >= v65 )
              goto LABEL_123;
          }
          v232 = 1;
        }
      }
    }
  }
LABEL_123:
  LOBYTE(v216) = 0;
  AcquireSRWLockShared((PSRWLOCK)v201 + 5);
  v67 = CSusService::ValidateServerConfigState(v201);
  if ( v67 >= 0 )
  {
    v68 = *((_DWORD *)v201 + 124) >> 18;
    LOBYTE(v68) = (*((_DWORD *)v201 + 124) & 0x40000) != 0;
    v216 = v68;
  }
  ReleaseSRWLockShared((PSRWLOCK)v201 + 5);
  if ( v67 < 0 )
    WUTrace(
      0,
      0,
      8,
      3,
      v67,
      L"Could not read config property SupportUpdateDeploymentId from GetConfig sent by service.");
  refreshed = (*(__int64 (__fastcall **)(struct ISusSearchAttributeProvider *, void **, int *))(*(_QWORD *)v218 + 56LL))(
                v218,
                &v260,
                &v270);
  v27 = 0;
  if ( refreshed < 0 )
  {
LABEL_416:
    v23 = v234;
    goto LABEL_375;
  }
  v70 = v270;
  v71 = v260;
  if ( v260 || !v270 )
  {
    CSusArrayList<wchar_t *,CSusArrayBSTRListItemOpDelete>::RemoveArraySection(v271);
    SusFree(v271[1]);
    v271[1] = v71;
    HIDWORD(v272) = v70;
    LODWORD(v272) = v70;
  }
  v23 = v234;
  while ( 2 )
  {
    v72 = v192;
    v73 = (***(__int64 (__fastcall ****)(_QWORD, __int64, __int64))v192)(*(_QWORD *)v192, v69, v27);
    v27 = 0;
    if ( v73 )
    {
LABEL_399:
      refreshed = -2145124341;
      goto LABEL_375;
    }
    v74 = 0;
    v237 = 0;
    if ( v20 )
    {
      if ( *((_BYTE *)v225 + 32) )
        v74 = (__int64)v20;
    }
    else if ( v242 )
    {
      v74 = v242;
    }
    else if ( (*((_BYTE *)v72 + 48) & 9) != 0 )
    {
      v75 = CAgentUpdateManager::InitializeAndGetRequestedAppCategoryIdList(*((_QWORD *)v196 + 3), (char *)v72 + 8, 0);
      v74 = v75;
      v237 = v75;
      if ( v75 )
      {
        LODWORD(v169) = *(_DWORD *)(v75 + 20);
        WUTrace(0, 0, 1, 5, 0, L"SyncUpdates adding %lu visited app categories", v169);
      }
    }
    v76 = *((_QWORD *)v72 + 41);
    v239 = v76;
    memset(v294, 0, sizeof(v294));
    if ( v76 )
    {
      v294[1] = *(_DWORD *)(v76 + 4);
      v294[2] = *(_DWORD *)(v76 + 8);
      v294[3] = *(_DWORD *)(v76 + 12);
      v294[4] = *(_DWORD *)(v76 + 16);
      v294[69] = *(_DWORD *)(v76 + 276);
      LOWORD(v294[70]) = *(_WORD *)(v76 + 280);
      BYTE2(v294[70]) = *(_BYTE *)(v76 + 282);
    }
    v77 = *((_QWORD *)v196 + 3);
    v189 = &v282;
    v188 = &v276;
    v187 = &v273;
    v186 = (CatScanContext *)&v285;
    v185 = v74;
    LODWORD(v184) = 1;
    LODWORD(v183) = 0;
    v182 = v296;
    LODWORD(v181) = 1;
    *(_QWORD *)v180 = 0;
    LODWORD(v179) = 0;
    *(_QWORD *)v178 = (*(__int64 (__fastcall **)(struct ISusSearchAttributeProvider *))(*(_QWORD *)v218 + 72LL))(v218);
    v177 = (wchar_t *)((unsigned __int64)v294 & -(__int64)(v239 != 0));
    v176 = *((_QWORD *)v192 + 5);
    LODWORD(v175) = *((_DWORD *)v192 + 12);
    v173 = (struct SusWsStructs::SusExtendedUpdateInfo *)*((_QWORD *)v192 + 79);
    v170 = v250;
    refreshed = CAgentUpdateManager::DetectForUpdates(v77, 0, *((_QWORD *)v192 + 40), *(_QWORD *)v192, v251, v214);
    v27 = 0;
    if ( refreshed < 0 )
    {
      WUTrace(0, 0, 8, 3, refreshed, L"CAgentUpdateManager::DetectForUpdates failed");
      goto LABEL_43;
    }
    if ( v22 )
    {
      refreshed = CAppCatIdProviderHelper::GetAllValidAppCategoryIds(v23, v22, 0);
      v27 = 0;
      if ( refreshed < 0 )
      {
        if ( refreshed == -2145124340 )
        {
          WUTrace(0, 0, 8, 4, 0, L"GetAllValidAppCategoryIds returned no categories, bailing service sync");
          v27 = 0;
          refreshed = 0;
          goto LABEL_375;
        }
        WUTrace(0, 0, 8, 3, refreshed, L"CAppCatIdProviderHelper::GetAllValidAppCategoryIds failed");
        goto LABEL_43;
      }
      *v249 = *((_DWORD *)v22 + 5);
    }
    v78 = DWORD1(v287);
    if ( DWORD1(v287) )
    {
      lpMem = v286;
      v286 = 0;
      *(_QWORD *)&v287 = 0;
      v199 = 1;
      v198 = v78;
    }
    if ( !v195 )
    {
      if ( v221 )
      {
        v79 = 0;
        v194 = 0;
        v80 = 0;
        v204 = 0;
        if ( v205 )
        {
          v81 = GetProcessHeap();
          v82 = HeapAlloc(v81, 0, 0x20u);
          v83 = v82;
          v268[0] = (__int64)v82;
          v27 = 0;
          if ( v82 )
          {
            *v82 = 0;
            v82[1] = 0;
            *((_QWORD *)v82 + 1) = 0;
            *((_QWORD *)v82 + 2) = 0;
            *(_QWORD *)v82 = &CSusSortedArrayList<long,CSusSortedArrayListItemOpsBasic<long>>::`vftable';
            *((_DWORD *)v82 + 6) = 0;
          }
          else
          {
            v83 = 0;
          }
          if ( v21 )
          {
            (**v21)(v21, 1, 0);
            v27 = 0;
          }
          v21 = (void (__fastcall ***)(_QWORD, __int64, _QWORD))v83;
          v244 = (void (__fastcall ***)(_QWORD, __int64, _QWORD))v83;
          if ( !v83 )
          {
            refreshed = -2147024882;
            goto LABEL_375;
          }
          SRWLock = 0;
          refreshed = (*(__int64 (__fastcall **)(_QWORD, PSRWLOCK *))(**((_QWORD **)v196 + 4) + 24LL))(
                        *((_QWORD *)v196 + 4),
                        &SRWLock);
          v27 = 0;
          if ( refreshed < 0 )
            goto LABEL_375;
          v85 = (*(__int64 (__fastcall **)(CSusService *, __int64, _QWORD))(*(_QWORD *)v201 + 8LL))(v201, v84, 0);
          refreshed = ConvertUpdateGUIDsToRevisionIds(v20, v83, SRWLock, v85);
          (*((void (__fastcall **)(PSRWLOCK))SRWLock->Ptr + 2))(SRWLock);
          if ( refreshed < 0 )
          {
            refreshed = 0;
            v79 = v194;
          }
          else
          {
            v204 = (CSusService *)*((_QWORD *)v83 + 1);
            v79 = *((_DWORD *)v83 + 5);
          }
          v80 = v204;
        }
        v86 = AreOldAndNewInstalledListsEqual(v220, (const int *)v229, v198, (const int *)lpMem, v79, (const int *)v80);
        v27 = 0;
        if ( v213 )
        {
          SusFree(v229);
          v27 = 0;
          v229 = 0;
          v213 = 0;
          v220 = 0;
        }
        if ( v86 )
        {
          v195 = 1;
          break;
        }
      }
      v92 = 0;
      v266 = 0;
      v267 = 0u;
      v93 = 0;
      v265 = &CSusSortedArrayList<long,CSusSortedArrayListItemOpsBasic<long>>::`vftable';
      v94 = 0;
      v95 = v192;
      if ( *((_DWORD *)v192 + 93) )
      {
        while ( 1 )
        {
          v194 = *(_DWORD *)(*((_QWORD *)v95 + 45) + 4LL * v94);
          refreshed = CSusSortedArrayList<int,CSusSortedArrayListItemOpsBasic<int>>::Add(&v265, &v194, 1);
          if ( (int)(refreshed + 0x80000000) >= 0 && refreshed != -2145124333 )
            goto LABEL_378;
          ++v94;
          v95 = v192;
          if ( v94 >= *((_DWORD *)v192 + 93) )
          {
            v93 = DWORD1(v267);
            v92 = v266;
            break;
          }
        }
      }
      v96 = 0;
      if ( v93 )
      {
        while ( 1 )
        {
          v194 = *(_DWORD *)(v92 + 4LL * v96);
          refreshed = CSusSortedArrayList<int,CSusSortedArrayListItemOpsBasic<int>>::Add(&v273, &v194, 1);
          if ( (int)(refreshed + 0x80000000) >= 0 && refreshed != -2145124333 )
            break;
          ++v96;
          v92 = v266;
          if ( v96 >= DWORD1(v267) )
            goto LABEL_191;
        }
LABEL_378:
        CSusArrayList<long,CSusSortedArrayListItemOpsBasic<long>>::~CSusArrayList<long,CSusSortedArrayListItemOpsBasic<long>>(&v265);
        goto LABEL_43;
      }
LABEL_191:
      v97 = DWORD1(v275);
      if ( DWORD1(v275) )
      {
        v226 = v274;
        v274 = 0;
        *(_QWORD *)&v275 = 0;
        v200 = v97;
        v212 = 1;
      }
      v98 = DWORD1(v284);
      if ( DWORD1(v284) )
      {
        v227 = v283;
        v283 = 0;
        *(_QWORD *)&v284 = 0;
        v222 = v98;
        v211 = 1;
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_OutOfScopeExemptUpdates>::__private_IsEnabled(
                              `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_OutOfScopeExemptUpdates>::GetImpl'::`2'::impl,
                              v92,
                              v95,
                              1) )
      {
        v99 = DWORD1(v281);
        if ( DWORD1(v281) )
        {
          v228 = v280;
          v280 = 0;
          *(_QWORD *)&v281 = 0;
          v223 = v99;
          v210 = 1;
        }
      }
      BYTE4(v262[8]) = 0;
      CSusArrayList<long,CSusSortedArrayListItemOpsBasic<long>>::~CSusArrayList<long,CSusSortedArrayListItemOpsBasic<long>>(&v265);
      v103 = v192;
LABEL_207:
      *((_QWORD *)&v262[0] + 1) = lpMem;
      LODWORD(v262[1]) = v198;
      v106 = v200;
      if ( !v200 )
      {
        *((_QWORD *)&v262[2] + 1) = 0;
        LODWORD(v262[3]) = 0;
        goto LABEL_220;
      }
      if ( (_BYTE)v216 )
      {
        v263 = 0;
        updated = CAgentProtocolTalker::FillCachedUpdateDeploymentIDs(
                    (_DWORD)v196,
                    (_DWORD)v103,
                    (_DWORD)v226,
                    v200,
                    (__int64)v214,
                    (__int64)v218,
                    (__int64)v271,
                    (__int64)&v263,
                    (__int64)&v259);
        if ( updated < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x9B6,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\ProtocolTalker.cpp",
            (const char *)(unsigned int)updated,
            lpString2a);
          goto LABEL_213;
        }
        *((_QWORD *)&v262[2] + 1) = v259;
        v259 = 0;
        LODWORD(v262[3]) = v263;
LABEL_220:
        *((_QWORD *)&v262[1] + 1) = 0;
        LODWORD(v262[2]) = 0;
      }
      else
      {
LABEL_213:
        *((_QWORD *)&v262[2] + 1) = 0;
        LODWORD(v262[3]) = 0;
        *((_QWORD *)&v262[1] + 1) = v226;
        LODWORD(v262[2]) = v106;
      }
      *((_QWORD *)&v262[4] + 1) = v227;
      LODWORD(v262[5]) = v222;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_OutOfScopeExemptUpdates>::__private_IsEnabled(
                              `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_OutOfScopeExemptUpdates>::GetImpl'::`2'::impl,
                              v100,
                              v101,
                              v102) )
      {
        *((_QWORD *)&v262[5] + 1) = v228;
        LODWORD(v262[6]) = v223;
      }
      if ( v19 && *((_DWORD *)v19 + 5) )
      {
        *((_QWORD *)&v262[8] + 1) = v19[1];
        LODWORD(v262[9]) = *((_DWORD *)v19 + 5);
      }
      else
      {
        *((_QWORD *)&v262[8] + 1) = 0;
        LODWORD(v262[9]) = 0;
      }
      refreshed = CAgentProtocolTalker::CombineAppCategoryIDs(
                    (_DWORD)v20,
                    (_DWORD)v22,
                    v242,
                    v237,
                    (__int64)&v257,
                    (__int64)&v264);
      v27 = 0;
      if ( refreshed < 0 )
        goto LABEL_375;
      if ( v257 && v264 )
      {
        *((_QWORD *)&v262[9] + 1) = v257;
        LODWORD(v262[10]) = v264;
      }
      else
      {
        *((_QWORD *)&v262[9] + 1) = 0;
        LODWORD(v262[10]) = 0;
      }
      v109 = v225;
      if ( v225 && *((_QWORD *)v225 + 1) || (*((_DWORD *)v103 + 12) & 0x2000002) != 0 )
      {
        v111 = (*((_DWORD *)v103 + 12) & 0x80) == 0;
        BYTE4(v262[10]) = 0;
      }
      else
      {
        if ( (*((_BYTE *)v103 + 48) & 4) == 0 )
        {
          v110 = (*(__int64 (__fastcall **)(CSusService *, __int64, _QWORD))(*(_QWORD *)v201 + 80LL))(v201, v108, 0);
          v27 = 0;
          if ( !v110 )
          {
            BYTE4(v262[9]) = 0;
            BYTE4(v262[10]) = 1;
            goto LABEL_236;
          }
        }
        v111 = 1;
        BYTE4(v262[10]) = 1;
      }
      BYTE4(v262[9]) = v111;
LABEL_236:
      LOBYTE(v262[14]) = v205 != 0;
      if ( v219 )
      {
        v112 = *(_QWORD *)(v235 + 16);
        v113 = *(_DWORD *)(v112 + 20);
        *(_QWORD *)&v262[12] = *(_QWORD *)(v112 + 8);
        DWORD2(v262[11]) = v113;
        v114 = *(_QWORD *)(v235 + 8);
        v115 = *(_DWORD *)(v114 + 20);
        *(_QWORD *)&v262[13] = *(_QWORD *)(v114 + 8);
        DWORD2(v262[12]) = v115;
        *((_QWORD *)&v262[13] + 1) = SysAllocString(psz);
        v27 = 0;
      }
      else
      {
        DWORD2(v262[11]) = 0;
        *(_QWORD *)&v262[12] = 0;
        DWORD2(v262[12]) = 0;
        v262[13] = 0;
      }
      if ( !v206 )
        goto LABEL_245;
      v263 = 0;
      if ( !v23 )
      {
        v116 = -2147467261;
        v117 = 73;
        goto LABEL_244;
      }
      v116 = (*(__int64 (__fastcall **)(struct CAppCatIdProvider *, char *, int *, char *))(*(_QWORD *)v23 + 16LL))(
               v23,
               (char *)&v262[14] + 8,
               &v263,
               (char *)&v262[15] + 8);
      if ( v116 >= 0 )
      {
        if ( (unsigned int)v263 <= 0x7FFFFFFF )
          LODWORD(v262[15]) = v263;
        else
          WUTrace(0, 0, 8, 3, v116, L"GetAllUserCompartments data unexpectedly large");
        v103 = v192;
      }
      else
      {
        v117 = 77;
LABEL_244:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v117,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\AppCatIdProviders\\AppCatIdProviderHelper.cpp",
          (const char *)(unsigned int)v116,
          lpString2b);
        WUTrace(0, 0, 8, 3, v116, L"GetAllUserCompartments failed");
        v27 = 0;
        v103 = v192;
LABEL_245:
        *((_QWORD *)&v262[15] + 1) = 0;
        *((_QWORD *)&v262[14] + 1) = 0;
      }
      if ( v109 )
        *(_OWORD *)((char *)&v262[17] + 8) = *(_OWORD *)((char *)v109 + 36);
      v118 = (***(__int64 (__fastcall ****)(_QWORD, __int64, __int64))v103)(*(_QWORD *)v103, v108, v27);
      v27 = 0;
      if ( v118 )
        goto LABEL_399;
      DumpSyncUpdateParameters((const struct SusWsStructs::SusSyncUpdateParameters *)v262, ++v190);
      v193 = v195;
      refreshed = CAgentProtocolTalker::SyncUpdates_WithRecovery(
                    v196,
                    v103,
                    (struct SusWsStructs::SusSyncUpdateParameters *)v262,
                    (struct SusWsStructs::SusSyncInfo *)v261);
      v27 = 0;
      if ( refreshed < 0 )
        goto LABEL_375;
      DumpSyncInfo((const struct SusWsStructs::SusSyncInfo *)v261, v190);
      if ( v261[8] )
      {
        refreshed = CAgentProtocolTalkerContext::SetServerCookie(
                      v103,
                      (const struct SusWsStructs::SusCookie *)&v261[6],
                      1,
                      v119);
        v27 = 0;
        if ( refreshed < 0 )
          goto LABEL_375;
      }
      v217 = SysStringLen((BSTR)v261[11]) && CompareStringW(0x7Fu, 1u, (PCNZWCH)v261[11], -1, L"true", -1) == 2;
      v120 = SysStringLen((BSTR)v261[13]);
      v27 = 0;
      if ( !v120 )
      {
LABEL_266:
        LODWORD(v236) = 0;
        v121 = 0;
        v122 = 0;
        if ( SLODWORD(v261[3]) > 0 )
        {
          v123 = v261[2];
          while ( !*(_DWORD *)v123 )
          {
            ++v122;
            v123 = (struct SusWsStructs::SusUpdateInfo *)((char *)v123 + 4);
            if ( v122 >= SLODWORD(v261[3]) )
              goto LABEL_272;
          }
          v27 = 1;
          LODWORD(v236) = 1;
        }
LABEL_272:
        v124 = 0;
        v263 = 0;
        v125 = 0;
        v126 = LODWORD(v261[10]);
        if ( SLODWORD(v261[10]) > 0 )
        {
          v127 = v261[9];
          while ( !*(_DWORD *)v127 )
          {
            ++v125;
            v127 = (struct SusWsStructs::SusUpdateInfo *)((char *)v127 + 4);
            if ( v125 >= SLODWORD(v261[10]) )
            {
              v124 = 0;
              goto LABEL_278;
            }
          }
          v124 = 1;
          v263 = 1;
        }
LABEL_278:
        if ( SLODWORD(v261[1]) > 0 || SLODWORD(v261[5]) > 0 || (_DWORD)v27 || v124 )
        {
          v265 = &CSusArrayList<IReportingEventHandler<CUpdateManagerReportingEvent> *,CSusArrayListItemOpNoop<IReportingEventHandler<CUpdateManagerReportingEvent> *>>::`vftable';
          v266 = 0;
          *(_QWORD *)&v267 = 0;
          v268[0] = 0;
          v207 = 0;
          v208 = v195 ? v208 : 0;
          if ( (***(unsigned int (__fastcall ****)(_QWORD, _QWORD, __int64))v103)(
                 *(_QWORD *)v103,
                 LODWORD(v261[10]),
                 v27) )
          {
            refreshed = -2145124341;
            goto LABEL_381;
          }
          v191 = 0;
          LODWORD(v237) = v261[1];
          v194 = 0;
          v128 = 0;
          if ( SLODWORD(v261[1]) > 0 )
            v128 = v261[0];
          v129 = CExternalCompressionProcessor::ProcessCoreMetadata(
                   (CExternalCompressionProcessor *)v295,
                   v196,
                   v103,
                   *((struct CSusEventSystem **)v196 + 7),
                   (const struct _GUID *)((char *)v103 + 8),
                   (unsigned int)v261[1],
                   v128,
                   *((void *const *)v196 + 16),
                   &v191);
          refreshed = v129;
          if ( v129 >= 0 )
          {
            v130 = (signed int)v261[1];
          }
          else
          {
            if ( v129 != -2145107921 )
            {
              WUTrace(0, 0, 8, 1, v129, L"ProcessCoreMetadata failed");
              goto LABEL_381;
            }
            v130 = v191;
            if ( !v191 )
            {
              WUTrace(0, 0, 8, 1, 0, L"ProcessCoreMetadata did not return any update to be committed");
              goto LABEL_381;
            }
            LODWORD(v261[1]) = v191;
            v194 = 1;
          }
          if ( !v241 )
          {
            if ( v130 > 0 )
            {
              v131 = 0;
              v132 = 0;
              do
              {
                v133 = v261[0];
                SysFreeString(*(BSTR *)((char *)v261[0] + v131 + 16));
                *(_QWORD *)((char *)v133 + v131 + 16) = 0;
                ++v132;
                v131 += 272;
                v130 = (signed int)v261[1];
              }
              while ( v132 < SLODWORD(v261[1]) );
              v22 = v243;
              v23 = v234;
              v21 = v244;
              v103 = v192;
            }
            if ( SLODWORD(v261[5]) > 0 )
            {
              v134 = 0;
              v135 = 0;
              do
              {
                v136 = v261[4];
                SysFreeString(*(BSTR *)((char *)v261[4] + v134 + 16));
                *(_QWORD *)((char *)v136 + v134 + 16) = 0;
                ++v135;
                v134 += 272;
              }
              while ( v135 < SLODWORD(v261[5]) );
              v22 = v243;
              v23 = v234;
              v21 = v244;
              v130 = (signed int)v261[1];
              v103 = v192;
            }
          }
          refreshed = MetadataIntegrity::AgentHelper::VerifyMetadataSignatures<SusWsStructs::SusUpdateInfo>(
                        v130,
                        v261[0],
                        (int)v196 + 8,
                        (_DWORD)v103,
                        *((_QWORD *)v196 + 16),
                        cchCount2,
                        (__int64)&v265);
          if ( refreshed < 0 )
          {
            WUTrace(0, 0, 8, 1, refreshed, L"MetadataIntegrity::AgentHelper::VerifyMetadataSignatures");
            goto LABEL_381;
          }
          v253 = 0u;
          v254 = 0;
          v255 = 0;
          refreshed = CAgentProtocolTalkerContext::GetMetadataIntegrityDataForScanEvent(
                        v103,
                        (struct MetadataIntegrity::MetadataIntegrityDataForScanEvent *)&v253);
          if ( refreshed < 0 )
          {
            v159 = v255;
            if ( !v255 )
              goto LABEL_381;
            goto LABEL_385;
          }
          v137 = MetadataIntegrity::EnforcementModeAsString((unsigned int)v253, 0);
          v138 = v255;
          LODWORD(v175) = HIDWORD(v253);
          LODWORD(v174) = v254;
          LODWORD(v169) = DWORD2(v253);
          LODWORD(v171) = DWORD1(v253);
          WUTrace(
            0,
            v139,
            (unsigned int)(v139 + 8),
            (unsigned int)(v139 + 4),
            v139,
            L"TMI %lu/%lu bad core; %lu/%lu bad behavior; mode: %ls (%ws)",
            v169,
            v171,
            v174,
            v175,
            v137,
            v255,
            *(_QWORD *)v178,
            v179,
            0,
            v181,
            v296,
            v183,
            v184,
            v185,
            &v285,
            &v273,
            &v276,
            &v282,
            &v279);
          v140 = 0;
          if ( v138 )
          {
            SusFree(v138);
            v140 = 0;
          }
          if ( DWORD1(v267) )
          {
            v268[0] = v266;
            v207 = DWORD1(v267);
          }
          v141 = 0;
          v191 = 0;
          v142 = 0;
          v202 = 0;
          v204 = 0;
          v143 = 0;
          *(_QWORD *)&v253 = 0;
          if ( (_DWORD)v236 )
          {
            v141 = (unsigned int)v261[3];
            v191 = (unsigned int)v261[3];
            v204 = v261[2];
          }
          if ( v263 )
          {
            v142 = (unsigned int)v261[10];
            v202 = (int)v261[10];
            v143 = v261[9];
            *(struct SusWsStructs::SusUpdateInfo **)&v253 = v261[9];
          }
          v144 = 0;
          v236 = 0;
          if ( v239 && v141 )
          {
            if ( v142 + v141 )
            {
              v144 = SafeSusAllocArray(v142 + v141, 4u);
              v236 = v144;
              refreshed = v144 == 0 ? 0x8007000E : 0;
              v142 = v202;
              v141 = v191;
            }
            else
            {
              refreshed = 0;
            }
            if ( refreshed < 0 )
              goto LABEL_383;
            if ( v142 )
            {
              v145 = v144;
              v146 = v253 - (_QWORD)v144;
              v147 = v142;
              do
              {
                *v145 = *(_DWORD *)((char *)v145 + v146);
                ++v145;
                --v147;
              }
              while ( v147 );
            }
            v148 = 0;
            v149 = v204;
            do
            {
              v144[v148 + v142] = *(_DWORD *)v149;
              ++v148;
              v149 = (CSusService *)((char *)v149 + 4);
            }
            while ( v148 < v141 );
            LODWORD(v169) = v141;
            WUTrace(
              0,
              0,
              8,
              4,
              0,
              L"Treating %lu OutOfScope revisionIds as DeployedOutOfScope for version override scan.",
              v169);
            v143 = (struct SusWsStructs::SusUpdateInfo *)v144;
            v202 += v191;
            v140 = 0;
            v204 = 0;
            v191 = 0;
          }
          v150 = 0;
          if ( SLODWORD(v261[5]) > 0 )
            v150 = v261[4];
          if ( v207 )
            v140 = v268[0];
          refreshed = CAgentUpdateManager::PopulateDataStore(
                        *((_QWORD *)v196 + 3),
                        *((_QWORD *)v192 + 40),
                        v203,
                        (int)v233,
                        *(_QWORD *)v192,
                        (__int64)v192 + 8,
                        *((_DWORD *)v192 + 18),
                        v140,
                        v207,
                        (__int64)v204,
                        v191,
                        (__int64)v143,
                        v202,
                        (__int64)v150,
                        (int)v261[5],
                        (__int64)psz,
                        v214,
                        v245,
                        (__int64)v192 + 352,
                        *((_QWORD *)v192 + 79) + 8LL,
                        v225,
                        v232,
                        (__int64)v291,
                        *((_QWORD *)v192 + 78));
          *v248 += v207;
          if ( v194 )
          {
            LODWORD(v261[1]) = v237;
            refreshed = -2145107921;
          }
          else
          {
            if ( refreshed >= 0 )
            {
              if ( !v219 )
                goto LABEL_345;
              v151 = v261[12];
              if ( !v261[12] || !DWORD1(v267) )
                goto LABEL_345;
              if ( DWORD1(v267) < LODWORD(v261[1]) )
              {
                refreshed = CAgentProtocolTalker::FilterExtendedUpdateInfo<SusWsStructs::SusUpdateInfo>(0, &v265);
                if ( refreshed < 0 )
                  goto LABEL_383;
                v151 = v261[12];
              }
              if ( *((int *)v151 + 2) <= 0 )
              {
LABEL_345:
                if ( !v195 )
                {
                  if ( BYTE4(v261[5]) )
                  {
                    v221 = 0;
                  }
                  else
                  {
                    v221 = 1;
                    v213 = v199;
                    v229 = lpMem;
                    v220 = v198;
                    v199 = 0;
                    lpMem = 0;
                    v198 = 0;
                  }
                }
                if ( v144 )
                  SusFree(v144);
                CSusArrayList<wchar_t *,CSusSortedArrayListItemOpsLPWSTRNoDelete>::~CSusArrayList<wchar_t *,CSusSortedArrayListItemOpsLPWSTRNoDelete>(&v265);
                v121 = 0;
                goto LABEL_352;
              }
              v268[0] = (__int64)&CSusArrayList<IReportingEventHandler<CUpdateManagerReportingEvent> *,CSusArrayListItemOpNoop<IReportingEventHandler<CUpdateManagerReportingEvent> *>>::`vftable';
              v268[1] = 0;
              v269 = 0;
              refreshed = CAgentProtocolTalker::VerifyExtendedMetadataSignatures(v196, v192, v151, v268);
              if ( refreshed < 0 )
                goto LABEL_390;
              v253 = 0u;
              v254 = 0;
              v255 = 0;
              refreshed = CAgentProtocolTalkerContext::GetMetadataIntegrityDataForScanEvent(
                            v192,
                            (struct MetadataIntegrity::MetadataIntegrityDataForScanEvent *)&v253);
              if ( refreshed < 0 )
              {
                v160 = v255;
                if ( !v255 )
                  goto LABEL_390;
              }
              else
              {
                v152 = MetadataIntegrity::EnforcementModeAsString((unsigned int)v253, 0);
                LODWORD(v169) = DWORD2(v253);
                LODWORD(v172) = DWORD1(v253);
                WUTrace(
                  0,
                  v153,
                  (unsigned int)(v153 + 8),
                  (unsigned int)(v153 + 4),
                  v153,
                  L"SyncUpdates - %lu bad out of %lu extended metadata signatures checked using %ls enforcement mode (raw mode: %ws).",
                  v169,
                  v172,
                  v152,
                  v255);
                v155 = v261[12];
                if ( HIDWORD(v269) >= *((_DWORD *)v261[12] + 2) )
                {
LABEL_341:
                  refreshed = CAgentUpdateManager::PopulateExtendedInfo(
                                *((CAgentUpdateManager **)v196 + 3),
                                *((struct CExpressionManager **)v192 + 40),
                                *(struct ISusCancellable **)v192,
                                (struct _GUID *)((char *)v192 + 8),
                                *((_DWORD *)v192 + 18),
                                (__int64)v214,
                                v155,
                                *(_QWORD *)(v235 + 8),
                                *(_QWORD *)(v235 + 16),
                                psz);
                  v156 = v255;
                  if ( refreshed < 0 )
                    goto LABEL_387;
                  if ( v255 )
                    SusFree(v255);
                  CSusArrayList<wchar_t *,CSusSortedArrayListItemOpsLPWSTRNoDelete>::~CSusArrayList<wchar_t *,CSusSortedArrayListItemOpsLPWSTRNoDelete>(v268);
                  goto LABEL_345;
                }
                refreshed = CAgentProtocolTalker::FilterExtendedUpdateInfo<SusWsStructs::SusUpdateInfo>(v154, v268);
                if ( refreshed >= 0 )
                {
                  v155 = v261[12];
                  goto LABEL_341;
                }
                v156 = v255;
LABEL_387:
                if ( !v156 )
                  goto LABEL_390;
                v160 = v156;
              }
              SusFree(v160);
LABEL_390:
              CSusArrayList<wchar_t *,CSusSortedArrayListItemOpsLPWSTRNoDelete>::~CSusArrayList<wchar_t *,CSusSortedArrayListItemOpsLPWSTRNoDelete>(v268);
              goto LABEL_383;
            }
            WUTrace(0, 0, 8, 3, refreshed, L"PopulateDataStore failed");
          }
LABEL_383:
          if ( v144 )
          {
            v159 = v144;
LABEL_385:
            SusFree(v159);
          }
LABEL_381:
          CSusArrayList<wchar_t *,CSusSortedArrayListItemOpsLPWSTRNoDelete>::~CSusArrayList<wchar_t *,CSusSortedArrayListItemOpsLPWSTRNoDelete>(&v265);
LABEL_43:
          v30 = v190;
LABEL_44:
          v27 = 0;
          goto LABEL_18;
        }
        if ( !v195 )
          v208 = 1;
LABEL_352:
        if ( v199 )
        {
          SusFree(lpMem);
          v121 = 0;
          lpMem = 0;
          v199 = 0;
          v198 = 0;
        }
        if ( v212 )
        {
          SusFree(v226);
          v121 = 0;
          v226 = 0;
          v212 = 0;
          v200 = 0;
        }
        if ( v211 )
        {
          SusFree(v227);
          v121 = 0;
          v227 = 0;
          v211 = 0;
          v222 = 0;
        }
        if ( v209 )
        {
          SusFree(v224);
          v224 = 0;
          v209 = 0;
          v197 = 0;
        }
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_OutOfScopeExemptUpdates>::__private_IsEnabled(
                                `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_OutOfScopeExemptUpdates>::GetImpl'::`2'::impl,
                                v126,
                                v27,
                                v121)
          && v210 )
        {
          SusFree(v228);
          v228 = 0;
          v210 = 0;
          v223 = 0;
        }
        v157 = v257;
        if ( v257 )
        {
          if ( v264 )
            memset(v257, 0, 16LL * v264);
          SusFree(v157);
        }
        SafeSusStructArrayFree<SusWsStructs::SusUpdateDeploymentIdentifier>(v200, *((_QWORD *)&v262[2] + 1));
        SafeSusStructArrayFree<SusWsStructs::SusUpdateDeploymentIdentifier>(
          (unsigned int)v197,
          *((_QWORD *)&v262[3] + 1));
        v257 = 0;
        *((_QWORD *)&v262[2] + 1) = 0;
        LODWORD(v262[3]) = 0;
        *((_QWORD *)&v262[3] + 1) = 0;
        LODWORD(v262[4]) = 0;
        v264 = 0;
        SysFreeString(*((BSTR *)&v262[14] + 1));
        SafeBstrArrayFree(SLODWORD(v262[15]), *((wchar_t ***)&v262[15] + 1));
        *(_OWORD *)((char *)&v262[14] + 8) = 0;
        *((_QWORD *)&v262[15] + 1) = 0;
        if ( v22 )
          CSusArrayList<_GUID,CSusArrayListItemOpNoop<_GUID>>::RemoveArraySection(v22, v158, 0xFFFFFFFFLL);
        SusWsStructs::SusSyncInfo::Clear((SusWsStructs::SusSyncInfo *)v261);
        v27 = 0;
        if ( v195 )
          goto LABEL_413;
        v195 = v208 != 0;
        if ( v190 > 0xC8 )
        {
          v30 = v190;
          goto LABEL_372;
        }
        continue;
      }
      if ( v261[13] )
      {
        refreshed = CServiceBackup::GetServiceRegistryPath((const struct _GUID *)((char *)v192 + 8), v297, 0);
        v27 = 0;
        if ( refreshed >= 0 )
        {
          refreshed = RegSetStringValue(-2147483646, v297, L"CountryCode");
          v27 = 0;
        }
        if ( refreshed < 0 )
          goto LABEL_375;
        v103 = v192;
        goto LABEL_266;
      }
      refreshed = -2147467261;
LABEL_375:
      v30 = v190;
      goto LABEL_18;
    }
    break;
  }
  if ( v270 || *((_DWORD *)v192 + 13) )
    goto LABEL_413;
  v204 = 0;
  refreshed = CAgentServiceManager::GetServiceObjectHelper((const struct _GUID *)((char *)v192 + 8), &v204);
  v27 = 0;
  if ( refreshed < 0 )
    goto LABEL_375;
  v191 = 1;
  v87 = v204;
  refreshed = CSusService::GetPerformDriverSync(v204, (int *)&v191);
  v27 = 0;
  if ( refreshed < 0 )
    goto LABEL_375;
  CAgentProtocolTalker::AddDependentSetDriversToList(
    (__int64)v196,
    (CAgentProtocolTalkerContext *)((char *)v192 + 8),
    (__int64)v214,
    (__int64)&v276,
    (__int64)&v273);
  if ( DWORD1(v278) )
  {
    v224 = v277;
    v197 = DWORD1(v278);
    v277 = 0;
    *(_QWORD *)&v278 = 0;
    v209 = 1;
  }
  v88 = v191;
  if ( !v191 )
    goto LABEL_402;
  if ( !v217 )
    goto LABEL_179;
  if ( (*(unsigned __int8 (__fastcall **)(CSusService *))(*(_QWORD *)v87 + 80LL))(v87) )
  {
    v263 = 0;
    PerformDriverSync = CSusService::GetPerformDriverSync(v87, &v263);
    v90 = v263;
    if ( PerformDriverSync < 0 )
      v90 = 0;
    if ( v90 )
    {
LABEL_179:
      if ( !v230 )
      {
        WUTrace(0, 0, 8, 4, 0, L"Skipping driver sync because system spec is not available.");
        goto LABEL_412;
      }
      v91 = v197;
      if ( !v197 )
      {
        *((_QWORD *)&v262[7] + 1) = 0;
        LODWORD(v262[8]) = 0;
        goto LABEL_203;
      }
      if ( (_BYTE)v216 )
      {
        v263 = 0;
        v104 = CAgentProtocolTalker::FillCachedUpdateDeploymentIDs(
                 (_DWORD)v196,
                 (_DWORD)v192,
                 (_DWORD)v224,
                 v197,
                 (__int64)v214,
                 (__int64)v218,
                 (__int64)v271,
                 (__int64)&v263,
                 (__int64)&v258);
        if ( v104 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x92F,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\ProtocolTalker.cpp",
            (const char *)(unsigned int)v104,
            lpString2);
          goto LABEL_202;
        }
        *((_QWORD *)&v262[3] + 1) = v258;
        v258 = 0;
        LODWORD(v262[4]) = v263;
        *((_QWORD *)&v262[7] + 1) = 0;
        LODWORD(v262[8]) = 0;
      }
      else
      {
LABEL_202:
        *((_QWORD *)&v262[7] + 1) = v224;
        LODWORD(v262[8]) = v91;
LABEL_203:
        LODWORD(v262[4]) = 0;
        *((_QWORD *)&v262[3] + 1) = 0;
      }
      *((_QWORD *)&v262[6] + 1) = *(_QWORD *)v252;
      LODWORD(v262[7]) = *((_DWORD *)v252 + 4);
      DWORD2(v262[10]) = *((_DWORD *)v252 + 6);
      *(_QWORD *)&v262[11] = *((_QWORD *)v252 + 4);
      v103 = v192;
      v105 = CAgentProtocolTalker::ConstructFeatureScoreMatchingKey(v252, v192, (wchar_t **)&v262[17]);
      if ( v105 < 0 )
        WUTrace(0, 0, 8, 3, v105, L"Failed to get feature score matching key");
      BYTE4(v262[8]) = 1;
      LOBYTE(v262[0]) = 0;
      goto LABEL_207;
    }
  }
  v88 = v191;
LABEL_402:
  if ( v197 > 0 )
  {
    v161 = v197;
    if ( v88 )
      v161 = 0;
    v162 = v224;
    if ( v88 )
      v162 = 0;
    refreshed = CAgentUpdateManager::PopulateDataStore(
                  *((_QWORD *)v196 + 3),
                  *((_QWORD *)v192 + 40),
                  v203,
                  (int)v233,
                  *(_QWORD *)v192,
                  (__int64)v192 + 8,
                  *((_DWORD *)v192 + 18),
                  0,
                  0,
                  (__int64)v162,
                  v161,
                  (unsigned __int64)v224 & -(__int64)(v88 != 0),
                  v197 & (unsigned int)-(v88 != 0),
                  0,
                  0,
                  (__int64)psz,
                  v214,
                  v245,
                  (__int64)v192 + 352,
                  *((_QWORD *)v192 + 79) + 8LL,
                  v225,
                  0,
                  0,
                  *((_QWORD *)v192 + 78));
    if ( refreshed < 0 )
    {
      WUTrace(0, 0, 8, 3, refreshed, L"PopulateDataStore to put cached drivers out of scope failed");
      goto LABEL_43;
    }
  }
  v163 = L"supported";
  if ( v191 )
    v163 = L"required";
  WUTrace(
    0,
    0,
    8,
    4,
    0,
    L"Skipping driver sync because it's not %ws.",
    v163,
    v170,
    v173,
    v175,
    v176,
    v177,
    *(_QWORD *)v178,
    v179,
    *(_QWORD *)v180,
    v181,
    v182,
    v183,
    v184,
    v185,
    v186,
    v187,
    v188,
    v189,
    &v279);
LABEL_412:
  v27 = 0;
LABEL_413:
  v30 = v190;
  if ( v190 > 0xC8 )
  {
LABEL_372:
    refreshed = -2145107952;
    WUTrace(0, 0, 8, 3, -2145107952, L"Exceeded max server round trips");
    goto LABEL_44;
  }
LABEL_18:
  v28 = a14;
LABEL_19:
  *v28 = v30;
  *v231 = v193;
  if ( v199 )
  {
    SusFree(lpMem);
    v27 = 0;
  }
  if ( v212 )
  {
    SusFree(v226);
    v27 = 0;
    v200 = 0;
  }
  if ( v211 )
    SusFree(v227);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_OutOfScopeExemptUpdates>::__private_IsEnabled(
                          `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_OutOfScopeExemptUpdates>::GetImpl'::`2'::impl,
                          v28,
                          v27,
                          v26)
    && v210 )
  {
    SusFree(v228);
  }
  if ( v209 )
  {
    SusFree(v224);
    v197 = 0;
  }
  if ( v213 )
    SusFree(v229);
  SysFreeString(*(BSTR *)&v262[17]);
  SysFreeString(*((BSTR *)&v262[14] + 1));
  SafeBstrArrayFree(SLODWORD(v262[15]), *((wchar_t ***)&v262[15] + 1));
  *(_OWORD *)((char *)&v262[14] + 8) = 0;
  *((_QWORD *)&v262[15] + 1) = 0;
  SusWsStructs::SusSyncInfo::Clear((SusWsStructs::SusSyncInfo *)v261);
  v34 = v257;
  if ( v257 )
  {
    if ( v264 )
      memset(v257, 0, 16LL * v264);
    SusFree(v34);
  }
  SafeSusStructArrayFree<SusWsStructs::SusUpdateDeploymentIdentifier>(v200, *((_QWORD *)&v262[2] + 1));
  SafeSusStructArrayFree<SusWsStructs::SusUpdateDeploymentIdentifier>((unsigned int)v197, *((_QWORD *)&v262[3] + 1));
  LODWORD(v169) = *a14;
  WUTrace(0, 0, 8, 4, 0, L"SyncUpdates round trips: %ld", v169);
  if ( refreshed < 0 )
  {
    if ( v195 )
    {
      WUTrace(0, 0, 8, 3, refreshed, L"Sync of Drivers failed (Software succeeded)");
      v35 = *((_QWORD *)v192 + 79) + 8LL;
      LODWORD(v231) = 2;
      HIDWORD(v231) = refreshed;
      if ( !*(_DWORD *)(v35 + 56) )
        *(_DWORD *)(v35 + 56) = refreshed;
      CSusSortedArrayList<tagSusWarning,CSusSortedArrayListItemOpsBasic<tagSusWarning>>::Add(v35, &v231);
      refreshed = 0;
    }
    else
    {
      WUTrace(0, 0, 8, 3, refreshed, L"Sync of Updates");
    }
  }
  CExternalCompressionProcessor::~CExternalCompressionProcessor((CExternalCompressionProcessor *)v295);
  CSusArrayList<wchar_t *,CSusArrayBSTRListItemOpDelete>::~CSusArrayList<wchar_t *,CSusArrayBSTRListItemOpDelete>(v271);
  CSusArrayList<wchar_t *,CSusArrayBSTRListItemOpDelete>::~CSusArrayList<wchar_t *,CSusArrayBSTRListItemOpDelete>(&v288);
  CSusArrayList<wchar_t *,CSusArrayBSTRListItemOpDelete>::~CSusArrayList<wchar_t *,CSusArrayBSTRListItemOpDelete>(v293);
  if ( v23 )
    (**(void (__fastcall ***)(struct CAppCatIdProvider *, __int64))v23)(v23, 1);
  if ( v22 )
    (*(void (__fastcall **)(_QWORD *, __int64))*v22)(v22, 1);
  if ( v21 )
    ((void (__fastcall *)(void (__fastcall ***)(_QWORD, __int64, _QWORD), __int64))**v21)(v21, 1);
  if ( v20 )
    (**(void (__fastcall ***)(_OWORD *, __int64))v20)(v20, 1);
  if ( v19 )
    (*(void (__fastcall **)(_QWORD *, __int64))*v19)(v19, 1);
  CSusArrayList<long,CSusSortedArrayListItemOpsBasic<long>>::~CSusArrayList<long,CSusSortedArrayListItemOpsBasic<long>>(v291);
  CSusArrayList<long,CSusSortedArrayListItemOpsBasic<long>>::~CSusArrayList<long,CSusSortedArrayListItemOpsBasic<long>>(&v279);
  CSusArrayList<long,CSusSortedArrayListItemOpsBasic<long>>::~CSusArrayList<long,CSusSortedArrayListItemOpsBasic<long>>(&v276);
  CSusArrayList<long,CSusSortedArrayListItemOpsBasic<long>>::~CSusArrayList<long,CSusSortedArrayListItemOpsBasic<long>>(&v282);
  CSusArrayList<long,CSusSortedArrayListItemOpsBasic<long>>::~CSusArrayList<long,CSusSortedArrayListItemOpsBasic<long>>(&v273);
  CSusArrayList<long,CSusSortedArrayListItemOpsBasic<long>>::~CSusArrayList<long,CSusSortedArrayListItemOpsBasic<long>>(&v285);
  return (unsigned int)refreshed;
}

```

## disassembly

```asm
0x18006a4a8  mov     rax, rsp
0x18006a4ab  push    rbp
0x18006a4ac  push    rbx
0x18006a4ad  push    rsi
0x18006a4ae  push    rdi
0x18006a4af  push    r12
0x18006a4b1  push    r13
0x18006a4b3  push    r14
0x18006a4b5  push    r15
0x18006a4b7  lea     rbp, [rax-9D8h]
0x18006a4be  sub     rsp, 0AE8h
0x18006a4c5  movaps  xmmword ptr [rax-58h], xmm6
0x18006a4c9  mov     rax, cs:__security_cookie
0x18006a4d0  xor     rax, rsp
0x18006a4d3  mov     [rbp+9D0h+var_60], rax
0x18006a4da  mov     [rbp+9D0h+var_988], r9
0x18006a4de  mov     rbx, r8
0x18006a4e1  mov     [rbp+9D0h+var_A38], rbx
0x18006a4e5  mov     [rbp+9D0h+var_9B0], rdx
0x18006a4e9  mov     [rbp+9D0h+var_A20], rcx
0x18006a4ed  mov     rax, [rbp+9D0h+arg_20]
0x18006a4f4  mov     [rbp+9D0h+var_938], rax
0x18006a4fb  mov     rdi, [rbp+9D0h+arg_30]
0x18006a502  mov     [rbp+9D0h+var_8B0], rdi
0x18006a509  mov     rax, [rbp+9D0h+arg_28]
0x18006a510  mov     [rbp+9D0h+var_918], rax
0x18006a517  mov     rax, [rbp+9D0h+arg_38]
0x18006a51e  mov     [rbp+9D0h+var_8B8], rax
0x18006a525  mov     rax, [rbp+9D0h+arg_40]
0x18006a52c  mov     [rbp+9D0h+psz], rax
0x18006a533  mov     rax, [rbp+9D0h+arg_48]
0x18006a53a  mov     [rbp+9D0h+var_9C8], rax
0x18006a53e  mov     rax, [rbp+9D0h+arg_58]
0x18006a545  mov     [rbp+9D0h+var_8C0], rax
0x18006a54c  mov     rax, [rbp+9D0h+arg_60]
0x18006a553  mov     [rbp+9D0h+var_8E8], rax
0x18006a55a  mov     rax, [rbp+9D0h+arg_68]
0x18006a561  mov     [rbp+9D0h+var_A48], rax
0x18006a565  mov     rax, [rbp+9D0h+arg_70]
0x18006a56c  mov     [rbp+9D0h+var_8D0], rax
0x18006a573  mov     rax, [rbp+9D0h+arg_78]
0x18006a57a  mov     [rbp+9D0h+var_8C8], rax
0x18006a581  mov     rax, [rbp+9D0h+arg_80]
0x18006a588  mov     [rbp+9D0h+var_958], rax
0x18006a58c  xor     edx, edx; Val
0x18006a58e  lea     r8d, [rdx+70h]; Size
0x18006a592  lea     rcx, [rbp+9D0h+var_850]; void *
0x18006a599  call    memset
0x18006a59e  xor     edx, edx; Val
0x18006a5a0  mov     r8d, 148h; Size
0x18006a5a6  lea     rcx, [rbp+9D0h+var_7E0]; void *
0x18006a5ad  call    memset
0x18006a5b2  mov     eax, 1
0x18006a5b7  xor     edx, edx
0x18006a5b9  test    rdi, rdi
0x18006a5bc  jz      short loc_18006A5C6
0x18006a5be  cmp     [rdi], rdx
0x18006a5c1  mov     [rbp+9D0h+var_960], eax
0x18006a5c4  jnz     short loc_18006A5C9
0x18006a5c6  mov     [rbp+9D0h+var_960], edx
0x18006a5c9  mov     [rbp+9D0h+var_A28], edx
0x18006a5cc  mov     [rbp+9D0h+var_9B4], edx
0x18006a5cf  mov     [rbp+9D0h+var_9E4], edx
0x18006a5d2  mov     [rbp+9D0h+var_9A0], edx
0x18006a5d5  mov     [rbp+9D0h+var_9F0], edx
0x18006a5d8  mov     [rbp+9D0h+var_9A8], edx
0x18006a5db  mov     [rbp+9D0h+var_690], edx
0x18006a5e1  mov     [rbp+9D0h+var_950], edx
0x18006a5e7  xorps   xmm0, xmm0
0x18006a5ea  movups  [rbp+9D0h+var_5A0], xmm0
0x18006a5f1  movups  [rbp+9D0h+var_590], xmm0
0x18006a5f8  mov     qword ptr [rbp+9D0h+var_5A0+8], rdx
0x18006a5ff  mov     qword ptr [rbp+9D0h+var_590], rdx
0x18006a606  lea     rax, ??_7?$CSusSortedArrayList@JV?$CSusSortedArrayListItemOpsBasic@J@@@@6B@; const CSusSortedArrayList<long,CSusSortedArrayListItemOpsBasic<long>>::`vftable'
0x18006a60d  mov     qword ptr [rbp+9D0h+var_5A0], rax
0x18006a614  mov     dword ptr [rbp+9D0h+var_590+8], edx
0x18006a61a  mov     [rbp+9D0h+lpMem], rdx
0x18006a61e  mov     [rbp+9D0h+var_A14], edx
0x18006a621  mov     [rbp+9D0h+var_A10], edx
0x18006a624  movups  [rbp+9D0h+var_620], xmm0
0x18006a62b  movups  [rbp+9D0h+var_610], xmm0
0x18006a632  mov     qword ptr [rbp+9D0h+var_620+8], rdx
0x18006a639  mov     qword ptr [rbp+9D0h+var_610], rdx
0x18006a640  mov     qword ptr [rbp+9D0h+var_620], rax
0x18006a647  mov     dword ptr [rbp+9D0h+var_610+8], edx
0x18006a64d  mov     [rbp+9D0h+var_980], rdx
0x18006a651  mov     [rbp+9D0h+var_A0C], edx
0x18006a654  mov     [rbp+9D0h+var_9D4], edx
0x18006a657  movups  [rbp+9D0h+var_5C0], xmm0
0x18006a65e  movups  [rbp+9D0h+var_5B0], xmm0
0x18006a665  mov     qword ptr [rbp+9D0h+var_5C0+8], rdx
0x18006a66c  mov     qword ptr [rbp+9D0h+var_5B0], rdx
0x18006a673  mov     qword ptr [rbp+9D0h+var_5C0], rax
0x18006a67a  mov     dword ptr [rbp+9D0h+var_5B0+8], edx
0x18006a680  mov     [rbp+9D0h+var_978], rdx
0x18006a684  mov     [rbp+9D0h+var_99C], edx
0x18006a687  mov     [rbp+9D0h+var_9D8], edx
0x18006a68a  movups  [rbp+9D0h+var_600], xmm0
0x18006a691  movups  [rbp+9D0h+var_5F0], xmm0
0x18006a698  mov     qword ptr [rbp+9D0h+var_600+8], rdx
0x18006a69f  mov     qword ptr [rbp+9D0h+var_5F0], rdx
0x18006a6a6  mov     qword ptr [rbp+9D0h+var_600], rax
0x18006a6ad  mov     dword ptr [rbp+9D0h+var_5F0+8], edx
0x18006a6b3  mov     [rbp+9D0h+var_990], rdx
0x18006a6b7  mov     [rbp+9D0h+var_A18], edx
0x18006a6ba  mov     [rbp+9D0h+var_9E0], edx
0x18006a6bd  movups  [rbp+9D0h+var_5E0], xmm0
0x18006a6c4  movups  [rbp+9D0h+var_5D0], xmm0
0x18006a6cb  mov     qword ptr [rbp+9D0h+var_5E0+8], rdx
0x18006a6d2  mov     qword ptr [rbp+9D0h+var_5D0], rdx
0x18006a6d9  mov     qword ptr [rbp+9D0h+var_5E0], rax
0x18006a6e0  mov     dword ptr [rbp+9D0h+var_5D0+8], edx
0x18006a6e6  mov     [rbp+9D0h+var_970], rdx
0x18006a6ea  mov     [rbp+9D0h+var_998], edx
0x18006a6ed  mov     [rbp+9D0h+var_9DC], edx
0x18006a6f0  movups  xmmword ptr [rbp+9D0h+var_568], xmm0
0x18006a6f7  movups  [rbp+9D0h+var_558], xmm0
0x18006a6fe  mov     [rbp+9D0h+var_568+8], rdx
0x18006a705  mov     qword ptr [rbp+9D0h+var_558], rdx
0x18006a70c  mov     [rbp+9D0h+var_568], rax
0x18006a713  mov     dword ptr [rbp+9D0h+var_558+8], edx
0x18006a719  mov     [rbp+9D0h+var_968], rdx
0x18006a71d  mov     [rbp+9D0h+var_9A4], edx
0x18006a720  mov     [rbp+9D0h+var_9D0], edx
0x18006a723  mov     [rbp+9D0h+var_9FC], edx
0x18006a726  mov     [rbp+9D0h+var_948], rdx
0x18006a72d  mov     r14, rdx
0x18006a730  mov     [rbp+9D0h+var_8D8], rdx
0x18006a737  mov     rdi, rdx
0x18006a73a  mov     [rbp+9D0h+var_8E0], rdx
0x18006a741  mov     r12, rdx
0x18006a744  mov     [rbp+9D0h+var_8F0], rdx
0x18006a74b  mov     [rbp+9D0h+var_878], rdx
0x18006a752  mov     [rbp+9D0h+var_68C], edx
0x18006a758  mov     [rbp+9D0h+var_870], rdx
0x18006a75f  mov     [rbp+9D0h+var_868], rdx
0x18006a766  mov     [rbp+9D0h+var_A50], edx
0x18006a769  mov     rsi, rdx
0x18006a76c  mov     [rbp+9D0h+var_8F8], rdx
0x18006a773  mov     [rbp+9D0h+var_910], rdx
0x18006a77a  mov     [rbp+9D0h+var_900], rdx
0x18006a781  mov     r15, rdx
0x18006a784  mov     [rbp+9D0h+var_940], rdx
0x18006a78b  movups  [rbp+9D0h+var_548], xmm0
0x18006a792  mov     qword ptr [rbp+9D0h+var_548+8], rdx
0x18006a799  mov     [rbp+9D0h+var_538], rdx
0x18006a7a0  lea     rcx, ??_7CBSTRList@@6B@; const CBSTRList::`vftable'
0x18006a7a7  mov     qword ptr [rbp+9D0h+var_548], rcx
0x18006a7ae  movups  [rbp+9D0h+var_580], xmm0
0x18006a7b5  mov     qword ptr [rbp+9D0h+var_580+8], rdx
0x18006a7bc  mov     [rbp+9D0h+var_570], rdx
0x18006a7c3  mov     qword ptr [rbp+9D0h+var_580], rcx
0x18006a7ca  movups  xmmword ptr [rbp+9D0h+var_638], xmm0
0x18006a7d1  lea     rax, ??_7CBSTRList@@6B@; const CBSTRList::`vftable'
0x18006a7d8  mov     [rbp+9D0h+var_638], rax
0x18006a7df  mov     [rbp+9D0h+var_638+8], rdx
0x18006a7e6  mov     [rbp+9D0h+var_628], rdx
0x18006a7ed  mov     [rbp+9D0h+var_640], edx
0x18006a7f3  mov     [rbp+9D0h+var_860], rdx
0x18006a7fa  mov     [rbp+9D0h+var_A30], dl
0x18006a7fd  test    rbx, rbx
0x18006a800  jz      loc_18006CE6B
0x18006a806  cmp     [rbx+270h], rdx
0x18006a80d  jz      loc_18006CE6B
0x18006a813  mov     r13, [rbx+60h]
0x18006a817  mov     [rbp+9D0h+var_A08], r13
0x18006a81b  xor     edx, edx; Val
0x18006a81d  mov     r8d, 108h; Size
0x18006a823  lea     rcx, [rbp+9D0h+var_410]; void *
0x18006a82a  call    memset
0x18006a82f  xor     eax, eax
0x18006a831  mov     [rbp+9D0h+var_410], rax
0x18006a838  mov     [rbp+9D0h+var_408], rax
0x18006a83f  mov     [rbp+9D0h+var_400], rax
0x18006a846  mov     rdx, [rbx+28h]; struct CCallerIdentity *
0x18006a84a  lea     rcx, [rbp+9D0h+var_3F8]; this
0x18006a851  call    ??0CDownloadSession@@QEAA@PEBVCCallerIdentity@@@Z; CDownloadSession::CDownloadSession(CCallerIdentity const *)
0x18006a856  nop
0x18006a857  lea     rdx, [rbp+9D0h+var_300]; char *
0x18006a85e  mov     rcx, rbx; this
0x18006a861  call    ?GetAndIncrementCorrelationVector@CAgentProtocolTalkerContext@@QEAAJPEAD@Z; CAgentProtocolTalkerContext::GetAndIncrementCorrelationVector(char *)
0x18006a866  xor     r8d, r8d
0x18006a869  test    eax, eax
0x18006a86b  jns     short loc_18006A874
0x18006a86d  mov     [rbp+9D0h+var_300], r8b
0x18006a874  mov     rdx, [rbp+9D0h+var_A48]
0x18006a878  cmp     [rbp+9D0h+var_9B0], r8
0x18006a87c  jnz     short loc_18006A889
0x18006a87e  mov     r13d, 80004003h
0x18006a884  mov     ebx, r8d
0x18006a887  jmp     short loc_18006A8EF
0x18006a889  test    rdx, rdx
0x18006a88c  jz      short loc_18006A87E
0x18006a88e  mov     rcx, [rbp+9D0h+var_8D0]
0x18006a895  test    rcx, rcx
0x18006a898  jz      short loc_18006A87E
0x18006a89a  mov     rax, [rbp+9D0h+var_8C8]
0x18006a8a1  test    rax, rax
0x18006a8a4  jz      short loc_18006A87E
0x18006a8a6  mov     r8, [rbp+9D0h+var_958]
0x18006a8aa  xor     r9d, r9d
0x18006a8ad  test    r8, r8
0x18006a8b0  jnz     short loc_18006A8BD
0x18006a8b2  mov     r13d, 80004003h
0x18006a8b8  mov     ebx, r9d
0x18006a8bb  jmp     short loc_18006A8EF
0x18006a8bd  mov     [rdx], r9d
0x18006a8c0  mov     [rcx], r9d
0x18006a8c3  mov     [rax], r9d
0x18006a8c6  mov     [r8], r9b
0x18006a8c9  mov     rcx, [rbx]
0x18006a8cc  mov     rax, [rcx]
0x18006a8cf  mov     rax, [rax]
0x18006a8d2  call    _guard_dispatch_icall
0x18006a8d7  xor     r8d, r8d
0x18006a8da  test    eax, eax
0x18006a8dc  jz      loc_18006AA9F
0x18006a8e2  mov     r13d, 8024000Bh
0x18006a8e8  mov     ebx, r8d
0x18006a8eb  mov     rdx, [rbp+9D0h+var_A48]
0x18006a8ef  mov     [rdx], ebx
0x18006a8f1  mov     rax, [rbp+9D0h+var_958]
0x18006a8f5  mov     cl, [rbp+9D0h+var_A30]
0x18006a8f8  mov     [rax], cl
0x18006a8fa  cmp     [rbp+9D0h+var_A10], r8d
0x18006a8fe  jz      short loc_18006A90C
0x18006a900  mov     rcx, [rbp+9D0h+lpMem]; lpMem
0x18006a904  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18006a909  xor     r8d, r8d
0x18006a90c  cmp     [rbp+9D0h+var_9D4], r8d
0x18006a910  jz      short loc_18006A922
0x18006a912  mov     rcx, [rbp+9D0h+var_980]; lpMem
0x18006a916  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18006a91b  xor     r8d, r8d
0x18006a91e  mov     [rbp+9D0h+var_A0C], r8d
0x18006a922  cmp     [rbp+9D0h+var_9D8], r8d
0x18006a926  jz      short loc_18006A931
0x18006a928  mov     rcx, [rbp+9D0h+var_978]; lpMem
0x18006a92c  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18006a931  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_OutOfScopeExemptUpdates@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_OutOfScopeExemptUpdates@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_OutOfScopeExemptUpdates> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_OutOfScopeExemptUpdates>::GetImpl(void)'::`2'::impl
0x18006a938  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_OutOfScopeExemptUpdates@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_OutOfScopeExemptUpdates>::__private_IsEnabled(void)
0x18006a93d  xor     ebx, ebx
0x18006a93f  test    al, al
0x18006a941  jz      short loc_18006A951
0x18006a943  cmp     [rbp+9D0h+var_9DC], ebx
0x18006a946  jz      short loc_18006A951
0x18006a948  mov     rcx, [rbp+9D0h+var_970]; lpMem
0x18006a94c  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18006a951  cmp     [rbp+9D0h+var_9E0], ebx
0x18006a954  jz      short loc_18006A962
0x18006a956  mov     rcx, [rbp+9D0h+var_990]; lpMem
0x18006a95a  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18006a95f  mov     [rbp+9D0h+var_A18], ebx
0x18006a962  cmp     [rbp+9D0h+var_9D0], ebx
0x18006a965  jz      short loc_18006A970
0x18006a967  mov     rcx, [rbp+9D0h+var_968]; lpMem
0x18006a96b  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18006a970  mov     rcx, [rbp+9D0h+bstrString]; bstrString
0x18006a977  call    cs:__imp_SysFreeString
0x18006a97d  mov     rcx, [rbp+9D0h+var_6F8]; bstrString
0x18006a984  call    cs:__imp_SysFreeString
0x18006a98a  movsxd  rcx, dword ptr [rbp+9D0h+var_6F8+8]; unsigned __int64
0x18006a991  mov     rdx, [rbp+9D0h+var_6E8]; wchar_t **
0x18006a998  call    ?SafeBstrArrayFree@@YAX_KPEAPEA_W@Z; SafeBstrArrayFree(unsigned __int64,wchar_t * *)
0x18006a99d  xorps   xmm0, xmm0
0x18006a9a0  xor     eax, eax
0x18006a9a2  movups  xmmword ptr [rbp+9D0h+var_6F8], xmm0
0x18006a9a9  mov     [rbp+9D0h+var_6E8], rax
0x18006a9b0  lea     rcx, [rbp+9D0h+var_850]; this
0x18006a9b7  call    ?Clear@SusSyncInfo@SusWsStructs@@QEAAXXZ; SusWsStructs::SusSyncInfo::Clear(void)
0x18006a9bc  mov     rbx, [rbp+9D0h+var_878]
0x18006a9c3  test    rbx, rbx
0x18006a9c6  jz      short loc_18006A9EB
0x18006a9c8  mov     eax, [rbp+9D0h+var_68C]
0x18006a9ce  test    eax, eax
0x18006a9d0  jz      short loc_18006A9E3
0x18006a9d2  mov     r8d, eax
0x18006a9d5  shl     r8, 4; Size
0x18006a9d9  xor     edx, edx; Val
0x18006a9db  mov     rcx, rbx; void *
0x18006a9de  call    memset
0x18006a9e3  mov     rcx, rbx; lpMem
0x18006a9e6  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18006a9eb  mov     rdx, [rbp+9D0h+var_7B8]
0x18006a9f2  mov     ecx, [rbp+9D0h+var_A0C]
0x18006a9f5  call    ??$SafeSusStructArrayFree@USusUpdateDeploymentIdentifier@SusWsStructs@@@@YAXIPEAUSusUpdateDeploymentIdentifier@SusWsStructs@@@Z; SafeSusStructArrayFree<SusWsStructs::SusUpdateDeploymentIdentifier>(uint,SusWsStructs::SusUpdateDeploymentIdentifier *)
0x18006a9fa  mov     rdx, [rbp+9D0h+var_7A8]
0x18006aa01  mov     ecx, [rbp+9D0h+var_A18]
0x18006aa04  call    ??$SafeSusStructArrayFree@USusUpdateDeploymentIdentifier@SusWsStructs@@@@YAXIPEAUSusUpdateDeploymentIdentifier@SusWsStructs@@@Z; SafeSusStructArrayFree<SusWsStructs::SusUpdateDeploymentIdentifier>(uint,SusWsStructs::SusUpdateDeploymentIdentifier *)
0x18006aa09  mov     rcx, [rbp+9D0h+var_A48]
0x18006aa0d  mov     eax, [rcx]
0x18006aa0f  mov     dword ptr [rsp+0B20h+var_AF0], eax
0x18006aa13  lea     rax, aSyncupdatesRou; "SyncUpdates round trips: %ld"
0x18006aa1a  mov     qword ptr [rsp+0B20h+cchCount2], rax
0x18006aa1f  xor     ebx, ebx
0x18006aa21  mov     [rsp+0B20h+lpString2], rbx
0x18006aa26  xor     edx, edx
0x18006aa28  xor     ecx, ecx
0x18006aa2a  lea     r9d, [rbx+4]
0x18006aa2e  lea     r8d, [rbx+8]
  ... truncated ...
```
