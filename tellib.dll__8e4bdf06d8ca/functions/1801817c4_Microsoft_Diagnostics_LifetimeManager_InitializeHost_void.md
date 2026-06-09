# Microsoft::Diagnostics::LifetimeManager::InitializeHost(void)

- ea: `0x1801817c4`
- end: `0x1801847ba`
- name: `?InitializeHost@LifetimeManager@Diagnostics@Microsoft@@QEAAXXZ`
- size: `12278`
- prototype: `void __fastcall(Microsoft::Diagnostics::LifetimeManager *__hidden this)`
- caller_count: `1`
- callee_count: `159`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800a2b98`

## callees

- `0x180001bf4`
- `0x180002058`
- `0x180003a00`
- `0x180015884`
- `0x18001d0ec`
- `0x18001d160`
- `0x180020fbc`
- `0x180026ef4`
- `0x1800277e8`
- `0x18003352c`
- `0x180035698`
- `0x1800363b4`
- `0x180038870`
- `0x18003f14c`
- `0x180048ff4`
- `0x1800494d0`
- `0x18004dcf0`
- `0x180052734`
- `0x180053a84`
- `0x18005479c`
- `0x1800552e4`
- `0x18005d050`
- `0x180065dec`
- `0x18006a3e0`
- `0x18006be9c`
- `0x18006dd10`
- `0x18006dd98`
- `0x18006ddbc`
- `0x18006de18`
- `0x18006de38`
- `0x18006e7e4`
- `0x18006ec80`
- `0x18006eec8`
- `0x18006ef00`
- `0x18006f018`
- `0x18006f088`
- `0x18006f0c0`
- `0x18006f0e4`
- `0x18006f140`
- `0x18006f178`
- `0x18006f24c`
- `0x18006f2d4`
- `0x18006f334`
- `0x18006f3f4`
- `0x18006f6c8`
- `0x18006f6f8`
- `0x18006f73c`
- `0x18006fd4c`
- `0x180070040`
- `0x180070128`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@K@Z` at `0x180182ba2`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@K@Z` at `0x180182bc7`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@K@Z` at `0x180182bec`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@K@Z` at `0x180182ba2`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@K@Z` at `0x180182bc7`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@K@Z` at `0x180182bec`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180183eed`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180183fcb`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18018402a`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180183eed`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180183fcb`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18018402a`
- `api-ms-win-core-registry-l1-1-0!RegCopyTreeW` at `0x180181b67`
- `api-ms-win-core-registry-l1-1-0!RegCopyTreeW` at `0x180181b67`
- `ntdll!RtlGetVersion` at `0x180182b83`
- `ntdll!RtlGetVersion` at `0x180182b83`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180182e79`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180182e79`
- `UMPDC!Pdcv2ActivationClientRegister` at `0x180182ef0`
- `UMPDC!Pdcv2ActivationClientRegister` at `0x180182ef0`

## string_xrefs

- `0x180181a53`: `onecore\base\telemetry\utc\service\engine\lifetimemanager.cpp`
- `0x180181a69`: `onecore\base\telemetry\utc\service\engine\lifetimemanager.cpp`
- `0x1801838ba`: `onecore\base\telemetry\utc\service\engine\lifetimemanager.cpp`
- `0x180183e05`: `onecore\base\telemetry\utc\service\engine\lifetimemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=48
void __fastcall Microsoft::Diagnostics::LifetimeManager::InitializeHost(Microsoft::Diagnostics::LifetimeManager *this)
{
  Microsoft::Diagnostics::LifetimeManager *v1; // r15
  Microsoft::Diagnostics::LifetimeManager *v2; // rcx
  int v3; // r8d
  int v4; // r9d
  Microsoft::Diagnostics::DevHealthMonTenant *v5; // rax
  Microsoft::Diagnostics::LifetimeManager *v6; // rcx
  Microsoft::Diagnostics::LifetimeManager *v7; // rcx
  Microsoft::Diagnostics::LifetimeManager *v8; // rcx
  __int64 v9; // r8
  int v10; // eax
  int Key; // eax
  unsigned int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  int v24; // eax
  int v25; // eax
  int v26; // eax
  __int64 MutableDataCollectionRegistryKeyPath; // rax
  __int64 v28; // rax
  int v29; // eax
  int v30; // eax
  int v31; // ecx
  WCHAR *v32; // rcx
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // rdx
  int Directory; // eax
  __int64 v37; // rcx
  __int64 v38; // rcx
  int v39; // eax
  int v40; // eax
  int v41; // eax
  int v42; // eax
  int v43; // eax
  int v44; // eax
  char IsEnabled; // al
  int v46; // eax
  __int64 v47; // rcx
  int v48; // eax
  int v49; // eax
  __int64 v50; // rcx
  int v51; // eax
  int v52; // eax
  int v53; // eax
  int v54; // eax
  int v55; // eax
  int v56; // eax
  int v57; // eax
  int v58; // eax
  int v59; // eax
  int v60; // eax
  int v61; // eax
  int v62; // eax
  int v63; // eax
  int v64; // eax
  int v65; // eax
  int v66; // eax
  int v67; // eax
  int v68; // eax
  int v69; // eax
  int v70; // eax
  int v71; // eax
  int v72; // eax
  __int64 v73; // rax
  __int64 v74; // rax
  __int64 v75; // rax
  __int64 v76; // rax
  __int64 v77; // rdx
  LPCWSTR *v78; // r8
  __int128 *v79; // rcx
  int v80; // ecx
  int v81; // r8d
  int v82; // r9d
  Microsoft::Diagnostics::DevHealthMonTenant *v83; // rax
  LPCWSTR *v84; // rax
  char v85; // bl
  _OWORD *v86; // rax
  int v87; // eax
  const WCHAR *v88; // rcx
  const char *v89; // r9
  int v90; // eax
  __int64 *v91; // rax
  __int64 v92; // rcx
  __int64 *v93; // rax
  __int64 v94; // rcx
  __int64 *v95; // rax
  __int64 v96; // rcx
  __int64 *v97; // rax
  __int64 v98; // rcx
  __int64 v99; // rax
  __int64 *v100; // rax
  __int64 v101; // rcx
  __int64 *v102; // rax
  __int64 v103; // rcx
  __int64 *v104; // rax
  __int64 v105; // rcx
  Microsoft::Diagnostics::EventMonitorManager *v106; // rbx
  __int64 *v107; // rax
  __int64 v108; // rcx
  __int64 v109; // rax
  __int64 v110; // r8
  Microsoft::Diagnostics::LifetimeManager *v111; // rcx
  __int64 v112; // rcx
  int v113; // eax
  __int64 v114; // rdi
  __int64 v115; // rbx
  struct Microsoft::Diagnostics::HeartbeatManager *HeartbeatManager; // rax
  __int64 *v117; // rax
  __int64 v118; // rcx
  __int64 v119; // rdx
  Microsoft::Diagnostics::LifetimeManager *v120; // rcx
  __int64 v121; // rdi
  __int64 v122; // rbx
  struct Microsoft::Diagnostics::HeartbeatManager *v123; // rax
  __int64 v124; // r8
  __int64 *v125; // rax
  __int64 v126; // rcx
  __int64 v127; // rdx
  __int64 *v128; // rax
  __int64 v129; // rcx
  __int64 *v130; // rax
  __int64 v131; // rcx
  bool v132; // dl
  __int64 v133; // rax
  __int64 v134; // rax
  __int64 v135; // rbx
  __int64 v136; // rax
  __int64 *v137; // rax
  __int64 v138; // rcx
  __int64 *v139; // rax
  __int64 v140; // rcx
  __int64 *v141; // rax
  __int64 v142; // rcx
  __int64 v143; // rax
  __int64 *v144; // rax
  __int64 v145; // rcx
  _QWORD *v146; // rax
  __int64 v147; // rax
  __int64 v148; // rax
  __int64 v149; // rdx
  Microsoft::Diagnostics::EnterpriseData *v150; // rcx
  const char *v151; // r9
  int v152; // ecx
  int v153; // r8d
  int v154; // r9d
  Microsoft::Diagnostics::DevHealthMonTenant *v155; // rax
  LPCWSTR *v156; // rax
  __int64 *v157; // rax
  __int64 v158; // rcx
  __int64 v159; // rax
  __int64 matched; // rax
  __int64 v161; // rax
  __int64 *v162; // rax
  __int64 v163; // rcx
  __int64 v164; // rax
  __int64 *v165; // rax
  __int64 v166; // rcx
  __int64 v167; // rax
  __int64 *v168; // rax
  __int64 v169; // rcx
  __int64 v170; // rax
  __int64 v171; // rax
  Microsoft::Diagnostics::ScenariosSqliteTable *v172; // rdi
  __int64 v173; // rax
  __int64 v174; // rax
  __int64 RegistryConfig; // rax
  int v176; // ebx
  __int64 v177; // rax
  __int64 v178; // rax
  __int64 *v179; // rax
  __int64 v180; // rcx
  Microsoft::Diagnostics::RemoteAggregatorManager *v181; // rcx
  const char *v182; // r9
  int v183; // eax
  HANDLE Thread; // rax
  const char *v185; // r9
  Microsoft::Diagnostics::ExporterManager *v186; // rcx
  _QWORD *started; // rbx
  HANDLE v188; // rax
  const char *v189; // r9
  HANDLE v190; // rax
  const char *v191; // r9
  Microsoft::Diagnostics::ApiServer *v192; // rcx
  int v193; // eax
  int v194; // eax
  int v195; // eax
  int v196; // eax
  int v197; // eax
  int v198; // eax
  int v199; // eax
  int v200; // eax
  int v201; // eax
  int v202; // eax
  Microsoft::Diagnostics::UtcWatchdog **v203; // rdi
  __int64 v204; // rbx
  __int64 v205; // r13
  int DwordAsBool; // eax
  int dwCreationFlags; // [rsp+20h] [rbp-768h]
  unsigned int dwCreationFlagsa; // [rsp+20h] [rbp-768h]
  int dwCreationFlagsb; // [rsp+20h] [rbp-768h]
  int dwCreationFlagsc; // [rsp+20h] [rbp-768h]
  int dwCreationFlagsd; // [rsp+20h] [rbp-768h]
  int dwCreationFlagse; // [rsp+20h] [rbp-768h]
  int dwCreationFlagsf; // [rsp+20h] [rbp-768h]
  int dwCreationFlagsg; // [rsp+20h] [rbp-768h]
  int dwCreationFlagsh; // [rsp+20h] [rbp-768h]
  int dwCreationFlagsi; // [rsp+20h] [rbp-768h]
  int dwCreationFlagsj; // [rsp+20h] [rbp-768h]
  int dwCreationFlagsk; // [rsp+20h] [rbp-768h]
  int dwCreationFlagsl; // [rsp+20h] [rbp-768h]
  int dwCreationFlagsm; // [rsp+20h] [rbp-768h]
  int dwCreationFlagsn; // [rsp+20h] [rbp-768h]
  int dwCreationFlagso; // [rsp+20h] [rbp-768h]
  int dwCreationFlagsp; // [rsp+20h] [rbp-768h]
  int dwCreationFlagsq; // [rsp+20h] [rbp-768h]
  int dwCreationFlagsr; // [rsp+20h] [rbp-768h]
  int dwCreationFlagss; // [rsp+20h] [rbp-768h]
  int v227[4]; // [rsp+50h] [rbp-738h] BYREF
  __int64 v228; // [rsp+60h] [rbp-728h]
  bool v229[16]; // [rsp+70h] [rbp-718h] BYREF
  int v230[4]; // [rsp+80h] [rbp-708h] BYREF
  char v231; // [rsp+90h] [rbp-6F8h]
  int v232[4]; // [rsp+A0h] [rbp-6E8h] BYREF
  Microsoft::Diagnostics::DevHealthMonTenant *v233; // [rsp+C0h] [rbp-6C8h] BYREF
  HKEY hKeyDest; // [rsp+C8h] [rbp-6C0h] BYREF
  unsigned int v235[2]; // [rsp+D0h] [rbp-6B8h] BYREF
  unsigned int v236[2]; // [rsp+D8h] [rbp-6B0h] BYREF
  int v237[2]; // [rsp+E0h] [rbp-6A8h] BYREF
  Microsoft::Diagnostics::ScenariosSqliteTable *v238[2]; // [rsp+E8h] [rbp-6A0h] BYREF
  LPVOID *v239; // [rsp+F8h] [rbp-690h] BYREF
  LPVOID *v240; // [rsp+100h] [rbp-688h] BYREF
  __int16 v241; // [rsp+108h] [rbp-680h] BYREF
  char v242; // [rsp+10Ah] [rbp-67Eh]
  bool v243; // [rsp+10Bh] [rbp-67Dh]
  __int128 v244; // [rsp+110h] [rbp-678h] BYREF
  int v245; // [rsp+120h] [rbp-668h] BYREF
  __int64 v246; // [rsp+128h] [rbp-660h] BYREF
  Microsoft::Diagnostics::LifetimeManager *v247; // [rsp+130h] [rbp-658h]
  PSECURITY_DESCRIPTOR v248; // [rsp+138h] [rbp-650h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+140h] [rbp-648h] BYREF
  _QWORD v250[3]; // [rsp+148h] [rbp-640h] BYREF
  __int128 v251; // [rsp+160h] [rbp-628h]
  __int64 v252; // [rsp+170h] [rbp-618h]
  __int128 v253; // [rsp+178h] [rbp-610h]
  __int64 v254; // [rsp+188h] [rbp-600h]
  struct _OSVERSIONINFOW VersionInformation; // [rsp+190h] [rbp-5F8h] BYREF
  __int128 v256; // [rsp+2B0h] [rbp-4D8h] BYREF
  __int64 v257; // [rsp+2C0h] [rbp-4C8h]
  unsigned __int64 v258; // [rsp+2C8h] [rbp-4C0h]
  LPCWSTR lpFileName[3]; // [rsp+2D0h] [rbp-4B8h] BYREF
  unsigned __int64 v260; // [rsp+2E8h] [rbp-4A0h]
  WCHAR Src[16]; // [rsp+2F0h] [rbp-498h] BYREF
  WCHAR v262[8]; // [rsp+310h] [rbp-478h] BYREF
  __int64 v263; // [rsp+320h] [rbp-468h]
  unsigned __int64 v264; // [rsp+328h] [rbp-460h]
  _QWORD v265[4]; // [rsp+330h] [rbp-458h] BYREF
  WCHAR v266[16]; // [rsp+350h] [rbp-438h] BYREF
  WCHAR v267[16]; // [rsp+370h] [rbp-418h] BYREF
  WCHAR v268[16]; // [rsp+390h] [rbp-3F8h] BYREF
  _BYTE v269[16]; // [rsp+3B0h] [rbp-3D8h] BYREF
  _BYTE v270[240]; // [rsp+3C0h] [rbp-3C8h] BYREF
  _BYTE v271[224]; // [rsp+4B0h] [rbp-2D8h] BYREF
  _BYTE v272[224]; // [rsp+590h] [rbp-1F8h] BYREF
  _BYTE v273[224]; // [rsp+670h] [rbp-118h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+788h] [rbp+0h]

  v1 = this;
  v247 = this;
  v246 = 0;
  *(_OWORD *)v227 = *(_OWORD *)&off_18035EE40;
  *(_OWORD *)v230 = *(_OWORD *)&off_180348A48;
  if ( (int)Microsoft::Diagnostics::Utils::Registry::GetQword(-2147483646, v230, v227, &v246) >= 0 )
    _InterlockedExchange((volatile __int32 *)v1, v246);
  Microsoft::Diagnostics::InitialConsentManager::StartupConsentCheck((Microsoft::Diagnostics::LifetimeManager *)((char *)v1 + 8));
  *(_OWORD *)v227 = *(_OWORD *)&Microsoft::Diagnostics::LifetimeManager::k_csVer4_0String;
  std::wstring::wstring((__int64)v265, v227);
  *(_OWORD *)v227 = *(_OWORD *)&off_18035EE30;
  *(_OWORD *)v230 = *(_OWORD *)&off_180348A48;
  Microsoft::Diagnostics::Utils::Registry::GetString(-2147483646, v230, v227, v265);
  if ( (unsigned int)dword_18042D328 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 16) )
  {
    v5 = (Microsoft::Diagnostics::DevHealthMonTenant *)v265;
    if ( v265[3] > 7u )
      v5 = (Microsoft::Diagnostics::DevHealthMonTenant *)v265[0];
    v233 = v5;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
      (unsigned int)&dword_18042D328,
      (unsigned int)&unk_1803C2901,
      v3,
      v4,
      (__int64)&v233);
  }
  v229[0] = 0;
  if ( !Microsoft::Diagnostics::LifetimeManager::WasCleanServiceShutdown(v2) )
  {
    v236[0] = 0;
    v235[0] = 0;
    Microsoft::Diagnostics::LifetimeManager::RecordDirtyShutdown(v6, v236, v235);
    v229[0] = Microsoft::Diagnostics::LifetimeManager::IsResetRequired(v7, v236[0], v235[0]);
    if ( v229[0] )
      Microsoft::Diagnostics::LifetimeManager::ResetState(v8);
  }
  Microsoft::Diagnostics::Utils::General::SetDiagTrackStatus(1);
  hKeyDest = 0;
  v245 = 0;
  *(_OWORD *)v230 = *(_OWORD *)&off_18035EE20;
  *(_QWORD *)v227 = L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Diagnostics\\DiagTrack";
  *(_QWORD *)&v227[2] = 63;
  if ( (int)Microsoft::Diagnostics::Utils::Registry::GetDword(-2147483646, v227, v230, &v245) >= 0 )
  {
    v236[0] = 0;
    *(_OWORD *)v227 = *(_OWORD *)&off_18035EE20;
    *(_OWORD *)v230 = *(_OWORD *)&off_180348A48;
    if ( (int)Microsoft::Diagnostics::Utils::Registry::GetDword(-2147483646, v230, v227, v236) < 0 || v245 != v236[0] )
    {
      *(_OWORD *)v227 = *(_OWORD *)&off_180348A48;
      LOBYTE(v9) = 1;
      v10 = Microsoft::Diagnostics::Utils::Registry::DeleteTree(-2147483646, v227, v9);
      if ( v10 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x17D,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
          (const char *)(unsigned int)v10,
          dwCreationFlags);
    }
  }
  *(_OWORD *)v227 = *(_OWORD *)&off_180348A48;
  if ( (int)Microsoft::Diagnostics::Utils::Registry::OpenKey(HKEY_LOCAL_MACHINE) < 0 )
  {
    *(_OWORD *)v227 = *(_OWORD *)&off_180348A48;
    Key = Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY_LOCAL_MACHINE, 0xF003Fu, 0);
    if ( Key < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x183,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
        (const char *)(unsigned int)Key,
        dwCreationFlagsa);
    std::wstring::wstring((__int64)Src, &off_180348A48);
    Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(Src);
    *(_OWORD *)v230 = *(_OWORD *)std::wstring::operator std::wstring_view(Src, v232);
    *(_QWORD *)v227 = L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Diagnostics\\DiagTrack";
    *(_QWORD *)&v227[2] = 63;
    if ( (unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(v227, v230) )
    {
      v12 = RegCopyTreeW(
              HKEY_LOCAL_MACHINE,
              L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Diagnostics\\DiagTrack",
              hKeyDest);
      if ( v12 )
        wil::details::in1diag3::_Log_Win32(
          retaddr,
          (void *)0x18A,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
          (const char *)v12,
          dwCreationFlagsa);
    }
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
  }
  *(_OWORD *)v227 = *(_OWORD *)&off_18035EE00;
  v13 = Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY_LOCAL_MACHINE, 0xF003Fu, 0);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x18E,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v13,
      dwCreationFlagsb);
  *(_OWORD *)v227 = *(_OWORD *)&off_18035EE10;
  v14 = Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY_LOCAL_MACHINE, 0xF003Fu, 0);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x18F,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v14,
      dwCreationFlagsc);
  *(_OWORD *)v227 = *(_OWORD *)&off_1803487F0;
  v15 = Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY_LOCAL_MACHINE, 0xF003Fu, 0);
  if ( v15 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x190,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v15,
      dwCreationFlagsd);
  *(_OWORD *)v227 = *(_OWORD *)&off_18035EDF0;
  v16 = Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY_LOCAL_MACHINE, 0xF003Fu, 0);
  if ( v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x191,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v16,
      dwCreationFlagse);
  *(_OWORD *)v227 = *(_OWORD *)&off_180347638;
  v17 = Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY_LOCAL_MACHINE, 0xF003Fu, 0);
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x192,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v17,
      dwCreationFlagsf);
  *(_OWORD *)v227 = *(_OWORD *)&off_180347648;
  v18 = Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY_LOCAL_MACHINE, 0xF003Fu, 0);
  if ( v18 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x193,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v18,
      dwCreationFlagsg);
  *(_OWORD *)v227 = *(_OWORD *)&off_1803475F8;
  v19 = Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY_LOCAL_MACHINE, 0xF003Fu, 0);
  if ( v19 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x194,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v19,
      dwCreationFlagsh);
  *(_OWORD *)v227 = *(_OWORD *)&off_180347628;
  v20 = Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY_LOCAL_MACHINE, 0xF003Fu, 0);
  if ( v20 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x195,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v20,
      dwCreationFlagsi);
  *(_OWORD *)v227 = *(_OWORD *)&off_180347608;
  v21 = Microsoft::Diagnostics::Utils::Registry::CreateGuaranteedVolatileKey(retaddr, v227, &hKeyDest);
  if ( v21 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x196,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v21,
      dwCreationFlagsi);
  *(_OWORD *)v227 = *(_OWORD *)&off_18035EDD0;
  v22 = Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY_LOCAL_MACHINE, 0xF003Fu, 0);
  if ( v22 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x197,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v22,
      dwCreationFlagsj);
  *(_OWORD *)v227 = *(_OWORD *)&off_18035EDE0;
  v23 = Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY_LOCAL_MACHINE, 0xF003Fu, 0);
  if ( v23 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x198,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v23,
      dwCreationFlagsk);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UtcExtendedMetricsSupport>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_UtcExtendedMetricsSupport>::GetImpl'::`2'::impl) )
  {
    *(_OWORD *)v227 = *(_OWORD *)&off_18035EDC0;
    v24 = Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY_LOCAL_MACHINE, 0xF003Fu, 0);
    if ( v24 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x19C,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
        (const char *)(unsigned int)v24,
        dwCreationFlagsl);
  }
  *(_OWORD *)v227 = *(_OWORD *)&off_1803475B8;
  Microsoft::Diagnostics::Utils::Os::CreateSecurityDecriptorFromSddl(&SecurityDescriptor);
  *(_QWORD *)v227 = 24;
  *(_QWORD *)&v227[2] = SecurityDescriptor;
  v228 = 0;
  v251 = *(_OWORD *)v227;
  v252 = 0;
  *(_OWORD *)v227 = *(_OWORD *)&off_180347618;
  v25 = Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY_LOCAL_MACHINE, 0xF003Fu, 0);
  if ( v25 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1A2,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v25,
      dwCreationFlagsm);
  *(_OWORD *)v227 = *(_OWORD *)&off_18035EDA0;
  Microsoft::Diagnostics::Utils::Os::CreateSecurityDecriptorFromSddl(&v248);
  *(_QWORD *)v227 = 24;
  *(_QWORD *)&v227[2] = v248;
  v228 = 0;
  v253 = *(_OWORD *)v227;
  v254 = 0;
  *(_OWORD *)v227 = *(_OWORD *)&off_18035EDB0;
  v26 = Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY_LOCAL_MACHINE, 0xF003Fu, 0);
  if ( v26 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1AB,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v26,
      dwCreationFlagsn);
  MutableDataCollectionRegistryKeyPath = Microsoft::Diagnostics::Utils::Os::GetMutableDataCollectionRegistryKeyPath(lpFileName);
  v28 = std::operator+<wchar_t>(Src, MutableDataCollectionRegistryKeyPath, L"\\Users");
  *(_OWORD *)v227 = *(_OWORD *)std::wstring::operator std::wstring_view(v28, v230);
  v29 = Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY_LOCAL_MACHINE, 0xF003Fu, 0);
  if ( v29 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1AE,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v29,
      dwCreationFlagso);
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpFileName);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DmaUtcUpdate>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_DmaUtcUpdate>::GetImpl'::`2'::impl) )
  {
    v30 = Microsoft::Diagnostics::LifetimeManager::PersistDmaApplicabilityToRegistry(v1);
    if ( v30 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1B3,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
        (const char *)(unsigned int)v30,
        dwCreationFlagso);
  }
  v233 = (Microsoft::Diagnostics::DevHealthMonTenant *)&unk_180439960;
  gsl::span<enum gsl::byte const,-1>::span<enum gsl::byte const,-1>(v227, &v233);
  *(_OWORD *)v230 = *(_OWORD *)&off_18035EAB0;
  *(_OWORD *)v232 = *(_OWORD *)&off_180348A48;
  Microsoft::Diagnostics::Utils::Registry::SetBinary(v31, (int)v232, (int)v230, (int)v227, 0);
  std::wstring::wstring((__int64)v262, &off_1803475C8);
  Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(v262);
  v32 = v262;
  if ( v264 > 7 )
    v32 = *(WCHAR **)v262;
  v33 = std::_Traits_rfind_ch<std::char_traits<wchar_t>>(v32, v263, -1, 92);
  if ( v33 == -1 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1BF,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)0x80070057LL,
      dwCreationFlagsp);
  v34 = std::wstring::substr(v262, Src, 0, v33);
  memset(v227, 0, sizeof(v227));
  *(_OWORD *)v230 = *(_OWORD *)std::wstring::operator std::wstring_view(v34, v232);
  LOBYTE(v35) = 1;
  Directory = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v230, v35, v227);
  if ( Directory < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1C0,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)Directory,
      dwCreationFlagsp);
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
  *(_OWORD *)v227 = *(_OWORD *)&off_1803475D8;
  *(_OWORD *)v230 = *(_OWORD *)std::wstring::operator std::wstring_view(v262, v232);
  Microsoft::Diagnostics::LifetimeManager::EnsureAclsOnFolder(v37, v230, v227);
  std::wstring::wstring((__int64)v268, &off_18035ED80);
  Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(v268);
  *(_OWORD *)v227 = *(_OWORD *)&off_18035ED90;
  *(_OWORD *)v230 = *(_OWORD *)std::wstring::operator std::wstring_view(v268, v232);
  Microsoft::Diagnostics::LifetimeManager::EnsureAclsOnFolder(v38, v230, v227);
  *(_OWORD *)v227 = *(_OWORD *)&off_1803475D8;
  *(_OWORD *)v230 = *(_OWORD *)&off_1803475C8;
  v39 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v230, 0, v227);
  if ( v39 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1CC,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v39,
      dwCreationFlagsp);
  memset(v227, 0, sizeof(v227));
  *(_OWORD *)v230 = *(_OWORD *)&off_180347658;
  v40 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v230, 0, v227);
  if ( v40 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1CE,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v40,
      dwCreationFlagsp);
  memset(v227, 0, sizeof(v227));
  *(_OWORD *)v230 = *(_OWORD *)&off_180348B18;
  v41 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v230, 0, v227);
  if ( v41 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1CF,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v41,
      dwCreationFlagsp);
  memset(v227, 0, sizeof(v227));
  *(_OWORD *)v230 = *(_OWORD *)&off_180348B08;
  v42 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v230, 0, v227);
  if ( v42 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1D0,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v42,
      dwCreationFlagsp);
  memset(v227, 0, sizeof(v227));
  *(_OWORD *)v230 = *(_OWORD *)&off_18035ED70;
  v43 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v230, 0, v227);
  if ( v43 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1D1,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v43,
      dwCreationFlagsp);
  memset(v227, 0, sizeof(v227));
  *(_OWORD *)v230 = *(_OWORD *)&off_180348B28;
  v44 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v230, 0, v227);
  if ( v44 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1D2,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v44,
      dwCreationFlagsp);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UsageAndQualityInsights>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_UsageAndQualityInsights>::GetImpl'::`2'::impl) )
  {
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_UtcExtendedMetricsSupport>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_UtcExtendedMetricsSupport>::GetImpl'::`2'::impl);
    *(_OWORD *)v227 = *(_OWORD *)&off_18035ED60;
    if ( IsEnabled )
    {
      *(_OWORD *)v230 = *(_OWORD *)&off_18035ED40;
      v49 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v230, 0, v227);
      if ( v49 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1D8,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
          (const char *)(unsigned int)v49,
          dwCreationFlagsp);
      std::wstring::wstring((__int64)Src, &off_18035ED40);
      Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(Src);
      *(_OWORD *)v227 = *(_OWORD *)&off_18035ED60;
      *(_OWORD *)v230 = *(_OWORD *)std::wstring::operator std::wstring_view(Src, v232);
      Microsoft::Diagnostics::LifetimeManager::EnsureAclsOnFolder(v50, v230, v227);
    }
    else
    {
      *(_OWORD *)v230 = *(_OWORD *)&off_180348B28;
      v46 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v230, 0, v227);
      if ( v46 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1DF,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
          (const char *)(unsigned int)v46,
          dwCreationFlagsp);
      std::wstring::wstring((__int64)Src, &off_180348B28);
      Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(Src);
      *(_OWORD *)v227 = *(_OWORD *)&off_18035ED60;
      *(_OWORD *)v230 = *(_OWORD *)std::wstring::operator std::wstring_view(Src, v232);
      Microsoft::Diagnostics::LifetimeManager::EnsureAclsOnFolder(v47, v230, v227);
    }
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
  }
  else
  {
    memset(v227, 0, sizeof(v227));
    *(_OWORD *)v230 = *(_OWORD *)&off_180348B28;
    v51 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v230, 0, v227);
    if ( v51 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1E8,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
        (const char *)(unsigned int)v51,
        dwCreationFlagsp);
  }
  memset(v227, 0, sizeof(v227));
  *(_OWORD *)v230 = *(_OWORD *)&off_18035ED50;
  v48 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v230, 0, v227);
  if ( v48 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1EB,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v48,
      dwCreationFlagsp);
  memset(v227, 0, sizeof(v227));
  *(_OWORD *)v230 = *(_OWORD *)&off_18035ED30;
  v52 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v230, 0, v227);
  if ( v52 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1EC,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v52,
      dwCreationFlagsp);
  memset(v227, 0, sizeof(v227));
  *(_OWORD *)v230 = *(_OWORD *)&Microsoft::Diagnostics::AlternativeSlot::k_traceProfileLocalStoreDirectory;
  v53 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v230, 0, v227);
  if ( v53 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1ED,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v53,
      dwCreationFlagsp);
  memset(v227, 0, sizeof(v227));
  *(_OWORD *)v230 = *(_OWORD *)&Microsoft::Diagnostics::ETWConsumer::k_etlFilesPath;
  v54 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v230, 0, v227);
  if ( v54 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1EE,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v54,
      dwCreationFlagsp);
  memset(v227, 0, sizeof(v227));
  *(_OWORD *)v230 = *(_OWORD *)&Microsoft::Diagnostics::ETWConsumer::k_autologgerFilesPath;
  v55 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v230, 0, v227);
  if ( v55 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1EF,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v55,
      dwCreationFlagsp);
  memset(v227, 0, sizeof(v227));
  *(_OWORD *)v230 = *(_OWORD *)&Microsoft::Diagnostics::ETWConsumer::k_dtShutdownLoggerStorePath;
  v56 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v230, 0, v227);
  if ( v56 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1F0,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v56,
      dwCreationFlagsp);
  memset(v227, 0, sizeof(v227));
  *(_OWORD *)v230 = *(_OWORD *)&off_18035ED00;
  v57 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v230, 0, v227);
  if ( v57 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1F1,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v57,
      dwCreationFlagsp);
  memset(v227, 0, sizeof(v227));
  *(_OWORD *)v230 = *(_OWORD *)&off_18035ECD0;
  v58 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v230, 0, v227);
  if ( v58 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1F2,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v58,
      dwCreationFlagsp);
  memset(v227, 0, sizeof(v227));
  *(_OWORD *)v230 = *(_OWORD *)&off_18035ECE0;
  v59 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v230, 0, v227);
  if ( v59 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1F3,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v59,
      dwCreationFlagsp);
  memset(v227, 0, sizeof(v227));
  *(_OWORD *)v230 = *(_OWORD *)&off_18035ECB0;
  v60 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v230, 0, v227);
  if ( v60 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1F4,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v60,
      dwCreationFlagsp);
  *(_OWORD *)v227 = *(_OWORD *)&off_18035ED90;
  *(_OWORD *)v230 = *(_OWORD *)&off_18035ED80;
  v61 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v230, 0, v227);
  if ( v61 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1F5,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v61,
      dwCreationFlagsp);
  memset(v227, 0, sizeof(v227));
  *(_OWORD *)v230 = *(_OWORD *)&off_18035EE70;
  v62 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v230, 0, v227);
  if ( v62 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1F6,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v62,
      dwCreationFlagsp);
  memset(v227, 0, sizeof(v227));
  *(_OWORD *)v230 = *(_OWORD *)&off_18035ECC0;
  v63 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v230, 0, v227);
  if ( v63 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1F7,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v63,
      dwCreationFlagsp);
  memset(v227, 0, sizeof(v227));
  *(_OWORD *)v230 = *(_OWORD *)&off_18035EC90;
  v64 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v230, 0, v227);
  if ( v64 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1F8,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v64,
      dwCreationFlagsp);
  std::wstring::wstring((__int64)v267, &off_18035ECA0);
  Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(v267);
  *(_OWORD *)v227 = *(_OWORD *)std::wstring::operator std::wstring_view(v267, v230);
  v65 = Microsoft::Diagnostics::Utils::FileSystem::RecursivelyDeleteDirectory();
  if ( v65 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1FE,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v65,
      dwCreationFlagsp);
  memset(v227, 0, sizeof(v227));
  *(_OWORD *)v230 = *(_OWORD *)&off_18035ECA0;
  v66 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v230, 0, v227);
  if ( v66 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x200,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v66,
      dwCreationFlagsp);
  *(_OWORD *)v227 = *(_OWORD *)&off_1803475E8;
  v67 = Microsoft::Diagnostics::Utils::FileSystem::RecursivelyDeleteDirectory();
  if ( v67 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x203,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v67,
      dwCreationFlagsp);
  memset(v227, 0, sizeof(v227));
  *(_OWORD *)v230 = *(_OWORD *)&off_1803475E8;
  v68 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v230, 0, v227);
  if ( v68 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x204,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v68,
      dwCreationFlagsp);
  *(_OWORD *)v227 = *(_OWORD *)&off_18035EC70;
  v69 = Microsoft::Diagnostics::Utils::FileSystem::RecursivelyDeleteDirectory();
  if ( v69 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x207,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v69,
      dwCreationFlagsp);
  memset(v227, 0, sizeof(v227));
  *(_OWORD *)v230 = *(_OWORD *)&off_18035EC70;
  v70 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v230, 0, v227);
  if ( v70 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x208,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v70,
      dwCreationFlagsp);
  *(_OWORD *)v227 = *(_OWORD *)&off_18035EC80;
  v71 = Microsoft::Diagnostics::Utils::FileSystem::RecursivelyDeleteDirectory();
  if ( v71 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x20B,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v71,
      dwCreationFlagsp);
  memset(v227, 0, sizeof(v227));
  *(_OWORD *)v230 = *(_OWORD *)&off_18035EC80;
  v72 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v230, 0, v227);
  if ( v72 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x20C,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v72,
      dwCreationFlagsp);
  std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v269);
  memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
  VersionInformation.dwOSVersionInfoSize = 284;
  if ( RtlGetVersion(&VersionInformation) < 0 )
  {
    std::operator<<<std::char_traits<char>>(v270, "0.0.0");
  }
  else
  {
    v73 = std::ostream::operator<<(v270, VersionInformation.dwMajorVersion);
    v74 = std::operator<<<std::char_traits<char>>(v73, ".");
    v75 = std::ostream::operator<<(v74, VersionInformation.dwMinorVersion);
    v76 = std::operator<<<std::char_traits<char>>(v75, ".");
    std::ostream::operator<<(v76, VersionInformation.dwBuildNumber);
  }
  std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::str(v269, lpFileName);
  std::wstring::wstring((__int64)Src, &off_18035EEA0);
  Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(Src);
  std::string::string(&v256);
  *(_OWORD *)v227 = *(_OWORD *)std::wstring::operator std::wstring_view(Src, v230);
  if ( (int)Microsoft::Diagnostics::Utils::FileSystem::ReadStringFromFile(v227, v77, 0xFFFFFFFFLL, &v256) < 0 )
    goto LABEL_253;
  v78 = lpFileName;
  if ( v260 > 0xF )
    v78 = (LPCWSTR *)lpFileName[0];
  v79 = &v256;
  if ( v258 > 0xF )
    v79 = (__int128 *)v256;
  if ( (unsigned __int8)std::_Traits_equal<std::char_traits<char>>(v79, v257, v78, lpFileName[2]) )
  {
    v231 = 0;
    if ( (unsigned int)dword_18042D328 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 16) )
    {
      v83 = (Microsoft::Diagnostics::DevHealthMonTenant *)&v256;
      if ( v258 > 0xF )
        v83 = (Microsoft::Diagnostics::DevHealthMonTenant *)v256;
      v233 = v83;
      v84 = lpFileName;
      if ( v260 > 0xF )
        v84 = (LPCWSTR *)lpFileName[0];
      *(_QWORD *)v237 = v84;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v80,
        (unsigned int)&unk_1803C25EA,
        v81,
        v82,
        (__int64)v237,
        (__int64)&v233);
    }
    v85 = v231;
  }
  else
  {
LABEL_253:
    if ( (unsigned int)dword_18042D328 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 16) )
    {
      v155 = (Microsoft::Diagnostics::DevHealthMonTenant *)&v256;
      if ( v258 > 0xF )
        v155 = (Microsoft::Diagnostics::DevHealthMonTenant *)v256;
      v233 = v155;
      v156 = lpFileName;
      if ( v260 > 0xF )
        v156 = (LPCWSTR *)lpFileName[0];
      *(_QWORD *)v237 = v156;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v152,
        (unsigned int)&unk_1803C263D,
        v153,
        v154,
        (__int64)v237,
        (__int64)&v233);
    }
    v85 = 1;
    v231 = 1;
  }
  v86 = (_OWORD *)gslp::container_to_bytes<std::string>(v238, lpFileName);
  *(_QWORD *)v227 = &::Src;
  *(_QWORD *)&v227[2] = 0;
  *(_OWORD *)v230 = *v86;
  *(_OWORD *)v232 = *(_OWORD *)std::wstring::operator std::wstring_view(Src, &v244);
  v87 = Microsoft::Diagnostics::Utils::FileSystem::WriteBytesToFile(v232, v230, v227);
  if ( v87 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x24A,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v87,
      dwCreationFlagsp);
  std::string::_Tidy_deallocate(&v256);
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
  std::string::_Tidy_deallocate(lpFileName);
  std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::`vbase destructor'(v269);
  if ( v85 )
  {
    std::wstring::wstring(
      (__int64)lpFileName,
      &Microsoft::Diagnostics::ETWConsumer::k_dtAutoLoggerShutdownOutputLocation);
    Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString((LPCWSTR)lpFileName);
    v88 = (const WCHAR *)lpFileName;
    if ( v260 > 7 )
      v88 = lpFileName[0];
    if ( !DeleteFileW(v88) )
      wil::details::in1diag3::_Log_GetLastError(
        retaddr,
        (void *)0x252,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
        v89);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpFileName);
  }
  v250[0] = 1;
  v250[1] = &Microsoft::Diagnostics::PdcNetworkActivation::PdcActivatorCallback;
  v250[2] = 0;
  wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&long Pdcv2ActivationClientUnregister(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    (char *)v1 + 2264,
    0);
  v90 = Pdcv2ActivationClientRegister(77, v250, (char *)v1 + 2264);
  if ( v90 < 0 )
    wil::details::in1diag3::_Log_NtStatus(
      retaddr,
      (void *)0x25B,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v90,
      dwCreationFlagsp);
  Microsoft::CommonDatapoints::UpdateStaticCommonDatapointsInRegistry();
  v91 = (__int64 *)std::make_unique<Microsoft::Diagnostics::UserManager,,0>(&v233);
  v92 = *v91;
  *v91 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 262, v92);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(&v233);
  v241 = 1;
  v242 = 0;
  v243 = v229[0];
  v93 = (__int64 *)std::make_unique<Microsoft::Diagnostics::SettingsManager,Microsoft::Diagnostics::SettingsManagerConfig &,0>(
                     &v239,
                     &v241);
  v94 = *v93;
  *v93 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 235, v94);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(&v239);
  v95 = (__int64 *)std::make_unique<Microsoft::Diagnostics::SevilleEventlogManager,,0>(&v240);
  v96 = *v95;
  *v95 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 271, v96);
  std::unique_ptr<Microsoft::Diagnostics::SevilleEventlogManager>::~unique_ptr<Microsoft::Diagnostics::SevilleEventlogManager>(&v240);
  v97 = (__int64 *)std::make_unique<Microsoft::Diagnostics::SyntheticAggregationManager,,0>(v236);
  v98 = *v97;
  *v97 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 278, v98);
  std::unique_ptr<Microsoft::Diagnostics::SyntheticAggregationManager>::~unique_ptr<Microsoft::Diagnostics::SyntheticAggregationManager>(v236);
  v99 = std::make_unique<Microsoft::Diagnostics::ProxySourceRegistry,,0>(v235);
  v100 = (__int64 *)std::make_unique<Microsoft::Diagnostics::SystemStateManager,std::unique_ptr<Microsoft::Diagnostics::ProxySourceMutable>,0>(
                      &v233,
                      v99);
  v101 = *v100;
  *v100 = 0;
  *(_QWORD *)v227 = (char *)v1 + 2064;
  _InterlockedExchange64((volatile __int64 *)v1 + 258, v101);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(&v233);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(v235);
  LOBYTE(v235[0]) = 1;
  v102 = (__int64 *)std::make_unique<Microsoft::Diagnostics::HeartbeatManager,bool,wil::basic_zstring_view<wchar_t> const &,std::bitset<9> const &,0>(
                      &v256,
                      v235,
                      &Microsoft::Diagnostics::HeartBeat::k_defaultHeartBeatName,
                      &Microsoft::Diagnostics::HeartBeat::k_defaultHeartBeatSections);
  v103 = *v102;
  *v102 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 254, v103);
  std::unique_ptr<Microsoft::Diagnostics::HeartbeatManager>::~unique_ptr<Microsoft::Diagnostics::HeartbeatManager>(&v256);
  v104 = (__int64 *)std::make_unique<Microsoft::Diagnostics::PrivacyKeyManager,,0>(&v244);
  v105 = *v104;
  *v104 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 246, v105);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(&v244);
  v106 = (Microsoft::Diagnostics::EventMonitorManager *)operator new(0x550u);
  *(_QWORD *)v230 = v106;
  *(_OWORD *)v232 = *(_OWORD *)std::wstring::operator std::wstring_view(&unk_18043C260, &v244);
  Microsoft::Diagnostics::EventMonitorManager::EventMonitorManager(v106);
  *(_QWORD *)&v244 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 264, (__int64)v106);
  std::unique_ptr<Microsoft::Diagnostics::EventMonitorManager>::~unique_ptr<Microsoft::Diagnostics::EventMonitorManager>(&v244);
  v107 = (__int64 *)std::make_unique<Microsoft::Diagnostics::EnterpriseData,,0>(v238);
  v108 = *v107;
  *v107 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 251, v108);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(v238);
  *(_QWORD *)v230 = operator new(0x108u);
  v109 = Microsoft::Diagnostics::RegionMetadata::RegionMetadata(*(Microsoft::Diagnostics::RegionMetadata **)v230);
  v238[0] = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 282, v109);
  std::unique_ptr<Microsoft::Diagnostics::RegionMetadata>::~unique_ptr<Microsoft::Diagnostics::RegionMetadata>(v238);
  v236[0] = 0;
  *(_OWORD *)v230 = *(_OWORD *)&off_18035EE90;
  *(_OWORD *)v232 = *(_OWORD *)&off_180348A48;
  Microsoft::Diagnostics::DynamicConfig<unsigned long>::CreateRegistryConfig(
    (unsigned int)v273,
    (unsigned int)v236,
    (unsigned int)v232,
    (unsigned int)v230,
    0);
  LODWORD(v233) = Microsoft::Diagnostics::DynamicConfig<unsigned long>::Get(v273);
  LOBYTE(v110) = 1;
  Microsoft::Diagnostics::LifetimeManager::GetAuthorizationInfo(v1, v237, v110);
  v111 = (Microsoft::Diagnostics::LifetimeManager *)*((unsigned int *)v1 + 568);
  if ( ((unsigned __int8)v111 & 4) == 0 )
  {
    v112 = (unsigned int)dword_18042D328;
    if ( (unsigned int)dword_18042D328 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 16) )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        &dword_18042D328,
        &unk_1803C2567);
    *(_OWORD *)v230 = *(_OWORD *)&off_180348A78;
    *(_OWORD *)v232 = *(_OWORD *)&off_180348A48;
    v113 = Microsoft::Diagnostics::Utils::Registry::DeleteValue(v112, v232, v230);
    v111 = retaddr;
    if ( v113 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x297,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
        (const char *)(unsigned int)v113,
        dwCreationFlagsq);
  }
  v237[0] = Microsoft::Diagnostics::LifetimeManager::GetUtcDefaultEventStoreSize(v111);
  std::wstring::wstring((__int64)v266, &off_180347658);
  Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(v266);
  v114 = std::make_unique<Microsoft::Diagnostics::XboxToastEventStoreUsageCallback,,0>(&v244);
  LOWORD(v235[0]) = 256;
  *(_QWORD *)v230 = v235;
  *(_QWORD *)&v230[2] = (char *)v235 + 2;
  v115 = std::vector<Microsoft::Diagnostics::StorageBufferType>::vector<Microsoft::Diagnostics::StorageBufferType>(
           v232,
           v230);
  v236[0] = Microsoft::Diagnostics::AsimovEventBuffer::GetEventBufferMaxBytes();
  LODWORD(v240) = Microsoft::Diagnostics::AsimovEventBuffer::GetCriticalEventBufferMaxEvents();
  LODWORD(v239) = Microsoft::Diagnostics::AsimovEventBuffer::GetNormalEventBufferMaxEvents();
  HeartbeatManager = Microsoft::Diagnostics::LifetimeManager::GetHeartbeatManager(v1);
  v117 = (__int64 *)std::make_unique<Microsoft::Diagnostics::SqliteEventStore,Microsoft::Diagnostics::HeartBeat &,std::wstring &,unsigned long &,unsigned long,unsigned long,unsigned long,std::vector<Microsoft::Diagnostics::StorageBufferType> &,std::unique_ptr<Microsoft::Diagnostics::SevilleEventStoreUsageCallback>,0>(
                      v238,
                      HeartbeatManager,
                      v266,
                      v237,
                      &v239,
                      &v240,
                      v236,
                      v115,
                      v114);
  v118 = *v117;
  *v117 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 244, v118);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(v238);
  std::vector<unsigned char>::_Tidy(v232, v119);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(&v244);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_LocalEncryptCertRemoval>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_LocalEncryptCertRemoval>::GetImpl'::`2'::impl) )
  {
    v236[0] = Microsoft::Diagnostics::LifetimeManager::GetUtcDefaultInMemoryEventStoreSize(v120);
    v121 = std::make_unique<Microsoft::Diagnostics::XboxToastEventStoreUsageCallback,,0>(&v244);
    LOWORD(v235[0]) = 256;
    *(_QWORD *)v230 = v235;
    *(_QWORD *)&v230[2] = (char *)v235 + 2;
    v122 = std::vector<Microsoft::Diagnostics::StorageBufferType>::vector<Microsoft::Diagnostics::StorageBufferType>(
             v232,
             v230);
    v237[0] = 102400;
    LODWORD(v239) = 50;
    LODWORD(v240) = 0;
    v123 = Microsoft::Diagnostics::LifetimeManager::GetHeartbeatManager(v1);
    v125 = (__int64 *)std::make_unique<Microsoft::Diagnostics::SqliteEventStore,Microsoft::Diagnostics::HeartBeat &,wchar_t const (&)[1],unsigned long const &,unsigned long,unsigned long,unsigned long,std::vector<Microsoft::Diagnostics::StorageBufferType>,std::unique_ptr<Microsoft::Diagnostics::XboxToastEventStoreUsageCallback>,0>(
                        v238,
                        v123,
                        v124,
                        v236,
                        &v240,
                        &v239,
                        v237,
                        v122,
                        v121);
    v126 = *v125;
    *v125 = 0;
    _InterlockedExchange64((volatile __int64 *)v1 + 245, v126);
    std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(v238);
    std::vector<unsigned char>::_Tidy(v232, v127);
    std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(&v244);
    if ( (unsigned int)dword_18042D328 > 4 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_18042D328, 48) )
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
          &dword_18042D328,
          &unk_1803C252F);
    }
  }
  v128 = (__int64 *)std::make_unique<Microsoft::Diagnostics::ScenarioCounterStorage,,0>(v238);
  v129 = *v128;
  *v128 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 249, v129);
  std::unique_ptr<Microsoft::Diagnostics::ScenarioCounterStorage>::~unique_ptr<Microsoft::Diagnostics::ScenarioCounterStorage>(v238);
  v130 = (__int64 *)std::make_unique<Microsoft::Diagnostics::LatencyData,,0>(&v244);
  v131 = *v130;
  *v130 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 255, v131);
  std::unique_ptr<Microsoft::Diagnostics::LatencyData>::~unique_ptr<Microsoft::Diagnostics::LatencyData>(&v244);
  *(_QWORD *)v230 = operator new(0x620u);
  v133 = Microsoft::Diagnostics::UsageAnalyzer::UsageAnalyzer(*(Microsoft::Diagnostics::UsageAnalyzer **)v230, v132);
  v238[0] = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 259, v133);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(v238);
  *(_QWORD *)v230 = operator new(0xB70u);
  v134 = Microsoft::Diagnostics::EventTranscriptManager::EventTranscriptManager(*(Microsoft::Diagnostics::EventTranscriptManager **)v230);
  v238[0] = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 260, v134);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(v238);
  *(_QWORD *)v230 = operator new(0x2A0u);
  v135 = Microsoft::Diagnostics::AsimovEndpointConfig::AsimovEndpointConfig(*(Microsoft::Diagnostics::AsimovEndpointConfig **)v230);
  v240 = (LPVOID *)v135;
  *(_QWORD *)v230 = operator new(0x330u);
  *(_QWORD *)v237 = 0;
  v240 = 0;
  v239 = (LPVOID *)v135;
  v136 = Microsoft::Diagnostics::AsimovUploadQueue::AsimovUploadQueue(*(_QWORD *)v230, &v239, v237, 180000);
  v238[0] = 0;
  *(_QWORD *)v230 = (char *)v1 + 2016;
  _InterlockedExchange64((volatile __int64 *)v1 + 252, v136);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(v238);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(&v240);
  v137 = (__int64 *)std::make_unique<Microsoft::Diagnostics::AsimovEventSerializer,,0>(&v256);
  v138 = *v137;
  *v137 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 253, v138);
  std::unique_ptr<Microsoft::Diagnostics::AsimovEventSerializer>::~unique_ptr<Microsoft::Diagnostics::AsimovEventSerializer>(&v256);
  v139 = (__int64 *)std::make_unique<Microsoft::Diagnostics::KillSwitchManager,,0>(v236);
  v140 = *v139;
  *v139 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 270, v140);
  std::unique_ptr<Microsoft::Diagnostics::KillSwitchManager>::~unique_ptr<Microsoft::Diagnostics::KillSwitchManager>(v236);
  v141 = (__int64 *)std::make_unique<Microsoft::Diagnostics::EscalationEngine,,0>(v235);
  v142 = *v141;
  *v141 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 247, v142);
  std::unique_ptr<Microsoft::Diagnostics::EscalationEngine>::~unique_ptr<Microsoft::Diagnostics::EscalationEngine>(v235);
  v238[0] = (Microsoft::Diagnostics::ScenariosSqliteTable *)operator new(0x138u);
  v244 = *(_OWORD *)&off_18035ED70;
  v143 = Microsoft::Diagnostics::ScenariosSqliteTable::ScenariosSqliteTable(v238[0]);
  v238[0] = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 273, v143);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(v238);
  v144 = (__int64 *)std::make_unique<Microsoft::Diagnostics::ScenarioObjectCache,,0>(v232);
  v145 = *v144;
  *v144 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 274, v145);
  std::unique_ptr<Microsoft::Diagnostics::ScenarioObjectCache>::~unique_ptr<Microsoft::Diagnostics::ScenarioObjectCache>(v232);
  v146 = operator new(8u);
  *v146 = &Microsoft::Diagnostics::ScenarioStorageSql::`vftable';
  *(_QWORD *)v232 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 257, (__int64)v146);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(v232);
  *(_QWORD *)v232 = operator new(0x220u);
  v147 = Microsoft::Diagnostics::ScenarioCacheLRU::ScenarioCacheLRU(*(Microsoft::Diagnostics::ScenarioCacheLRU **)v232);
  *(_QWORD *)v232 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 256, v147);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(v232);
  *(_QWORD *)v232 = operator new(0x528u);
  v148 = Microsoft::Diagnostics::ScenarioManager::ScenarioManager(*(Microsoft::Diagnostics::ScenarioManager **)v232);
  *(_QWORD *)v232 = 0;
  *(_QWORD *)v236 = (char *)v1 + 1904;
  _InterlockedExchange64((volatile __int64 *)v1 + 238, v148);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(v232);
  if ( *((_BYTE *)v1 + 2278) )
    *(_BYTE *)(*((_QWORD *)v1 + 238) + 618LL) = 1;
  LOBYTE(v149) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_DpswOneSettingsControl>::ReportUsage(
    &`wil::Feature<__WilFeatureTraits_Feature_DpswOneSettingsControl>::GetImpl'::`2'::impl,
    v149);
  v150 = (Microsoft::Diagnostics::EnterpriseData *)*((_QWORD *)v1 + 251);
  if ( v150 )
  {
    try
    {
      Microsoft::Diagnostics::EnterpriseData::Initialize(v150);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x2EF,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
        v151);
      v1 = v247;
    }
  }
  v157 = (__int64 *)std::make_unique<Microsoft::Diagnostics::TelemetryAssert,,0>(v232);
  v158 = *v157;
  *v157 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 266, v158);
  std::unique_ptr<Microsoft::Diagnostics::TelemetryAssert>::~unique_ptr<Microsoft::Diagnostics::TelemetryAssert>(v232);
  *(_QWORD *)v232 = operator new(0x48u);
  v159 = Microsoft::Diagnostics::OsEvents::OsEvents(*(Microsoft::Diagnostics::OsEvents **)v232);
  *(_QWORD *)v232 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 242, v159);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(v232);
  *(_QWORD *)v232 = operator new(0x188u);
  matched = Microsoft::Diagnostics::MatchEngine::MatchEngine(*(Microsoft::Diagnostics::MatchEngine **)v232);
  *(_QWORD *)v232 = 0;
  v240 = (LPVOID *)((char *)v1 + 1888);
  _InterlockedExchange64((volatile __int64 *)v1 + 236, matched);
  std::unique_ptr<Microsoft::Diagnostics::MatchEngine>::~unique_ptr<Microsoft::Diagnostics::MatchEngine>(v232);
  *(_QWORD *)v232 = operator new(0x440u);
  v161 = Microsoft::Diagnostics::TriggerListener::TriggerListener(*(Microsoft::Diagnostics::TriggerListener **)v232);
  *(_QWORD *)v232 = 0;
  v239 = (LPVOID *)((char *)v1 + 1920);
  _InterlockedExchange64((volatile __int64 *)v1 + 240, v161);
  std::unique_ptr<Microsoft::Diagnostics::TriggerListener>::~unique_ptr<Microsoft::Diagnostics::TriggerListener>(v232);
  v162 = (__int64 *)std::make_unique<Microsoft::Diagnostics::TraceManager,,0>(v238);
  v163 = *v162;
  *v162 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 248, v163);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(v238);
  *(_QWORD *)v232 = operator new(0x158u);
  v164 = Microsoft::Diagnostics::MetadataEngine::MetadataEngine(*(Microsoft::Diagnostics::MetadataEngine **)v232, 0);
  *(_QWORD *)v232 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 250, v164);
  std::unique_ptr<Microsoft::Diagnostics::MetadataEngine>::~unique_ptr<Microsoft::Diagnostics::MetadataEngine>(v232);
  v165 = (__int64 *)std::make_unique<Microsoft::Diagnostics::DTraceManager,,0>(&v244);
  v166 = *v165;
  *v165 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 276, v166);
  std::unique_ptr<Microsoft::Diagnostics::DTraceManager>::~unique_ptr<Microsoft::Diagnostics::DTraceManager>(&v244);
  *(_QWORD *)v232 = operator new(0x80u);
  v167 = Microsoft::Diagnostics::PiiScrubberManager::PiiScrubberManager(*(Microsoft::Diagnostics::PiiScrubberManager **)v232);
  *(_QWORD *)v232 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 277, v167);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(v232);
  v168 = (__int64 *)std::make_unique<Microsoft::Diagnostics::UtcWatchdog,,0>(&v256);
  v169 = *v168;
  *v168 = 0;
  *(_QWORD *)v235 = (char *)v1 + 2152;
  _InterlockedExchange64((volatile __int64 *)v1 + 269, v169);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(&v256);
  *(_QWORD *)v232 = operator new(0x10u);
  v170 = Microsoft::Diagnostics::TenantManager::TenantManager(*(Microsoft::Diagnostics::TenantManager **)v232);
  *(_QWORD *)v232 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 263, v170);
  std::unique_ptr<Microsoft::Diagnostics::TenantManager>::~unique_ptr<Microsoft::Diagnostics::TenantManager>(v232);
  *(_QWORD *)v232 = operator new(0x400u);
  v171 = Microsoft::Diagnostics::UtcApiManager::UtcApiManager(*(Microsoft::Diagnostics::UtcApiManager **)v232);
  *(_QWORD *)v232 = 0;
  v172 = (Microsoft::Diagnostics::LifetimeManager *)((char *)v1 + 2088);
  v238[0] = (Microsoft::Diagnostics::LifetimeManager *)((char *)v1 + 2088);
  _InterlockedExchange64((volatile __int64 *)v1 + 261, v171);
  std::unique_ptr<Microsoft::Diagnostics::AgentUtcApiManager>::~unique_ptr<Microsoft::Diagnostics::AgentUtcApiManager>(v232);
  *(_QWORD *)v232 = operator new(0x930u);
  v244 = *(_OWORD *)&Microsoft::Diagnostics::ETWConsumer::k_dtSessionName;
  v173 = Microsoft::Diagnostics::TriggerAggregator::TriggerAggregator(*(_QWORD *)v232, &v244);
  *(_QWORD *)v232 = 0;
  *(_QWORD *)&v244 = (char *)v1 + 2240;
  _InterlockedExchange64((volatile __int64 *)v1 + 280, v173);
  std::unique_ptr<Microsoft::Diagnostics::TriggerAggregator>::~unique_ptr<Microsoft::Diagnostics::TriggerAggregator>(v232);
  *(_QWORD *)v232 = operator new(0x90u);
  v174 = Microsoft::Diagnostics::AggregatedEventManager::AggregatedEventManager(*(Microsoft::Diagnostics::AggregatedEventManager **)v232);
  *(_QWORD *)v232 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 281, v174);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(v232);
  v237[0] = 0;
  *(_OWORD *)v232 = *(_OWORD *)&off_18035EC30;
  v256 = *(_OWORD *)&off_180348A48;
  RegistryConfig = Microsoft::Diagnostics::DynamicConfig<unsigned long>::CreateRegistryConfig(
                     (unsigned int)v269,
                     (unsigned int)v237,
                     (unsigned int)&v256,
                     (unsigned int)v232,
                     0);
  v176 = Microsoft::Diagnostics::DynamicConfig<unsigned long>::Get(RegistryConfig);
  Microsoft::Diagnostics::DynamicConfig<unsigned long>::~DynamicConfig<unsigned long>((struct Microsoft::Diagnostics::ISettingReceiver *)v269);
  if ( v176 == 1 )
  {
    *(_QWORD *)v232 = operator new(0xE8u);
    v177 = Microsoft::Diagnostics::ExporterManager::ExporterManager(*(Microsoft::Diagnostics::ExporterManager **)v232);
    *(_QWORD *)v232 = 0;
    _InterlockedExchange64((volatile __int64 *)v1 + 279, v177);
    std::unique_ptr<Microsoft::Diagnostics::ExporterManager>::~unique_ptr<Microsoft::Diagnostics::ExporterManager>(v232);
  }
  else if ( (unsigned int)dword_18042D328 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 16) )
  {
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_18042D328,
      &unk_1803C24FC);
  }
  *(_QWORD *)v232 = operator new(0x8D8u);
  v178 = Microsoft::Diagnostics::RemoteAggregatorManager::RemoteAggregatorManager(*(Microsoft::Diagnostics::RemoteAggregatorManager **)v232);
  *(_QWORD *)v232 = 0;
  _InterlockedExchange64((volatile __int64 *)v1 + 275, v178);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(v232);
  if ( *((_BYTE *)v1 + 2288)
    || (_DWORD)v233 != *((_DWORD *)v1 + 568)
    && (*((_DWORD *)v1 + 568) & 8) == 0
    && (*((_DWORD *)v1 + 568) & 0x400) == 0
    && ((unsigned __int8)v233 & 4) != 0 )
  {
    Microsoft::Diagnostics::LifetimeManager::ClearEventStoresOnOptInChange(v1);
  }
  LODWORD(v233) = 0;
  *(_OWORD *)v232 = *(_OWORD *)&off_18035EC20;
  v256 = *(_OWORD *)&off_180348A48;
  Microsoft::Diagnostics::DynamicConfig<unsigned long>::CreateRegistryConfig(
    (unsigned int)v272,
    (unsigned int)&v233,
    (unsigned int)&v256,
    (unsigned int)v232,
    0);
  if ( (unsigned int)Microsoft::Diagnostics::DynamicConfig<unsigned long>::Get(v272) != 1 )
  {
    v179 = (__int64 *)std::make_unique<Microsoft::Diagnostics::AgentManager,,0>(v232);
    v180 = *v179;
    *v179 = 0;
    _InterlockedExchange64((volatile __int64 *)v1 + 265, v180);
    std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(v232);
  }
  Microsoft::Diagnostics::AsimovUploadQueue::StartTimers(**(Microsoft::Diagnostics::AsimovUploadQueue ***)v230);
  v233 = 0;
  *(_OWORD *)v230 = *(_OWORD *)&off_18035EC00;
  Microsoft::Diagnostics::TenantManager::GetTenant(*((_QWORD *)v1 + 263), v230, &v233);
  if ( v233 )
    Microsoft::Diagnostics::DevHealthMonTenant::StartMdmListener(v233);
  Microsoft::Diagnostics::SystemStateManager::BeginTrackingSystemState(**(Microsoft::Diagnostics::SystemStateManager ***)v227);
  v181 = (Microsoft::Diagnostics::RemoteAggregatorManager *)*((_QWORD *)v1 + 275);
  if ( v181 )
  {
    try
    {
      Microsoft::Diagnostics::RemoteAggregatorManager::Initialize(v181);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x343,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
        v182);
      v1 = v247;
      v172 = v238[0];
    }
  }
  LODWORD(v233) = 0;
  *(_OWORD *)v227 = *(_OWORD *)&off_18035EC10;
  *(_OWORD *)v230 = *(_OWORD *)&off_180348A48;
  Microsoft::Diagnostics::DynamicConfig<unsigned long>::CreateRegistryConfig(
    (unsigned int)v271,
    (unsigned int)&v233,
    (unsigned int)v230,
    (unsigned int)v227,
    0);
  if ( (unsigned int)Microsoft::Diagnostics::DynamicConfig<unsigned long>::Get(v271) == 1 )
  {
    memset(v227, 0, sizeof(v227));
    *(_OWORD *)v230 = *(_OWORD *)&off_18035EBF0;
    v183 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v230, 0, v227);
    if ( v183 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x34C,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
        (const char *)(unsigned int)v183,
        dwCreationFlagsr);
  }
  Thread = CreateThread(0, 0xB000u, Microsoft::Diagnostics::MatchEngine::StartMatchEngine, *v240, 0, 0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    (char *)v1 + 1896,
    Thread);
  if ( ((*((_QWORD *)v1 + 237) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x351,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      v185);
  v186 = (Microsoft::Diagnostics::ExporterManager *)*((_QWORD *)v1 + 279);
  if ( v186 )
    Microsoft::Diagnostics::ExporterManager::Initialize(v186);
  started = (_QWORD *)Microsoft::Diagnostics::TriggerListener::StartConsumerThreads(*v239, v227);
  if ( (_QWORD *)((char *)v1 + 2328) != started )
  {
    std::vector<std::pair<std::string_view,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>>::_Tidy((char *)v1 + 2328);
    *((_QWORD *)v1 + 291) = *started;
    *((_QWORD *)v1 + 292) = started[1];
    *((_QWORD *)v1 + 293) = started[2];
    *started = 0;
    started[1] = 0;
    started[2] = 0;
  }
  std::vector<std::pair<std::string_view,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>>::_Tidy(v227);
  Microsoft::Diagnostics::TriggerAggregator::StartAggregation(*(Microsoft::Diagnostics::TriggerAggregator **)v244);
  v188 = CreateThread(0, 0x8000u, Microsoft::Diagnostics::TriggerListener::StartThread, *v239, 0, 0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    (char *)v1 + 1928,
    v188);
  if ( ((*((_QWORD *)v1 + 241) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x35E,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      v189);
  v190 = CreateThread(
           0,
           0xC000u,
           Microsoft::Diagnostics::ScenarioManager::StaticRuleUpdateThreadProc,
           **(LPVOID **)v236,
           0,
           0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    (char *)v1 + 1912,
    v190);
  if ( ((*((_QWORD *)v1 + 239) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x361,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      v191);
  *(_OWORD *)v227 = *(_OWORD *)&off_18035EBE0;
  if ( !(unsigned __int8)Microsoft::Diagnostics::Utils::General::IsTestHookEnabled(v227) )
  {
    v193 = Microsoft::Diagnostics::ApiServer::StartRpcServer(v192);
    if ( v193 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x366,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
        (const char *)(unsigned int)v193,
        dwCreationFlagss);
    *(_OWORD *)v227 = *(_OWORD *)&off_180347700;
    v194 = Microsoft::Diagnostics::ApiServer::RegisterInterface(*(_QWORD *)v172, v227, &unk_180347690);
    if ( v194 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x367,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
        (const char *)(unsigned int)v194,
        dwCreationFlagss);
    *(_OWORD *)v227 = *(_OWORD *)&off_18035EBD0;
    v195 = Microsoft::Diagnostics::ApiServer::RegisterInterface(*(_QWORD *)v172, v227, &unk_180364E30);
    if ( v195 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x368,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
        (const char *)(unsigned int)v195,
        dwCreationFlagss);
    *(_OWORD *)v227 = *(_OWORD *)&off_180347710;
    v196 = Microsoft::Diagnostics::ApiServer::RegisterInterface(*(_QWORD *)v172, v227, &unk_180347720);
    if ( v196 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x369,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
        (const char *)(unsigned int)v196,
        dwCreationFlagss);
    *(_OWORD *)v227 = *(_OWORD *)&off_18035EBC0;
    v197 = Microsoft::Diagnostics::ApiServer::RegisterInterface(*(_QWORD *)v172, v227, &unk_1803657E0);
    if ( v197 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x36A,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
        (const char *)(unsigned int)v197,
        dwCreationFlagss);
    *(_OWORD *)v227 = *(_OWORD *)&off_180347780;
    v198 = Microsoft::Diagnostics::ApiServer::RegisterInterface(*(_QWORD *)v172, v227, &unk_180347840);
    if ( v198 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x36B,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
        (const char *)(unsigned int)v198,
        dwCreationFlagss);
    *(_OWORD *)v227 = *(_OWORD *)&off_18035EBA0;
    v199 = Microsoft::Diagnostics::ApiServer::RegisterInterface(*(_QWORD *)v172, v227, &unk_180365EA0);
    if ( v199 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x36C,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
        (const char *)(unsigned int)v199,
        dwCreationFlagss);
    *(_OWORD *)v227 = *(_OWORD *)&off_18035EBB0;
    v200 = Microsoft::Diagnostics::ApiServer::RegisterInterface(*(_QWORD *)v172, v227, &unk_180366DF0);
    if ( v200 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x36D,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
        (const char *)(unsigned int)v200,
        dwCreationFlagss);
    *(_OWORD *)v227 = *(_OWORD *)&off_180347700;
    v201 = Microsoft::Diagnostics::ApiServer::RegisterInterface(*(_QWORD *)v172, v227, &unk_180367260);
    if ( v201 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x36E,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
        (const char *)(unsigned int)v201,
        dwCreationFlagss);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UsageAndQualityInsights>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_UsageAndQualityInsights>::GetImpl'::`2'::impl) )
    {
      *(_OWORD *)v227 = *(_OWORD *)&off_18035EB80;
      v202 = Microsoft::Diagnostics::ApiServer::RegisterInterface(*(_QWORD *)v172, v227, &unk_180367770);
      if ( v202 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x371,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
          (const char *)(unsigned int)v202,
          dwCreationFlagss);
    }
  }
  *(_OWORD *)v227 = *(_OWORD *)&off_18035EB90;
  v203 = *(Microsoft::Diagnostics::UtcWatchdog ***)v235;
  Microsoft::Diagnostics::UtcWatchdog::AddPermanentThread(**(_QWORD **)v235, v227, *((_QWORD *)v1 + 237));
  *(_OWORD *)v227 = *(_OWORD *)&off_18035EB70;
  Microsoft::Diagnostics::UtcWatchdog::AddPermanentThread(*v203, v227, *((_QWORD *)v1 + 241));
  *(_OWORD *)v227 = *(_OWORD *)&off_18035EB60;
  Microsoft::Diagnostics::UtcWatchdog::AddPermanentThread(*v203, v227, *((_QWORD *)v1 + 239));
  v204 = *((_QWORD *)v1 + 291);
  if ( v204 != *((_QWORD *)v1 + 292) )
  {
    v205 = *((_QWORD *)v1 + 292);
    do
    {
      *(_OWORD *)v227 = *(_OWORD *)v204;
      Microsoft::Diagnostics::UtcWatchdog::AddPermanentThread(*v203, v227, *(_QWORD *)(v204 + 16));
      v204 += 24;
    }
    while ( v204 != v205 );
  }
  Microsoft::Diagnostics::UtcWatchdog::StartTimer(*v203);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UtcJobObjectRestriction>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_UtcJobObjectRestriction>::GetImpl'::`2'::impl) )
  {
    v229[0] = 1;
    *(_OWORD *)v227 = *(_OWORD *)&off_18035EB50;
    *(_OWORD *)v230 = *(_OWORD *)&off_180348A48;
    DwordAsBool = Microsoft::Diagnostics::Utils::Registry::GetDwordAsBool(-2147483646, v230, v227, v229);
    if ( DwordAsBool < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x387,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
        (const char *)(unsigned int)DwordAsBool,
        dwCreationFlagss);
    if ( v229[0] )
      Microsoft::Diagnostics::LifetimeManager::UtcJobObjectImpl(v1);
  }
  Microsoft::Diagnostics::DynamicConfig<unsigned long>::~DynamicConfig<unsigned long>((struct Microsoft::Diagnostics::ISettingReceiver *)v271);
  Microsoft::Diagnostics::DynamicConfig<unsigned long>::~DynamicConfig<unsigned long>((struct Microsoft::Diagnostics::ISettingReceiver *)v272);
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v266);
  Microsoft::Diagnostics::DynamicConfig<unsigned long>::~DynamicConfig<unsigned long>((struct Microsoft::Diagnostics::ISettingReceiver *)v273);
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v267);
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v268);
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v262);
  wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&v248);
  wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&SecurityDescriptor);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKeyDest);
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v265);
}

