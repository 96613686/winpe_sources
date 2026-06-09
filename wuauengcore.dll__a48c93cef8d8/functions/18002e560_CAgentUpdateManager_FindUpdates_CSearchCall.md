# CAgentUpdateManager::FindUpdates(CSearchCall &)

- ea: `0x18002e560`
- end: `0x18003110c`
- name: `?FindUpdates@CAgentUpdateManager@@QEAAXAEAVCSearchCall@@@Z`
- size: `11180`
- prototype: `void __fastcall(CAgentUpdateManager *__hidden this, struct CSearchCall *)`
- caller_count: `2`
- callee_count: `95`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800c166c`
- `0x1800c19d0`

## callees

- `0x18000def4`
- `0x180014964`
- `0x180015710`
- `0x180015c04`
- `0x180015c98`
- `0x18001a06c`
- `0x18001a7f0`
- `0x18001dae0`
- `0x18001dffc`
- `0x180022b0c`
- `0x18002532c`
- `0x1800266bc`
- `0x180027bb4`
- `0x180028374`
- `0x1800295a8`
- `0x18002aedc`
- `0x18002b044`
- `0x18002d148`
- `0x18002e20c`
- `0x18002e560`
- `0x180031158`
- `0x1800322ec`
- `0x1800327bc`
- `0x180032ab0`
- `0x180033adc`
- `0x180034160`
- `0x1800344f0`
- `0x180034540`
- `0x180034c68`
- `0x180034d24`
- `0x180034eec`
- `0x180035460`
- `0x180035e44`
- `0x180036560`
- `0x180037ae0`
- `0x18003a304`
- `0x18003b104`
- `0x18003b668`
- `0x18003b9c4`
- `0x18005c9a4`
- `0x180061c70`
- `0x180062124`
- `0x180064320`
- `0x180067efc`
- `0x180068360`
- `0x180073b88`
- `0x18007413c`
- `0x1800758dc`
- `0x1800759b8`
- `0x1800b6640`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002ff2b`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18003028b`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002ff2b`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18003028b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002eed5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030bb3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002eed5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030bb3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002efc4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030cc9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002efc4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030cc9`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002e843`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002e843`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002e824`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002e857`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002e824`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002e857`

## string_xrefs

- `0x18002e745`: `* START * Finding updates CallerId = %ws  Id = %d (cV = %hs)`
- `0x18002e935`: `CheckAccessByPolicy`
- `0x18002ea06`: `Service doesn't support product specific search.`
- `0x18002eab5`: `Service doesn't support category specific search for the given categories.`
- `0x18002eb5c`: `Cached search result is available; will perform offline scan instead.`
- `0x18002ef7c`: `Generating system driver spec for offline scan because cache was empty`
- `0x180030627`: `failed to Detect updates after driver processing`
- `0x180030f90`: `* END * Finding updates CallerId = %ws, Id = %d, Exit code = 0x%08lX (cV = %hs)`
- `0x180030f22`: `Some appCategoryId LastOnlineScanTime cache is not refreshed`
- `0x18002f038`: `C:\__w\1\s\src\Client\Engine\Agent\driverutilbase.cpp`
- `0x18002f08e`: `C:\__w\1\s\src\Client\Engine\Agent\driverutilbase.cpp`
- `0x180030116`: `update manager failed to record start of sync updates call to performance log`
- `0x18003023e`: `update manager failed to record end of sync updates call to performance log`
- `0x18002f3e5`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\Test`
- `0x180030d6d`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\Test`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
void __fastcall CAgentUpdateManager::FindUpdates(CAgentUpdateManager *this, struct CSearchCall *a2)
{
  struct CSearchCall *v2; // r12
  CAgentUpdateManager *v3; // r15
  struct CAgentProtocolTalker *v4; // r14
  struct CExpressionManager *v5; // rsi
  const struct _GUID *v6; // rbx
  char *v7; // rdi
  __int64 v8; // rbx
  int v9; // eax
  int RegionString; // r13d
  void *v11; // rdx
  PSID v12; // rbx
  bool v13; // r14
  CSusService *v14; // rbx
  int v15; // eax
  int IsOfflineSync; // eax
  int v17; // ecx
  const struct _GUID *v18; // rdx
  const struct _GUID *v19; // rax
  const struct _GUID *v20; // rdi
  struct CExpressionManager *v21; // rax
  _DWORD *v22; // r8
  bool v23; // r13
  unsigned __int64 v24; // r9
  unsigned __int64 v25; // rcx
  __int64 v26; // rdx
  _DWORD *v27; // rax
  __int64 v28; // rdx
  int v29; // edi
  __int64 v30; // rax
  __int64 v31; // r15
  char v32; // r14
  struct _RTL_CRITICAL_SECTION *v33; // rbx
  int v34; // eax
  unsigned __int64 v35; // rbx
  __int64 v36; // r14
  int v37; // eax
  HANDLE OwningThread; // rcx
  int v39; // eax
  int v40; // ebx
  void **v41; // rbx
  char *v42; // r14
  char *v43; // r15
  _DWORD *v44; // rbx
  CSusService *v45; // rdi
  unsigned int v46; // eax
  char *v47; // rcx
  void *v48; // r13
  int v49; // eax
  unsigned int v50; // eax
  int v51; // ebx
  int v52; // eax
  __int64 v53; // rcx
  __int64 v54; // rax
  unsigned int v55; // ecx
  unsigned __int64 v56; // rdx
  unsigned int v57; // r9d
  struct CAgentProtocolTalker *v58; // rdx
  unsigned int v59; // r10d
  __int64 v60; // r13
  int v61; // edi
  __int64 v62; // r8
  __int64 v63; // r9
  __int64 v64; // r13
  unsigned int v65; // ebx
  __int64 v66; // rsi
  __int64 v67; // r8
  __int64 v68; // rax
  unsigned int v69; // eax
  unsigned int v70; // ebx
  char *v71; // rcx
  _DWORD *v72; // rax
  __int64 v73; // r9
  char *v74; // rdx
  _OWORD *v75; // r8
  char *v76; // r9
  __int64 v77; // r10
  unsigned int v78; // r11d
  __int64 v79; // rcx
  __int64 v80; // rax
  __int64 v81; // rax
  unsigned int v82; // r10d
  unsigned int v83; // r9d
  unsigned int v84; // eax
  __int64 v85; // r8
  _QWORD *v86; // rdx
  _QWORD *v87; // rcx
  struct CAgentProtocolTalker *v88; // rdx
  int v89; // edx
  __int64 v90; // rax
  char *v91; // r8
  __int64 v92; // rdx
  _DWORD *v93; // r13
  struct _GUID *v94; // rax
  __int64 v95; // r8
  _DWORD *v96; // rcx
  signed __int64 v97; // rdx
  struct _GUID *v98; // rsi
  unsigned int v99; // r12d
  unsigned int v100; // r15d
  struct _GUID *v101; // rbx
  unsigned int v102; // r14d
  __int64 v103; // rcx
  __int64 v104; // rax
  int v105; // eax
  int v106; // eax
  unsigned int v107; // r13d
  BOOL v108; // edx
  __int64 v109; // rcx
  __int64 v110; // rcx
  int DesiredLangList; // eax
  int v112; // eax
  void ***v113; // r10
  int v114; // eax
  CAgentUpdateManager *v115; // rcx
  struct CUpdateDetectInfoList *v116; // r13
  struct CUpdateDetectInfoList *v117; // r9
  CAgentUpdateManager *v118; // r13
  int v119; // eax
  __int64 v120; // rdx
  unsigned __int64 v121; // r8
  unsigned __int64 v122; // r9
  _DWORD *v123; // rcx
  int v124; // eax
  int v125; // r13d
  unsigned int v126; // edx
  const unsigned __int8 *v127; // r8
  int fixed; // eax
  unsigned int v129; // ebx
  struct CUpdateDetectInfoList *v130; // r8
  int refreshed; // eax
  const struct CSusAsyncCall *v132; // rdx
  int v133; // ecx
  __int64 v134; // r8
  __int64 v135; // rcx
  char *v136; // r14
  unsigned int v137; // edi
  unsigned int v138; // r15d
  char v139; // r12
  unsigned int v140; // ebx
  int v141; // eax
  bool v142; // zf
  int v143; // r14d
  unsigned int v144; // ebx
  __int64 v145; // rcx
  int v146; // ebx
  __int64 v147; // rdx
  __int64 v148; // r8
  wchar_t **v149; // r9
  const wchar_t *RegKeyPath; // rax
  int v151; // eax
  CWUEtwConsumer *v152; // rcx
  int v153; // eax
  int v154; // [rsp+20h] [rbp-130h]
  int v155; // [rsp+20h] [rbp-130h]
  int v156; // [rsp+20h] [rbp-130h]
  int v157; // [rsp+20h] [rbp-130h]
  const wchar_t *v158; // [rsp+28h] [rbp-128h]
  wchar_t *v159; // [rsp+30h] [rbp-120h]
  __int64 *v160; // [rsp+38h] [rbp-118h]
  struct CCallerIdentity *v161; // [rsp+38h] [rbp-118h]
  char *v162; // [rsp+40h] [rbp-110h]
  char *v163; // [rsp+40h] [rbp-110h]
  int v164; // [rsp+48h] [rbp-108h]
  int v165; // [rsp+58h] [rbp-F8h]
  bool v166; // [rsp+D0h] [rbp-80h]
  int v167; // [rsp+D8h] [rbp-78h]
  int v168; // [rsp+D8h] [rbp-78h]
  struct _GUID *v169; // [rsp+D8h] [rbp-78h]
  int v170; // [rsp+E0h] [rbp-70h]
  bool v171; // [rsp+E4h] [rbp-6Ch] BYREF
  unsigned __int64 v172; // [rsp+E8h] [rbp-68h] BYREF
  CAgentUpdateManager *v173; // [rsp+F0h] [rbp-60h]
  unsigned int v174; // [rsp+F8h] [rbp-58h]
  CExpressionManager *v175; // [rsp+100h] [rbp-50h]
  unsigned int v176; // [rsp+108h] [rbp-48h]
  int v177; // [rsp+10Ch] [rbp-44h]
  PSID pSid; // [rsp+110h] [rbp-40h] BYREF
  int v179; // [rsp+118h] [rbp-38h]
  int v180; // [rsp+11Ch] [rbp-34h]
  struct CExpressionManager *v181; // [rsp+120h] [rbp-30h]
  void *v182; // [rsp+128h] [rbp-28h]
  unsigned int v183; // [rsp+130h] [rbp-20h]
  _DWORD *v184; // [rsp+138h] [rbp-18h] BYREF
  int v185; // [rsp+140h] [rbp-10h]
  wchar_t *v186; // [rsp+148h] [rbp-8h] BYREF
  CSusService *v187; // [rsp+150h] [rbp+0h] BYREF
  unsigned int v188; // [rsp+158h] [rbp+8h]
  int v189; // [rsp+15Ch] [rbp+Ch]
  int v190; // [rsp+160h] [rbp+10h]
  _DWORD *v191; // [rsp+168h] [rbp+18h]
  void *v192[2]; // [rsp+170h] [rbp+20h] BYREF
  char *v193; // [rsp+180h] [rbp+30h]
  _DWORD v194[2]; // [rsp+188h] [rbp+38h] BYREF
  PSID v195; // [rsp+190h] [rbp+40h]
  CSusService *v196; // [rsp+198h] [rbp+48h]
  __int64 v197; // [rsp+1A0h] [rbp+50h]
  struct CExpressionManager *v198; // [rsp+1A8h] [rbp+58h]
  struct _GUID v199; // [rsp+1B0h] [rbp+60h] BYREF
  _DWORD v200[71]; // [rsp+1C0h] [rbp+70h] BYREF
  _BYTE v201[80]; // [rsp+2E0h] [rbp+190h] BYREF
  void *lpMem; // [rsp+330h] [rbp+1E0h] BYREF
  struct CSearchCall *v203; // [rsp+338h] [rbp+1E8h] BYREF
  char v204[4]; // [rsp+340h] [rbp+1F0h] BYREF
  int v205; // [rsp+344h] [rbp+1F4h] BYREF
  int v206; // [rsp+348h] [rbp+1F8h] BYREF
  unsigned int v207; // [rsp+34Ch] [rbp+1FCh] BYREF
  __int64 v208; // [rsp+350h] [rbp+200h] BYREF
  _BYTE v209[24]; // [rsp+358h] [rbp+208h] BYREF
  void *v210; // [rsp+370h] [rbp+220h]
  unsigned int v211; // [rsp+378h] [rbp+228h] BYREF
  unsigned int v212; // [rsp+37Ch] [rbp+22Ch] BYREF
  int v213; // [rsp+380h] [rbp+230h] BYREF
  _BYTE v214[24]; // [rsp+388h] [rbp+238h] BYREF
  void *v215; // [rsp+3A0h] [rbp+250h]
  int v216; // [rsp+3A8h] [rbp+258h] BYREF
  __int64 v217[2]; // [rsp+3B0h] [rbp+260h] BYREF
  __int64 v218; // [rsp+3C0h] [rbp+270h]
  _QWORD v219[3]; // [rsp+3C8h] [rbp+278h] BYREF
  __int64 v220[2]; // [rsp+3E0h] [rbp+290h] BYREF
  __int64 v221; // [rsp+3F0h] [rbp+2A0h]
  void **v222; // [rsp+3F8h] [rbp+2A8h] BYREF
  __int64 v223; // [rsp+400h] [rbp+2B0h]
  __int128 v224; // [rsp+408h] [rbp+2B8h]
  _QWORD v225[2]; // [rsp+418h] [rbp+2C8h] BYREF
  __int128 v226; // [rsp+428h] [rbp+2D8h]
  _QWORD v227[3]; // [rsp+438h] [rbp+2E8h] BYREF
  _QWORD v228[80]; // [rsp+450h] [rbp+300h] BYREF
  __int64 v229[20]; // [rsp+6D0h] [rbp+580h] BYREF
  char v230[144]; // [rsp+770h] [rbp+620h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+848h] [rbp+6F8h]

  v2 = a2;
  v203 = a2;
  v3 = this;
  v173 = this;
  v179 = 0;
  v189 = 1;
  v188 = 0;
  `eh vector constructor iterator'(
    v229,
    0x20u,
    5u,
    CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>>::CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>>,
    CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>>::~CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>>);
  v4 = (struct CSearchCall *)((char *)v2 + 760);
  v227[0] = &CSearchCancelObject::`vftable';
  v227[1] = (char *)v2 + 760;
  v225[1] = 0;
  v226 = 0u;
  v225[0] = &CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>>::`vftable';
  v223 = 0;
  v224 = 0u;
  v222 = &CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>>::`vftable';
  v190 = 0;
  v180 = 0;
  v206 = 0;
  v185 = 0;
  v183 = 0;
  v212 = 0;
  v211 = 0;
  v216 = 0;
  v197 = *((_QWORD *)v3 + 280);
  v166 = 0;
  v207 = 0;
  memset(v228, 0, sizeof(v228));
  CAgentProtocolTalkerContext::CAgentProtocolTalkerContext(
    (CAgentProtocolTalkerContext *)v228,
    (struct CSearchCall *)((char *)v2 + 1072),
    &v207);
  lpMem = 0;
  v5 = 0;
  v181 = 0;
  v198 = 0;
  v213 = 0;
  v187 = 0;
  v204[0] = 0;
  v186 = 0;
  v6 = (const struct _GUID *)((char *)v2 + 272);
  if ( CSearchCall::GetAndIncrementCorrelationVector(v2, v230) < 0 )
    v230[0] = 0;
  WUTrace(
    0,
    0,
    1,
    4,
    0,
    L"* START * Finding updates CallerId = %ws  Id = %d (cV = %hs)",
    *(_QWORD *)(*((_QWORD *)v2 + 17) + 136LL),
    *((_DWORD *)v2 + 33),
    v230);
  v7 = (char *)v2 + 952;
  if ( (*(__int64 (__fastcall **)(__int64))(*((_QWORD *)v2 + 119) + 72LL))((__int64)v2 + 952) )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 72LL))((__int64)v2 + 952);
    WUTrace(0, 0, 1, 4, 0, L"IntentPFNs = %ws (cV = %hs)");
  }
  CSearchCall::TraceProperties(v2);
  if ( (*((_BYTE *)v2 + 1248) & 2) != 0 )
  {
    v8 = *((_QWORD *)v2 + 17);
    pSid = 0;
    v9 = SusAllocLocalSystemSid(&pSid);
    RegionString = v9;
    v167 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x318,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\lib\\susenginelib\\calleridentity.cpp",
        (const char *)(unsigned int)v9,
        v154);
      if ( pSid )
        FreeSid(pSid);
      goto LABEL_363;
    }
    v11 = *(void **)(v8 + 120);
    if ( !v11 )
      v11 = *(void **)(v8 + 88);
    v12 = pSid;
    v13 = EqualSid(pSid, v11);
    if ( v12 )
      FreeSid(v12);
    if ( v13 )
    {
      RegionString = -2145124283;
      v167 = -2145124283;
      v158 = L"Blocking current user search for localsystem. Failing scan.";
      v155 = 0;
LABEL_15:
      WUTrace(0, 0, 1, 1, v155, v158);
      goto LABEL_363;
    }
    v6 = (const struct _GUID *)((char *)v2 + 272);
    v4 = (struct CSearchCall *)((char *)v2 + 760);
  }
  RegionString = GetRegionString(&v186);
  v167 = RegionString;
  if ( RegionString < 0 )
    goto LABEL_363;
  if ( (unsigned int)IsSystemSetupBlockingWU() )
  {
    RegionString = -2145124278;
    v167 = -2145124278;
    WUTrace(0, 0, 1, 5, 0, L" OS setup in progress. Failing scan");
    goto LABEL_363;
  }
  RegionString = CAgentServiceManager::GetServiceObjectHelper(v6, &v187);
  v167 = RegionString;
  if ( RegionString >= 0 )
  {
    RegionString = CSearchCall::ParseFilter(v2);
    v167 = RegionString;
    if ( RegionString >= 0 )
    {
      v14 = v187;
      RegionString = CSusService::CheckAccessByPolicy(v187);
      v167 = RegionString;
      if ( RegionString < 0 )
      {
        v158 = L"CheckAccessByPolicy";
        v155 = RegionString;
        goto LABEL_15;
      }
      if ( (*(unsigned __int8 (__fastcall **)(CSusService *))(*(_QWORD *)v14 + 24LL))(v14) )
      {
        v15 = (*(__int64 (__fastcall **)(CSusService *, int *))(*(_QWORD *)v14 + 56LL))(v14, &v213);
        if ( v15 < 0 )
        {
          v213 = 1;
          WUTrace(0, 0, 1, 4, v15, L"GetIsInventoryRequired");
        }
      }
      if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v7 + 32LL))((__int64)v2 + 952) )
      {
        LODWORD(v172) = 0;
        IsOfflineSync = CSusService::GetIsOfflineSync(v14, (int *)&v172);
        v17 = v172;
        if ( IsOfflineSync < 0 )
          v17 = 0;
        if ( !v17
          && !(*(unsigned __int8 (__fastcall **)(CSusService *))(*(_QWORD *)v14 + 24LL))(v14)
          && !(*(unsigned __int8 (__fastcall **)(CSusService *))(*(_QWORD *)v14 + 80LL))(v14) )
        {
          WUTrace(0, 0, 1, 4, 0, L"Service doesn't support product specific search.");
LABEL_34:
          RegionString = 2359312;
LABEL_35:
          v167 = RegionString;
          goto LABEL_363;
        }
      }
      if ( !(**(unsigned __int8 (__fastcall ***)(__int64))v7)((__int64)v2 + 952) )
      {
        v19 = (const struct _GUID *)(*(__int64 (__fastcall **)(CSusService *))(*(_QWORD *)v14 + 8LL))(v14);
        if ( IsServiceInLoadSheddingSession(v19) )
        {
          RegionString = -2145107922;
          goto LABEL_35;
        }
      }
      if ( (*((_DWORD *)v2 + 312) & 0x400000) != 0 )
      {
        v171 = 1;
        RegionString = CSearchCall::IsLegacyCatScanRequired(v2, v14, &v171);
        v167 = RegionString;
        if ( RegionString < 0 )
          goto LABEL_363;
        if ( !v171 )
        {
          *((_DWORD *)v2 + 312) |= 0x4000000u;
          WUTrace(0, 0, 1, 4, 0, L"Service doesn't support category specific search for the given categories.");
          goto LABEL_34;
        }
      }
      if ( (*((_DWORD *)v2 + 312) & 0x8000) != 0 )
      {
        RegionString = CSearchCall::GetAllAppCategoryIDs(v2, &v222);
        v167 = RegionString;
        if ( RegionString < 0 )
        {
          WUTrace(0, 0, 1, 3, RegionString, L"Failed to get appCategoryIds for AppCatScan");
          CSusArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>>::RemoveArraySection(&v222, 0, 0xFFFFFFFFLL);
          goto LABEL_363;
        }
        v20 = (const struct _GUID *)((char *)v2 + 272);
        if ( (*((_DWORD *)v2 + 312) & 0x10000010) == 0x10000010
          && (unsigned __int8)CAgentUpdateManager::IsCachedSearchResultsAvailable(v3, (char *)v2 + 272, &v222) )
        {
          WUTrace(0, 0, 1, 4, 0, L"Cached search result is available; will perform offline scan instead.");
          *((_DWORD *)v2 + 312) &= ~0x10u;
        }
      }
      else
      {
        v20 = (const struct _GUID *)((char *)v2 + 272);
      }
      CUpdateDeferralPolicyChecker::RefreshDeferralPolicy(
        (struct CSearchCall *)((char *)v2 + 336),
        v18,
        *((_DWORD *)v2 + 312));
      if ( *((_DWORD *)v4 + 18)
        || (RegionString = CAgentProtocolTalker::Init(
                             v4,
                             v3,
                             *((struct ISusDatastore **)v3 + 281),
                             (struct CSusSettingCache *)(*((_QWORD *)v3 + 280) + 112LL),
                             (struct CReporter *)(*((_QWORD *)v3 + 280) + 2408LL),
                             (struct CSusEventSystem *)(*((_QWORD *)v3 + 280) + 216LL),
                             (struct ISusIdleTimer *)(*((_QWORD *)v3 + 280) + 9992LL)),
            v167 = RegionString,
            RegionString >= 0) )
      {
        v21 = (struct CExpressionManager *)operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
        v5 = v21;
        v181 = v21;
        *(_QWORD *)&v199.Data1 = v21;
        if ( !v21 )
        {
          v5 = 0;
          v181 = 0;
          v198 = 0;
          RegionString = -2147024882;
          goto LABEL_35;
        }
        *(_QWORD *)v21 = &CExpressionManager::`vftable';
        *((_DWORD *)v21 + 2) = 0;
        *((_QWORD *)v21 + 2) = &CSusArrayList<CExpressionHandlerPlugin *,CSusArrayListItemOpDelete<CExpressionHandlerPlugin *>>::`vftable';
        *((_QWORD *)v21 + 3) = 0;
        *((_QWORD *)v21 + 4) = 0;
        *((_QWORD *)v21 + 5) = 0;
        v198 = v21;
        RegionString = CExpressionManager::Init(v21);
        v167 = RegionString;
        if ( RegionString < 0 )
          goto LABEL_363;
        RegionString = CAgentProtocolTalkerContext::Initialize(
                         (CAgentProtocolTalkerContext *)v228,
                         v5,
                         v4,
                         v2,
                         v20,
                         *((struct ISusDatastore **)v3 + 281),
                         (struct CSusSettingCache *)(*((_QWORD *)v3 + 280) + 112LL),
                         *((const struct CCallerIdentity **)v2 + 17),
                         v230,
                         *((_DWORD *)v2 + 312),
                         (struct CSearchCall *)((char *)v2 + 944));
        v167 = RegionString;
        if ( RegionString < 0 )
          goto LABEL_363;
        if ( (**(unsigned int (__fastcall ***)(struct CSearchCall *))v2)(v2) )
        {
          LODWORD(v159) = *((_DWORD *)v2 + 22);
          WUTrace(0, 0, 1, 3, 0, L"Search call was cancelled with context %d (cV = %hs)", v159, v230);
          RegionString = -2145124341;
          goto LABEL_35;
        }
        RegionString = CAgentProtocolTalker::InitializeForSearch(v4, v20, &v206);
        v167 = RegionString;
        if ( RegionString < 0 )
        {
          v180 = v206;
          goto LABEL_363;
        }
        v190 = 1;
        v23 = 0;
        v183 = 0;
        v24 = 0;
        v25 = *((_QWORD *)v2 + 121);
        v175 = v5;
        if ( v25 )
        {
          v22 = (_DWORD *)*((_QWORD *)v2 + 122);
          v175 = v5;
          while ( *v22 != 3 && *v22 != 4 )
          {
            ++v24;
            v22 += 52;
            if ( v24 >= v25 )
              goto LABEL_63;
          }
          v28 = 1;
          v183 = 1;
        }
        else
        {
LABEL_63:
          v26 = 0;
          if ( (*((_DWORD *)v2 + 312) & 0x8000) == 0 )
            goto LABEL_71;
          v22 = 0;
          if ( !v25 )
            goto LABEL_71;
          v27 = (_DWORD *)(*((_QWORD *)v2 + 122) + 180LL);
          do
          {
            v26 = (unsigned int)(*v27 + v26);
            if ( (unsigned int)v26 > 1 )
              goto LABEL_71;
            v22 = (_DWORD *)((char *)v22 + 1);
            v27 += 52;
          }
          while ( (unsigned __int64)v22 < v25 );
          if ( (_DWORD)v26 != 1 )
          {
LABEL_71:
            v180 = v206;
            if ( !v206 )
            {
              v29 = 0;
              v166 = 1;
              v30 = *((_QWORD *)v2 + 122);
              if ( *(_DWORD *)v30 == 4
                && *(_DWORD *)(v30 + 84) == 1
                && *(_DWORD *)(v30 + 120) == 4
                && (v31 = *(_QWORD *)(v30 + 8)) != 0 )
              {
                v32 = 1;
              }
              else
              {
                v32 = 0;
                v31 = 0;
              }
              if ( (*(unsigned __int8 (__fastcall **)(__int64, __int64, _DWORD *, unsigned __int64))(*((_QWORD *)v2 + 119) + 40LL))(
                     (__int64)v2 + 952,
                     v26,
                     v22,
                     v24)
                || (*(unsigned __int8 (__fastcall **)(__int64))(*((_QWORD *)v2 + 119) + 32LL))((__int64)v2 + 952) )
              {
                v166 = 0;
                goto LABEL_114;
              }
              v206 = 0;
              if ( (int)CSusService::GetPerformDriverSync(v14, &v206) >= 0 )
              {
                v23 = v206 != 0;
                v166 = v206 != 0;
                if ( !v206 )
                  goto LABEL_114;
              }
              v33 = (struct _RTL_CRITICAL_SECTION *)v173;
              pSid = (char *)v173 + 3680;
              EnterCriticalSection((LPCRITICAL_SECTION)v173 + 92);
              v34 = *((_DWORD *)v2 + 312);
              if ( (v34 & 0x10) != 0 )
              {
                if ( v32 || (v34 & 0x80000) != 0 )
                {
                  v29 = 1;
                  v189 = 0;
                }
                if ( (v34 & 0x200) == 0 )
                  v29 = 1;
                if ( (int)CThreadSafeMapEnumerator<_GUID,tagSystemSpec *,CSusSortedArrayListItemOpsBasic<_GUID>,CAgentUpdateManager::CSusArrayListItemOpSystemSpec>::get_Value(
                            &pSid,
                            (char *)v2 + 272,
                            &lpMem) < 0 )
                  v29 = 1;
              }
              else if ( (int)CThreadSafeMapEnumerator<_GUID,tagSystemSpec *,CSusSortedArrayListItemOpsBasic<_GUID>,CAgentUpdateManager::CSusArrayListItemOpSystemSpec>::get_Value(
                               &pSid,
                               (char *)v2 + 272,
                               &lpMem) < 0 )
              {
                v35 = 0;
                v36 = 0;
                do
                {
                  if ( v35 >= *((_QWORD *)v2 + 121) )
                    break;
                  if ( *(_DWORD *)(v36 + *((_QWORD *)v2 + 122)) != 1 )
                  {
                    WUTrace(0, 0, 1, 5, 0, L"Generating system driver spec for offline scan because cache was empty");
                    v29 = 1;
                  }
                  ++v35;
                  v36 += 208;
                }
                while ( !v29 );
                v5 = v181;
                v33 = (struct _RTL_CRITICAL_SECTION *)v173;
              }
              LeaveCriticalSection((LPCRITICAL_SECTION)pSid);
              if ( !v29 )
              {
                v23 = v166;
                goto LABEL_114;
              }
              WUTrace(0, 0, 1, 5, 0, L"Generating new system driver spec ...");
              CSusThreadSafeMap<_GUID,tagSystemSpec *,CSusSortedArrayListItemOpsBasic<_GUID>,CAgentUpdateManager::CSusArrayListItemOpSystemSpec>::Remove(v33 + 92);
              v206 = 0;
              v37 = *((_DWORD *)v2 + 312) & 0x80000;
              lpMem = 0;
              OwningThread = v33[3].OwningThread;
              if ( !OwningThread )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x75,
                  (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\driverutilbase.cpp",
                  (const char *)0x8000000ELL,
                  v156);
                v179 = -2147483634;
LABEL_103:
                WUTrace(0, 0, 1, 3, 0, L"driver util unavailable - assuming system doesn't support driver sync.");
                v23 = 0;
                v166 = 0;
LABEL_114:
                v3 = v173;
                goto LABEL_115;
              }
              v39 = (*(__int64 (__fastcall **)(HANDLE, __int64, bool, int *))(*(_QWORD *)OwningThread + 24LL))(
                      OwningThread,
                      v31,
                      v37 != 0,
                      &v206);
              v40 = v39;
              v179 = v39;
              if ( v39 >= 0 )
              {
                if ( v206 != -1 )
                  *((_DWORD *)v2 + 358) = v206;
                v3 = v173;
                v179 = CSusThreadSafeMap<_GUID,tagSystemSpec *,CSusSortedArrayListItemOpsBasic<_GUID>,CAgentUpdateManager::CSusArrayListItemOpSystemSpec>::Add((LPCRITICAL_SECTION)v173 + 92);
                if ( v179 < 0 )
                {
                  v41 = (void **)lpMem;
                  if ( lpMem )
                  {
                    SafeSusStructArrayFree<SusWsStructs::SusDevice>(*((unsigned int *)lpMem + 4), *(_QWORD *)lpMem);
                    SusFree(v41[1]);
                    SusFree(v41[4]);
                    SusFree(v41);
                  }
                  lpMem = 0;
                }
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x76,
                  (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\driverutilbase.cpp",
                  (const char *)(unsigned int)v39,
                  (int)&lpMem);
                v175 = v5;
                if ( v40 == -2147483634 )
                  goto LABEL_103;
                WUTrace(0, 0, 1, 3, v40, L"driver util object failed to GetSystemSpec");
                v179 = v40;
                v3 = v173;
              }
              v175 = v5;
              v23 = v166;
            }
LABEL_115:
            CAgentUpdateManager::RefreshRebootPendingUpdateGuids(v3, (const struct _GUID *)v2 + 17);
            while ( 1 )
            {
              v217[0] = (__int64)&CSusArrayList<_GUID,CSusArrayListItemOpNoop<_GUID>>::`vftable';
              v217[1] = 0;
              v218 = 0;
              v220[0] = (__int64)&CSusArrayList<_GUID,CSusArrayListItemOpNoop<_GUID>>::`vftable';
              v220[1] = 0;
              v221 = 0;
              v174 = 0;
              v42 = 0;
              pSid = 0;
              v195 = 0;
              LODWORD(v172) = 0;
              v43 = 0;
              v193 = 0;
              *(_QWORD *)&v199.Data1 = 0;
              v44 = 0;
              v191 = 0;
              v184 = 0;
              v45 = 0;
              v196 = 0;
              v187 = 0;
              v205 = 0;
              v206 = 0;
              *(_QWORD *)&v214[8] = 0;
              *(_QWORD *)&v214[16] = 0;
              *(_QWORD *)v214 = &CBSTRList::`vftable';
              v46 = 3591;
              v176 = 3591;
              if ( v23 )
              {
                if ( lpMem )
                  v46 = 3623;
                v176 = v46;
              }
              LODWORD(v228[9]) = v46;
              v219[0] = &CSusArrayList<enum SusWsStructs::SusXmlUpdateFragmentType,CSusArrayListItemOpNoop<enum SusWsStructs::SusXmlUpdateFragmentType>>::`vftable';
              v219[1] = 0;
              v219[2] = 0;
              CSusArrayList<CSusMap<tagDSGlobalUpdateId,CUpdateDetectInfo,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>,CUpdateDetectInfo>::_tagMapEntry,CSusMap<tagDSGlobalUpdateId,CUpdateDetectInfo,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>,CUpdateDetectInfo>::CMapEntryOps>::RemoveArraySection(
                (char *)v2 + 1176,
                0,
                0xFFFFFFFFLL,
                1);
              v47 = (char *)v2 + 1072;
              *((_DWORD *)v2 + 268) = 0;
              if ( *((_DWORD *)v2 + 275) )
                *((_DWORD *)v2 + 275) = 0;
              if ( *((_DWORD *)v2 + 283) )
                *((_DWORD *)v2 + 283) = 0;
              *((_QWORD *)v2 + 142) = 0;
              *((_QWORD *)v2 + 143) = 0;
              *((_DWORD *)v2 + 288) = 0;
              *((_DWORD *)v2 + 290) = 0;
              v48 = (void *)*((_QWORD *)v2 + 146);
              if ( v48 )
              {
                CExternalCompressionCabDownloadInfo::~CExternalCompressionCabDownloadInfo(*((CExternalCompressionCabDownloadInfo **)v2
                                                                                          + 146));
                operator delete(v48, (const struct std::nothrow_t *)0x18);
                v47 = (char *)v2 + 1072;
              }
              *((_QWORD *)v47 + 12) = 0;
              CSearchCallbackInfo::Reset((struct CSearchCall *)((char *)v2 + 984), 0);
              if ( v166 && !lpMem && (*((_BYTE *)v2 + 1248) & 0x10) != 0 )
              {
                v49 = -2145075194;
                if ( v179 < 0 )
                  v49 = v179;
                v194[0] = 2;
                v194[1] = v49;
                if ( !*((_DWORD *)v2 + 284) )
                  *((_DWORD *)v2 + 284) = v49;
                CSusSortedArrayList<tagSusWarning,CSusSortedArrayListItemOpsBasic<tagSusWarning>>::Add(
                  (char *)v2 + 1080,
                  v194);
              }
              v207 = 0;
              v170 = 0;
              v50 = v188++;
              if ( v50 >= 4 )
              {
                RegionString = -2145124295;
                v167 = -2145124295;
                CSusArrayList<enum SusWsStructs::SusXmlUpdateFragmentType,CSusArrayListItemOpNoop<enum SusWsStructs::SusXmlUpdateFragmentType>>::~CSusArrayList<enum SusWsStructs::SusXmlUpdateFragmentType,CSusArrayListItemOpNoop<enum SusWsStructs::SusXmlUpdateFragmentType>>(v219);
                CSusArrayList<wchar_t *,CSusArrayBSTRListItemOpDelete>::~CSusArrayList<wchar_t *,CSusArrayBSTRListItemOpDelete>(v214);
                WuSmartPtr::XPtrBase<CatScanContext,WuSmartPtr::Policies::STPolicy<CatScanContext>>::InternalRelease(&v184);
                goto LABEL_361;
              }
              if ( (**(unsigned int (__fastcall ***)(struct CSearchCall *))v2)(v2) )
                goto LABEL_136;
              v177 = 0;
              v52 = *((_DWORD *)v2 + 312);
              if ( (v52 & 0x1000) != 0
                && ((v52 & 0x10) == 0 || !v185)
                && (!(unsigned int)AreTestKeysAllowed(1)
                 || (unsigned int)RegQueryDwordValueWithDefaultAndRangeCheck(
                                    v53,
                                    L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Test",
                                    L"DisableCatScan",
                                    0,
                                    0,
                                    -1) != 1) )
              {
                v177 = 1;
                v42 = (char *)SafeSusAllocArray(*((_QWORD *)v2 + 121), 0x10u);
                pSid = v42;
                v195 = v42;
                if ( !v42 )
                {
                  RegionString = -2147024882;
LABEL_137:
                  v167 = RegionString;
                  goto LABEL_138;
                }
                v174 = *((_DWORD *)v2 + 242);
                LODWORD(v208) = v174;
                v54 = 0;
                v55 = 0;
                v56 = *((_QWORD *)v2 + 121);
                v57 = v172;
                if ( v56 )
                {
                  do
                  {
                    v57 += *(_DWORD *)(208 * v54 + *((_QWORD *)v2 + 122) + 156);
                    v54 = ++v55;
                  }
                  while ( v55 < v56 );
                  v5 = v181;
                }
                v43 = (char *)SafeSusAllocArray(v57, 0x14u);
                v193 = v43;
                *(_QWORD *)&v199.Data1 = v43;
                if ( !v43 )
                {
                  RegionString = -2147024882;
                  v167 = -2147024882;
                  v51 = 0;
                  goto LABEL_335;
                }
                v59 = 0;
                v168 = 0;
                if ( *((_QWORD *)v2 + 121) )
                {
                  v60 = 0;
                  v61 = 0;
                  do
                  {
                    v62 = 208 * v60;
                    v63 = *((_QWORD *)v2 + 122);
                    v58 = (struct CAgentProtocolTalker *)*(unsigned int *)(208 * v60 + v63 + 156);
                    if ( (_DWORD)v58 )
                    {
                      v64 = 2 * v60;
                      *(_DWORD *)&v42[8 * v64 + 8] = (_DWORD)v58;
                      *(_QWORD *)&v42[8 * v64] = &v43[20 * v61];
                      v65 = 0;
                      v66 = v62 + v63;
                      do
                      {
                        CSusArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>>::get_Item(
                          v66 + 136,
                          v65,
                          &v43[20 * v61]);
                        *(_DWORD *)(v67 + 16) = -1;
                        ++v61;
                        v68 = Trace::GuidToString::GuidToString(
                                (Trace::GuidToString *)v201,
                                (const struct _GUID *)(*(_QWORD *)&v42[8 * v64] + 20LL * v65));
                        LODWORD(v160) = v168;
                        WUTrace(0, 0, 1, 5, 0, L"Category %ws is in filter list, group %d", v68, v160);
                        ++v65;
                      }
                      while ( v65 < *(_DWORD *)&v42[8 * v64 + 8] );
                      v2 = v203;
                      v59 = v168;
                    }
                    v168 = ++v59;
                    v60 = v59;
                  }
                  while ( (unsigned __int64)v59 < *((_QWORD *)v2 + 121) );
                  v44 = v191;
                  v45 = v196;
                  v5 = v181;
                }
                if ( (*((_BYTE *)v2 + 1248) & 0x10) != 0 )
                {
                  CAgentProtocolTalkerContext::SetScanContextAndLoadInitialCookie(
                    (CAgentProtocolTalkerContext *)v228,
                    v58,
                    0);
                  RegionString = CAgentProtocolTalker::StartCategoryScan(
                                   (struct CSearchCall *)((char *)v2 + 760),
                                   (struct CAgentProtocolTalkerContext *)v228,
                                   (__int64)v42,
                                   (__int64)v217,
                                   (__int64)v220,
                                   (__int64)v2 + 1072);
                  v167 = RegionString;
                  v228[8] = 0;
                  SusWsStructs::SusCookie::Clear((SusWsStructs::SusCookie *)&v228[15]);
                  if ( RegionString == -2145123274 )
                  {
                    v51 = 1;
                    WUTrace(0, 0, 1, 5, 0, L"Server does not support CatScan. Falling back to full catalog sync...");
                    v185 = 1;
                    goto LABEL_335;
                  }
                  if ( RegionString == -2145107947 )
                  {
                    v51 = 1;
                    goto LABEL_335;
                  }
                  if ( RegionString < 0 )
                  {
                    WUTrace(0, 0, 1, 5, RegionString, L"fail to get server instructions on catscan");
                    goto LABEL_138;
                  }
                  v69 = HIDWORD(v218);
                  v174 = HIDWORD(v218);
                  if ( HIDWORD(v218) && (unsigned int)v208 >= HIDWORD(v218) )
                  {
                    *(_QWORD *)v209 = &CSusArrayList<unsigned int,CSusArrayListItemOpNoop<unsigned int>>::`vftable';
                    *(_QWORD *)&v209[8] = 0;
                    *(_QWORD *)&v209[16] = 0;
                    v70 = 0;
                    v71 = 0;
                    v182 = 0;
                    while ( 1 )
                    {
                      LODWORD(v172) = 0;
                      if ( v70 >= v69 )
                      {
                        RegionString = -2145124345;
                        goto LABEL_178;
                      }
                      *(_OWORD *)v192 = *(_OWORD *)&v71[v217[1]];
                      RegionString = CSusMap<_GUID,int,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpNoop<int>>::get_Value(
                                       *((_QWORD *)v2 + 120),
                                       v192,
                                       &v172);
                      v167 = RegionString;
                      if ( RegionString == -2145124345 )
                      {
                        RegionString = -2145120257;
                        v167 = -2145120257;
LABEL_359:
                        CSusArrayList<long,CSusSortedArrayListItemOpsBasic<long>>::~CSusArrayList<long,CSusSortedArrayListItemOpsBasic<long>>(v209);
                        CSusArrayList<enum SusWsStructs::SusXmlUpdateFragmentType,CSusArrayListItemOpNoop<enum SusWsStructs::SusXmlUpdateFragmentType>>::~CSusArrayList<enum SusWsStructs::SusXmlUpdateFragmentType,CSusArrayListItemOpNoop<enum SusWsStructs::SusXmlUpdateFragmentType>>(v219);
                        CSusArrayList<wchar_t *,CSusArrayBSTRListItemOpDelete>::~CSusArrayList<wchar_t *,CSusArrayBSTRListItemOpDelete>(v214);
                        WuSmartPtr::XPtrBase<CatScanContext,WuSmartPtr::Policies::STPolicy<CatScanContext>>::InternalRelease(&v184);
                        SusFree(v43);
                        goto LABEL_360;
                      }
                      if ( RegionString < 0 )
                        goto LABEL_179;
                      if ( (_DWORD)v172 )
                      {
                        v205 = 1;
                        ++v206;
                      }
                      RegionString = CSusArrayList<int,CSusSortedArrayListItemOpsBasic<int>>::Add(v209, &v172, 0);
                      v167 = RegionString;
                      if ( RegionString < 0 )
                        goto LABEL_359;
                      ++v70;
                      v71 = (char *)v182 + 16;
                      v182 = (char *)v182 + 16;
                      if ( v70 >= v174 )
                        break;
                      v69 = HIDWORD(v218);
                    }
                    v72 = operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
                    v44 = v72;
                    v191 = v72;
                    v182 = v72;
                    if ( v72 )
                    {
                      *v72 = 0;
                      *((_QWORD *)v72 + 1) = 0;
                      *((_QWORD *)v72 + 2) = 0;
                      *((_QWORD *)v72 + 3) = 0;
                      *((_BYTE *)v72 + 32) = 1;
                      *(_OWORD *)(v72 + 9) = 0;
                    }
                    else
                    {
                      v44 = 0;
                      v191 = 0;
                    }
                    WuSmartPtr::XPtrBase<CatScanContext,WuSmartPtr::Policies::STPolicy<CatScanContext>>::InternalRelease(&v184);
                    v184 = v44;
                    if ( !v44 )
                    {
                      RegionString = -2147024882;
LABEL_178:
                      v167 = RegionString;
LABEL_179:
                      CSusArrayList<long,CSusSortedArrayListItemOpsBasic<long>>::~CSusArrayList<long,CSusSortedArrayListItemOpsBasic<long>>(v209);
                      goto LABEL_138;
                    }
                    v73 = *((_DWORD *)v2 + 312) >> 7;
                    LOBYTE(v73) = (*((_DWORD *)v2 + 312) & 0x80) == 0;
                    RegionString = CatScanContext::Init(v44, v217, v209, v73);
                    v167 = RegionString;
                    if ( RegionString < 0 )
                      goto LABEL_179;
                    if ( v174 )
                    {
                      v74 = v42;
                      v75 = v43;
                      v76 = v43;
                      v77 = v174;
                      do
                      {
                        *v75 = *(_OWORD *)(v74 - v42 + *((_QWORD *)v44 + 1));
                        *((_DWORD *)v74 + 2) = 1;
                        *(_QWORD *)v74 = v76;
                        v76 += 20;
                        v75 = (_OWORD *)((char *)v75 + 20);
                        v74 += 16;
                        --v77;
                      }
                      while ( v77 );
                      v5 = v181;
                    }
                    CSusArrayList<long,CSusSortedArrayListItemOpsBasic<long>>::~CSusArrayList<long,CSusSortedArrayListItemOpsBasic<long>>(v209);
                  }
                  else
                  {
                    v177 = 0;
                    SusFree(v42);
                    v42 = 0;
                    pSid = 0;
                    v195 = 0;
                    v174 = 0;
                  }
                  LODWORD(v172) = HIDWORD(v221);
                  if ( HIDWORD(v221) )
                  {
                    v208 = 0;
                    v182 = (void *)v220[1];
                    RegionString = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)v173 + 281) + 24LL))(
                                     *((_QWORD *)v173 + 281),
                                     &v208);
                    v167 = RegionString;
                    if ( RegionString >= 0 )
                    {
                      RegionString = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, void *))(*(_QWORD *)v208
                                                                                                 + 416LL))(
                                       v208,
                                       (__int64)v2 + 272,
                                       (unsigned int)v172,
                                       v182);
                      v167 = RegionString;
                      if ( RegionString >= 0 )
                      {
                        v207 |= 1u;
                        v78 = 0;
                        if ( *((_QWORD *)v2 + 121) )
                        {
                          v79 = *((_QWORD *)v2 + 122);
                          v80 = 0;
                          do
                          {
                            v81 = 208 * v80;
                            v82 = *(_DWORD *)(v81 + v79 + 156);
                            v192[0] = *(void **)(v81 + v79 + 144);
                            v83 = 0;
                            v84 = v172;
                            while ( 1 )
                            {
                              v85 = 0;
                              if ( v82 )
                                break;
LABEL_210:
                              if ( ++v83 >= v84 )
                              {
                                if ( v208 )
                                  (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v208 + 16LL))(
                                    v208,
                                    0,
                                    v85);
                                goto LABEL_218;
                              }
                            }
                            v86 = (char *)v182 + 16 * v83;
                            while ( 1 )
                            {
                              v87 = (char *)v192[0] + 16 * (unsigned int)v85;
                              if ( *v86 == *v87 && v86[1] == v87[1] )
                                break;
                              v85 = (unsigned int)(v85 + 1);
                              if ( (unsigned int)v85 >= v82 )
                              {
                                v84 = v172;
                                goto LABEL_210;
                              }
                            }
                            v80 = ++v78;
                            v79 = *((_QWORD *)v2 + 122);
                          }
                          while ( (unsigned __int64)v78 < *((_QWORD *)v2 + 121) );
                        }
                        if ( v208 )
                          (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v208 + 16LL))(v208, 0);
                      }
                      else if ( v208 )
                      {
                        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v208 + 16LL))(v208, 0);
                      }
                    }
                    else if ( v208 )
                    {
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v208 + 16LL))(v208);
                    }
                    goto LABEL_138;
                  }
                }
              }
LABEL_218:
              LODWORD(v162) = 0;
              RegionString = CAgentUpdateManager::PrepareUpdateListForDetection(
                               v173,
                               0,
                               0,
                               0,
                               (unsigned int (__fastcall ***)(_QWORD))v2,
                               (struct _GUID *)v2 + 17,
                               v176,
                               (__int64)v2 + 1176,
                               (__int64)v162,
                               v44,
                               v174,
                               (__int64)v42,
                               0);
              v167 = RegionString;
              if ( RegionString < 0 )
              {
                v51 = 0;
                goto LABEL_335;
              }
              if ( (*((_DWORD *)v2 + 312) & 0x8000) != 0 )
              {
                v169 = 0;
                *(_QWORD *)&v209[8] = 0;
                *(_QWORD *)&v209[16] = 0;
                v89 = 0;
                *(_QWORD *)v209 = &CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>>::`vftable';
                v210 = 0;
                v90 = 0;
                LODWORD(v172) = 0;
                v91 = (char *)v2 + 1176;
                if ( *((_DWORD *)v2 + 299) )
                {
                  do
                  {
                    v92 = *((_QWORD *)v91 + 1) + 1048 * v90;
                    if ( (*(_DWORD *)(v92 + 272) & 0x120) == 0x120 && *(_DWORD *)(v92 + 168) == 16 )
                    {
                      RegionString = CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>>::Add(
                                       v209,
                                       v92,
                                       0);
                      v167 = RegionString;
                      if ( RegionString < 0 )
                        goto LABEL_249;
                      v91 = (char *)v2 + 1176;
                    }
                    v90 = (unsigned int)(v172 + 1);
                    LODWORD(v172) = v90;
                  }
                  while ( (unsigned int)v90 < *((_DWORD *)v91 + 5) );
                  v169 = *(struct _GUID **)&v209[8];
                  v89 = *(_DWORD *)&v209[20];
                }
                if ( v89 )
                {
                  LODWORD(v172) = v89 + v174;
                  v93 = SafeSusAllocArray(v89 + v174, 0x10u);
                  v182 = v93;
                  v94 = (struct _GUID *)SafeSusAllocArray(*(unsigned int *)&v209[20], 0x14u);
                  v192[0] = v94;
                  if ( !v94 || !v93 )
                  {
                    RegionString = -2147024882;
                    v167 = -2147024882;
                    if ( v94 )
                      SusFree(v94);
                    if ( v182 )
                      SusFree(v182);
LABEL_249:
                    CSusArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>>::~CSusArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>>(v209);
LABEL_138:
                    v51 = v170;
                    goto LABEL_335;
                  }
                  v95 = v174;
                  if ( v174 )
                  {
                    v96 = v93 + 2;
                    v97 = v42 - (char *)v93;
                    do
                    {
                      *v96 = *(_DWORD *)((char *)v96 + v97);
                      *((_QWORD *)v96 - 1) = *(_QWORD *)((char *)v96 + v97 - 8);
                      v96 += 4;
                      --v95;
                    }
                    while ( v95 );
                    v94 = (struct _GUID *)v192[0];
                  }
                  if ( *(_DWORD *)&v209[20] )
                  {
                    v98 = v94;
                    v99 = *(_DWORD *)&v209[20];
                    v100 = 0;
                    v101 = v169;
                    v102 = v174;
                    do
                    {
                      *v98 = *v101;
                      v98[1].Data1 = -1;
                      v103 = 2LL * (v100 + v102);
                      v93[2 * v103 + 2] = 1;
                      *(_QWORD *)&v93[2 * v103] = v98;
                      v104 = Trace::GuidToString::GuidToString((Trace::GuidToString *)v201, v98);
                      WUTrace(0, 0, 1, 5, 0, L"Adding Framework category %ws to filter list.", v104);
                      ++v100;
                      ++v101;
                      v98 = (struct _GUID *)((char *)v98 + 20);
                    }
                    while ( v100 < v99 );
                    v44 = v191;
                    v45 = v196;
                    v5 = v181;
                    v42 = (char *)pSid;
                    v43 = v193;
                    v2 = v203;
                  }
                  LODWORD(v162) = 0;
                  RegionString = CAgentUpdateManager::PrepareUpdateListForDetection(
                                   v173,
                                   0,
                                   0,
                                   0,
                                   (unsigned int (__fastcall ***)(_QWORD))v2,
                                   (struct _GUID *)v2 + 17,
                                   v176,
                                   (__int64)v2 + 1176,
                                   (__int64)v162,
                                   v44,
                                   v172,
                                   (__int64)v93,
                                   0);
                  v167 = RegionString;
                  SusFree(v192[0]);
                  SusFree(v182);
                  if ( RegionString < 0 )
                    goto LABEL_249;
                }
                CSusArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>>::~CSusArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>>(v209);
              }
              if ( (*((_BYTE *)v2 + 1248) & 0x10) == 0 )
              {
                v105 = CAgentUpdateManager::AssembleDependentSetBundleIfNeeded(
                         v173,
                         v175,
                         v176,
                         (struct CSearchCall *)((char *)v2 + 1176),
                         v2,
                         (const struct _GUID *)v2 + 17,
                         v186,
                         &v207,
                         0);
                if ( v105 < 0 )
                  WUTrace(0, 0, 1, 5, v105, L"AssembleDependentSetBundleIfNeeded (continuing...)");
              }
              v106 = v177;
              *((_DWORD *)v2 + 317) = v177;
              if ( v106 && v44 )
                *((_DWORD *)v2 + 318) = *v44;
              *((_DWORD *)v2 + 319) = *((_DWORD *)v2 + 299) == 0;
              CAgentProtocolTalkerContext::SetScanContextAndLoadInitialCookie(
                (CAgentProtocolTalkerContext *)v228,
                v88,
                (struct CatScanContext *)v44);
              v107 = v205;
              v108 = !v205 || v206 != 1;
              CExpressionManager::ResetForSearch(v175, v108);
              if ( (*((_BYTE *)v2 + 1248) & 0x10) != 0 && **((_DWORD **)v2 + 122) != 3 )
              {
                memset(v200, 0, sizeof(v200));
                (*(void (__fastcall **)(struct CSearchCall *, _QWORD *))(*(_QWORD *)v2 + 8LL))(v2, v227);
                if ( (**(unsigned int (__fastcall ***)(struct CSearchCall *))v2)(v2) )
                {
                  (*(void (__fastcall **)(struct CSearchCall *, _QWORD))(*(_QWORD *)v2 + 8LL))(v2, 0);
                  if ( *((_DWORD *)v2 + 208) )
                  {
                    _InterlockedExchange(&CClientService_Nws::m_fClientServiceDisabled, 0);
                    ResetEvent(*((HANDLE *)v2 + 111));
                  }
LABEL_136:
                  RegionString = -2145124341;
                  goto LABEL_137;
                }
                v109 = *((_QWORD *)v2 + 176);
                if ( v109 )
                {
                  v200[1] = *(_DWORD *)(v109 + 4);
                  v200[2] = *(_DWORD *)(v109 + 8);
                  v200[3] = *(_DWORD *)(v109 + 12);
                  v200[4] = *(_DWORD *)(v109 + 16);
                  v200[69] = *(_DWORD *)(v109 + 276);
                  LOWORD(v200[70]) = *(_WORD *)(v109 + 280);
                  BYTE2(v200[70]) = *(_BYTE *)(v109 + 282);
                }
                *((_DWORD *)v2 + 268) = 0;
                if ( v107 )
                {
                  if ( v44 )
                  {
                    if ( *((_QWORD *)v2 + 121) == 1 )
                    {
                      v110 = *((_QWORD *)v2 + 122);
                      if ( *(_DWORD *)(v110 + 156) == 1 && *(_DWORD *)(v110 + 204) == 1 )
                        CSusArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>>::get_Item(v110 + 184, 0, v44 + 9);
                    }
                  }
                }
                v45 = (CSusService *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
                if ( v45 )
                {
                  *(_QWORD *)v45 = 0;
                  *((_QWORD *)v45 + 1) = 0;
                  *((_QWORD *)v45 + 2) = 0;
                  v187 = v45;
                  LODWORD(v208) = *((_DWORD *)v2 + 316);
                  DesiredLangList = CreateDesiredLangList(
                                      (unsigned __int64)&v208 & -(__int64)(*((_DWORD *)v2 + 315) != 0),
                                      v107,
                                      v214);
                  if ( DesiredLangList < 0 )
                  {
                    WUTrace(0, 0, 1, 5, DesiredLangList, L"fail to get language list for round trip reduction");
                    operator delete(v45, (const struct std::nothrow_t *)0x18);
                    v45 = 0;
                    v187 = 0;
                  }
                  else
                  {
                    *((_QWORD *)v45 + 1) = v214;
                    *((_QWORD *)v45 + 2) = v219;
                    v205 = 2;
                    CSusArrayList<enum SusWsStructs::SusXmlUpdateFragmentType,CSusArrayListItemOpNoop<enum SusWsStructs::SusXmlUpdateFragmentType>>::Add(
                      v219,
                      &v205,
                      0);
                    v205 = 4;
                    CSusArrayList<enum SusWsStructs::SusXmlUpdateFragmentType,CSusArrayListItemOpNoop<enum SusWsStructs::SusXmlUpdateFragmentType>>::Add(
                      v219,
                      &v205,
                      0);
                    v205 = 5;
                    CSusArrayList<enum SusWsStructs::SusXmlUpdateFragmentType,CSusArrayListItemOpNoop<enum SusWsStructs::SusXmlUpdateFragmentType>>::Add(
                      v219,
                      &v205,
                      0);
                    *(_DWORD *)v45 = 1;
                  }
                }
                else
                {
                  v45 = 0;
                  v187 = 0;
                }
                v112 = CSearchCall::LogPerformanceEvent(v2, 508);
                if ( v112 < 0 )
                  WUTrace(
                    0,
                    0,
                    1,
                    5,
                    v112,
                    L"update manager failed to record start of sync updates call to performance log");
                v113 = 0;
                if ( !v177 )
                {
                  v113 = &v222;
                  if ( (*((_DWORD *)v2 + 312) & 0x8000) == 0 )
                    v113 = 0;
                }
                RegionString = CAgentProtocolTalker::SyncServerUpdates(
                                 (struct CSearchCall *)((char *)v2 + 760),
                                 (__int64)v45,
                                 (__int64)v113,
                                 (struct _WU_OSVERSIONINFO *)((unsigned __int64)v200
                                                            & -(__int64)(*((_QWORD *)v2 + 176) != 0)),
                                 (__int64)lpMem,
                                 (__int64)v2 + 336,
                                 (__int64)v186,
                                 (__int64)v2 + 1176,
                                 v165,
                                 (__int64)v229,
                                 (__int64)v225,
                                 (__int64)&v212,
                                 (__int64)&v211,
                                 (__int64)&v216,
                                 (__int64)v2 + 1072,
                                 (__int64)v204);
                v167 = RegionString;
                v114 = CSearchCall::LogPerformanceEvent(v2, 509);
                if ( v114 < 0 )
                  WUTrace(
                    0,
                    0,
                    1,
                    5,
                    v114,
                    L"update manager failed to record end of sync updates call to performance log");
                (*(void (__fastcall **)(struct CSearchCall *, _QWORD))(*(_QWORD *)v2 + 8LL))(v2, 0);
                if ( *((_DWORD *)v2 + 208) )
                {
                  _InterlockedExchange(&CClientService_Nws::m_fClientServiceDisabled, 0);
                  ResetEvent(*((HANDLE *)v2 + 111));
                }
                if ( RegionString < 0 )
                {
                  if ( RegionString == -2145107947 )
                  {
                    v185 = 0;
                    v51 = 1;
                  }
                  else
                  {
                    v51 = RegionString == -2145107931;
                  }
                  WUTrace(0, 0, 1, 3, RegionString, L"Synchronize");
                  goto LABEL_335;
                }
              }
              if ( (**(unsigned int (__fastcall ***)(struct CSearchCall *))v2)(v2) )
                goto LABEL_136;
              v116 = (struct CSearchCall *)((char *)v2 + 1176);
              CAgentUpdateManager::MakeupDeploymentForBundledUpdates(v115, (struct CSearchCall *)((char *)v2 + 1176));
              if ( v166 && !v180 )
              {
                RegionString = CAgentUpdateManager::ProcessDriverBehavior(
                                 v173,
                                 (char *)v2 + 760,
                                 v228,
                                 v2,
                                 lpMem,
                                 v186,
                                 (char *)v2 + 1176,
                                 5,
                                 v229,
                                 v225,
                                 (char *)v2 + 1072,
                                 v44);
                v167 = RegionString;
                if ( RegionString < 0 )
                {
                  WUTrace(0, 0, 1, 5, RegionString, L"failed to process driver behavior");
                  goto LABEL_138;
                }
                v116 = (struct CSearchCall *)((char *)v2 + 1176);
              }
              v205 = 0;
              v117 = v116;
              v118 = v173;
              v119 = CAgentUpdateManager::AssembleDependentSetBundleIfNeeded(
                       v173,
                       v175,
                       v176,
                       v117,
                       v2,
                       (const struct _GUID *)v2 + 17,
                       v186,
                       &v207,
                       &v205);
              if ( v119 >= 0 )
              {
                if ( v205 )
                {
                  WUTrace(0, 0, 1, 5, 0, L"Dependent set bundle changed; forcing resync");
                  v170 = 1;
                }
              }
              else
              {
                WUTrace(0, 0, 1, 5, v119, L"AssembleDependentSetBundleIfNeeded (continuing...)");
              }
              if ( (**(unsigned int (__fastcall ***)(struct CSearchCall *))v2)(v2) )
                goto LABEL_136;
              v121 = 0;
              v122 = *((_QWORD *)v2 + 121);
              if ( v122 )
              {
                v123 = (_DWORD *)(*((_QWORD *)v2 + 122) + 120LL);
                do
                {
                  v120 = (unsigned int)(*(v123 - 9) - 1);
                  if ( *(v123 - 9) == 1 )
                  {
                    if ( *v123 != 4 )
                      goto LABEL_307;
                  }
                  else if ( *(v123 - 9) != 2 || *v123 == 4 )
                  {
                    goto LABEL_307;
                  }
                  ++v121;
                  v123 += 52;
                }
                while ( v121 < v122 );
              }
              if ( (unsigned int)(**((_DWORD **)v2 + 122) - 2) > 2 )
              {
LABEL_307:
                v124 = *((_DWORD *)v2 + 312);
                v125 = v124 | 0x200000;
                if ( v177 && (v124 & 0x10) != 0 )
                  v125 = *((_DWORD *)v2 + 312) | 0x202000;
                (*(void (__fastcall **)(__int64, __int64, unsigned __int64))(*((_QWORD *)v2 + 119) + 72LL))(
                  (__int64)v2 + 952,
                  v120,
                  v121);
                v164 = v125;
                v162 = (char *)v2 + 1072;
                v160 = v229;
                RegionString = CAgentUpdateManager::DetectForUpdates(
                                 v173,
                                 0,
                                 v175,
                                 v2,
                                 (char *)v2 + 336,
                                 (char *)v2 + 1176);
                v167 = RegionString;
                if ( RegionString < 0 )
                {
                  WUTrace(0, 0, 1, 5, RegionString, L"failed to Detect updates after driver processing");
                  goto LABEL_138;
                }
                v118 = v173;
                if ( v44 )
                {
                  if ( (*((_BYTE *)v2 + 1248) & 0x10) != 0 )
                  {
                    fixed = CAgentUpdateManager::FixUpAndPersistScanContextAfterOnlineScan(
                              v173,
                              v126,
                              v127,
                              (const struct _GUID *)v2 + 17,
                              (struct CSearchCall *)((char *)v2 + 1176),
                              (struct CatScanContext *)v44);
                    if ( fixed < 0 )
                      WUTrace(0, 0, 1, 3, fixed, L"fail to persist scan contexts");
                  }
                }
              }
              v129 = 0;
              v130 = (struct CSearchCall *)((char *)v2 + 1176);
              if ( *((_DWORD *)v2 + 299) )
              {
                do
                  CUpdateDetectInfo::FilterUpdateForGenericMatch((GUID *)(*((_QWORD *)v2 + 148) + 1048LL * v129++));
                while ( v129 < *((_DWORD *)v2 + 299) );
                v5 = v181;
                v42 = (char *)pSid;
                v130 = (struct CSearchCall *)((char *)v2 + 1176);
              }
              if ( (*((_BYTE *)v2 + 1248) & 0x10) == 0 )
                break;
              v205 = 0;
              LODWORD(v208) = *((_DWORD *)v2 + 316);
              RegionString = CAgentUpdateManager::GetMissingExtendedInfo(
                               v118,
                               (struct CSearchCall *)((char *)v2 + 952),
                               (struct CSearchCall *)((char *)v2 + 760),
                               (struct CAgentProtocolTalkerContext *)v228,
                               v2,
                               v45,
                               (const struct _GUID *)v2 + 17,
                               v180,
                               (const unsigned int *)((unsigned __int64)&v208 & -(__int64)(*((_DWORD *)v2 + 315) != 0)),
                               v176,
                               v130,
                               &v205);
              v167 = RegionString;
              if ( v205 )
                v207 |= 1u;
              v51 = v205 | v170;
              if ( RegionString < 0 )
              {
                WUTrace(0, 0, 1, 5, RegionString, L"Failed to get missing extended info");
                goto LABEL_335;
              }
              if ( !v51 )
                goto LABEL_327;
LABEL_335:
              refreshed = CAgentUpdateManager::RefreshIDPExtendedAndLocalizedInfo(
                            v173,
                            v175,
                            0,
                            0,
                            v2,
                            (const struct _GUID *)v2 + 17,
                            (struct CSearchCall *)((char *)v2 + 1176));
              if ( refreshed < 0 )
                WUTrace(0, 0, 1, 5, refreshed, L"Failed to refresh IDP extended/localized info");
              if ( v207 )
                CAgentUpdateManager::HandleServerOrUpdateChange(v173, v132, (const struct _GUID *)v2 + 17, v207);
              if ( v51 )
              {
                WUTrace(0, 0, 1, 4, 0, L"Server changed and need resyncing with server");
                if ( RegionString < 0 )
                {
                  CSearchCall::ReportRetry(v2, RegionString, v212, v211, (struct CSearchCall *)((char *)v2 + 1176));
                  memset(v209, 0, 20);
                  v210 = 0;
                  if ( CAgentProtocolTalkerContext::GetMetadataIntegrityDataForScanEvent(
                         (CAgentProtocolTalkerContext *)v228,
                         (struct MetadataIntegrity::MetadataIntegrityDataForScanEvent *)v209) < 0 )
                  {
                    *(_QWORD *)v209 = 0;
                    *(_DWORD *)&v209[8] = 0;
                    if ( v210 )
                      SusFree(v210);
                    v210 = 0;
                    *(_QWORD *)&v209[12] = 0;
                  }
                  v133 = ((unsigned int)CNetworkListManagerHelper::IsInternetConnectionAvailable(v197 + 1304, 2) != 0)
                       + 1;
                  if ( HIDWORD(v228[6]) || !v228[10] )
                    v134 = 0;
                  else
                    v134 = *(_QWORD *)(v228[10] + 136LL);
                  LOBYTE(v164) = v204[0];
                  LOWORD(v160) = v228[42];
                  CSearchCall::ReportScanQOS(v2, 145, v134, v212, v211, (char *)v2 + 1176, v133, v160, v209, v164, 0);
                  if ( v210 )
                    SusFree(v210);
                }
              }
              CSusArrayList<enum SusWsStructs::SusXmlUpdateFragmentType,CSusArrayListItemOpNoop<enum SusWsStructs::SusXmlUpdateFragmentType>>::~CSusArrayList<enum SusWsStructs::SusXmlUpdateFragmentType,CSusArrayListItemOpNoop<enum SusWsStructs::SusXmlUpdateFragmentType>>(v219);
              CSusArrayList<wchar_t *,CSusArrayBSTRListItemOpDelete>::~CSusArrayList<wchar_t *,CSusArrayBSTRListItemOpDelete>(v214);
              if ( v45 )
                operator delete(v45, (const struct std::nothrow_t *)0x18);
              WuSmartPtr::XPtrBase<CatScanContext,WuSmartPtr::Policies::STPolicy<CatScanContext>>::InternalRelease(&v184);
              if ( v43 )
                SusFree(v43);
              if ( v42 )
                SusFree(v42);
              CSusArrayList<_GUID,CSusArrayListItemOpNoop<_GUID>>::~CSusArrayList<_GUID,CSusArrayListItemOpNoop<_GUID>>(v220);
              CSusArrayList<_GUID,CSusArrayListItemOpNoop<_GUID>>::~CSusArrayList<_GUID,CSusArrayListItemOpNoop<_GUID>>(v217);
              if ( !v51 )
                goto LABEL_362;
              v23 = v166;
            }
            v51 = v170;
LABEL_327:
            RegionString = CAgentUpdateManager::FilterForSearchResult(
                             v173,
                             (struct CSearchCall *)((char *)v2 + 1176),
                             v2);
            v167 = RegionString;
            if ( RegionString < 0 )
            {
              WUTrace(0, 0, 1, 5, RegionString, L"FilterForSearchResult");
              CSusArrayList<enum SusWsStructs::SusXmlUpdateFragmentType,CSusArrayListItemOpNoop<enum SusWsStructs::SusXmlUpdateFragmentType>>::~CSusArrayList<enum SusWsStructs::SusXmlUpdateFragmentType,CSusArrayListItemOpNoop<enum SusWsStructs::SusXmlUpdateFragmentType>>(v219);
              CSusArrayList<wchar_t *,CSusArrayBSTRListItemOpDelete>::~CSusArrayList<wchar_t *,CSusArrayBSTRListItemOpDelete>(v214);
              if ( v45 )
                operator delete(v45, (const struct std::nothrow_t *)0x18);
              WuSmartPtr::XPtrBase<CatScanContext,WuSmartPtr::Policies::STPolicy<CatScanContext>>::InternalRelease(&v184);
              if ( v43 )
                SusFree(v43);
              if ( v42 )
LABEL_360:
                SusFree(v42);
LABEL_361:
              CSusArrayList<_GUID,CSusArrayListItemOpNoop<_GUID>>::~CSusArrayList<_GUID,CSusArrayListItemOpNoop<_GUID>>(v220);
              CSusArrayList<_GUID,CSusArrayListItemOpNoop<_GUID>>::~CSusArrayList<_GUID,CSusArrayListItemOpNoop<_GUID>>(v217);
LABEL_362:
              v3 = v173;
              goto LABEL_363;
            }
            goto LABEL_335;
          }
          v28 = 2;
          v183 = 2;
        }
        CSearchCall::LogStartOfScan(v2, v28, v22, v24);
        goto LABEL_71;
      }
    }
  }
