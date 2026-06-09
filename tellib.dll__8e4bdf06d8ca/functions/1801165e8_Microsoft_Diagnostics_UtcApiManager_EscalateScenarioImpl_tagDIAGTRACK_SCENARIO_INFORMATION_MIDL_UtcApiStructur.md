# Microsoft::Diagnostics::UtcApiManager::EscalateScenarioImpl(tagDIAGTRACK_SCENARIO_INFORMATION,__MIDL_UtcApiStructures_0001,wchar_t const *,int,int,__MIDL_UtcApiStructures_0004,ulong,wchar_t const * *,wchar_t const * *,std::function<void (long,_GUID,_GUID)> const &,ulong *,_GUID *)

- ea: `0x1801165e8`
- end: `0x18011885c`
- name: `?EscalateScenarioImpl@UtcApiManager@Diagnostics@Microsoft@@AEAAJUtagDIAGTRACK_SCENARIO_INFORMATION@@W4__MIDL_UtcApiStructures_0001@@PEB_WHHW4__MIDL_UtcApiStructures_0004@@KPEAPEB_W4AEBV?$function@$$A6AXJU_GUID@@0@Z@std@@PEAKPEAU_GUID@@@Z`
- size: `8820`
- prototype: `__int64 __fastcall(__int64, struct _GUID *, unsigned int, const WCHAR *, int, int, unsigned int, unsigned int, __int64, __int64, __int64, _DWORD *, GUID *)`
- caller_count: `4`
- callee_count: `71`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800941a0`
- `0x1801164e0`
- `0x1801d49d0`
- `0x1801d66f0`

## callees

- `0x180001d28`
- `0x1800072fc`
- `0x180007918`
- `0x18001d160`
- `0x180020fbc`
- `0x180026ecc`
- `0x180027be0`
- `0x180030a50`
- `0x1800326cc`
- `0x180032718`
- `0x1800333b0`
- `0x1800340c0`
- `0x180034d94`
- `0x1800363b4`
- `0x180046c94`
- `0x1800498f0`
- `0x18004ab70`
- `0x18004be40`
- `0x18005178c`
- `0x180052734`
- `0x180053a84`
- `0x18005b974`
- `0x18005d050`
- `0x18006c984`
- `0x18006fd10`
- `0x18007fae8`
- `0x180080054`
- `0x180090614`
- `0x180092df8`
- `0x180092e98`
- `0x180093f0c`
- `0x1800a4068`
- `0x1800a5324`
- `0x1800a8e5c`
- `0x1800a9250`
- `0x1800af524`
- `0x1800af5f0`
- `0x1800b0628`
- `0x1800b2cf4`
- `0x1800ccdf0`
- `0x1800d0d9c`
- `0x18010d8c0`
- `0x18011131c`
- `0x1801165e8`
- `0x18012de40`
- `0x18012eae4`
- `0x180177b0c`
- `0x1801ba8e0`
- `0x1801cf9d8`
- `0x1801cfb18`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1801171e3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1801171e3`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x180116a8a`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x180116a8a`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1801170c1`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1801170c1`

## string_xrefs