```

## disassembly

```asm
0x1801817c4  mov     r11, rsp
0x1801817c7  mov     [r11+10h], rbx
0x1801817cb  mov     [r11+18h], rsi
0x1801817cf  push    rdi
0x1801817d0  push    r12
0x1801817d2  push    r13
0x1801817d4  push    r14
0x1801817d6  push    r15
0x1801817d8  sub     rsp, 760h
0x1801817df  mov     rax, cs:__security_cookie
0x1801817e6  xor     rax, rsp
0x1801817e9  mov     [rsp+788h+var_38], rax
0x1801817f1  mov     r15, rcx
0x1801817f4  mov     [rsp+788h+var_658], rcx
0x1801817fc  xor     esi, esi
0x1801817fe  mov     [r11-660h], rsi
0x180181805  movups  xmm0, xmmword ptr cs:off_18035EE40; "SubsystemShutdownTimeoutMillis"
0x18018180c  movdqu  xmmword ptr [rsp+788h+var_738], xmm0
0x180181812  movups  xmm1, xmmword ptr cs:off_180348A48; "%DiagtrackRegistryRoot%"
0x180181819  movdqu  xmmword ptr [rsp+788h+var_708], xmm1
0x180181822  lea     r9, [r11-660h]
0x180181829  lea     r8, [rsp+788h+var_738]
0x18018182e  lea     rdx, [r11-708h]
0x180181835  mov     r13, 0FFFFFFFF80000002h
0x18018183c  mov     rcx, r13
0x18018183f  call    ?GetQword@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@1AEA_K@Z; Microsoft::Diagnostics::Utils::Registry::GetQword(HKEY__ *,std::wstring_view,std::wstring_view,unsigned __int64 &)
0x180181844  test    eax, eax
0x180181846  js      short loc_180181852
0x180181848  mov     eax, dword ptr [rsp+788h+var_660]
0x18018184f  xchg    eax, [r15]
0x180181852  lea     rcx, [r15+8]; this
0x180181856  call    ?StartupConsentCheck@InitialConsentManager@Diagnostics@Microsoft@@QEAAXXZ; Microsoft::Diagnostics::InitialConsentManager::StartupConsentCheck(void)
0x18018185b  movups  xmm0, xmmword ptr cs:?k_csVer4_0String@LifetimeManager@Diagnostics@Microsoft@@0V?$basic_zstring_view@_W@wil@@B; wil::basic_zstring_view<wchar_t> const Microsoft::Diagnostics::LifetimeManager::k_csVer4_0String
0x180181862  movdqu  xmmword ptr [rsp+788h+var_738], xmm0
0x180181868  lea     rdx, [rsp+788h+var_738]
0x18018186d  lea     rcx, [rsp+788h+var_458]
0x180181875  call    ??$?0V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_zstring_view@_W@wil@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wil::basic_zstring_view<wchar_t> const &,std::allocator<wchar_t> const &)
0x18018187a  nop
0x18018187b  movups  xmm0, xmmword ptr cs:off_18035EE30; "LastCsVersion"
0x180181882  movdqu  xmmword ptr [rsp+788h+var_738], xmm0
0x180181888  movups  xmm1, xmmword ptr cs:off_180348A48; "%DiagtrackRegistryRoot%"
0x18018188f  movdqu  xmmword ptr [rsp+788h+var_708], xmm1
0x180181898  lea     r9, [rsp+788h+var_458]
0x1801818a0  lea     r8, [rsp+788h+var_738]
0x1801818a5  lea     rdx, [rsp+788h+var_708]
0x1801818ad  mov     rcx, r13
0x1801818b0  call    ?GetString@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@1AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@7@@Z; Microsoft::Diagnostics::Utils::Registry::GetString(HKEY__ *,std::wstring_view,std::wstring_view,std::wstring &)
0x1801818b5  mov     eax, cs:dword_18042D328
0x1801818bb  mov     ebx, 10h
0x1801818c0  lea     rdi, dword_18042D328
0x1801818c7  cmp     eax, 4
0x1801818ca  jbe     short loc_180181918
0x1801818cc  mov     edx, ebx
0x1801818ce  mov     rcx, rdi
0x1801818d1  call    _tlgKeywordOn
0x1801818d6  test    al, al
0x1801818d8  jz      short loc_180181918
0x1801818da  lea     rax, [rsp+788h+var_458]
0x1801818e2  cmp     [rsp+788h+var_440], 7
0x1801818eb  cmova   rax, [rsp+788h+var_458]
0x1801818f4  mov     [rsp+788h+var_6C8], rax
0x1801818fc  lea     rax, [rsp+788h+var_6C8]
0x180181904  mov     qword ptr [rsp+788h+dwCreationFlags], rax; int
0x180181909  lea     rdx, unk_1803C2901
0x180181910  mov     rcx, rdi
0x180181913  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x180181918  mov     [rsp+788h+var_718], sil
0x18018191d  call    ?WasCleanServiceShutdown@LifetimeManager@Diagnostics@Microsoft@@AEAA_NXZ; Microsoft::Diagnostics::LifetimeManager::WasCleanServiceShutdown(void)
0x180181922  test    al, al
0x180181924  jnz     short loc_18018196A
0x180181926  mov     [rsp+788h+var_6B0], esi
0x18018192d  mov     [rsp+788h+var_6B8], esi
0x180181934  lea     r8, [rsp+788h+var_6B8]; unsigned int *
0x18018193c  lea     rdx, [rsp+788h+var_6B0]; unsigned int *
0x180181944  call    ?RecordDirtyShutdown@LifetimeManager@Diagnostics@Microsoft@@AEAAXAEAK0@Z; Microsoft::Diagnostics::LifetimeManager::RecordDirtyShutdown(ulong &,ulong &)
0x180181949  mov     r8d, [rsp+788h+var_6B8]; unsigned int
0x180181951  mov     edx, [rsp+788h+var_6B0]; unsigned int
0x180181958  call    ?IsResetRequired@LifetimeManager@Diagnostics@Microsoft@@AEAA_NKK@Z; Microsoft::Diagnostics::LifetimeManager::IsResetRequired(ulong,ulong)
0x18018195d  mov     [rsp+788h+var_718], al
0x180181961  test    al, al
0x180181963  jz      short loc_18018196A
0x180181965  call    ?ResetState@LifetimeManager@Diagnostics@Microsoft@@AEAAXXZ; Microsoft::Diagnostics::LifetimeManager::ResetState(void)
0x18018196a  mov     r12d, 1
0x180181970  movzx   ecx, r12w
0x180181974  call    ?SetDiagTrackStatus@General@Utils@Diagnostics@Microsoft@@SAXVDiagTrackStatus@EnumDetails@234@@Z; Microsoft::Diagnostics::Utils::General::SetDiagTrackStatus(Microsoft::Diagnostics::Utils::EnumDetails::DiagTrackStatus)
0x180181979  mov     [rsp+788h+hKeyDest], rsi
0x180181981  mov     [rsp+788h+var_668], esi
0x180181988  movups  xmm0, xmmword ptr cs:off_18035EE20; "ComponentManifestVersion"
0x18018198f  movdqu  xmmword ptr [rsp+788h+var_708], xmm0
0x180181998  mov     rax, cs:off_18035EE60; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18018199f  mov     qword ptr [rsp+788h+var_738], rax
0x1801819a4  mov     qword ptr [rsp+788h+var_738+8], 3Fh ; '?'
0x1801819ad  lea     r9, [rsp+788h+var_668]
0x1801819b5  lea     r8, [rsp+788h+var_708]
0x1801819bd  lea     rdx, [rsp+788h+var_738]
0x1801819c2  mov     rcx, r13
0x1801819c5  call    ?GetDword@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@1AEAK@Z; Microsoft::Diagnostics::Utils::Registry::GetDword(HKEY__ *,std::wstring_view,std::wstring_view,ulong &)
0x1801819ca  test    eax, eax
0x1801819cc  js      loc_180181A69
0x1801819d2  mov     [rsp+788h+var_6B0], esi
0x1801819d9  movups  xmm0, xmmword ptr cs:off_18035EE20; "ComponentManifestVersion"
0x1801819e0  movdqu  xmmword ptr [rsp+788h+var_738], xmm0
0x1801819e6  movups  xmm1, xmmword ptr cs:off_180348A48; "%DiagtrackRegistryRoot%"
0x1801819ed  movdqu  xmmword ptr [rsp+788h+var_708], xmm1
0x1801819f6  lea     r9, [rsp+788h+var_6B0]
0x1801819fe  lea     r8, [rsp+788h+var_738]
0x180181a03  lea     rdx, [rsp+788h+var_708]
0x180181a0b  mov     rcx, r13
0x180181a0e  call    ?GetDword@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@1AEAK@Z; Microsoft::Diagnostics::Utils::Registry::GetDword(HKEY__ *,std::wstring_view,std::wstring_view,ulong &)
0x180181a13  test    eax, eax
0x180181a15  js      short loc_180181A27
0x180181a17  mov     eax, [rsp+788h+var_6B0]
0x180181a1e  cmp     [rsp+788h+var_668], eax
0x180181a25  jz      short loc_180181A69
0x180181a27  movups  xmm0, xmmword ptr cs:off_180348A48; "%DiagtrackRegistryRoot%"
0x180181a2e  movdqu  xmmword ptr [rsp+788h+var_738], xmm0
0x180181a34  mov     r8b, r12b
0x180181a37  lea     rdx, [rsp+788h+var_738]
0x180181a3c  mov     rcx, r13
0x180181a3f  call    ?DeleteTree@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@_N@Z; Microsoft::Diagnostics::Utils::Registry::DeleteTree(HKEY__ *,std::wstring_view,bool)
0x180181a44  mov     rcx, [rsp+788h]; this
0x180181a4c  test    eax, eax
0x180181a4e  jns     short loc_180181A69
0x180181a50  mov     r9d, eax; char *
0x180181a53  lea     r14, aOnecoreBaseTel_210; "onecore\\base\\telemetry\\utc\\service"...
0x180181a5a  mov     r8, r14; unsigned int
0x180181a5d  mov     edx, 17Dh; void *
0x180181a62  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180181a67  jmp     short loc_180181A70
0x180181a69  lea     r14, aOnecoreBaseTel_210; "onecore\\base\\telemetry\\utc\\service"...
0x180181a70  movups  xmm0, xmmword ptr cs:off_180348A48; "%DiagtrackRegistryRoot%"
0x180181a77  movdqu  xmmword ptr [rsp+788h+var_738], xmm0
0x180181a7d  mov     r9d, 0F003Fh
0x180181a83  lea     r8, [rsp+788h+hKeyDest]
0x180181a8b  lea     rdx, [rsp+788h+var_738]
0x180181a90  mov     rcx, r13; hKey
0x180181a93  call    ?OpenKey@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@K@Z; Microsoft::Diagnostics::Utils::Registry::OpenKey(HKEY__ *,std::wstring_view,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,ulong)
0x180181a98  test    eax, eax
0x180181a9a  jns     loc_180181B9D
0x180181aa0  movups  xmm0, xmmword ptr cs:off_180348A48; "%DiagtrackRegistryRoot%"
0x180181aa7  movdqu  xmmword ptr [rsp+788h+var_738], xmm0
0x180181aad  mov     dword ptr [rsp+788h+lpThreadId], esi; DWORD
0x180181ab1  mov     [rsp+788h+dwCreationFlags], 0F003Fh; int
0x180181ab9  xor     r9d, r9d
0x180181abc  lea     r8, [rsp+788h+hKeyDest]
0x180181ac4  lea     rdx, [rsp+788h+var_738]
0x180181ac9  mov     rcx, r13; hKey
0x180181acc  call    ?CreateKey@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAU_SECURITY_ATTRIBUTES@@KK@Z; Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY__ *,std::wstring_view,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x180181ad1  mov     rcx, [rsp+788h]; this
0x180181ad9  test    eax, eax
0x180181adb  js      loc_1801844C3
0x180181ae1  lea     rdx, off_180348A48; "%DiagtrackRegistryRoot%"
0x180181ae8  lea     rcx, [rsp+788h+Src]
0x180181af0  call    ??$?0V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_zstring_view@_W@wil@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wil::basic_zstring_view<wchar_t> const &,std::allocator<wchar_t> const &)
0x180181af5  nop
0x180181af6  xor     r8d, r8d
0x180181af9  mov     dl, r12b
0x180181afc  lea     rcx, [rsp+788h+Src]; lpSrc
0x180181b04  call    ?ExpandEnvironmentStringsInString@String@Utils@Diagnostics@Microsoft@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_NPEAX@Z; Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(std::wstring &,bool,void *)
0x180181b09  lea     rdx, [rsp+788h+var_6E8]
0x180181b11  lea     rcx, [rsp+788h+Src]
0x180181b19  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x180181b1e  movups  xmm0, xmmword ptr [rax]
0x180181b21  movdqu  xmmword ptr [rsp+788h+var_708], xmm0
0x180181b2a  mov     rax, cs:off_18035EE60; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180181b31  mov     qword ptr [rsp+788h+var_738], rax
0x180181b36  mov     qword ptr [rsp+788h+var_738+8], 3Fh ; '?'
0x180181b3f  lea     rdx, [rsp+788h+var_708]
0x180181b47  lea     rcx, [rsp+788h+var_738]
0x180181b4c  call    ?ICompare@String@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Microsoft::Diagnostics::Utils::String::ICompare(std::wstring_view,std::wstring_view)
0x180181b51  test    eax, eax
0x180181b53  jz      short loc_180181B90
0x180181b55  mov     r8, [rsp+788h+hKeyDest]; hKeyDest
0x180181b5d  mov     rdx, cs:off_18035EE60; lpSubKey
0x180181b64  mov     rcx, r13; hKeySrc
0x180181b67  call    cs:__imp_RegCopyTreeW
0x180181b6e  nop     dword ptr [rax+rax+00h]
0x180181b73  mov     rcx, [rsp+788h]; this
0x180181b7b  test    eax, eax
0x180181b7d  jz      short loc_180181B90
0x180181b7f  mov     r9d, eax; char *
0x180181b82  mov     r8, r14; unsigned int
0x180181b85  mov     edx, 18Ah; void *
0x180181b8a  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180181b8f  nop
0x180181b90  lea     rcx, [rsp+788h+Src]; this
0x180181b98  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x180181b9d  movups  xmm0, xmmword ptr cs:off_18035EE00; "%DiagtrackRegistryRoot%\\Scenarios"
0x180181ba4  movdqu  xmmword ptr [rsp+788h+var_738], xmm0
0x180181baa  mov     dword ptr [rsp+788h+lpThreadId], esi; DWORD
0x180181bae  mov     [rsp+788h+dwCreationFlags], 0F003Fh; int
0x180181bb6  xor     r9d, r9d
0x180181bb9  lea     r8, [rsp+788h+hKeyDest]
0x180181bc1  lea     rdx, [rsp+788h+var_738]
0x180181bc6  mov     rcx, r13; hKey
0x180181bc9  call    ?CreateKey@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAU_SECURITY_ATTRIBUTES@@KK@Z; Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY__ *,std::wstring_view,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x180181bce  mov     rcx, [rsp+788h]; this
0x180181bd6  test    eax, eax
0x180181bd8  js      loc_1801844D4
0x180181bde  movups  xmm0, xmmword ptr cs:off_18035EE10; "%DiagtrackRegistryRoot%\\TraceManager"
0x180181be5  movdqu  xmmword ptr [rsp+788h+var_738], xmm0
0x180181beb  mov     dword ptr [rsp+788h+lpThreadId], esi; DWORD
0x180181bef  mov     [rsp+788h+dwCreationFlags], 0F003Fh; int
0x180181bf7  xor     r9d, r9d
0x180181bfa  lea     r8, [rsp+788h+hKeyDest]
0x180181c02  lea     rdx, [rsp+788h+var_738]
0x180181c07  mov     rcx, r13; hKey
0x180181c0a  call    ?CreateKey@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAU_SECURITY_ATTRIBUTES@@KK@Z; Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY__ *,std::wstring_view,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x180181c0f  mov     rcx, [rsp+788h]; this
0x180181c17  test    eax, eax
0x180181c19  js      loc_1801844E5
0x180181c1f  movups  xmm0, xmmword ptr cs:off_1803487F0; "%DiagtrackRegistryRoot%\\SettingsReques"...
0x180181c26  movdqu  xmmword ptr [rsp+788h+var_738], xmm0
0x180181c2c  mov     dword ptr [rsp+788h+lpThreadId], esi; DWORD
0x180181c30  mov     [rsp+788h+dwCreationFlags], 0F003Fh; int
0x180181c38  xor     r9d, r9d
0x180181c3b  lea     r8, [rsp+788h+hKeyDest]
0x180181c43  lea     rdx, [rsp+788h+var_738]
0x180181c48  mov     rcx, r13; hKey
0x180181c4b  call    ?CreateKey@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAU_SECURITY_ATTRIBUTES@@KK@Z; Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY__ *,std::wstring_view,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x180181c50  mov     rcx, [rsp+788h]; this
0x180181c58  test    eax, eax
0x180181c5a  js      loc_1801844F6
0x180181c60  movups  xmm0, xmmword ptr cs:off_18035EDF0; "%DiagtrackRegistryRoot%\\TelemetryNames"...
0x180181c67  movdqu  xmmword ptr [rsp+788h+var_738], xmm0
0x180181c6d  mov     dword ptr [rsp+788h+lpThreadId], esi; DWORD
0x180181c71  mov     [rsp+788h+dwCreationFlags], 0F003Fh; int
0x180181c79  xor     r9d, r9d
0x180181c7c  lea     r8, [rsp+788h+hKeyDest]
0x180181c84  lea     rdx, [rsp+788h+var_738]
0x180181c89  mov     rcx, r13; hKey
0x180181c8c  call    ?CreateKey@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAU_SECURITY_ATTRIBUTES@@KK@Z; Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY__ *,std::wstring_view,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x180181c91  mov     rcx, [rsp+788h]; this
0x180181c99  test    eax, eax
0x180181c9b  js      loc_180184507
0x180181ca1  movups  xmm0, xmmword ptr cs:off_180347638; "%DiagtrackRegistryRoot%\\FailFastCounte"...
0x180181ca8  movdqu  xmmword ptr [rsp+788h+var_738], xmm0
0x180181cae  mov     dword ptr [rsp+788h+lpThreadId], esi; DWORD
0x180181cb2  mov     [rsp+788h+dwCreationFlags], 0F003Fh; int
0x180181cba  xor     r9d, r9d
0x180181cbd  lea     r8, [rsp+788h+hKeyDest]
0x180181cc5  lea     rdx, [rsp+788h+var_738]
0x180181cca  mov     rcx, r13; hKey
0x180181ccd  call    ?CreateKey@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAU_SECURITY_ATTRIBUTES@@KK@Z; Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY__ *,std::wstring_view,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x180181cd2  mov     rcx, [rsp+788h]; this
0x180181cda  test    eax, eax
0x180181cdc  js      loc_180184518
0x180181ce2  movups  xmm0, xmmword ptr cs:off_180347648; "%DiagtrackRegistryRoot%\\HeartBeats"
0x180181ce9  movdqu  xmmword ptr [rsp+788h+var_738], xmm0
0x180181cef  mov     dword ptr [rsp+788h+lpThreadId], esi; DWORD
0x180181cf3  mov     [rsp+788h+dwCreationFlags], 0F003Fh; int
0x180181cfb  xor     r9d, r9d
0x180181cfe  lea     r8, [rsp+788h+hKeyDest]
0x180181d06  lea     rdx, [rsp+788h+var_738]
0x180181d0b  mov     rcx, r13; hKey
0x180181d0e  call    ?CreateKey@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAU_SECURITY_ATTRIBUTES@@KK@Z; Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY__ *,std::wstring_view,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x180181d13  mov     rcx, [rsp+788h]; this
0x180181d1b  test    eax, eax
0x180181d1d  js      loc_180184529
0x180181d23  movups  xmm0, xmmword ptr cs:off_1803475F8; "%DiagtrackRegistryRoot%\\SevilleEventlo"...
0x180181d2a  movdqu  xmmword ptr [rsp+788h+var_738], xmm0
0x180181d30  mov     dword ptr [rsp+788h+lpThreadId], esi; DWORD
0x180181d34  mov     [rsp+788h+dwCreationFlags], 0F003Fh; int
0x180181d3c  xor     r9d, r9d
0x180181d3f  lea     r8, [rsp+788h+hKeyDest]
0x180181d47  lea     rdx, [rsp+788h+var_738]
0x180181d4c  mov     rcx, r13; hKey
0x180181d4f  call    ?CreateKey@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAU_SECURITY_ATTRIBUTES@@KK@Z; Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY__ *,std::wstring_view,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x180181d54  mov     rcx, [rsp+788h]; this
0x180181d5c  test    eax, eax
0x180181d5e  js      loc_18018453A
0x180181d64  movups  xmm0, xmmword ptr cs:off_180347628; "%DiagtrackRegistryRoot%\\TestHooks"
0x180181d6b  movdqu  xmmword ptr [rsp+788h+var_738], xmm0
0x180181d71  mov     dword ptr [rsp+788h+lpThreadId], esi; DWORD
0x180181d75  mov     [rsp+788h+dwCreationFlags], 0F003Fh; int
0x180181d7d  xor     r9d, r9d
0x180181d80  lea     r8, [rsp+788h+hKeyDest]
0x180181d88  lea     rdx, [rsp+788h+var_738]
0x180181d8d  mov     rcx, r13; hKey
0x180181d90  call    ?CreateKey@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAU_SECURITY_ATTRIBUTES@@KK@Z; Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY__ *,std::wstring_view,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x180181d95  mov     rcx, [rsp+788h]; this
0x180181d9d  test    eax, eax
0x180181d9f  js      loc_18018454B
0x180181da5  movups  xmm0, xmmword ptr cs:off_180347608; "%DiagtrackRegistryRoot%\\TestHooks\\Vol"...
0x180181dac  movdqu  xmmword ptr [rsp+788h+var_738], xmm0
0x180181db2  lea     r8, [rsp+788h+hKeyDest]
0x180181dba  lea     rdx, [rsp+788h+var_738]
0x180181dbf  call    ?CreateGuaranteedVolatileKey@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAU_SECURITY_ATTRIBUTES@@KK@Z; Microsoft::Diagnostics::Utils::Registry::CreateGuaranteedVolatileKey(HKEY__ *,std::wstring_view,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x180181dc4  mov     rcx, [rsp+788h]; this
0x180181dcc  test    eax, eax
0x180181dce  js      loc_18018455C
0x180181dd4  movups  xmm0, xmmword ptr cs:off_18035EDD0; "%DiagtrackRegistryRoot%\\exporters"
0x180181ddb  movdqu  xmmword ptr [rsp+788h+var_738], xmm0
0x180181de1  mov     dword ptr [rsp+788h+lpThreadId], esi; DWORD
0x180181de5  mov     [rsp+788h+dwCreationFlags], 0F003Fh; int
0x180181ded  xor     r9d, r9d
0x180181df0  lea     r8, [rsp+788h+hKeyDest]
0x180181df8  lea     rdx, [rsp+788h+var_738]
0x180181dfd  mov     rcx, r13; hKey
0x180181e00  call    ?CreateKey@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAU_SECURITY_ATTRIBUTES@@KK@Z; Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY__ *,std::wstring_view,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,_SECURITY_ATTRIBUTES *,ulong,ulong)
  ... truncated ...
```