LABEL_363:
  v135 = *((_QWORD *)v2 + 17);
  if ( v135 )
    CTokenCache::ReleaseToken((CTokenCache *)(v135 + 24));
  if ( !v189 )
    CSusThreadSafeMap<_GUID,tagSystemSpec *,CSusSortedArrayListItemOpsBasic<_GUID>,CAgentUpdateManager::CSusArrayListItemOpSystemSpec>::Remove((LPCRITICAL_SECTION)v3 + 92);
  v163 = (char *)v2 + 1072;
  HIDWORD(v161) = 0;
  v157 = (_DWORD)v2 + 1176;
  CAgentUpdateManager::PrepareSearchCallbackInfo(v3, 0, 0, v2);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)v3 + 2616));
  v136 = (char *)v3 + 2656;
  *(_OWORD *)v214 = 0;
  *(_OWORD *)&v214[8] = *((_OWORD *)v2 + 17);
  v137 = *((_DWORD *)v3 + 669);
  if ( v137 )
  {
    v138 = 0;
    v139 = 0;
    do
    {
      v140 = (v137 + v138) >> 1;
      v141 = CSusSortedArrayList<CSusMap<_GUID,CSusMap<_GUID,DownloadHeartbeatBundle *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<DownloadHeartbeatBundle *>> *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<CSusMap<_GUID,DownloadHeartbeatBundle *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<DownloadHeartbeatBundle *>> *>>::_tagMapEntry,CSusMap<_GUID,CSusMap<_GUID,DownloadHeartbeatBundle *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<DownloadHeartbeatBundle *>> *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<CSusMap<_GUID,DownloadHeartbeatBundle *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<DownloadHeartbeatBundle *>> *>>::CMapEntryOps>::InternalCompare(
               v136,
               v214,
               v140);
      if ( v141 )
      {
        if ( v141 <= 0 )
          v137 = (v137 + v138) >> 1;
        else
          v138 = v140 + 1;
      }
      else
      {
        v139 = 1;
      }
    }
    while ( v137 > v138 && !v139 );
    v142 = v139 == 0;
    v5 = v181;
    v2 = v203;
    RegionString = v167;
    if ( !v142 && v140 < *((_DWORD *)v136 + 5) )
      CSusArrayList<CSusMap<_GUID,CSusArrayList<FlatBundleFileIdList::FileIdListData,CSusArrayListItemOpNoop<FlatBundleFileIdList::FileIdListData>> *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<CSusArrayList<FlatBundleFileIdList::FileIdListData,CSusArrayListItemOpNoop<FlatBundleFileIdList::FileIdListData>> *>>::_tagMapEntry,CSusMap<_GUID,CSusArrayList<FlatBundleFileIdList::FileIdListData,CSusArrayListItemOpNoop<FlatBundleFileIdList::FileIdListData>> *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<CSusArrayList<FlatBundleFileIdList::FileIdListData,CSusArrayListItemOpNoop<FlatBundleFileIdList::FileIdListData>> *>>::CMapEntryOps>::RemoveArraySection(
        v136,
        v140,
        v140,
        1);
    v3 = v173;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v3 + 2616));
  v203 = 0;
  if ( (*(int (__fastcall **)(_QWORD, struct CSearchCall **))(**((_QWORD **)v3 + 281) + 24LL))(
         *((_QWORD *)v3 + 281),
         &v203) >= 0 )
  {
    (*(void (__fastcall **)(struct CSearchCall *))(*(_QWORD *)v203 + 272LL))(v203);
    (*(void (__fastcall **)(struct CSearchCall *))(*(_QWORD *)v203 + 16LL))(v203);
  }
  if ( v190 )
    CAgentProtocolTalker::SearchCompleted((struct CSearchCall *)((char *)v2 + 760), (const struct _GUID *)v2 + 17);
  v143 = v180;
  v144 = 0;
  if ( !v180
    || (unsigned int)AreTestKeysAllowed(1)
    && (unsigned int)RegQueryDwordValueWithDefaultAndRangeCheck(
                       v145,
                       L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Test",
                       L"AlwaysFireScanEvent",
                       0,
                       0,
                       -1) )
  {
    v146 = ((unsigned int)CNetworkListManagerHelper::IsInternetConnectionAvailable(v197 + 1304, 2) != 0) + 1;
    memset(v214, 0, 20);
    v215 = 0;
    if ( CAgentProtocolTalkerContext::GetMetadataIntegrityDataForScanEvent(
           (CAgentProtocolTalkerContext *)v228,
           (struct MetadataIntegrity::MetadataIntegrityDataForScanEvent *)v214) < 0 )
    {
      *(_QWORD *)v214 = 0;
      *(_DWORD *)&v214[8] = 0;
      if ( v215 )
        SusFree(v215);
      v215 = 0;
      *(_QWORD *)&v214[12] = 0;
    }
    CSearchCall::ReportResult(
      v2,
      v157,
      (__int64)v229,
      v212,
      v211,
      v216,
      v146,
      v228[42],
      (__int64)v214,
      v204[0],
      (__int64)&v228[43]);
    v144 = 0;
    if ( v215 )
      SusFree(v215);
  }
  if ( RegionString >= 0 && (*((_DWORD *)v2 + 312) & 0x8000) != 0 )
  {
    CAgentUpdateManager::AddRequestedAppCategoryIdList(v3, (char *)v2 + 272, &v222);
    if ( (*((_BYTE *)v2 + 1248) & 0x10) != 0 )
    {
      if ( DWORD1(v224) )
      {
        do
        {
          v199 = *(struct _GUID *)(v223 + 16LL * v144);
          RegKeyPath = (const wchar_t *)GetRegKeyPath(3, v147, v148, v149);
          v151 = RegAddValueGuidTimestamp((const struct _GUID *)v2 + 17, RegKeyPath, &v199);
          if ( v151 < 0 )
            WUTrace(0, 0, 1, 4, v151, L"Some appCategoryId LastOnlineScanTime cache is not refreshed");
          ++v144;
        }
        while ( v144 < DWORD1(v224) );
        v5 = v181;
      }
    }
  }
  LODWORD(v163) = RegionString;
  LODWORD(v161) = *((_DWORD *)v2 + 33);
  WUTrace(
    0,
    0,
    1,
    (unsigned int)((RegionString >> 31) + 4),
    0,
    L"* END * Finding updates CallerId = %ws, Id = %d, Exit code = 0x%08lX (cV = %hs)",
    *(_QWORD *)(*((_QWORD *)v2 + 17) + 136LL),
    v161,
    v163,
    v230);
  if ( v183 )
    CSearchCall::LogEndOfScan(v2, v183, *((unsigned int *)v2 + 268));
  if ( RegionString >= 0
    && !(**((unsigned __int8 (__fastcall ***)(__int64))v2 + 119))((__int64)v2 + 952)
    && (*((_BYTE *)v2 + 1248) & 0x10) != 0
    && v213
    && !v143
    && !*((_BYTE *)v2 + 1300) )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_ModernStandby>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_ModernStandby>::GetImpl'::`2'::impl) )
      *((_DWORD *)v3 + 618) = *((_DWORD *)v2 + 312);
    v153 = CInventoryEngine::ProcessInventory((CAgentUpdateManager *)((char *)v3 + 2472));
    WUTrace(0, 0, 1, 4, v153, L"Started inventory process");
  }
  CWUEtwConsumer::RotatePastLogsOverLimit(v152, 0);
  if ( v186 )
    SusFree(v186);
  if ( v5 )
  {
    CExpressionManager::~CExpressionManager(v5);
    operator delete(v5, (const struct std::nothrow_t *)0x30);
  }
  CAgentProtocolTalkerContext::~CAgentProtocolTalkerContext((CAgentProtocolTalkerContext *)v228);
  CSusArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>>::~CSusArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>>(&v222);
  CSusArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>>::~CSusArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>>(v225);
  v227[0] = &CSearchCancelObject::`vftable';
  `eh vector destructor iterator'(
    v229,
    0x20u,
    5u,
    CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>>::~CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>>);
}