- `0x180116798`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x18011684b`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x180116917`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801169c5`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x180116aae`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x180116b9a`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x180116c60`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x180116d1e`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x180116f0f`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x180116fdc`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801170e2`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801172f4`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x18011762a`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x18011841f`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x180118458`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x180118654`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801186ed`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x180118788`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801187c3`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801187fe`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x180117454`: `ScenarioApiCompleted_0`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall Microsoft::Diagnostics::UtcApiManager::EscalateScenarioImpl(
        __int64 a1,
        struct _GUID *a2,
        unsigned int a3,
        const WCHAR *a4,
        int a5,
        int a6,
        unsigned int a7,
        unsigned int a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        _DWORD *a12,
        GUID *a13)
{
  _DWORD *v15; // rdx
  GUID *v16; // rcx
  int v17; // ecx
  __int64 v18; // r9
  char v19; // r15
  __int64 v20; // rcx
  int RpcImpersonationToken; // eax
  unsigned int v22; // ebx
  __int64 v24; // rcx
  unsigned int i; // ebx
  WCHAR *v26; // rcx
  struct Microsoft::Diagnostics::ScenarioManager *ScenarioManager; // rax
  Microsoft::Diagnostics::ScenarioManager *v28; // rax
  int ScenarioById; // eax
  unsigned int v30; // ebx
  std::_Ref_count_base *v31; // r14
  int v32; // ebx
  __int64 v33; // rcx
  __int64 v34; // r8
  HRESULT v35; // eax
  __int64 v36; // rax
  std::_Ref_count_base *v37; // rdi
  __int64 *v38; // rbx
  __int64 v39; // rcx
  __int64 v40; // rcx
  char v41; // di
  __int64 v42; // rdx
  __int64 v43; // rax
  char v44; // bl
  int v45; // eax
  __int64 v46; // rax
  __int64 v47; // r8
  __int64 v48; // r8
  _QWORD *v49; // rax
  __int128 v50; // xmm6
  __int64 v51; // rax
  __int64 v52; // rax
  _QWORD *v53; // rax
  int v54; // eax
  const char *v55; // r9
  __int64 v56; // rdx
  struct Microsoft::Diagnostics::MetadataEngine *MetadataEngine; // rax
  _QWORD *v58; // rax
  struct Microsoft::Diagnostics::MetadataEngine *v59; // rax
  _QWORD *v60; // rax
  struct Microsoft::Diagnostics::MetadataEngine *v61; // rax
  _QWORD *v62; // rax
  struct Microsoft::Diagnostics::MetadataEngine *v63; // rax
  _QWORD *v64; // rax
  struct Microsoft::Diagnostics::MetadataEngine *v65; // rax
  _QWORD *v66; // rax
  struct Microsoft::Diagnostics::MetadataEngine *v67; // rax
  _QWORD *v68; // rax
  struct Microsoft::Diagnostics::MetadataEngine *v69; // rax
  _QWORD *v70; // rax
  struct Microsoft::Diagnostics::MetadataEngine *v71; // rax
  _QWORD *v72; // rax
  struct Microsoft::Diagnostics::MetadataEngine *v73; // rax
  _QWORD *v74; // rax
  struct Microsoft::Diagnostics::MetadataEngine *v75; // rax
  _QWORD *v76; // rax
  struct Microsoft::Diagnostics::MetadataEngine *v77; // rax
  _QWORD *v78; // rax
  struct Microsoft::Diagnostics::MetadataEngine *v79; // rax
  _QWORD *v80; // rax
  struct Microsoft::Diagnostics::MetadataEngine *v81; // rax
  _QWORD *v82; // rax
  struct Microsoft::Diagnostics::MetadataEngine *v83; // rax
  _QWORD *v84; // rax
  _QWORD *v85; // rax
  _QWORD *v86; // rax
  __int64 v87; // rdx
  __int64 v88; // r8
  struct Microsoft::Diagnostics::ScenarioCounterStorage *v89; // rbx
  __int64 v90; // rdx
  __int64 v91; // r8
  __int64 v92; // rdx
  __int64 v93; // r8
  __int64 v94; // rdx
  __int64 v95; // r8
  __int64 v96; // rdx
  __int64 v97; // r8
  __int64 v98; // rbx
  _QWORD *v99; // rax
  __int64 v100; // rbx
  int v101; // ecx
  int v102; // r8d
  int v103; // r9d
  __int64 v104; // rdx
  __int64 v105; // rdx
  int v106; // eax
  struct Microsoft::Diagnostics::EscalationEngine *EscalationEngine; // rbx
  __int64 v108; // rax
  __int64 v109; // r12
  __int64 v110; // r9
  __int64 v111; // rax
  __int64 v112; // r8
  _QWORD *v113; // rax
  __int128 v114; // xmm6
  __int64 v115; // rax
  __int64 v116; // rax
  _QWORD *v117; // rax
  int v118; // eax
  unsigned int v119; // ebx
  unsigned int v120; // ebx
  unsigned int v121; // ebx
  unsigned int v122; // [rsp+20h] [rbp-C48h]
  int v123; // [rsp+20h] [rbp-C48h]
  int v124; // [rsp+20h] [rbp-C48h]
  bool v125; // [rsp+140h] [rbp-B28h] BYREF
  _BYTE v126[3]; // [rsp+141h] [rbp-B27h] BYREF
  _DWORD v127[3]; // [rsp+144h] [rbp-B24h] BYREF
  __int128 v128; // [rsp+150h] [rbp-B18h] BYREF
  struct _GUID *v129; // [rsp+160h] [rbp-B08h] BYREF
  char v130; // [rsp+168h] [rbp-B00h]
  __int64 v131; // [rsp+170h] [rbp-AF8h] BYREF
  __int64 v132; // [rsp+178h] [rbp-AF0h]
  _BYTE v133[4]; // [rsp+180h] [rbp-AE8h] BYREF
  _WORD v134[6]; // [rsp+184h] [rbp-AE4h] BYREF
  std::_Ref_count_base *v135[2]; // [rsp+190h] [rbp-AD8h] BYREF
  unsigned int v136; // [rsp+1A0h] [rbp-AC8h] BYREF
  _DWORD *v137; // [rsp+1A8h] [rbp-AC0h] BYREF
  int v138; // [rsp+1B0h] [rbp-AB8h]
  int CurrentScenarioEscalationsByType; // [rsp+1B4h] [rbp-AB4h] BYREF
  int v140; // [rsp+1B8h] [rbp-AB0h] BYREF
  _BYTE v141[16]; // [rsp+1C0h] [rbp-AA8h] BYREF
  std::_Ref_count_base *v142[2]; // [rsp+1D0h] [rbp-A98h] BYREF
  std::_Ref_count_base *v143[2]; // [rsp+1E0h] [rbp-A88h] BYREF
  unsigned int v144[2]; // [rsp+1F0h] [rbp-A78h] BYREF
  GUID *v145; // [rsp+1F8h] [rbp-A70h] BYREF
  __int64 v146; // [rsp+200h] [rbp-A68h]
  int v147; // [rsp+208h] [rbp-A60h] BYREF
  int v148; // [rsp+20Ch] [rbp-A5Ch] BYREF
  int CurrentScenarioReportsByType; // [rsp+210h] [rbp-A58h] BYREF
  __int64 v150; // [rsp+218h] [rbp-A50h] BYREF
  struct Microsoft::Diagnostics::ScenarioCounterStorage *ScenarioCounterStorage; // [rsp+220h] [rbp-A48h] BYREF
  char *v152; // [rsp+228h] [rbp-A40h] BYREF
  __int64 v153; // [rsp+230h] [rbp-A38h] BYREF
  int v154; // [rsp+238h] [rbp-A30h]
  __int64 v155; // [rsp+240h] [rbp-A28h]
  _QWORD *v156; // [rsp+248h] [rbp-A20h] BYREF
  _QWORD v157[3]; // [rsp+250h] [rbp-A18h] BYREF
  _QWORD *v158; // [rsp+268h] [rbp-A00h] BYREF
  _QWORD *v159; // [rsp+270h] [rbp-9F8h] BYREF
  _QWORD *v160; // [rsp+278h] [rbp-9F0h] BYREF
  _QWORD *v161; // [rsp+280h] [rbp-9E8h] BYREF
  const wchar_t *v162; // [rsp+288h] [rbp-9E0h] BYREF
  _QWORD *v163; // [rsp+290h] [rbp-9D8h] BYREF
  _QWORD *v164; // [rsp+298h] [rbp-9D0h] BYREF
  _QWORD *v165; // [rsp+2A0h] [rbp-9C8h] BYREF
  _QWORD *v166; // [rsp+2A8h] [rbp-9C0h] BYREF
  _QWORD *v167; // [rsp+2B0h] [rbp-9B8h] BYREF
  _QWORD *v168; // [rsp+2B8h] [rbp-9B0h] BYREF
  _BYTE v169[8]; // [rsp+2C0h] [rbp-9A8h] BYREF
  std::_Ref_count_base *v170; // [rsp+2C8h] [rbp-9A0h]
  unsigned int *v171; // [rsp+2D0h] [rbp-998h] BYREF
  int v172; // [rsp+2D8h] [rbp-990h]
  _QWORD *v173; // [rsp+2E0h] [rbp-988h] BYREF
  _QWORD *v174; // [rsp+2E8h] [rbp-980h] BYREF
  _BYTE v175[16]; // [rsp+2F0h] [rbp-978h] BYREF
  _QWORD *v176; // [rsp+300h] [rbp-968h] BYREF
  __int64 v177; // [rsp+308h] [rbp-960h] BYREF
  int v178; // [rsp+310h] [rbp-958h]
  _BYTE v179[16]; // [rsp+318h] [rbp-950h] BYREF
  _BYTE v180[16]; // [rsp+328h] [rbp-940h] BYREF
  _BYTE v181[16]; // [rsp+338h] [rbp-930h] BYREF
  _BYTE v182[16]; // [rsp+348h] [rbp-920h] BYREF
  _BYTE v183[16]; // [rsp+358h] [rbp-910h] BYREF
  _BYTE v184[16]; // [rsp+368h] [rbp-900h] BYREF
  _BYTE v185[16]; // [rsp+378h] [rbp-8F0h] BYREF
  _BYTE v186[16]; // [rsp+388h] [rbp-8E0h] BYREF
  _BYTE v187[32]; // [rsp+398h] [rbp-8D0h] BYREF
  PWSTR pszPathOut[4]; // [rsp+3B8h] [rbp-8B0h] BYREF
  __int128 v189; // [rsp+3D8h] [rbp-890h] BYREF
  __int64 v190; // [rsp+3E8h] [rbp-880h]
  _BYTE v191[16]; // [rsp+3F8h] [rbp-870h] BYREF
  __int64 v192; // [rsp+408h] [rbp-860h]
  __int128 v193; // [rsp+418h] [rbp-850h] BYREF
  __int64 v194; // [rsp+428h] [rbp-840h]
  _BYTE v195[4]; // [rsp+438h] [rbp-830h] BYREF
  int v196; // [rsp+43Ch] [rbp-82Ch]
  _BYTE v197[4]; // [rsp+440h] [rbp-828h] BYREF
  GUID Buf1; // [rsp+444h] [rbp-824h] BYREF
  _BYTE v199[32]; // [rsp+458h] [rbp-810h] BYREF
  _BYTE v200[32]; // [rsp+478h] [rbp-7F0h] BYREF
  _BYTE v201[72]; // [rsp+498h] [rbp-7D0h] BYREF
  _BYTE v202[8]; // [rsp+4E0h] [rbp-788h] BYREF
  _BYTE v203[64]; // [rsp+4E8h] [rbp-780h] BYREF
  _BYTE v204[16]; // [rsp+528h] [rbp-740h] BYREF
  _BYTE v205[40]; // [rsp+538h] [rbp-730h] BYREF
  _BYTE v206[40]; // [rsp+560h] [rbp-708h] BYREF
  _BYTE v207[40]; // [rsp+588h] [rbp-6E0h] BYREF
  _BYTE v208[40]; // [rsp+5B0h] [rbp-6B8h] BYREF
  _BYTE v209[40]; // [rsp+5D8h] [rbp-690h] BYREF
  _BYTE v210[40]; // [rsp+600h] [rbp-668h] BYREF
  _BYTE v211[40]; // [rsp+628h] [rbp-640h] BYREF
  _BYTE v212[40]; // [rsp+650h] [rbp-618h] BYREF
  _BYTE v213[40]; // [rsp+678h] [rbp-5F0h] BYREF
  _BYTE v214[40]; // [rsp+6A0h] [rbp-5C8h] BYREF
  _BYTE v215[40]; // [rsp+6C8h] [rbp-5A0h] BYREF
  _BYTE v216[40]; // [rsp+6F0h] [rbp-578h] BYREF
  _BYTE v217[40]; // [rsp+718h] [rbp-550h] BYREF
  _BYTE v218[48]; // [rsp+740h] [rbp-528h] BYREF
  _BYTE v219[704]; // [rsp+770h] [rbp-4F8h] BYREF
  _BYTE v220[344]; // [rsp+A30h] [rbp-238h] BYREF
  _BYTE v221[80]; // [rsp+B88h] [rbp-E0h] BYREF
  _BYTE v222[56]; // [rsp+BD8h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C68h] [rbp+0h]

  v136 = a3;
  v150 = a1;
  CurrentScenarioEscalationsByType = a5;
  v140 = a6;
  v155 = a11;
  v15 = a12;
  v137 = a12;
  v16 = a13;
  v145 = a13;
  if ( (unsigned int)dword_18042D328 > 4 )
  {
    if ( (unsigned __int8)tlgKeywordOn(&dword_18042D328, 0x2000) )
    {
      v125 = *(_QWORD *)(v18 + 56) == 0;
      *(_QWORD *)v144 = a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<1>>(
        v17,
        (unsigned int)&unk_1803C9724,
        a3,
        v18,
        (__int64)v144,
        (__int64)&v125);
      a3 = v136;
    }
    v15 = v137;
    v16 = v145;
  }
  v129 = a2;
  v19 = 1;
  v130 = 1;
  if ( !a4 || !a9 || !a10 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B2,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
      (const char *)0x80070057LL,
      v122);
    v130 = 0;
    Microsoft::Diagnostics::UtcApiManager::EscalateScenarioImpl_::_3_::_lambda_1_::operator()(&v129);
    return 2147942487LL;
  }
  if ( v15 )
    *v15 = 0;
  if ( v16 )
    *v16 = GUID_NULL;
  if ( a3 > 1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C4,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
      (const char *)0x80070057LL,
      v122);
    v130 = 0;
    Microsoft::Diagnostics::UtcApiManager::EscalateScenarioImpl_::_3_::_lambda_1_::operator()(&v129);
    return 2147942487LL;
  }
  if ( a7 > 2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C9,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
      (const char *)0x80070057LL,
      v122);
    v130 = 0;
    Microsoft::Diagnostics::UtcApiManager::EscalateScenarioImpl_::_3_::_lambda_1_::operator()(&v129);
    return 2147942487LL;
  }
  *(_QWORD *)&v127[1] = 0;
  std::wstring::wstring(v187);
  RpcImpersonationToken = Microsoft::Diagnostics::ApiServer::GetRpcImpersonationToken(v20, &v127[1], v187);
  v22 = RpcImpersonationToken;
  if ( RpcImpersonationToken < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1CF,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
      (const char *)(unsigned int)RpcImpersonationToken,
      v122);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v187);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v127[1]);
    v130 = 0;
    Microsoft::Diagnostics::UtcApiManager::EscalateScenarioImpl_::_3_::_lambda_1_::operator()(&v129);
    return v22;
  }
  std::map<std::wstring,std::wstring,Microsoft::Diagnostics::Utils::String::CaseInsensitiveLessThanPredicate,std::allocator<std::pair<std::wstring const,std::wstring>>>::map<std::wstring,std::wstring,Microsoft::Diagnostics::Utils::String::CaseInsensitiveLessThanPredicate,std::allocator<std::pair<std::wstring const,std::wstring>>>(&v131);
  for ( i = 0; i < a8; ++i )
  {
    if ( !*(_QWORD *)(a9 + 8LL * i) || !*(_QWORD *)(a10 + 8LL * i) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1D8,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
        (const char *)0x80070057LL,
        v122);
      std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
        &v131,
        &v131);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v187);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v127[1]);
      v130 = 0;
      Microsoft::Diagnostics::UtcApiManager::EscalateScenarioImpl_::_3_::_lambda_1_::operator()(&v129);
      return 2147942487LL;
    }
    std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Emplace<wchar_t const * &,wchar_t const * &>(
      &v131,
      v135);
  }
  Microsoft::Diagnostics::UtcApiManager::ProcessApiMetaProperties(v24, v195, &v127[1], &v131);
  *(_QWORD *)v144 = v196;
  std::unique_lock<std::recursive_timed_mutex>::unique_lock<std::recursive_timed_mutex>(v141, v150 + 224, v144);
  if ( !v141[8] )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E7,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
      (const char *)0x87C5102BLL,
      v122);
    std::unique_lock<std::recursive_timed_mutex>::~unique_lock<std::recursive_timed_mutex>(v141);
    std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
      &v131,
      &v131);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v187);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v127[1]);
    v130 = 0;
    Microsoft::Diagnostics::UtcApiManager::EscalateScenarioImpl_::_3_::_lambda_1_::operator()(&v129);
    return 2277838891LL;
  }
  std::wstring::wstring(v191);
  if ( std::wstring::find_first_of(v191, 47, 0) != -1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1F0,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
      (const char *)0x80070057LL,
      v122);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v191);
    std::unique_lock<std::recursive_timed_mutex>::~unique_lock<std::recursive_timed_mutex>(v141);
    std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
      &v131,
      &v131);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v187);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v127[1]);
    v130 = 0;
    Microsoft::Diagnostics::UtcApiManager::EscalateScenarioImpl_::_3_::_lambda_1_::operator()(&v129);
    return 2147942487LL;
  }
  std::wstring::wstring(pszPathOut, v192, 0);
  v26 = (WCHAR *)pszPathOut;
  if ( pszPathOut[3] > (PWSTR)7 )
    v26 = pszPathOut[0];
  if ( PathCchCanonicalizeEx(v26, (size_t)pszPathOut[2] + 1, a4, 1u) < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1F7,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
      (const char *)0x80070057LL,
      v122);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPathOut);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v191);
    std::unique_lock<std::recursive_timed_mutex>::~unique_lock<std::recursive_timed_mutex>(v141);
    std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
      &v131,
      &v131);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v187);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v127[1]);
    v130 = 0;
    Microsoft::Diagnostics::UtcApiManager::EscalateScenarioImpl_::_3_::_lambda_1_::operator()(&v129);
    return 2147942487LL;
  }
  if ( !_InterlockedCompareExchange64((volatile signed __int64 *)&xmmword_18043BF10, 0, 0) )
  {
    v121 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x1FD,
             (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
             (const char *)0x15,
             v122);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPathOut);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v191);
    std::unique_lock<std::recursive_timed_mutex>::~unique_lock<std::recursive_timed_mutex>(v141);
    std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
      &v131,
      &v131);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v187);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v127[1]);
    v130 = 0;
    Microsoft::Diagnostics::UtcApiManager::EscalateScenarioImpl_::_3_::_lambda_1_::operator()(&v129);
    return v121;
  }
  if ( !_InterlockedCompareExchange64((_QWORD *)&xmmword_18043BF50 + 1, 0, 0) )
  {
    v120 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x203,
             (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
             (const char *)0x15,
             v122);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPathOut);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v191);
    std::unique_lock<std::recursive_timed_mutex>::~unique_lock<std::recursive_timed_mutex>(v141);
    std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
      &v131,
      &v131);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v187);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v127[1]);
    v130 = 0;
    Microsoft::Diagnostics::UtcApiManager::EscalateScenarioImpl_::_3_::_lambda_1_::operator()(&v129);
    return v120;
  }
  ScenarioManager = Microsoft::Diagnostics::LifetimeManager::GetScenarioManager((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
  Microsoft::Diagnostics::ScenarioManager::GetScenarioState(ScenarioManager, v133, a2);
  if ( v133[0] )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x20A,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
      (const char *)0x87C51005LL,
      v122);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPathOut);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v191);
    std::unique_lock<std::recursive_timed_mutex>::~unique_lock<std::recursive_timed_mutex>(v141);
    std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
      &v131,
      &v131);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v187);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v127[1]);
    v130 = 0;
    Microsoft::Diagnostics::UtcApiManager::EscalateScenarioImpl_::_3_::_lambda_1_::operator()(&v129);
    return 2277838853LL;
  }
  *(_OWORD *)v143 = 0;
  v28 = Microsoft::Diagnostics::LifetimeManager::GetScenarioManager((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
  ScenarioById = Microsoft::Diagnostics::ScenarioManager::TryGetScenarioById(v28, a2);
  v30 = ScenarioById;
  if ( ScenarioById < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x210,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
      (const char *)(unsigned int)ScenarioById,
      v122);
    if ( v143[1] )
      std::_Ref_count_base::_Decref(v143[1]);
LABEL_37:
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPathOut);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v191);
    std::unique_lock<std::recursive_timed_mutex>::~unique_lock<std::recursive_timed_mutex>(v141);
    std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
      &v131,
      &v131);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v187);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v127[1]);
    v130 = 0;
    Microsoft::Diagnostics::UtcApiManager::EscalateScenarioImpl_::_3_::_lambda_1_::operator()(&v129);
    return v30;
  }
  v31 = v143[0];
  if ( !v143[0] )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x211,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
      (const char *)0x87C51005LL,
      v122);
    if ( v143[1] )
      std::_Ref_count_base::_Decref(v143[1]);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPathOut);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v191);
    std::unique_lock<std::recursive_timed_mutex>::~unique_lock<std::recursive_timed_mutex>(v141);
    std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
      &v131,
      &v131);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v187);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v127[1]);
    v130 = 0;
    Microsoft::Diagnostics::UtcApiManager::EscalateScenarioImpl_::_3_::_lambda_1_::operator()(&v129);
    return 2277838853LL;
  }
  v32 = (*(__int64 (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v143[0] + 336LL))(v143[0]);
  v138 = v32;
  if ( *(_WORD *)(*(__int64 (__fastcall **)(std::_Ref_count_base *, _WORD *))(*(_QWORD *)v31 + 80LL))(v31, v134) == 1 )
  {
    if ( !(unsigned __int8)Microsoft::Diagnostics::ApiServer::IsRpcCallerUif(v33, &v127[1]) )
    {
      v127[0] = v32;
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_UtcFeedbackHubApiCheck>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_UtcFeedbackHubApiCheck>::GetImpl'::`2'::impl) )
        goto LABEL_60;
    }
    LOBYTE(v34) = 1;
    Microsoft::Diagnostics::LifetimeManager::GetAuthorizationInfo(&gs_lifetimeManager, v127, v34);
    if ( a7 )
    {
      if ( (v127[0] & 0x200) == 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x227,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
          (const char *)0x87C5101BLL,
          v122);
        if ( v143[1] )
          std::_Ref_count_base::_Decref(v143[1]);
        goto LABEL_53;
      }
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_UtcFeedbackHubApiCheck>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_UtcFeedbackHubApiCheck>::GetImpl'::`2'::impl) )
      {
        std::wstring::wstring(&v189);
        Microsoft::Diagnostics::Utils::Os::GetDeviceClass(&v189);
        v142[0] = (std::_Ref_count_base *)L"Windows.Desktop";
        v142[1] = (std::_Ref_count_base *)15;
        *(_OWORD *)v135 = *(_OWORD *)std::wstring::operator std::wstring_view(&v189, &v153);
        if ( !(unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(v135, v142)
          && SLOBYTE(v127[0]) >= 0
          && !(unsigned __int8)Microsoft::Diagnostics::ApiServer::SoftIsAdminCheck(&v127[1]) )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x240,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
            (const char *)0x87C5101BLL,
            v122);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)&v189);
          if ( v143[1] )
            std::_Ref_count_base::_Decref(v143[1]);
LABEL_53:
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPathOut);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v191);
          std::unique_lock<std::recursive_timed_mutex>::~unique_lock<std::recursive_timed_mutex>(v141);
          std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
            &v131,
            &v131);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v187);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v127[1]);
          v130 = 0;
          Microsoft::Diagnostics::UtcApiManager::EscalateScenarioImpl_::_3_::_lambda_1_::operator()(&v129);
          return 2277838875LL;
        }
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)&v189);
      }
    }
    v32 &= ~0x80u;
  }
  v127[0] = v32;
  v138 = v32;
LABEL_60:
  *(_OWORD *)v142 = 0;
  if ( !memcmp_0(&Buf1, &GUID_NULL, 0x10u) )
  {
    v35 = CoCreateGuid(&Buf1);
    v30 = v35;
    if ( v35 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x251,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
        (const char *)(unsigned int)v35,
        v122);
      if ( v143[1] )
        std::_Ref_count_base::_Decref(v143[1]);
      goto LABEL_37;
    }
  }
  if ( v145 )
    *v145 = Buf1;
  v36 = std::make_shared<Microsoft::Diagnostics::ScenarioInst,std::shared_ptr<Microsoft::Diagnostics::IScenarioDef const> &,_GUID &>(
          v135,
          v143,
          &Buf1);
  std::shared_ptr<Concurrency::details::_Task_impl<std::shared_ptr<Microsoft::Diagnostics::HttpResponse>>>::operator=(
    v142,
    v36);
  if ( v135[1] )
    std::_Ref_count_base::_Decref(v135[1]);
  v37 = v142[0];
  GetSystemTimeAsFileTime((LPFILETIME)((char *)v142[0] + 36));
  *((_BYTE *)v37 + 72) = 1;
  v38 = (__int64 *)((char *)v37 + 80);
  if ( (__int64 *)((char *)v37 + 80) != &v131 )
  {
    std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::clear((char *)v37 + 80);
    v39 = *v38;
    *v38 = v131;
    v131 = v39;
    v40 = *((_QWORD *)v37 + 11);
    *((_QWORD *)v37 + 11) = v132;
    v132 = v40;
  }
  wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
    (char *)v37 + 96,
    &v127[1]);
  std::wstring::operator=((char *)v37 + 104, v187);
  v41 = 0;
  v125 = 0;
  (*(void (__fastcall **)(std::_Ref_count_base *, _QWORD *))(*(_QWORD *)v31 + 264LL))(v31, v157);
  if ( v136 == 1 )
  {
    v41 = 1;
    v125 = 1;
    v43 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, __int128 *))(*(_QWORD *)v31 + 272LL))(v31, &v189);
    std::vector<std::shared_ptr<Microsoft::Diagnostics::IActionDef const>>::operator=(v157, v43);
    std::vector<std::shared_ptr<Microsoft::Diagnostics::ITriggerDef const>>::_Tidy(&v189);
  }
  if ( v157[0] == v157[1] )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x275,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
      (const char *)0x87C51057LL,
      v122);
    std::vector<std::shared_ptr<Microsoft::Diagnostics::ITriggerDef const>>::_Tidy(v157);
    if ( v142[1] )
      std::_Ref_count_base::_Decref(v142[1]);
    if ( v143[1] )
      std::_Ref_count_base::_Decref(v143[1]);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPathOut);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v191);
    std::unique_lock<std::recursive_timed_mutex>::~unique_lock<std::recursive_timed_mutex>(v141);
    std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
      &v131,
      &v131);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v187);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v127[1]);
    v130 = 0;
    Microsoft::Diagnostics::UtcApiManager::EscalateScenarioImpl_::_3_::_lambda_1_::operator()(&v129);
    return 2277838935LL;
  }
  else
  {
    v44 = (v41 ^ 1) - 4;
    v126[0] = v44;
    if ( v137 )
    {
      LOBYTE(v42) = (v41 ^ 1) - 4;
      v45 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, __int64))(*(_QWORD *)v31 + 224LL))(v31, v42);
      *v137 = v45 + 5000;
    }
    v46 = (*(__int64 (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v31 + 72LL))(v31);
    LOBYTE(v47) = 1;
    Microsoft::Diagnostics::Utils::String::StringFromGuidW(v199, v46, v47);
    Microsoft::Diagnostics::Utils::String::NormalizeToBracelessUppercaseGuidString(v199);
    v152 = (char *)v142[0] + 12;
    LOBYTE(v48) = 1;
    Microsoft::Diagnostics::Utils::String::StringFromGuidW(v200, (char *)v142[0] + 12, v48);
    Microsoft::Diagnostics::Utils::String::NormalizeToBracelessUppercaseGuidString(v200);
    *(_QWORD *)&v128 = L"ScenarioApiCompleted_0";
    *((_QWORD *)&v128 + 1) = 22;
    Microsoft::Diagnostics::AsimovSyntheticEvent::MakeScenarioSyntheticEvent(
      (unsigned int)v219,
      (unsigned int)&v128,
      0x1000000,
      0,
      0);
    v49 = (_QWORD *)std::wstring::operator std::wstring_view(v200, v135);
    std::wstring::_Assign<wchar_t>(v220, *v49);
    (*(void (__fastcall **)(std::_Ref_count_base *, std::_Ref_count_base **))(*(_QWORD *)v31 + 88LL))(v31, v135);
    *(_QWORD *)&v128 = L"ScenarioName";
    *((_QWORD *)&v128 + 1) = 12;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring_view>((unsigned int)v219, (unsigned int)v222);
    *(_QWORD *)&v128 = L"ScenarioId";
    *((_QWORD *)&v128 + 1) = 10;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring>((unsigned int)v219, (unsigned int)v222);
    v50 = *(_OWORD *)(*(__int64 (__fastcall **)(std::_Ref_count_base *, __int64 *))(*(_QWORD *)v31 + 88LL))(v31, &v153);
    v51 = std::wstring::wstring(&v193);
    *(_OWORD *)v135 = v50;
    v52 = Microsoft::Diagnostics::operator+(&v189, v51, v135);
    v53 = (_QWORD *)std::wstring::operator std::wstring_view(v52, &v171);
    std::wstring::_Assign<wchar_t>(v221, *v53);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)&v189);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)&v193);
    *(_OWORD *)v135 = 0;
    Microsoft::Diagnostics::Utils::Enum::MakeEnumSet<Microsoft::Diagnostics::PersistSyntheticOptions>(&v137, v135);
    v54 = Microsoft::Diagnostics::AsimovEventSerializer::PersistSyntheticEvent((Microsoft::Diagnostics::IAsimovEvent *)v219);
    if ( v54 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x29D,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
        (const char *)(unsigned int)v54,
        v123);
    if ( dword_18042D328 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 0x400000002LL) )
    {
      ScenarioCounterStorage = Microsoft::Diagnostics::LifetimeManager::GetScenarioCounterStorage((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
      v189 = 0;
      v190 = 0;
      v134[0] = 0;
      v193 = 0;
      v194 = 0;
      LOWORD(v136) = 0;
      try
      {
        v134[0] = Microsoft::Diagnostics::ScenarioInst::PopulateTriggerInfoTlg();
        LOWORD(v136) = Microsoft::Diagnostics::ScenarioInst::PopulateSelectFieldsTlg(v142[0], &v193);
      }
      catch ( ... )
      {
        wil::details::in1diag3::Log_CaughtException(
          retaddr,
          (void *)0x2AD,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
          v55);
        v19 = v130;
        v31 = v143[0];
        v138 = v127[0];
        v41 = v125;
        a5 = CurrentScenarioEscalationsByType;
        a6 = v140;
        v44 = v126[0];
      }
      v56 = 0x400000002LL;
      if ( (unsigned int)dword_18042D328 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 0x400000002LL) )
      {
        v177 = v193;
        v178 = (unsigned __int16)(WORD4(v193) - v193);
        v171 = &v136;
        v172 = 2;
        v153 = v189;
        v154 = (unsigned __int16)(WORD4(v189) - v189);
        v135[0] = (std::_Ref_count_base *)v134;
        LODWORD(v135[1]) = 2;
        MetadataEngine = Microsoft::Diagnostics::LifetimeManager::GetMetadataEngine((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
        v128 = *(_OWORD *)&off_1803602C0;
        v58 = (_QWORD *)Microsoft::Diagnostics::MetadataEngine::QueryMetadata(MetadataEngine, v201, &v128);
        if ( v58[3] > 7u )
          v58 = (_QWORD *)*v58;
        v168 = v58;
        v59 = Microsoft::Diagnostics::LifetimeManager::GetMetadataEngine((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
        v128 = *(_OWORD *)&off_180360280;
        v60 = (_QWORD *)Microsoft::Diagnostics::MetadataEngine::QueryMetadata(v59, v218, &v128);
        if ( v60[3] > 7u )
          v60 = (_QWORD *)*v60;
        v173 = v60;
        v61 = Microsoft::Diagnostics::LifetimeManager::GetMetadataEngine((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
        v128 = *(_OWORD *)&off_180360290;
        v62 = (_QWORD *)Microsoft::Diagnostics::MetadataEngine::QueryMetadata(v61, v217, &v128);
        if ( v62[3] > 7u )
          v62 = (_QWORD *)*v62;
        v174 = v62;
        v63 = Microsoft::Diagnostics::LifetimeManager::GetMetadataEngine((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
        v128 = *(_OWORD *)&off_1803602A0;
        v64 = (_QWORD *)Microsoft::Diagnostics::MetadataEngine::QueryMetadata(v63, v216, &v128);
        if ( v64[3] > 7u )
          v64 = (_QWORD *)*v64;
        v176 = v64;
        v65 = Microsoft::Diagnostics::LifetimeManager::GetMetadataEngine((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
        v128 = *(_OWORD *)&off_1803602B0;
        v66 = (_QWORD *)Microsoft::Diagnostics::MetadataEngine::QueryMetadata(v65, v215, &v128);
        if ( v66[3] > 7u )
          v66 = (_QWORD *)*v66;
        v158 = v66;
        v67 = Microsoft::Diagnostics::LifetimeManager::GetMetadataEngine((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
        v128 = *(_OWORD *)&off_180360240;
        v68 = (_QWORD *)Microsoft::Diagnostics::MetadataEngine::QueryMetadata(v67, v214, &v128);
        if ( v68[3] > 7u )
          v68 = (_QWORD *)*v68;
        v159 = v68;
        v69 = Microsoft::Diagnostics::LifetimeManager::GetMetadataEngine((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
        v128 = *(_OWORD *)&off_180360250;
        v70 = (_QWORD *)Microsoft::Diagnostics::MetadataEngine::QueryMetadata(v69, v213, &v128);
        if ( v70[3] > 7u )
          v70 = (_QWORD *)*v70;
        v160 = v70;
        v71 = Microsoft::Diagnostics::LifetimeManager::GetMetadataEngine((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
        v128 = *(_OWORD *)&off_180360260;
        v72 = (_QWORD *)Microsoft::Diagnostics::MetadataEngine::QueryMetadata(v71, v212, &v128);
        if ( v72[3] > 7u )
          v72 = (_QWORD *)*v72;
        v161 = v72;
        v162 = L"0";
        v73 = Microsoft::Diagnostics::LifetimeManager::GetMetadataEngine((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
        v128 = *(_OWORD *)&off_180360270;
        v74 = (_QWORD *)Microsoft::Diagnostics::MetadataEngine::QueryMetadata(v73, v211, &v128);
        if ( v74[3] > 7u )
          v74 = (_QWORD *)*v74;
        v167 = v74;
        v75 = Microsoft::Diagnostics::LifetimeManager::GetMetadataEngine((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
        v128 = *(_OWORD *)&off_180360200;
        v76 = (_QWORD *)Microsoft::Diagnostics::MetadataEngine::QueryMetadata(v75, v210, &v128);
        if ( v76[3] > 7u )
          v76 = (_QWORD *)*v76;
        v163 = v76;
        v77 = Microsoft::Diagnostics::LifetimeManager::GetMetadataEngine((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
        v128 = *(_OWORD *)&off_180360210;
        v78 = (_QWORD *)Microsoft::Diagnostics::MetadataEngine::QueryMetadata(v77, v209, &v128);
        if ( v78[3] > 7u )
          v78 = (_QWORD *)*v78;
        v164 = v78;
        v79 = Microsoft::Diagnostics::LifetimeManager::GetMetadataEngine((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
        v128 = *(_OWORD *)&off_180360220;
        v80 = (_QWORD *)Microsoft::Diagnostics::MetadataEngine::QueryMetadata(v79, v208, &v128);
        if ( v80[3] > 7u )
          v80 = (_QWORD *)*v80;
        v165 = v80;
        v81 = Microsoft::Diagnostics::LifetimeManager::GetMetadataEngine((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
        v128 = *(_OWORD *)&off_180360230;
        v82 = (_QWORD *)Microsoft::Diagnostics::MetadataEngine::QueryMetadata(v81, v207, &v128);
        if ( v82[3] > 7u )
          v82 = (_QWORD *)*v82;
        v166 = v82;
        v83 = Microsoft::Diagnostics::LifetimeManager::GetMetadataEngine((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
        v128 = *(_OWORD *)&off_1803601F0;
        v84 = (_QWORD *)Microsoft::Diagnostics::MetadataEngine::QueryMetadata(v83, v206, &v128);
        if ( v84[3] > 7u )
          v84 = (_QWORD *)*v84;
        v156 = v84;
        v146 = *(_QWORD *)((*(__int64 (__fastcall **)(std::_Ref_count_base *, _BYTE *))(*(_QWORD *)v31 + 136LL))(
                             v31,
                             v186)
                         + 8);
        v85 = (_QWORD *)(*(__int64 (__fastcall **)(std::_Ref_count_base *, _BYTE *))(*(_QWORD *)v31 + 136LL))(v31, v180);
        *(_QWORD *)&v128 = _tlgWrapBinary<wchar_t,2>(v181, *v85, (unsigned int)v146);
        v146 = *(_QWORD *)((*(__int64 (__fastcall **)(std::_Ref_count_base *, _BYTE *))(*(_QWORD *)v31 + 128LL))(
                             v31,
                             v182)
                         + 8);
        v86 = (_QWORD *)(*(__int64 (__fastcall **)(std::_Ref_count_base *, _BYTE *))(*(_QWORD *)v31 + 128LL))(v31, v183);
        v146 = _tlgWrapBinary<wchar_t,2>(v184, *v86, (unsigned int)v146);
        v126[0] = v44;
        LOBYTE(v87) = -4;
        v140 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, __int64))(*(_QWORD *)v31 + 192LL))(v31, v87);
        LOBYTE(v88) = -4;
        v89 = ScenarioCounterStorage;
        CurrentScenarioEscalationsByType = Microsoft::Diagnostics::ScenarioCounterStorage::GetCurrentScenarioEscalationsByType(
                                             ScenarioCounterStorage,
                                             v31,
                                             v88);
        LOBYTE(v90) = -3;
        v127[0] = (*(__int64 (__fastcall **)(std::_Ref_count_base *, __int64))(*(_QWORD *)v31 + 192LL))(v31, v90);
        LOBYTE(v91) = -3;
        v147 = Microsoft::Diagnostics::ScenarioCounterStorage::GetCurrentScenarioEscalationsByType(v89, v31, v91);
        LOBYTE(v92) = -4;
        v148 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, __int64))(*(_QWORD *)v31 + 184LL))(v31, v92);
        LOBYTE(v93) = -4;
        CurrentScenarioReportsByType = Microsoft::Diagnostics::ScenarioCounterStorage::GetCurrentScenarioReportsByType(
                                         v89,
                                         v31,
                                         v93);
        LOBYTE(v94) = -5;
        LODWORD(v150) = (*(__int64 (__fastcall **)(std::_Ref_count_base *, __int64))(*(_QWORD *)v31 + 184LL))(v31, v94);
        LOBYTE(v95) = -5;
        v144[0] = Microsoft::Diagnostics::ScenarioCounterStorage::GetCurrentScenarioReportsByType(v89, v31, v95);
        LOBYTE(v96) = -3;
        LODWORD(v145) = (*(__int64 (__fastcall **)(std::_Ref_count_base *, __int64))(*(_QWORD *)v31 + 184LL))(v31, v96);
        LOBYTE(v97) = -3;
        LODWORD(v137) = Microsoft::Diagnostics::ScenarioCounterStorage::GetCurrentScenarioReportsByType(v89, v31, v97);
        v98 = *(_QWORD *)((*(__int64 (__fastcall **)(std::_Ref_count_base *, _BYTE *))(*(_QWORD *)v31 + 88LL))(
                            v31,
                            v185)
                        + 8);
        v99 = (_QWORD *)(*(__int64 (__fastcall **)(std::_Ref_count_base *, _BYTE *))(*(_QWORD *)v31 + 88LL))(v31, v179);
        v100 = _tlgWrapBinary<wchar_t,2>(v175, *v99, (unsigned int)v98);
        ScenarioCounterStorage = (struct Microsoft::Diagnostics::ScenarioCounterStorage *)(*(__int64 (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v31 + 72LL))(v31);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperArray<1>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperPtrSize,_tlgWrapperPtrSize,_tlgWrapperPtrSize,_tlgWrapperPtrSize>(
          v101,
          (unsigned int)&unk_1803C9359,
          v102,
          v103,
          (__int64)&ScenarioCounterStorage,
          (__int64)&v152,
          v100,
          (__int64)&v137,
          (__int64)&v145,
          (__int64)v144,
          (__int64)&v150,
          (__int64)&CurrentScenarioReportsByType,
          (__int64)&v148,
          (__int64)&v147,
          (__int64)v127,
          (__int64)&CurrentScenarioEscalationsByType,
          (__int64)&v140,
          (__int64)v126,
          v146,
          v128,
          (__int64)&v156,
          (__int64)&v166,
          (__int64)&v165,
          (__int64)&v164,
          (__int64)&v163,
          (__int64)&v167,
          (__int64)&v162,
          (__int64)&v161,
          (__int64)&v160,
          (__int64)&v159,
          (__int64)&v158,
          (__int64)&v176,
          (__int64)&v174,
          (__int64)&v173,
          (__int64)&v168,
          (__int64)v135,
          (__int64)&v153,
          (__int64)&v171,
          (__int64)&v177);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v206);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v207);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v208);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v209);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v210);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v211);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v212);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v213);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v214);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v215);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v216);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v217);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v218);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v201);
      }
      std::vector<unsigned char>::_Tidy(&v193, v56);
      std::vector<unsigned char>::_Tidy(&v189, v104);
    }
    Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v219);
    v126[0] = a6 != 0;
    v125 = a5 != 0;
    LOBYTE(v105) = a7;
    v106 = Microsoft::Diagnostics::EscalationUploadAction::_from_integral(&v136, v105);
    std::make_shared<Microsoft::Diagnostics::EscalationWorkItemOverrides,Microsoft::Diagnostics::EscalationUploadAction,std::wstring &,bool,bool,bool &>(
      (unsigned int)v169,
      v106,
      (unsigned int)pszPathOut,
      (unsigned int)&v125,
      (__int64)v126,
      (__int64)v197);
    v202[0] = v195[0];
    std::function<void (long,_GUID,_GUID)>::function<void (long,_GUID,_GUID)>(v203, v155);
    std::shared_ptr<Microsoft::Diagnostics::IScenarioDef const>::shared_ptr<Microsoft::Diagnostics::IScenarioDef const>(
      v204,
      v142);
    std::wstring::wstring(v205, v199);
    EscalationEngine = Microsoft::Diagnostics::LifetimeManager::GetEscalationEngine((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
    *(_QWORD *)&v128 = v135;
    std::shared_ptr<Microsoft::Diagnostics::IScenarioDef const>::shared_ptr<Microsoft::Diagnostics::IScenarioDef const>(
      v135,
      v169);
    v109 = v108;
    std::function_void___cdecl_long__::function_void___cdecl_long____Microsoft::Diagnostics::UtcApiManager::EscalateScenarioImpl_::_3_::_lambda_2____0_(
      v201,
      v202);
    std::shared_ptr<Microsoft::Diagnostics::IScenarioDef const>::shared_ptr<Microsoft::Diagnostics::IScenarioDef const>(
      &v153,
      v142);
    LOBYTE(v110) = v41;
    v127[0] = Microsoft::Diagnostics::EscalationEngine::Execute(EscalationEngine, v31, v111, v110, v138, v112, v109);
    v135[0] = (std::_Ref_count_base *)L"EscalateApiFinished_0";
    v135[1] = (std::_Ref_count_base *)21;
    Microsoft::Diagnostics::AsimovSyntheticEvent::MakeScenarioSyntheticEvent(
      (unsigned int)v219,
      (unsigned int)v135,
      0x1000000,
      0,
      0);
    v113 = (_QWORD *)std::wstring::operator std::wstring_view(v200, v175);
    std::wstring::_Assign<wchar_t>(v220, *v113);
    (*(void (__fastcall **)(std::_Ref_count_base *, _BYTE *))(*(_QWORD *)v31 + 88LL))(v31, v175);
    v135[0] = (std::_Ref_count_base *)L"ScenarioName";
    v135[1] = (std::_Ref_count_base *)12;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring_view>((unsigned int)v219, (unsigned int)v222);
    v135[0] = (std::_Ref_count_base *)L"ScenarioId";
    v135[1] = (std::_Ref_count_base *)10;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring>((unsigned int)v219, (unsigned int)v222);
    v135[0] = (std::_Ref_count_base *)L"HRESULT";
    v135[1] = (std::_Ref_count_base *)7;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<long>((unsigned int)v219, (unsigned int)v222);
    v114 = *(_OWORD *)(*(__int64 (__fastcall **)(std::_Ref_count_base *, _BYTE *))(*(_QWORD *)v31 + 88LL))(v31, v175);
    v115 = std::wstring::wstring(&v193);
    *(_OWORD *)v135 = v114;
    v116 = Microsoft::Diagnostics::operator+(&v189, v115, v135);
    v117 = (_QWORD *)std::wstring::operator std::wstring_view(v116, v179);
    std::wstring::_Assign<wchar_t>(v221, *v117);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)&v189);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)&v193);
    *(_OWORD *)v135 = 0;
    Microsoft::Diagnostics::Utils::Enum::MakeEnumSet<Microsoft::Diagnostics::PersistSyntheticOptions>(&v137, v135);
    v118 = Microsoft::Diagnostics::AsimovEventSerializer::PersistSyntheticEvent((Microsoft::Diagnostics::IAsimovEvent *)v219);
    if ( v118 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x326,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
        (const char *)(unsigned int)v118,
        v124);
    Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v219);
    v119 = v127[0];
    if ( v127[0] >= 0 )
    {
      Microsoft::Diagnostics::UtcApiManager::EscalateScenarioImpl_::_3_::_lambda_2_::__lambda_2_(v202);
      if ( v170 )
        std::_Ref_count_base::_Decref(v170);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v200);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v199);
      std::vector<std::shared_ptr<Microsoft::Diagnostics::ITriggerDef const>>::_Tidy(v157);
      if ( v142[1] )
        std::_Ref_count_base::_Decref(v142[1]);
      if ( v143[1] )
        std::_Ref_count_base::_Decref(v143[1]);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPathOut);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v191);
      std::unique_lock<std::recursive_timed_mutex>::~unique_lock<std::recursive_timed_mutex>(v141);
      std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
        &v131,
        &v131);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v187);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v127[1]);
      if ( v19 )
      {
        v130 = 0;
        Microsoft::Diagnostics::UtcApiManager::EscalateScenarioImpl_::_3_::_lambda_1_::operator()(&v129);
      }
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x329,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
        (const char *)v127[0],
        v124);
      Microsoft::Diagnostics::UtcApiManager::EscalateScenarioImpl_::_3_::_lambda_2_::__lambda_2_(v202);
      if ( v170 )
        std::_Ref_count_base::_Decref(v170);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v200);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v199);
      std::vector<std::shared_ptr<Microsoft::Diagnostics::ITriggerDef const>>::_Tidy(v157);
      if ( v142[1] )
        std::_Ref_count_base::_Decref(v142[1]);
      if ( v143[1] )
        std::_Ref_count_base::_Decref(v143[1]);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPathOut);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v191);
      std::unique_lock<std::recursive_timed_mutex>::~unique_lock<std::recursive_timed_mutex>(v141);
      std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
        &v131,
        &v131);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v187);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v127[1]);
      if ( v19 )
      {
        v130 = 0;
        Microsoft::Diagnostics::UtcApiManager::EscalateScenarioImpl_::_3_::_lambda_1_::operator()(&v129);
      }
      return v119;
    }
  }
}