```

## disassembly

```asm
0x18002e560  mov     [rsp-8+arg_10], rbx
0x18002e565  push    rbp
0x18002e566  push    rsi
0x18002e567  push    rdi
0x18002e568  push    r12
0x18002e56a  push    r13
0x18002e56c  push    r14
0x18002e56e  push    r15
0x18002e570  lea     rbp, [rsp-6C0h]
0x18002e578  sub     rsp, 810h
0x18002e57f  mov     rax, cs:__security_cookie
0x18002e586  xor     rax, rsp
0x18002e589  mov     [rbp+6F0h+var_40], rax
0x18002e590  mov     r12, rdx
0x18002e593  mov     [rbp+6F0h+var_508], rdx
0x18002e59a  mov     r15, rcx
0x18002e59d  mov     [rbp+6F0h+var_750], rcx
0x18002e5a1  xor     r13d, r13d
0x18002e5a4  mov     [rbp+6F0h+var_728], r13d
0x18002e5a8  lea     edi, [r13+1]
0x18002e5ac  mov     [rbp+6F0h+var_6E4], edi
0x18002e5af  mov     [rbp+6F0h+var_6E8], r13d
0x18002e5b3  lea     rax, ??1?$CSusSortedArrayList@U_GUID@@V?$CSusSortedArrayListItemOpsBasic@U_GUID@@@@@@UEAA@XZ; CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>>::~CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>>(void)
0x18002e5ba  mov     [rsp+840h+var_820], rax; void (*)(void *)
0x18002e5bf  lea     r9, ??0?$CSusSortedArrayList@U_GUID@@V?$CSusSortedArrayListItemOpsBasic@U_GUID@@@@@@QEAA@XZ; void (*)(void *)
0x18002e5c6  lea     edx, [rdi+1Fh]; unsigned __int64
0x18002e5c9  lea     r8d, [r13+5]; unsigned __int64
0x18002e5cd  lea     rcx, [rbp+6F0h+var_170]; void *
0x18002e5d4  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x18002e5d9  nop
0x18002e5da  lea     r14, [r12+2F8h]
0x18002e5e2  xorps   xmm0, xmm0
0x18002e5e5  movups  xmmword ptr [rbp+6F0h+var_408], xmm0
0x18002e5ec  lea     rax, ??_7CSearchCancelObject@@6B@; const CSearchCancelObject::`vftable'
0x18002e5f3  mov     [rbp+6F0h+var_408], rax
0x18002e5fa  mov     [rbp+6F0h+var_408+8], r14
0x18002e601  movups  [rbp+6F0h+var_428], xmm0
0x18002e608  movups  [rbp+6F0h+var_418], xmm0
0x18002e60f  mov     qword ptr [rbp+6F0h+var_428+8], r13
0x18002e616  mov     qword ptr [rbp+6F0h+var_418], r13
0x18002e61d  lea     rax, ??_7?$CSusSortedArrayList@U_GUID@@V?$CSusSortedArrayListItemOpsBasic@U_GUID@@@@@@6B@; const CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>>::`vftable'
0x18002e624  mov     qword ptr [rbp+6F0h+var_428], rax
0x18002e62b  mov     dword ptr [rbp+6F0h+var_418+8], r13d
0x18002e632  movups  [rbp+6F0h+var_448], xmm0
0x18002e639  movups  [rbp+6F0h+var_438], xmm0
0x18002e640  mov     qword ptr [rbp+6F0h+var_448+8], r13
0x18002e647  mov     qword ptr [rbp+6F0h+var_438], r13
0x18002e64e  mov     qword ptr [rbp+6F0h+var_448], rax
0x18002e655  mov     dword ptr [rbp+6F0h+var_438+8], r13d
0x18002e65c  mov     [rbp+6F0h+var_6E0], r13d
0x18002e660  mov     eax, r13d
0x18002e663  mov     [rbp+6F0h+var_724], eax
0x18002e666  mov     [rbp+6F0h+var_4F8], eax
0x18002e66c  mov     [rbp+6F0h+var_700], r13d
0x18002e670  mov     [rbp+6F0h+var_710], r13d
0x18002e674  mov     [rbp+6F0h+var_4C4], r13d
0x18002e67b  mov     [rbp+6F0h+var_4C8], r13d
0x18002e682  mov     [rbp+6F0h+var_498], r13d
0x18002e689  mov     rax, [r15+8C0h]
0x18002e690  mov     [rbp+6F0h+var_6A0], rax
0x18002e694  mov     [rbp+6F0h+var_770], r13b
0x18002e698  mov     [rbp+6F0h+var_4F4], r13d
0x18002e69f  xor     edx, edx; Val
0x18002e6a1  mov     r8d, 280h; Size
0x18002e6a7  lea     rcx, [rbp+6F0h+var_3F0]; void *
0x18002e6ae  call    memset
0x18002e6b3  lea     r8, [rbp+6F0h+var_4F4]; unsigned int *
0x18002e6ba  lea     rdx, [r12+430h]; struct CSusError *
0x18002e6c2  lea     rcx, [rbp+6F0h+var_3F0]; this
0x18002e6c9  call    ??0CAgentProtocolTalkerContext@@QEAA@AEAVCSusError@@PEAK@Z; CAgentProtocolTalkerContext::CAgentProtocolTalkerContext(CSusError &,ulong *)
0x18002e6ce  nop
0x18002e6cf  mov     [rbp+6F0h+lpMem], r13
0x18002e6d6  mov     esi, r13d
0x18002e6d9  mov     [rbp+6F0h+var_720], r13
0x18002e6dd  mov     [rbp+6F0h+var_698], r13
0x18002e6e1  mov     [rbp+6F0h+var_4C0], r13d
0x18002e6e8  mov     [rbp+6F0h+var_6F0], r13
0x18002e6ec  mov     [rbp+6F0h+var_500], r13b
0x18002e6f3  mov     [rbp+6F0h+var_6F8], r13
0x18002e6f7  lea     rbx, [r12+110h]
0x18002e6ff  lea     rdx, [rbp+6F0h+var_D0]; char *
0x18002e706  mov     rcx, r12; this
0x18002e709  call    ?GetAndIncrementCorrelationVector@CSearchCall@@QEAAJPEAD@Z; CSearchCall::GetAndIncrementCorrelationVector(char *)
0x18002e70e  test    eax, eax
0x18002e710  jns     short loc_18002E719
0x18002e712  mov     [rbp+6F0h+var_D0], r13b
0x18002e719  mov     rcx, [r12+88h]
0x18002e721  lea     rax, [rbp+6F0h+var_D0]
0x18002e728  mov     [rsp+840h+var_800], rax
0x18002e72d  mov     eax, [r12+84h]
0x18002e735  mov     dword ptr [rsp+840h+var_808], eax
0x18002e739  mov     rax, [rcx+88h]
0x18002e740  mov     [rsp+840h+var_810], rax
0x18002e745  lea     rax, aStartFindingUp; "* START * Finding updates CallerId = %w"...
0x18002e74c  mov     [rsp+840h+var_818], rax
0x18002e751  mov     [rsp+840h+var_820], r13
0x18002e756  mov     r9d, 4
0x18002e75c  mov     r8d, edi
0x18002e75f  xor     edx, edx
0x18002e761  xor     ecx, ecx
0x18002e763  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18002e768  lea     rdi, [r12+3B8h]
0x18002e770  mov     rax, [rdi]
0x18002e773  mov     rcx, rdi
0x18002e776  mov     rax, [rax+48h]
0x18002e77a  call    _guard_dispatch_icall
0x18002e77f  test    rax, rax
0x18002e782  jz      short loc_18002E7C6
0x18002e784  mov     rax, [rdi]
0x18002e787  mov     rcx, rdi
0x18002e78a  mov     rax, [rax+48h]
0x18002e78e  call    _guard_dispatch_icall
0x18002e793  lea     rcx, [rbp+6F0h+var_D0]
0x18002e79a  mov     [rsp+840h+var_808], rcx
0x18002e79f  mov     [rsp+840h+var_810], rax
0x18002e7a4  lea     rax, aIntentpfnsWsCv; "IntentPFNs = %ws (cV = %hs)"
0x18002e7ab  mov     [rsp+840h+var_818], rax
0x18002e7b0  mov     [rsp+840h+var_820], r13; int
0x18002e7b5  xor     edx, edx
0x18002e7b7  xor     ecx, ecx
0x18002e7b9  lea     r9d, [rdx+4]
0x18002e7bd  lea     r8d, [rdx+1]
0x18002e7c1  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18002e7c6  mov     rcx, r12; this
0x18002e7c9  call    ?TraceProperties@CSearchCall@@QEAAXXZ; CSearchCall::TraceProperties(void)
0x18002e7ce  test    byte ptr [r12+4E0h], 2
0x18002e7d7  jz      loc_18002E8A6
0x18002e7dd  mov     rbx, [r12+88h]
0x18002e7e5  mov     [rbp+6F0h+pSid], r13
0x18002e7e9  lea     rcx, [rbp+6F0h+pSid]
0x18002e7ed  call    SusAllocLocalSystemSid
0x18002e7f2  mov     r13d, eax
0x18002e7f5  mov     dword ptr [rbp+6F0h+var_768], eax
0x18002e7f8  test    eax, eax
0x18002e7fa  jns     short loc_18002E82F
0x18002e7fc  mov     rcx, [rbp+6F8h]; this
0x18002e803  mov     r9d, eax; char *
0x18002e806  lea     r8, aCW1SSrcClientE_103; "C:\\__w\\1\\s\\src\\Client\\Engine\\lib"...
0x18002e80d  mov     edx, 318h; void *
0x18002e812  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e817  mov     rcx, [rbp+6F0h+pSid]; pSid
0x18002e81b  test    rcx, rcx
0x18002e81e  jz      loc_180030B16
0x18002e824  call    cs:__imp_FreeSid
0x18002e82a  jmp     loc_180030B16
0x18002e82f  mov     rdx, [rbx+78h]
0x18002e833  test    rdx, rdx
0x18002e836  jnz     short loc_18002E83C
0x18002e838  mov     rdx, [rbx+58h]; pSid2
0x18002e83c  mov     rbx, [rbp+6F0h+pSid]
0x18002e840  mov     rcx, rbx; pSid1
0x18002e843  call    cs:__imp_EqualSid
0x18002e849  test    eax, eax
0x18002e84b  setnz   r14b
0x18002e84f  test    rbx, rbx
0x18002e852  jz      short loc_18002E85D
0x18002e854  mov     rcx, rbx; pSid
0x18002e857  call    cs:__imp_FreeSid
0x18002e85d  test    r14b, r14b
0x18002e860  jz      short loc_18002E896
0x18002e862  mov     r13d, 80240045h
0x18002e868  mov     dword ptr [rbp+6F0h+var_768], r13d
0x18002e86c  lea     rax, aBlockingCurren; "Blocking current user search for locals"...
0x18002e873  mov     [rsp+840h+var_818], rax
0x18002e878  xor     eax, eax
0x18002e87a  mov     [rsp+840h+var_820], rax
0x18002e87f  lea     edi, [rax+1]
0x18002e882  mov     r9d, edi
0x18002e885  mov     r8d, edi
0x18002e888  xor     edx, edx
0x18002e88a  xor     ecx, ecx
0x18002e88c  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18002e891  jmp     loc_180030B16
0x18002e896  lea     rbx, [r12+110h]
0x18002e89e  lea     r14, [r12+2F8h]
0x18002e8a6  lea     rcx, [rbp+6F0h+var_6F8]; wchar_t **
0x18002e8aa  call    ?GetRegionString@@YAJPEAPEA_W@Z; GetRegionString(wchar_t * *)
0x18002e8af  mov     r13d, eax
0x18002e8b2  mov     dword ptr [rbp+6F0h+var_768], eax
0x18002e8b5  test    eax, eax
0x18002e8b7  js      loc_180030B16
0x18002e8bd  call    ?IsSystemSetupBlockingWU@@YAHXZ; IsSystemSetupBlockingWU(void)
0x18002e8c2  xor     ecx, ecx
0x18002e8c4  test    eax, eax
0x18002e8c6  jz      short loc_18002E8EF
0x18002e8c8  mov     r13d, 8024004Ah
0x18002e8ce  mov     dword ptr [rbp+6F0h+var_768], r13d
0x18002e8d2  lea     rax, aOsSetupInProgr; " OS setup in progress. Failing scan"
0x18002e8d9  mov     [rsp+840h+var_818], rax
0x18002e8de  mov     [rsp+840h+var_820], rcx
0x18002e8e3  xor     edx, edx
0x18002e8e5  lea     r9d, [rcx+5]
0x18002e8e9  lea     r8d, [rcx+1]
0x18002e8ed  jmp     short loc_18002E88C
0x18002e8ef  lea     rdx, [rbp+6F0h+var_6F0]; struct CSusService **
0x18002e8f3  mov     rcx, rbx; struct _GUID *
0x18002e8f6  call    ?GetServiceObjectHelper@CAgentServiceManager@@SAJAEBU_GUID@@PEAPEAVCSusService@@@Z; CAgentServiceManager::GetServiceObjectHelper(_GUID const &,CSusService * *)
0x18002e8fb  mov     r13d, eax
0x18002e8fe  mov     dword ptr [rbp+6F0h+var_768], eax
0x18002e901  test    eax, eax
0x18002e903  js      loc_180030B16
0x18002e909  mov     rcx, r12; this
0x18002e90c  call    ?ParseFilter@CSearchCall@@QEAAJXZ; CSearchCall::ParseFilter(void)
0x18002e911  mov     r13d, eax
0x18002e914  mov     dword ptr [rbp+6F0h+var_768], eax
0x18002e917  test    eax, eax
0x18002e919  js      loc_180030B16
0x18002e91f  mov     rbx, [rbp+6F0h+var_6F0]
0x18002e923  mov     rcx, rbx; this
0x18002e926  call    ?CheckAccessByPolicy@CSusService@@QEAAJXZ; CSusService::CheckAccessByPolicy(void)
0x18002e92b  mov     r13d, eax
0x18002e92e  mov     dword ptr [rbp+6F0h+var_768], eax
0x18002e931  test    eax, eax
0x18002e933  jns     short loc_18002E956
0x18002e935  lea     rax, aCheckaccessbyp; "CheckAccessByPolicy"
0x18002e93c  mov     [rsp+840h+var_818], rax
0x18002e941  mov     dword ptr [rsp+840h+var_820], r13d
0x18002e946  mov     eax, 1
0x18002e94b  mov     r9d, eax
0x18002e94e  mov     r8d, eax
0x18002e951  jmp     loc_18002E888
0x18002e956  mov     rax, [rbx]
0x18002e959  mov     rcx, rbx
0x18002e95c  mov     rax, [rax+18h]
0x18002e960  call    _guard_dispatch_icall
0x18002e965  xor     r13d, r13d
0x18002e968  test    al, al
0x18002e96a  jz      short loc_18002E9B0
0x18002e96c  mov     rax, [rbx]
0x18002e96f  lea     rdx, [rbp+6F0h+var_4C0]
0x18002e976  mov     rcx, rbx
0x18002e979  mov     rax, [rax+38h]
0x18002e97d  call    _guard_dispatch_icall
0x18002e982  test    eax, eax
0x18002e984  jns     short loc_18002E9B0
0x18002e986  lea     edx, [r13+1]
0x18002e98a  mov     [rbp+6F0h+var_4C0], edx
0x18002e990  lea     rcx, aGetisinventory; "GetIsInventoryRequired"
0x18002e997  mov     [rsp+840h+var_818], rcx
0x18002e99c  mov     dword ptr [rsp+840h+var_820], eax
0x18002e9a0  lea     r9d, [r13+4]
0x18002e9a4  mov     r8d, edx
0x18002e9a7  xor     edx, edx
0x18002e9a9  xor     ecx, ecx
0x18002e9ab  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18002e9b0  mov     rax, [rdi]
0x18002e9b3  mov     rcx, rdi
0x18002e9b6  mov     rax, [rax+20h]
0x18002e9ba  call    _guard_dispatch_icall
0x18002e9bf  test    al, al
0x18002e9c1  jz      short loc_18002EA39
0x18002e9c3  mov     dword ptr [rbp+6F0h+var_758], r13d
0x18002e9c7  lea     rdx, [rbp+6F0h+var_758]; int *
0x18002e9cb  mov     rcx, rbx; this
0x18002e9ce  call    ?GetIsOfflineSync@CSusService@@QEAAJPEAH@Z; CSusService::GetIsOfflineSync(int *)
0x18002e9d3  mov     ecx, dword ptr [rbp+6F0h+var_758]
0x18002e9d6  test    eax, eax
0x18002e9d8  cmovs   ecx, r13d
0x18002e9dc  test    ecx, ecx
0x18002e9de  jnz     short loc_18002EA39
0x18002e9e0  mov     rax, [rbx]
0x18002e9e3  mov     rcx, rbx
0x18002e9e6  mov     rax, [rax+18h]
0x18002e9ea  call    _guard_dispatch_icall
0x18002e9ef  test    al, al
0x18002e9f1  jnz     short loc_18002EA39
0x18002e9f3  mov     rax, [rbx]
0x18002e9f6  mov     rcx, rbx
0x18002e9f9  mov     rax, [rax+50h]
0x18002e9fd  call    _guard_dispatch_icall
0x18002ea02  test    al, al
0x18002ea04  jnz     short loc_18002EA39
0x18002ea06  lea     rax, aServiceDoesnTS; "Service doesn't support product specifi"...
0x18002ea0d  mov     r8d, 1
0x18002ea13  xor     edx, edx
0x18002ea15  mov     [rsp+840h+var_818], rax
0x18002ea1a  lea     r9d, [rdx+4]
0x18002ea1e  xor     ecx, ecx
0x18002ea20  mov     [rsp+840h+var_820], r13
0x18002ea25  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18002ea2a  mov     r13d, 240010h
0x18002ea30  mov     dword ptr [rbp+6F0h+var_768], r13d
0x18002ea34  jmp     loc_180030B16
0x18002ea39  mov     rax, [rdi]
0x18002ea3c  mov     rcx, rdi
0x18002ea3f  mov     rax, [rax]
0x18002ea42  call    _guard_dispatch_icall
0x18002ea47  test    al, al
0x18002ea49  jnz     short loc_18002EA6E
0x18002ea4b  mov     rax, [rbx]
0x18002ea4e  mov     rcx, rbx
0x18002ea51  mov     rax, [rax+8]
0x18002ea55  call    _guard_dispatch_icall
0x18002ea5a  mov     rcx, rax; struct _GUID *
0x18002ea5d  call    ?IsServiceInLoadSheddingSession@@YA_NAEBU_GUID@@@Z; IsServiceInLoadSheddingSession(_GUID const &)
0x18002ea62  test    al, al
0x18002ea64  jz      short loc_18002EA6E
0x18002ea66  mov     r13d, 8024402Eh
0x18002ea6c  jmp     short loc_18002EA30
0x18002ea6e  mov     edi, 1
  ... truncated ...
```