```

## disassembly

```asm
0x1801165e8  mov     rax, rsp
0x1801165eb  push    rbx
0x1801165ec  push    rsi
0x1801165ed  push    rdi
0x1801165ee  push    r12
0x1801165f0  push    r13
0x1801165f2  push    r14
0x1801165f4  push    r15
0x1801165f6  sub     rsp, 0C30h
0x1801165fd  movaps  xmmword ptr [rax-48h], xmm6
0x180116601  mov     rax, cs:__security_cookie
0x180116608  xor     rax, rsp
0x18011660b  mov     [rsp+0C68h+var_58], rax
0x180116613  mov     r14, r9
0x180116616  mov     [rsp+0C68h+var_AC8], r8d
0x18011661e  mov     rdi, rdx
0x180116621  mov     [rsp+0C68h+var_A50], rcx
0x180116629  mov     eax, [rsp+0C68h+arg_20]
0x180116630  mov     [rsp+0C68h+var_AB4], eax
0x180116637  mov     eax, [rsp+0C68h+arg_28]
0x18011663e  mov     [rsp+0C68h+var_AB0], eax
0x180116645  mov     r12, [rsp+0C68h+arg_40]
0x18011664d  mov     r13, [rsp+0C68h+arg_48]
0x180116655  mov     r9, [rsp+0C68h+arg_50]
0x18011665d  mov     [rsp+0C68h+var_A28], r9
0x180116665  mov     rdx, [rsp+0C68h+arg_58]
0x18011666d  mov     [rsp+0C68h+var_AC0], rdx
0x180116675  mov     rcx, [rsp+0C68h+arg_60]
0x18011667d  mov     [rsp+0C68h+var_A70], rcx
0x180116685  mov     eax, cs:dword_18042D328
0x18011668b  cmp     eax, 4
0x18011668e  jbe     loc_180116834
0x180116694  mov     edx, 2000h
0x180116699  lea     rcx, dword_18042D328
0x1801166a0  call    _tlgKeywordOn
0x1801166a5  xor     esi, esi
0x1801166a7  test    al, al
0x1801166a9  jz      short loc_1801166ED
0x1801166ab  cmp     [r9+38h], rsi
0x1801166af  setz    [rsp+0C68h+var_B28]
0x1801166b7  mov     qword ptr [rsp+0C68h+var_A78], rdi
0x1801166bf  lea     rax, [rsp+0C68h+var_B28]
0x1801166c7  mov     [rsp+0C68h+var_C40], rax
0x1801166cc  lea     rax, [rsp+0C68h+var_A78]
0x1801166d4  mov     qword ptr [rsp+0C68h+var_C48], rax; int
0x1801166d9  lea     rdx, unk_1803C9724
0x1801166e0  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &)
0x1801166e5  mov     r8d, [rsp+0C68h+var_AC8]
0x1801166ed  mov     rdx, [rsp+0C68h+var_AC0]
0x1801166f5  mov     rcx, [rsp+0C68h+var_A70]
0x1801166fd  mov     [rsp+0C68h+var_B08], rdi
0x180116705  mov     r15d, 1
0x18011670b  mov     [rsp+0C68h+var_B00], r15b
0x180116713  test    r14, r14
0x180116716  jz      loc_1801187EE
0x18011671c  test    r12, r12
0x18011671f  jz      loc_1801187EE
0x180116725  test    r13, r13
0x180116728  jz      loc_1801187EE
0x18011672e  test    rdx, rdx
0x180116731  jz      short loc_180116735
0x180116733  mov     [rdx], esi
0x180116735  test    rcx, rcx
0x180116738  jz      short loc_180116745
0x18011673a  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180116741  movdqu  xmmword ptr [rcx], xmm0
0x180116745  cmp     r8d, r15d
0x180116748  ja      loc_1801187B3
0x18011674e  cmp     [rsp+0C68h+arg_30], 2
0x180116756  ja      loc_180118778
0x18011675c  mov     qword ptr [rsp+0C68h+var_B24+4], rsi
0x180116764  lea     rcx, [rsp+0C68h+var_8D0]; void *
0x18011676c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180116771  nop
0x180116772  lea     r8, [rsp+0C68h+var_8D0]
0x18011677a  lea     rdx, [rsp+0C68h+var_B24+4]
0x180116782  call    ?GetRpcImpersonationToken@ApiServer@Diagnostics@Microsoft@@IEBAJAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::ApiServer::GetRpcImpersonationToken(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &,std::wstring &)
0x180116787  mov     ebx, eax
0x180116789  test    eax, eax
0x18011678b  jns     short loc_1801167E2
0x18011678d  mov     rcx, [rsp+0C68h]; this
0x180116795  mov     r9d, eax; char *
0x180116798  lea     r8, aOnecoreBaseTel_272; "onecore\\base\\telemetry\\utc\\service"...
0x18011679f  mov     edx, 1CFh; void *
0x1801167a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801167a9  nop
0x1801167aa  lea     rcx, [rsp+0C68h+var_8D0]; this
0x1801167b2  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1801167b7  nop
0x1801167b8  lea     rcx, [rsp+0C68h+var_B24+4]
0x1801167c0  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801167c5  nop
0x1801167c6  mov     [rsp+0C68h+var_B00], sil
0x1801167ce  lea     rcx, [rsp+0C68h+var_B08]
0x1801167d6  call    _Microsoft__Diagnostics__UtcApiManager__EscalateScenarioImpl____3____lambda_1___operator__
0x1801167db  mov     eax, ebx
0x1801167dd  jmp     loc_180118830
0x1801167e2  lea     rcx, [rsp+0C68h+var_AF8]
0x1801167ea  call    ??0?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@UCaseInsensitiveLessThanPredicate@String@Utils@Diagnostics@Microsoft@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,std::wstring,Microsoft::Diagnostics::Utils::String::CaseInsensitiveLessThanPredicate,std::allocator<std::pair<std::wstring const,std::wstring>>>::map<std::wstring,std::wstring,Microsoft::Diagnostics::Utils::String::CaseInsensitiveLessThanPredicate,std::allocator<std::pair<std::wstring const,std::wstring>>>(void)
0x1801167ef  nop
0x1801167f0  mov     ebx, esi
0x1801167f2  cmp     ebx, [rsp+0C68h+arg_38]
0x1801167f9  jnb     loc_1801168AB
0x1801167ff  mov     eax, ebx
0x180116801  lea     r8, [r12+rax*8]
0x180116805  cmp     [r8], rsi
0x180116808  jz      short loc_18011683B
0x18011680a  lea     r9, ds:0[rax*8]
0x180116812  add     r9, r13
0x180116815  cmp     [r9], rsi
0x180116818  jz      short loc_18011683B
0x18011681a  lea     rdx, [rsp+0C68h+var_AD8]
0x180116822  lea     rcx, [rsp+0C68h+var_AF8]
0x18011682a  call    ??$_Emplace@AEAPEB_WAEAPEB_W@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@PEAX@std@@_N@1@AEAPEB_W0@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<void>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Emplace<wchar_t const * &,wchar_t const * &>(wchar_t const * &,wchar_t const * &)
0x18011682f  add     ebx, r15d
0x180116832  jmp     short loc_1801167F2
0x180116834  xor     esi, esi
0x180116836  jmp     loc_1801166FD
0x18011683b  mov     rcx, [rsp+0C68h]; this
0x180116843  mov     ebx, 80070057h
0x180116848  mov     r9d, ebx; char *
0x18011684b  lea     r8, aOnecoreBaseTel_272; "onecore\\base\\telemetry\\utc\\service"...
0x180116852  mov     edx, 1D8h; void *
0x180116857  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011685c  nop
0x18011685d  lea     rdx, [rsp+0C68h+var_AF8]
0x180116865  lea     rcx, [rsp+0C68h+var_AF8]
0x18011686d  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>> &)
0x180116872  nop
0x180116873  lea     rcx, [rsp+0C68h+var_8D0]; this
0x18011687b  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x180116880  nop
0x180116881  lea     rcx, [rsp+0C68h+var_B24+4]
0x180116889  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18011688e  nop
0x18011688f  mov     [rsp+0C68h+var_B00], sil
0x180116897  lea     rcx, [rsp+0C68h+var_B08]
0x18011689f  call    _Microsoft__Diagnostics__UtcApiManager__EscalateScenarioImpl____3____lambda_1___operator__
0x1801168a4  mov     eax, ebx
0x1801168a6  jmp     loc_180118830
0x1801168ab  lea     r9, [rsp+0C68h+var_AF8]
0x1801168b3  lea     r8, [rsp+0C68h+var_B24+4]
0x1801168bb  lea     rdx, [rsp+0C68h+var_830]
0x1801168c3  call    ?ProcessApiMetaProperties@UtcApiManager@Diagnostics@Microsoft@@AEAA?AV?$tuple@U_GUID@@_NJ_N@std@@AEBV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEAV?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@@5@@Z; Microsoft::Diagnostics::UtcApiManager::ProcessApiMetaProperties(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> const &,std::map<std::wstring,std::wstring> &)
0x1801168c8  movsxd  rax, [rsp+0C68h+var_82C]
0x1801168d0  mov     qword ptr [rsp+0C68h+var_A78], rax
0x1801168d8  mov     rdx, [rsp+0C68h+var_A50]
0x1801168e0  add     rdx, 0E0h
0x1801168e7  lea     r8, [rsp+0C68h+var_A78]
0x1801168ef  lea     rcx, [rsp+0C68h+var_AA8]
0x1801168f7  call    ??$?0_JU?$ratio@$00$0DOI@@std@@@?$unique_lock@Vrecursive_timed_mutex@std@@@std@@QEAA@AEAVrecursive_timed_mutex@1@AEBV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@1@@Z; std::unique_lock<std::recursive_timed_mutex>::unique_lock<std::recursive_timed_mutex>(std::recursive_timed_mutex &,std::chrono::duration<__int64,std::ratio<1,1000>> const &)
0x1801168fc  nop
0x1801168fd  cmp     [rsp+0C68h+var_AA0], sil
0x180116905  jnz     short loc_180116985
0x180116907  mov     rcx, [rsp+0C68h]; this
0x18011690f  mov     ebx, 87C5102Bh
0x180116914  mov     r9d, ebx; char *
0x180116917  lea     r8, aOnecoreBaseTel_272; "onecore\\base\\telemetry\\utc\\service"...
0x18011691e  mov     edx, 1E7h; void *
0x180116923  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180116928  nop
0x180116929  lea     rcx, [rsp+0C68h+var_AA8]
0x180116931  call    ??1?$unique_lock@Vrecursive_timed_mutex@std@@@std@@QEAA@XZ; std::unique_lock<std::recursive_timed_mutex>::~unique_lock<std::recursive_timed_mutex>(void)
0x180116936  nop
0x180116937  lea     rdx, [rsp+0C68h+var_AF8]
0x18011693f  lea     rcx, [rsp+0C68h+var_AF8]
0x180116947  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>> &)
0x18011694c  nop
0x18011694d  lea     rcx, [rsp+0C68h+var_8D0]; this
0x180116955  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18011695a  nop
0x18011695b  lea     rcx, [rsp+0C68h+var_B24+4]
0x180116963  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180116968  nop
0x180116969  mov     [rsp+0C68h+var_B00], sil
0x180116971  lea     rcx, [rsp+0C68h+var_B08]
0x180116979  call    _Microsoft__Diagnostics__UtcApiManager__EscalateScenarioImpl____3____lambda_1___operator__
0x18011697e  mov     eax, ebx
0x180116980  jmp     loc_180118830
0x180116985  mov     rdx, r14
0x180116988  lea     rcx, [rsp+0C68h+var_870]
0x180116990  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180116995  nop
0x180116996  mov     edx, 2Fh ; '/'
0x18011699b  xor     r8d, r8d
0x18011699e  lea     rcx, [rsp+0C68h+var_870]
0x1801169a6  call    ?find_first_of@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA_K_W_K@Z; std::wstring::find_first_of(wchar_t,unsigned __int64)
0x1801169ab  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801169af  jz      loc_180116A41
0x1801169b5  mov     rcx, [rsp+0C68h]; this
0x1801169bd  mov     ebx, 80070057h
0x1801169c2  mov     r9d, ebx; char *
0x1801169c5  lea     r8, aOnecoreBaseTel_272; "onecore\\base\\telemetry\\utc\\service"...
0x1801169cc  mov     edx, 1F0h; void *
0x1801169d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801169d6  nop
0x1801169d7  lea     rcx, [rsp+0C68h+var_870]; this
0x1801169df  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1801169e4  nop
0x1801169e5  lea     rcx, [rsp+0C68h+var_AA8]
0x1801169ed  call    ??1?$unique_lock@Vrecursive_timed_mutex@std@@@std@@QEAA@XZ; std::unique_lock<std::recursive_timed_mutex>::~unique_lock<std::recursive_timed_mutex>(void)
0x1801169f2  nop
0x1801169f3  lea     rdx, [rsp+0C68h+var_AF8]
0x1801169fb  lea     rcx, [rsp+0C68h+var_AF8]
0x180116a03  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>> &)
0x180116a08  nop
0x180116a09  lea     rcx, [rsp+0C68h+var_8D0]; this
0x180116a11  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x180116a16  nop
0x180116a17  lea     rcx, [rsp+0C68h+var_B24+4]
0x180116a1f  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180116a24  nop
0x180116a25  mov     [rsp+0C68h+var_B00], sil
0x180116a2d  lea     rcx, [rsp+0C68h+var_B08]
0x180116a35  call    _Microsoft__Diagnostics__UtcApiManager__EscalateScenarioImpl____3____lambda_1___operator__
0x180116a3a  mov     eax, ebx
0x180116a3c  jmp     loc_180118830
0x180116a41  xor     r8d, r8d
0x180116a44  mov     rdx, [rsp+0C68h+var_860]
0x180116a4c  lea     rcx, [rsp+0C68h+pszPathOut]
0x180116a54  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@_K_W@Z; std::wstring::wstring(unsigned __int64,wchar_t)
0x180116a59  nop
0x180116a5a  mov     rdx, [rsp+0C68h+var_8A0]
0x180116a62  lea     rcx, [rsp+0C68h+pszPathOut]
0x180116a6a  mov     r13d, 7
0x180116a70  cmp     [rsp+0C68h+var_898], r13
0x180116a78  cmova   rcx, [rsp+0C68h+pszPathOut]; pszPathOut
0x180116a81  inc     rdx; cchPathOut
0x180116a84  mov     r9d, r15d; dwFlags
0x180116a87  mov     r8, r14; pszPathIn
0x180116a8a  call    cs:__imp_PathCchCanonicalizeEx
0x180116a91  nop     dword ptr [rax+rax+00h]
0x180116a96  test    eax, eax
0x180116a98  jns     loc_180116B38
0x180116a9e  mov     rcx, [rsp+0C68h]; this
0x180116aa6  mov     ebx, 80070057h
0x180116aab  mov     r9d, ebx; char *
0x180116aae  lea     r8, aOnecoreBaseTel_272; "onecore\\base\\telemetry\\utc\\service"...
0x180116ab5  mov     edx, 1F7h; void *
0x180116aba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180116abf  nop
0x180116ac0  lea     rcx, [rsp+0C68h+pszPathOut]; this
0x180116ac8  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x180116acd  nop
0x180116ace  lea     rcx, [rsp+0C68h+var_870]; this
0x180116ad6  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x180116adb  nop
0x180116adc  lea     rcx, [rsp+0C68h+var_AA8]
0x180116ae4  call    ??1?$unique_lock@Vrecursive_timed_mutex@std@@@std@@QEAA@XZ; std::unique_lock<std::recursive_timed_mutex>::~unique_lock<std::recursive_timed_mutex>(void)
0x180116ae9  nop
0x180116aea  lea     rdx, [rsp+0C68h+var_AF8]
0x180116af2  lea     rcx, [rsp+0C68h+var_AF8]
0x180116afa  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>> &)
0x180116aff  nop
0x180116b00  lea     rcx, [rsp+0C68h+var_8D0]; this
0x180116b08  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x180116b0d  nop
0x180116b0e  lea     rcx, [rsp+0C68h+var_B24+4]
0x180116b16  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180116b1b  nop
0x180116b1c  mov     [rsp+0C68h+var_B00], sil
0x180116b24  lea     rcx, [rsp+0C68h+var_B08]
0x180116b2c  call    _Microsoft__Diagnostics__UtcApiManager__EscalateScenarioImpl____3____lambda_1___operator__
0x180116b31  mov     eax, ebx
0x180116b33  jmp     loc_180118830
0x180116b38  xor     eax, eax
0x180116b3a  lock cmpxchg qword ptr cs:xmmword_18043BF10, rsi
0x180116b43  jz      loc_1801186DF
0x180116b49  xor     eax, eax
0x180116b4b  lock cmpxchg qword ptr cs:xmmword_18043BF50+8, rsi
0x180116b54  jz      loc_180118646
0x180116b5a  lea     r12, ?gs_lifetimeManager@@3VLifetimeManager@Diagnostics@Microsoft@@A; Microsoft::Diagnostics::LifetimeManager gs_lifetimeManager
0x180116b61  mov     rcx, r12; this
0x180116b64  call    ?GetScenarioManager@LifetimeManager@Diagnostics@Microsoft@@QEAAAEAVScenarioManager@23@XZ; Microsoft::Diagnostics::LifetimeManager::GetScenarioManager(void)
0x180116b69  mov     r8, rdi
0x180116b6c  lea     rdx, [rsp+0C68h+var_AE8]
0x180116b74  mov     rcx, rax
0x180116b77  call    ?GetScenarioState@ScenarioManager@Diagnostics@Microsoft@@QEBA?AVScenarioActivityState@23@AEBU_GUID@@@Z; Microsoft::Diagnostics::ScenarioManager::GetScenarioState(_GUID const &)
0x180116b7c  cmp     [rsp+0C68h+var_AE8], sil
0x180116b84  jz      loc_180116C24
0x180116b8a  mov     rcx, [rsp+0C68h]; this
0x180116b92  mov     ebx, 87C51005h
0x180116b97  mov     r9d, ebx; char *
0x180116b9a  lea     r8, aOnecoreBaseTel_272; "onecore\\base\\telemetry\\utc\\service"...
0x180116ba1  mov     edx, 20Ah; void *
0x180116ba6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180116bab  nop
0x180116bac  lea     rcx, [rsp+0C68h+pszPathOut]; this
0x180116bb4  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x180116bb9  nop
0x180116bba  lea     rcx, [rsp+0C68h+var_870]; this
0x180116bc2  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x180116bc7  nop
0x180116bc8  lea     rcx, [rsp+0C68h+var_AA8]
0x180116bd0  call    ??1?$unique_lock@Vrecursive_timed_mutex@std@@@std@@QEAA@XZ; std::unique_lock<std::recursive_timed_mutex>::~unique_lock<std::recursive_timed_mutex>(void)
0x180116bd5  nop
0x180116bd6  lea     rdx, [rsp+0C68h+var_AF8]
0x180116bde  lea     rcx, [rsp+0C68h+var_AF8]
0x180116be6  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>> &)
0x180116beb  nop
  ... truncated ...
```
