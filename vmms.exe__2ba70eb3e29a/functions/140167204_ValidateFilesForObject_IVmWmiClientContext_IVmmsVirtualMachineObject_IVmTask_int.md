# ValidateFilesForObject(IVmWmiClientContext *,IVmmsVirtualMachineObject *,IVmTask *,int)

- ea: `0x140167204`
- end: `0x14016827f`
- name: `?ValidateFilesForObject@@YAHPEAUIVmWmiClientContext@@PEAUIVmmsVirtualMachineObject@@PEAUIVmTask@@H@Z`
- size: `4219`
- prototype: `__int64 __fastcall(struct IVmWmiClientContext *, struct IVmmsVirtualMachineObject *, struct IVmTask *, int)`
- caller_count: `1`
- callee_count: `41`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1402f4a20`

## callees

- `0x14001a000`
- `0x140022640`
- `0x140032594`
- `0x1400342a0`
- `0x14003d89c`
- `0x14004bf10`
- `0x140077b60`
- `0x14007ee00`
- `0x14007ee50`
- `0x14007ee88`
- `0x14007eed8`
- `0x140081828`
- `0x1400826e0`
- `0x1400bf3cc`
- `0x1400bf564`
- `0x1400e1338`
- `0x1400ebf20`
- `0x1400f682c`
- `0x140100f5c`
- `0x140166c24`
- `0x140166d1c`
- `0x140166f38`
- `0x140166ff8`
- `0x140167204`
- `0x140168288`
- `0x140168368`
- `0x14016978c`
- `0x140188e18`
- `0x1401be65c`
- `0x14021c290`
- `0x140233d0c`
- `0x1402340e0`
- `0x140267544`
- `0x1403157fc`
- `0x140315924`
- `0x1404828e0`
- `0x1405cb3e0`
- `0x1407e8134`
- `0x1407e82f0`
- `0x1407e83e4`
- `0x1408aa010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1401677dc`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1401678f1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140167984`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1401677dc`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1401678f1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140167984`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAddBackslashW` at `0x1401674f5`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAddBackslashW` at `0x14016768e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAddBackslashW` at `0x1401676bd`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAddBackslashW` at `0x1401676ec`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAddBackslashW` at `0x1401674f5`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAddBackslashW` at `0x14016768e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAddBackslashW` at `0x1401676bd`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAddBackslashW` at `0x1401676ec`
- `vmprox!GetVmErrInfo` at `0x140167c28`
- `vmprox!GetVmErrInfo` at `0x140167ed5`
- `vmprox!GetVmErrInfo` at `0x140168090`
- `vmprox!GetVmErrInfo` at `0x14016810a`
- `vmprox!GetVmErrInfo` at `0x140167c28`
- `vmprox!GetVmErrInfo` at `0x140167ed5`
- `vmprox!GetVmErrInfo` at `0x140168090`
- `vmprox!GetVmErrInfo` at `0x14016810a`
- `api-ms-win-core-path-l1-1-0!PathIsUNCEx` at `0x140167bc2`
- `api-ms-win-core-path-l1-1-0!PathIsUNCEx` at `0x140167bc2`

## string_xrefs

- `0x140167514`: `onecore\vm\vmms\common\vmmsvalidation.cpp`
- `0x1401675a4`: `onecore\vm\vmms\common\vmmsvalidation.cpp`
- `0x140167b04`: `onecore\vm\vmms\common\vmmsvalidation.cpp`
- `0x140167b24`: `onecore\vm\vmms\common\vmmsvalidation.cpp`
- `0x140167c98`: `onecore\vm\vmms\common\vmmsvalidation.cpp`
- `0x140167d7e`: `onecore\vm\vmms\common\vmmsvalidation.cpp`
- `0x140167f51`: `onecore\vm\vmms\common\vmmsvalidation.cpp`
- `0x1401681f6`: `onecore\vm\vmms\common\vmmsvalidation.cpp`
- `0x1401675c9`: `/configuration/global_settings/data_root`
- `0x140167292`: `/configuration/savedstate/vsvlocation`
- `0x140167336`: `/configuration/savedstate/memlocation`
- `0x14016761a`: `/configuration/global_settings/slp_data_root`
- `0x1401675f3`: `/configuration/global_settings/snapshots/data_root`

## pseudocode

```c
// Hidden C++ exception states: #wind=33
__int64 __fastcall ValidateFilesForObject(
        struct IVmWmiClientContext *a1,
        struct IVmmsVirtualMachineObject *a2,
        struct IVmTask *a3,
        int a4)
{
  struct IVmTask *v5; // r13
  struct IVmmsVirtualMachineObject *v6; // r14
  struct IVmWmiClientContext *v7; // r15
  unsigned int v8; // esi
  __int64 v9; // rax
  const struct _GUID *v10; // r8
  const unsigned __int16 *v11; // r9
  struct IVmWmiObject *v12; // rbx
  const struct _GUID *v13; // r8
  const unsigned __int16 *v14; // r9
  int v15; // eax
  __m128i si128; // xmm6
  struct IVmErrInfo *v17; // r12
  __int64 *v18; // rcx
  __int64 v19; // rax
  __int64 v20; // r8
  WCHAR *v21; // rcx
  LPWSTR *v22; // rax
  __int64 v23; // r12
  __int64 v24; // rdx
  WCHAR *v25; // rcx
  WCHAR *v26; // rcx
  WCHAR *v27; // rcx
  LPWSTR *v28; // rax
  __int64 v29; // rdx
  LPWSTR *v30; // rax
  __int64 v31; // rdx
  LPWSTR *v32; // rax
  LPWSTR *v33; // rdx
  LPWSTR *v34; // rcx
  int v35; // r12d
  const struct Vml::ExceptionTraceParameters *v36; // r8
  LPWSTR *v37; // rdx
  LPWSTR *v38; // rcx
  int v39; // eax
  int v40; // edx
  LPWSTR *v41; // rdx
  LPWSTR *v42; // rcx
  int v43; // eax
  unsigned int v44; // r12d
  int v45; // edx
  int v46; // ecx
  int v47; // r8d
  int v48; // r9d
  int v49; // eax
  unsigned __int64 i; // r12
  __int64 v51; // rcx
  __int64 v52; // rbx
  const WCHAR *v53; // rcx
  const struct _GUID *v54; // r8
  const unsigned __int16 *v55; // r9
  __int64 v56; // rax
  __int64 v57; // rdx
  struct IVmErrInfo *v58; // rbx
  int v59; // eax
  _QWORD *v60; // rcx
  LPWSTR *v61; // rdx
  __int64 v62; // rdx
  int PnpDevicePathFromPhysicalPath; // eax
  const char *v64; // r9
  unsigned int v65; // ebx
  struct _GUID *v66; // rax
  int v67; // edx
  int v68; // ecx
  int v69; // r8d
  int v70; // r9d
  LPWSTR *v71; // rax
  __int64 v72; // rax
  __int64 v73; // rdx
  struct IVmErrInfo *v74; // rbx
  int v75; // eax
  struct IVmWmiClientContext *v76; // rax
  __int64 v77; // rdx
  __int64 VmErrInfo; // rax
  const struct _GUID *v79; // r8
  const unsigned __int16 *v80; // r9
  __int64 v81; // rax
  struct IVmErrInfo *v82; // rbx
  __int64 v83; // rdx
  int v84; // eax
  struct IVmErrInfo *v85; // r8
  __int64 v86; // rdx
  __int64 v88; // rdx
  __int64 v89; // rcx
  void *v90; // [rsp+20h] [rbp-1E8h]
  int v91; // [rsp+50h] [rbp-1B8h]
  unsigned __int64 v92; // [rsp+58h] [rbp-1B0h] BYREF
  bool v93; // [rsp+60h] [rbp-1A8h]
  struct IVmErrInfo *v94; // [rsp+68h] [rbp-1A0h] BYREF
  __int64 v95; // [rsp+70h] [rbp-198h] BYREF
  struct IVmWmiObject *v96; // [rsp+78h] [rbp-190h] BYREF
  struct IVmWmiClientContext *v97; // [rsp+80h] [rbp-188h]
  struct IVmmsVirtualMachineObject *v98; // [rsp+88h] [rbp-180h]
  struct IVmTask *v99; // [rsp+90h] [rbp-178h]
  struct IVmErrInfo *v100; // [rsp+98h] [rbp-170h] BYREF
  LPWSTR Src[2]; // [rsp+A0h] [rbp-168h] BYREF
  __m128i v102; // [rsp+B0h] [rbp-158h]
  LPWSTR v103[2]; // [rsp+C0h] [rbp-148h] BYREF
  __m128i v104; // [rsp+D0h] [rbp-138h]
  LPWSTR v105[2]; // [rsp+E0h] [rbp-128h] BYREF
  __m128i v106; // [rsp+F0h] [rbp-118h]
  __int128 v107; // [rsp+100h] [rbp-108h] BYREF
  __int64 v108; // [rsp+110h] [rbp-F8h]
  __int64 v109[2]; // [rsp+118h] [rbp-F0h] BYREF
  __m128i v110; // [rsp+128h] [rbp-E0h]
  __int64 v111; // [rsp+150h] [rbp-B8h]
  LPWSTR pszPath[2]; // [rsp+158h] [rbp-B0h] BYREF
  __m128i v113; // [rsp+168h] [rbp-A0h]
  char *v114[2]; // [rsp+178h] [rbp-90h] BYREF
  __m128i v115; // [rsp+188h] [rbp-80h]
  unsigned __int16 v116[8]; // [rsp+198h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+0h]

  v5 = a3;
  v6 = a2;
  v7 = a1;
  v97 = a1;
  v98 = a2;
  v99 = a3;
  v94 = 0;
  v8 = 1;
  v91 = 1;
  v96 = 0;
  v9 = (*(__int64 (__fastcall **)(struct IVmmsVirtualMachineObject *, _QWORD))(*(_QWORD *)a2 + 160LL))(a2, 0);
  Vml::VmComPtr<IICShutdown>::Attach<IICShutdown>(&v96, v9);
  if ( a4 )
  {
    if ( (unsigned int)FindRuntimeFileInternal(v7) )
    {
      v100 = 0;
      if ( !(*(unsigned int (__fastcall **)(struct IVmmsVirtualMachineObject *, struct IVmWmiClientContext *, __int64, struct IVmErrInfo **))(*(_QWORD *)v6 + 560LL))(
              v6,
              v7,
              1,
              &v100) )
      {
        v8 = 0;
        v91 = 0;
        if ( v100 )
          AddVmErrInfoToChain(&v94, v100);
      }
      Vml::VmComPtr<IVssAsync>::~VmComPtr<IVssAsync>(&v100);
      v12 = v96;
    }
    else
    {
      v8 = 0;
      v91 = 0;
      VmEventWriteAndReport(&MSVM_VMMS_VALIDATION_SAVE_STATE_FILE_MISSING, 1u, v10, v11);
      v12 = v96;
      CollectAndAddVmErrInfoToChain(&v94, v7, v96);
    }
    if ( !(unsigned int)FindRuntimeFileInternal(v7) )
    {
      v8 = 0;
      v91 = 0;
      VmEventWriteAndReport(&MSVM_VMMS_VALIDATION_MEMORY_FILE_MISSING, 1u, v13, v14);
      CollectAndAddVmErrInfoToChain(&v94, v7, v12);
    }
  }
  else
  {
    v12 = v96;
  }
  v15 = (*(__int64 (__fastcall **)(struct IVmmsVirtualMachineObject *))(*(_QWORD *)v6 + 88LL))(v6);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  if ( !v15 )
  {
    *(_OWORD *)Src = 0;
    v102 = si128;
    LOWORD(Src[0]) = 0;
    *(_OWORD *)v103 = 0;
    v104 = si128;
    LOWORD(v103[0]) = 0;
    *(_OWORD *)v105 = 0;
    v106 = si128;
    LOWORD(v105[0]) = 0;
    *(_OWORD *)pszPath = 0;
    v113 = si128;
    LOWORD(pszPath[0]) = 0;
    v92 = 0;
    v17 = (struct IVmErrInfo *)(*(__int64 (__fastcall **)(struct IVmmsVirtualMachineObject *))(*(_QWORD *)v6 + 120LL))(v6);
    v100 = v17;
    Vml::VmReferencePtr<SavedStateRepository,Vml::VmUserReferenceTraits>::Reset(&v92, 0);
    v92 = (unsigned __int64)v17;
    *(_OWORD *)v109 = 0;
    v110 = si128;
    LOWORD(v109[0]) = 0;
    (*(void (__fastcall **)(struct IVmmsVirtualMachineObject *, __int64 *))(*(_QWORD *)v6 + 8LL))(v6, v109);
    *(_OWORD *)v114 = 0;
    v18 = (__int64 *)std::make_unique<Vml::VmMachineLocalSettingsStore,,0>(v116);
    v19 = *v18;
    *v18 = 0;
    v95 = v19;
    VmmsSettings::VmmsSettings(v114, 0, v20, &v95);
    std::unique_ptr<Vml::VmDispatchContextWithParams<void,bool,IVmTask *>>::~unique_ptr<Vml::VmDispatchContextWithParams<void,bool,IVmTask *>>(&v95);
    std::unique_ptr<Vml::VmDispatchContextWithParams<void,bool,IVmTask *>>::~unique_ptr<Vml::VmDispatchContextWithParams<void,bool,IVmTask *>>(v116);
    VmmsSettings::GetDefaultExternalDataRoot(v114, pszPath);
    std::wstring::resize(pszPath);
    v21 = (WCHAR *)pszPath;
    if ( v113.m128i_i64[1] > 7uLL )
      v21 = pszPath[0];
    if ( !PathAddBackslashW(v21) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x327,
        (unsigned int)"onecore\\vm\\vmms\\common\\vmmsvalidation.cpp",
        (const char *)0x8007000ELL,
        (int)v90);
    v22 = pszPath;
    if ( v113.m128i_i64[1] > 7uLL )
      v22 = (LPWSTR *)pszPath[0];
    v23 = -1;
    v24 = -1;
    do
      ++v24;
    while ( *((_WORD *)v22 + v24) );
    std::wstring::resize(pszPath);
    VmmsSettings::~VmmsSettings((VmmsSettings *)v114);
    *(_OWORD *)v114 = 0;
    VmRepositoryAutoLock::VmRepositoryAutoLock(v114, v100, 0);
    if ( SLODWORD(v114[1]) < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x330,
        (unsigned int)"onecore\\vm\\vmms\\common\\vmmsvalidation.cpp",
        (const char *)LODWORD(v114[1]),
        (int)v90);
    *(_DWORD *)v116 = (*(__int64 (__fastcall **)(struct IVmErrInfo *, const unsigned __int16 *, LPWSTR *))(*(_QWORD *)v100 + 104LL))(
                        v100,
                        L"/configuration/global_settings/data_root",
                        Src);
    LODWORD(v95) = (*(__int64 (__fastcall **)(struct IVmErrInfo *, const unsigned __int16 *, LPWSTR *))(*(_QWORD *)v100 + 104LL))(
                     v100,
                     L"/configuration/global_settings/snapshots/data_root",
                     v103);
    LODWORD(v100) = (*(__int64 (__fastcall **)(struct IVmErrInfo *, const unsigned __int16 *, LPWSTR *))(*(_QWORD *)v100 + 104LL))(
                      v100,
                      L"/configuration/global_settings/slp_data_root",
                      v105);
    VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v114);
    std::wstring::resize(Src);
    std::wstring::resize(v103);
    std::wstring::resize(v105);
    v25 = (WCHAR *)Src;
    if ( v102.m128i_i64[1] > 7uLL )
      v25 = Src[0];
    if ( !PathAddBackslashW(v25) )
      goto LABEL_70;
    v26 = (WCHAR *)v103;
    if ( v104.m128i_i64[1] > 7uLL )
      v26 = v103[0];
    if ( !PathAddBackslashW(v26) )
      goto LABEL_70;
    v27 = (WCHAR *)v105;
    if ( v106.m128i_i64[1] > 7uLL )
      v27 = v105[0];
    if ( !PathAddBackslashW(v27) )
LABEL_70:
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x344,
        (unsigned int)"onecore\\vm\\vmms\\common\\vmmsvalidation.cpp",
        (const char *)0x8007000ELL,
        (int)v90);
    v28 = Src;
    if ( v102.m128i_i64[1] > 7uLL )
      v28 = (LPWSTR *)Src[0];
    v29 = -1;
    do
      ++v29;
    while ( *((_WORD *)v28 + v29) );
    std::wstring::resize(Src);
    v30 = v103;
    if ( v104.m128i_i64[1] > 7uLL )
      v30 = (LPWSTR *)v103[0];
    v31 = -1;
    do
      ++v31;
    while ( *((_WORD *)v30 + v31) );
    std::wstring::resize(v103);
    v32 = v105;
    if ( v106.m128i_i64[1] > 7uLL )
      v32 = (LPWSTR *)v105[0];
    do
      ++v23;
    while ( *((_WORD *)v32 + v23) );
    std::wstring::resize(v105);
    if ( *(int *)v116 >= 0 )
    {
      v33 = Src;
      if ( v102.m128i_i64[1] > 7uLL )
        v33 = (LPWSTR *)Src[0];
      v34 = pszPath;
      if ( v113.m128i_i64[1] > 7uLL )
        v34 = (LPWSTR *)pszPath[0];
      if ( (unsigned int)_o__wcsicmp(v34, v33) )
      {
        v35 = CheckTargetDataPaths(v7);
        *(_DWORD *)v116 = v35;
        if ( v35 < 0 )
        {
          v8 = 0;
          v91 = 0;
          *(_OWORD *)v114 = 0;
          v115 = si128;
          LOWORD(v114[0]) = 0;
          try
          {
            GetUserNameFromWmiClientContext(v7, v114);
          }
          catch ( ... )
          {
            Vml::GetHResultFromThrownExceptionAndTrace((Vml *)0x8061, (unsigned __int16)&off_14093DC18, v36);
            v8 = 0;
            v12 = v96;
            v35 = *(_DWORD *)v116;
            si128 = _mm_load_si128((const __m128i *)&_xmm);
            v7 = v97;
            v6 = v98;
            v5 = v99;
          }
          v90 = Src;
          ReportAndLogAdminErrorMessage2<std::wstring,std::wstring>(v89, v88, (unsigned int)v35, v114);
          CollectAndAddVmErrInfoToChain(&v94, v7, v12);
          std::wstring::_Tidy_deallocate(v114);
        }
      }
    }
    if ( (int)v95 >= 0 )
    {
      v37 = v103;
      if ( v104.m128i_i64[1] > 7uLL )
        v37 = (LPWSTR *)v103[0];
      v38 = pszPath;
      if ( v113.m128i_i64[1] > 7uLL )
        v38 = (LPWSTR *)pszPath[0];
      if ( (unsigned int)_o__wcsicmp(v38, v37) )
      {
        v39 = CheckTargetDataPaths(v7);
        if ( v39 < 0 )
        {
          v8 = 0;
          v91 = 0;
          ReportAndLogVmErrorMessage1<std::wstring>((unsigned int)v103, v40, (_DWORD)v6, v39, (__int64)v103);
          CollectAndAddVmErrInfoToChain(&v94, v7, v12);
        }
      }
    }
    if ( (int)v100 >= 0 )
    {
      v41 = v105;
      if ( v106.m128i_i64[1] > 7uLL )
        v41 = (LPWSTR *)v105[0];
      v42 = pszPath;
      if ( v113.m128i_i64[1] > 7uLL )
        v42 = (LPWSTR *)pszPath[0];
      if ( (unsigned int)_o__wcsicmp(v42, v41) )
      {
        v43 = CheckTargetDataPaths(v7);
        if ( v43 < 0 )
        {
          v8 = 0;
          v91 = 0;
          v44 = v43 & 0xEFFFFFFF;
          _snwprintf_s<16>(v116, 16, L"%%%%%u", v43 & 0xEFFFFFFF);
          _snwprintf_s<16>(v114, 16, L"0x%08X", v44);
          v100 = (struct IVmErrInfo *)(*(__int64 (__fastcall **)(struct IVmmsVirtualMachineObject *))(*(_QWORD *)v6 + 32LL))(v6);
          VmEventWriteAndReport<std::wstring &,unsigned short const *,std::wstring &,unsigned short (&)[16],unsigned short (&)[16]>(
            v46,
            v45,
            v47,
            v48,
            (__int64)v109,
            (__int64)&v100,
            (__int64)v105,
            v116,
            (unsigned __int16 *)v114);
          CollectAndAddVmErrInfoToChain(&v94, v7, v12);
        }
      }
    }
    std::wstring::_Tidy_deallocate(v109);
    Vml::VmReferencePtr<SnapshotRepository,Vml::VmUserReferenceTraits>::~VmReferencePtr<SnapshotRepository,Vml::VmUserReferenceTraits>(&v92);
    std::wstring::_Tidy_deallocate(pszPath);
    std::wstring::_Tidy_deallocate(v105);
    std::wstring::_Tidy_deallocate(v103);
    std::wstring::_Tidy_deallocate(Src);
  }
  v107 = 0;
  v108 = 0;
  v111 = 0;
  v49 = (*(__int64 (__fastcall **)(struct IVmmsVirtualMachineObject *, __int128 *, struct IVmWmiClientContext *, __int64 *))(*(_QWORD *)v6 + 384LL))(
          v6,
          &v107,
          v7,
          v109);
  if ( v49 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x38D,
      (unsigned int)"onecore\\vm\\vmms\\common\\vmmsvalidation.cpp",
      (const char *)(unsigned int)v49,
      (int)v90);
  *(_OWORD *)v114 = 0;
  VmmsMigrationSettings::VmmsMigrationSettings((VmmsMigrationSettings *)v114, 0);
  v93 = VmmsMigrationSettings::UseStorageCachedCredentials((VmmsMigrationSettings *)v114);
  VmmsMigrationSettings::~VmmsMigrationSettings((VmmsMigrationSettings *)v114);
  for ( i = 0; ; ++i )
  {
    v92 = i;
    v51 = v107;
    if ( i >= 0xD37A6F4DE9BD37A7uLL * ((__int64)(*((_QWORD *)&v107 + 1) - v107) >> 3) )
      break;
    v52 = 184 * i;
    if ( !v93 )
      goto LABEL_78;
    v53 = (const WCHAR *)(v52 + v107);
    if ( *(_QWORD *)(v52 + v107 + 24) > 7u )
      v53 = *(const WCHAR **)v53;
    if ( !PathIsUNCEx(v53, 0) )
    {
      v51 = v107;
LABEL_78:
      if ( !*(_DWORD *)(v51 + v52 + 160) || *(_DWORD *)(v51 + v52 + 176) )
      {
        *(_OWORD *)v116 = 0;
        v76 = Vml::VmWmiImpersonator::Impersonate(v7);
        *(_QWORD *)v116 = v76;
        if ( v76 )
          (*(void (__fastcall **)(struct IVmWmiClientContext *))(*(_QWORD *)v76 + 8LL))(v76);
        LOBYTE(v116[4]) = 1;
        v77 = v52 + v107 + 128;
        if ( *(_QWORD *)(v77 + 24) > 7u )
          v77 = *(_QWORD *)v77;
        v95 = 0;
        Vml::VmBstr::Assign((Vml::VmBstr *)&v95, (const unsigned __int16 *)v77);
        *(_OWORD *)Src = 0;
        v102 = si128;
        LOWORD(Src[0]) = 0;
        *(_OWORD *)v109 = 0;
        v110 = si128;
        LOWORD(v109[0]) = 0;
        v92 = 0;
        VmErrInfo = GetVmErrInfo();
        Vml::VmComPtr<IICShutdown>::Attach<IICShutdown>(&v92, VmErrInfo);
        Vml::VmComPtr<IVssAsync>::~VmComPtr<IVssAsync>(&v92);
        v90 = v109;
        if ( (unsigned int)VmmsBlockDeviceUtils::RemapStorageFilePath(1, v95, v52 + v107, Src) == 1 )
          VmEventWriteAndReport(&MSVM_VMMS_VALIDATION_VHD_MISSING, 1u, v79, v80);
        v100 = 0;
        v81 = GetVmErrInfo();
        Vml::VmComPtr<IICShutdown>::Attach<IICShutdown>(&v100, v81);
        v82 = v100;
        if ( v100 )
        {
          v83 = 184 * i + v107 + 96;
          if ( *(_QWORD *)(v83 + 24) > 7u )
            v83 = *(_QWORD *)v83;
          v92 = 0;
          Vml::VmBstr::Assign((Vml::VmBstr *)&v92, (const unsigned __int16 *)v83);
          v84 = (*(__int64 (__fastcall **)(struct IVmErrInfo *, unsigned __int64))(*(_QWORD *)v82 + 120LL))(v82, v92);
          if ( v84 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x40F,
              (unsigned int)"onecore\\vm\\vmms\\common\\vmmsvalidation.cpp",
              (const char *)(unsigned int)v84,
              (int)v109);
          v8 = 0;
          v91 = 0;
          AddVmErrInfoToChain(&v94, v82);
          Vml::VmBstr::~VmBstr((Vml::VmBstr *)&v92);
        }
        Vml::VmComPtr<IVssAsync>::~VmComPtr<IVssAsync>(&v100);
        std::wstring::_Tidy_deallocate(v109);
        std::wstring::_Tidy_deallocate(Src);
        Vml::VmBstr::~VmBstr((Vml::VmBstr *)&v95);
        LOBYTE(v116[4]) = 0;
        Vml::VmWmiImpersonator::~VmWmiImpersonator((Vml::VmWmiImpersonator *)v116);
      }
      else if ( (*(unsigned int (__fastcall **)(struct IVmmsVirtualMachineObject *))(*(_QWORD *)v6 + 88LL))(v6) )
      {
        v100 = 0;
        VmEventWriteAndReport(&MSVM_VMMS_VALIDATION_PASS_THROUGH_DISK, 1u, v54, v55);
        v56 = GetVmErrInfo();
        Vml::VmComPtr<IICShutdown>::Attach<IICShutdown>(&v100, v56);
        v57 = v52 + v107 + 96;
        if ( *(_QWORD *)(v57 + 24) > 7u )
          v57 = *(_QWORD *)v57;
        v92 = 0;
        Vml::VmBstr::Assign((Vml::VmBstr *)&v92, (const unsigned __int16 *)v57);
        v58 = v100;
        v59 = (*(__int64 (__fastcall **)(struct IVmErrInfo *, unsigned __int64))(*(_QWORD *)v100 + 120LL))(v100, v92);
        if ( v59 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x3AF,
            (unsigned int)"onecore\\vm\\vmms\\common\\vmmsvalidation.cpp",
            (const char *)(unsigned int)v59,
            (int)v90);
        v8 = 0;
        v91 = 0;
        AddVmErrInfoToChain(&v94, v58);
        Vml::VmBstr::~VmBstr((Vml::VmBstr *)&v92);
        Vml::VmComPtr<IVssAsync>::~VmComPtr<IVssAsync>(&v100);
      }
      else
      {
        *(_OWORD *)v105 = 0;
        v106 = si128;
        LOWORD(v105[0]) = 0;
        *(_OWORD *)Src = 0;
        v102 = si128;
        LOWORD(Src[0]) = 0;
        v60 = (_QWORD *)(v52 + v107);
        if ( *(_QWORD *)(v52 + v107 + 24) > 7u )
          v60 = (_QWORD *)*v60;
        try
        {
          WmiStorageUtilities::GetWin32DeviceName(v60, Src);
          v61 = Src;
          if ( v102.m128i_i64[1] > 7uLL )
            v61 = (LPWSTR *)Src[0];
          std::wstring::wstring(v109, v61);
          PnpDevicePathFromPhysicalPath = GetPnpDevicePathFromPhysicalPath(v109, v62, v105);
          if ( PnpDevicePathFromPhysicalPath < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x3BD,
              (unsigned int)"onecore\\vm\\vmms\\common\\vmmsvalidation.cpp",
              (const char *)(unsigned int)PnpDevicePathFromPhysicalPath,
              (int)v90);
          std::wstring::_Tidy_deallocate(v109);
        }
        catch ( ... )
        {
          LODWORD(v100) = wil::details::in1diag3::Log_CaughtException(
                            retaddr,
                            (void *)0x3BF,
                            (unsigned int)"onecore\\vm\\vmms\\common\\vmmsvalidation.cpp",
                            v64);
          if ( (int)v100 >= 0 )
          {
            v8 = v91;
            si128 = _mm_load_si128((const __m128i *)&_xmm);
            i = v92;
            v6 = v98;
          }
          else
          {
            v65 = (unsigned int)v100 & 0xEFFFFFFF;
            _snwprintf_s<16>(v114, 16, L"%%%%%u", (unsigned int)v100 & 0xEFFFFFFF);
            _snwprintf_s<16>(pszPath, 16, L"0x%08X", v65);
            v100 = 0;
            *(_OWORD *)v103 = 0;
            si128 = _mm_load_si128((const __m128i *)&_xmm);
            v104 = si128;
            LOWORD(v103[0]) = 0;
            *(_OWORD *)v109 = 0;
            v110 = si128;
            LOWORD(v109[0]) = 0;
            v6 = v98;
            (*(void (__fastcall **)(struct IVmmsVirtualMachineObject *, LPWSTR *))(*(_QWORD *)v98 + 8LL))(v98, v103);
            v66 = (struct _GUID *)(*(__int64 (__fastcall **)(struct IVmmsVirtualMachineObject *))(*(_QWORD *)v6 + 24LL))(v6);
            Vml::VmGuid::ToString(v66, v109);
            v71 = Src;
            if ( v102.m128i_i64[1] > 7uLL )
              v71 = (LPWSTR *)Src[0];
            v95 = (__int64)v71;
            VmEventWriteAndReport<std::wstring &,std::wstring &,unsigned short const *,unsigned short (&)[16],unsigned short (&)[16]>(
              v68,
              v67,
              v69,
              v70,
              (__int64)v103,
              (__int64)v109,
              (__int64)&v95,
              (unsigned __int16 *)v114,
              (unsigned __int16 *)pszPath);
            v72 = GetVmErrInfo();
            Vml::VmComPtr<IICShutdown>::Attach<IICShutdown>(&v100, v72);
            i = v92;
            v73 = 184 * v92 + v107 + 96;
            if ( *(_QWORD *)(v73 + 24) > 7u )
              v73 = *(_QWORD *)v73;
            v92 = 0;
            Vml::VmBstr::Assign((Vml::VmBstr *)&v92, (const unsigned __int16 *)v73);
            v74 = v100;
            v75 = (*(__int64 (__fastcall **)(struct IVmErrInfo *, unsigned __int64))(*(_QWORD *)v100 + 120LL))(
                    v100,
                    v92);
            if ( v75 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x3DB,
                (unsigned int)"onecore\\vm\\vmms\\common\\vmmsvalidation.cpp",
                (const char *)(unsigned int)v75,
                (int)v90);
            v8 = 0;
            v91 = 0;
            AddVmErrInfoToChain(&v94, v74);
            Vml::VmBstr::~VmBstr((Vml::VmBstr *)&v92);
            std::wstring::_Tidy_deallocate(v109);
            std::wstring::_Tidy_deallocate(v103);
            Vml::VmComPtr<IVssAsync>::~VmComPtr<IVssAsync>(&v100);
          }
          v5 = v99;
          v7 = v97;
        }
        std::wstring::_Tidy_deallocate(Src);
        std::wstring::_Tidy_deallocate(v105);
      }
      continue;
    }
  }
  if ( v8 )
  {
    v85 = 0;
    v86 = 0;
  }
  else
  {
    v85 = v94;
    v86 = 270338;
  }
  (*(void (__fastcall **)(struct IVmTask *, __int64, struct IVmErrInfo *))(*(_QWORD *)v5 + 96LL))(v5, v86, v85);
  std::vector<VirtualHardDiskReference>::_Tidy(&v107);
  Vml::VmComPtr<IVssAsync>::~VmComPtr<IVssAsync>(&v96);
  Vml::VmComPtr<IVssAsync>::~VmComPtr<IVssAsync>(&v94);
  return v8;
}

```

## disassembly

```asm
0x140167204  mov     rax, rsp
0x140167207  push    rbx
0x140167208  push    rsi
0x140167209  push    rdi
0x14016720a  push    r12
0x14016720c  push    r13
0x14016720e  push    r14
0x140167210  push    r15
0x140167212  sub     rsp, 1D0h
0x140167219  movaps  xmmword ptr [rax-48h], xmm6
0x14016721d  mov     rax, cs:__security_cookie
0x140167224  xor     rax, rsp
0x140167227  mov     [rsp+208h+var_50], rax
0x14016722f  mov     ebx, r9d
0x140167232  mov     r13, r8
0x140167235  mov     r14, rdx
0x140167238  mov     r15, rcx
0x14016723b  mov     [rsp+208h+var_188], rcx
0x140167243  mov     [rsp+208h+var_180], rdx
0x14016724b  mov     [rsp+208h+var_178], r8
0x140167253  xor     edi, edi
0x140167255  mov     [rsp+208h+var_1A0], rdi
0x14016725a  lea     esi, [rdi+1]
0x14016725d  mov     [rsp+208h+var_1B8], esi
0x140167261  mov     [rsp+208h+var_190], rdi
0x140167266  mov     rax, [rdx]
0x140167269  xor     edx, edx
0x14016726b  mov     rcx, r14
0x14016726e  mov     rax, [rax+0A0h]
0x140167275  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14016727a  mov     rdx, rax
0x14016727d  lea     rcx, [rsp+208h+var_190]
0x140167282  call    ??$Attach@UIICShutdown@@@?$VmComPtr@UIICShutdown@@@Vml@@QEAAXPEAUIICShutdown@@@Z; Vml::VmComPtr<IICShutdown>::Attach<IICShutdown>(IICShutdown *)
0x140167287  test    ebx, ebx
0x140167289  jz      loc_140167373
0x14016728f  xor     r9d, r9d
0x140167292  lea     r8, ?VIRTUAL_MACHINE_CURRENT_SAVED_STATE_FILE@@3QBGB; "/configuration/savedstate/vsvlocation"
0x140167299  mov     rdx, r14
0x14016729c  mov     rcx, r15; struct IVmWmiClientContext *
0x14016729f  call    FindRuntimeFileInternal
0x1401672a4  test    eax, eax
0x1401672a6  jnz     short loc_1401672D4
0x1401672a8  mov     esi, edi
0x1401672aa  mov     [rsp+208h+var_1B8], edi
0x1401672ae  lea     edx, [rdi+1]; unsigned int
0x1401672b1  lea     rcx, MSVM_VMMS_VALIDATION_SAVE_STATE_FILE_MISSING; struct _EVENT_DESCRIPTOR *
0x1401672b8  call    ?VmEventWriteAndReport@@YAXPEBU_EVENT_DESCRIPTOR@@IAEBU_GUID@@PEBG@Z; VmEventWriteAndReport(_EVENT_DESCRIPTOR const *,uint,_GUID const &,ushort const *)
0x1401672bd  mov     rbx, [rsp+208h+var_190]
0x1401672c2  mov     r8, rbx; struct IVmWmiObject *
0x1401672c5  mov     rdx, r15; struct IVmWmiClientContext *
0x1401672c8  lea     rcx, [rsp+208h+var_1A0]; struct IVmErrInfo **
0x1401672cd  call    ?CollectAndAddVmErrInfoToChain@@YAXPEAPEAUIVmErrInfo@@PEAUIVmWmiClientContext@@PEAUIVmWmiObject@@@Z; CollectAndAddVmErrInfoToChain(IVmErrInfo * *,IVmWmiClientContext *,IVmWmiObject *)
0x1401672d2  jmp     short loc_140167333
0x1401672d4  mov     [rsp+208h+var_170], rdi
0x1401672dc  mov     rax, [r14]
0x1401672df  lea     r9, [rsp+208h+var_170]
0x1401672e7  mov     r8d, 1
0x1401672ed  mov     rdx, r15
0x1401672f0  mov     rcx, r14
0x1401672f3  mov     rax, [rax+230h]
0x1401672fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401672ff  test    eax, eax
0x140167301  jnz     short loc_140167321
0x140167303  mov     esi, edi
0x140167305  mov     [rsp+208h+var_1B8], edi
0x140167309  mov     rdx, [rsp+208h+var_170]; struct IVmErrInfo *
0x140167311  test    rdx, rdx
0x140167314  jz      short loc_140167321
0x140167316  lea     rcx, [rsp+208h+var_1A0]; struct IVmErrInfo **
0x14016731b  call    ?AddVmErrInfoToChain@@YAXPEAPEAUIVmErrInfo@@PEAU1@@Z; AddVmErrInfoToChain(IVmErrInfo * *,IVmErrInfo *)
0x140167320  nop
0x140167321  lea     rcx, [rsp+208h+var_170]; void *
0x140167329  call    ??1?$VmComPtr@UIVssAsync@@@Vml@@QEAA@XZ; Vml::VmComPtr<IVssAsync>::~VmComPtr<IVssAsync>(void)
0x14016732e  mov     rbx, [rsp+208h+var_190]
0x140167333  xor     r9d, r9d
0x140167336  lea     r8, ?VIRTUAL_MACHINE_CURRENT_MEMORY_FILE@@3QBGB; "/configuration/savedstate/memlocation"
0x14016733d  mov     rdx, r14
0x140167340  mov     rcx, r15; struct IVmWmiClientContext *
0x140167343  call    FindRuntimeFileInternal
0x140167348  test    eax, eax
0x14016734a  jnz     short loc_140167378
0x14016734c  mov     esi, edi
0x14016734e  mov     [rsp+208h+var_1B8], edi
0x140167352  lea     edx, [rax+1]; unsigned int
0x140167355  lea     rcx, MSVM_VMMS_VALIDATION_MEMORY_FILE_MISSING; struct _EVENT_DESCRIPTOR *
0x14016735c  call    ?VmEventWriteAndReport@@YAXPEBU_EVENT_DESCRIPTOR@@IAEBU_GUID@@PEBG@Z; VmEventWriteAndReport(_EVENT_DESCRIPTOR const *,uint,_GUID const &,ushort const *)
0x140167361  mov     r8, rbx; struct IVmWmiObject *
0x140167364  mov     rdx, r15; struct IVmWmiClientContext *
0x140167367  lea     rcx, [rsp+208h+var_1A0]; struct IVmErrInfo **
0x14016736c  call    ?CollectAndAddVmErrInfoToChain@@YAXPEAPEAUIVmErrInfo@@PEAUIVmWmiClientContext@@PEAUIVmWmiObject@@@Z; CollectAndAddVmErrInfoToChain(IVmErrInfo * *,IVmWmiClientContext *,IVmWmiObject *)
0x140167371  jmp     short loc_140167378
0x140167373  mov     rbx, [rsp+208h+var_190]
0x140167378  mov     rax, [r14]
0x14016737b  mov     rcx, r14
0x14016737e  mov     rax, [rax+58h]
0x140167382  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140167387  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x14016738f  test    eax, eax
0x140167391  jnz     loc_140167AB4
0x140167397  xorps   xmm0, xmm0
0x14016739a  movups  xmmword ptr [rsp+208h+Src], xmm0
0x1401673a2  movdqu  [rsp+208h+var_158], xmm6
0x1401673ab  mov     word ptr [rsp+208h+Src], di
0x1401673b3  movups  xmmword ptr [rsp+208h+var_148], xmm0
0x1401673bb  movdqu  [rsp+208h+var_138], xmm6
0x1401673c4  mov     word ptr [rsp+208h+var_148], di
0x1401673cc  movups  xmmword ptr [rsp+208h+var_128], xmm0
0x1401673d4  movdqu  [rsp+208h+var_118], xmm6
0x1401673dd  mov     word ptr [rsp+208h+var_128], di
0x1401673e5  movups  xmmword ptr [rsp+208h+pszPath], xmm0
0x1401673ed  movdqu  [rsp+208h+var_A0], xmm6
0x1401673f6  mov     word ptr [rsp+208h+pszPath], di
0x1401673fe  mov     [rsp+208h+var_1B0], rdi
0x140167403  mov     rax, [r14]
0x140167406  mov     rcx, r14
0x140167409  mov     rax, [rax+78h]
0x14016740d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140167412  mov     r12, rax
0x140167415  mov     [rsp+208h+var_170], rax
0x14016741d  xor     edx, edx
0x14016741f  lea     rcx, [rsp+208h+var_1B0]
0x140167424  call    ?Reset@?$VmReferencePtr@VSavedStateRepository@@VVmUserReferenceTraits@Vml@@@Vml@@QEAAXPEAVSavedStateRepository@@@Z; Vml::VmReferencePtr<SavedStateRepository,Vml::VmUserReferenceTraits>::Reset(SavedStateRepository *)
0x140167429  mov     [rsp+208h+var_1B0], r12
0x14016742e  xorps   xmm0, xmm0
0x140167431  movups  xmmword ptr [rsp+208h+var_F0], xmm0
0x140167439  movdqu  [rsp+208h+var_E0], xmm6
0x140167442  mov     word ptr [rsp+208h+var_F0], di
0x14016744a  mov     rax, [r14]
0x14016744d  lea     rdx, [rsp+208h+var_F0]
0x140167455  mov     rcx, r14
0x140167458  mov     rax, [rax+8]
0x14016745c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140167461  xorps   xmm0, xmm0
0x140167464  movups  xmmword ptr [rsp+208h+var_90], xmm0
0x14016746c  lea     rcx, [rsp+208h+var_70]
0x140167474  call    ??$make_unique@VVmMachineLocalSettingsStore@Vml@@$$V$0A@@std@@YA?AV?$unique_ptr@VVmMachineLocalSettingsStore@Vml@@U?$default_delete@VVmMachineLocalSettingsStore@Vml@@@std@@@0@XZ; std::make_unique<Vml::VmMachineLocalSettingsStore,,0>(void)
0x140167479  mov     rcx, rax
0x14016747c  mov     rax, [rax]
0x14016747f  mov     [rcx], rdi
0x140167482  mov     [rsp+208h+var_198], rax
0x140167487  lea     r9, [rsp+208h+var_198]
0x14016748c  xor     edx, edx
0x14016748e  lea     rcx, [rsp+208h+var_90]
0x140167496  call    ??0VmmsSettings@@QEAA@HPEBG$$QEAV?$unique_ptr@VISettingsStore@@U?$default_delete@VISettingsStore@@@std@@@std@@@Z; VmmsSettings::VmmsSettings(int,ushort const *,std::unique_ptr<ISettingsStore> &&)
0x14016749b  nop
0x14016749c  lea     rcx, [rsp+208h+var_198]
0x1401674a1  call    ??1?$unique_ptr@V?$VmDispatchContextWithParams@X_NPEAUIVmTask@@@Vml@@U?$default_delete@V?$VmDispatchContextWithParams@X_NPEAUIVmTask@@@Vml@@@std@@@std@@QEAA@XZ; std::unique_ptr<Vml::VmDispatchContextWithParams<void,bool,IVmTask *>>::~unique_ptr<Vml::VmDispatchContextWithParams<void,bool,IVmTask *>>(void)
0x1401674a6  nop
0x1401674a7  lea     rcx, [rsp+208h+var_70]
0x1401674af  call    ??1?$unique_ptr@V?$VmDispatchContextWithParams@X_NPEAUIVmTask@@@Vml@@U?$default_delete@V?$VmDispatchContextWithParams@X_NPEAUIVmTask@@@Vml@@@std@@@std@@QEAA@XZ; std::unique_ptr<Vml::VmDispatchContextWithParams<void,bool,IVmTask *>>::~unique_ptr<Vml::VmDispatchContextWithParams<void,bool,IVmTask *>>(void)
0x1401674b4  lea     rdx, [rsp+208h+pszPath]
0x1401674bc  lea     rcx, [rsp+208h+var_90]
0x1401674c4  call    ?GetDefaultExternalDataRoot@VmmsSettings@@QEBAHAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; VmmsSettings::GetDefaultExternalDataRoot(std::wstring &)
0x1401674c9  mov     edx, 104h
0x1401674ce  lea     rcx, [rsp+208h+pszPath]; Src
0x1401674d6  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x1401674db  lea     rcx, [rsp+208h+pszPath]
0x1401674e3  cmp     qword ptr [rsp+208h+var_A0+8], 7
0x1401674ec  cmova   rcx, [rsp+208h+pszPath]; pszPath
0x1401674f5  call    cs:__imp_PathAddBackslashW
0x1401674fc  nop     dword ptr [rax+rax+00h]
0x140167501  test    rax, rax
0x140167504  jnz     short loc_140167526
0x140167506  mov     rcx, [rsp+208h]; this
0x14016750e  mov     r9d, 8007000Eh; char *
0x140167514  lea     r8, aOnecoreVmVmmsC_13; "onecore\\vm\\vmms\\common\\vmmsvalidati"...
0x14016751b  mov     edx, 327h; void *
0x140167520  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140167526  lea     rax, [rsp+208h+pszPath]
0x14016752e  cmp     qword ptr [rsp+208h+var_A0+8], 7
0x140167537  cmova   rax, [rsp+208h+pszPath]
0x140167540  or      r12, 0FFFFFFFFFFFFFFFFh
0x140167544  mov     rdx, r12
0x140167547  inc     rdx
0x14016754a  cmp     [rax+rdx*2], di
0x14016754e  jnz     short loc_140167547
0x140167550  lea     rcx, [rsp+208h+pszPath]; Src
0x140167558  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x14016755d  nop
0x14016755e  lea     rcx, [rsp+208h+var_90]; this
0x140167566  call    ??1VmmsSettings@@QEAA@XZ; VmmsSettings::~VmmsSettings(void)
0x14016756b  xorps   xmm0, xmm0
0x14016756e  movups  xmmword ptr [rsp+208h+var_90], xmm0
0x140167576  xor     r8d, r8d
0x140167579  mov     rdx, [rsp+208h+var_170]
0x140167581  lea     rcx, [rsp+208h+var_90]
0x140167589  call    ??0VmRepositoryAutoLock@@QEAA@PEAVVmRepository@@W4VmRepositoryLockFlags@@@Z; VmRepositoryAutoLock::VmRepositoryAutoLock(VmRepository *,VmRepositoryLockFlags)
0x14016758e  nop
0x14016758f  mov     r9d, dword ptr [rsp+208h+var_90+8]; char *
0x140167597  mov     rcx, [rsp+208h]; this
0x14016759f  test    r9d, r9d
0x1401675a2  jns     short loc_1401675B6
0x1401675a4  lea     r8, aOnecoreVmVmmsC_13; "onecore\\vm\\vmms\\common\\vmmsvalidati"...
0x1401675ab  mov     edx, 330h; void *
0x1401675b0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1401675b6  mov     rcx, [rsp+208h+var_170]
0x1401675be  mov     rax, [rcx]
0x1401675c1  lea     r8, [rsp+208h+Src]
0x1401675c9  lea     rdx, ?VIRTUAL_MACHINE_DATA_ROOT_XPATH@@3QBGB; "/configuration/global_settings/data_roo"...
0x1401675d0  mov     rax, [rax+68h]
0x1401675d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401675d9  mov     dword ptr [rsp+208h+var_70], eax
0x1401675e0  mov     rcx, [rsp+208h+var_170]
0x1401675e8  mov     rax, [rcx]
0x1401675eb  lea     r8, [rsp+208h+var_148]
0x1401675f3  lea     rdx, ?VIRTUAL_MACHINE_SNAPSHOT_DATA_ROOT_XPATH@@3QBGB; "/configuration/global_settings/snapshot"...
0x1401675fa  mov     rax, [rax+68h]
0x1401675fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140167603  mov     dword ptr [rsp+208h+var_198], eax
0x140167607  mov     rcx, [rsp+208h+var_170]
0x14016760f  mov     rax, [rcx]
0x140167612  lea     r8, [rsp+208h+var_128]
0x14016761a  lea     rdx, ?VIRTUAL_MACHINE_SLP_DATA_ROOT_XPATH@@3QBGB; "/configuration/global_settings/slp_data"...
0x140167621  mov     rax, [rax+68h]
0x140167625  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14016762a  mov     dword ptr [rsp+208h+var_170], eax
0x140167631  lea     rcx, [rsp+208h+var_90]; this
0x140167639  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x14016763e  mov     edx, 104h
0x140167643  lea     rcx, [rsp+208h+Src]; Src
0x14016764b  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x140167650  mov     edx, 104h
0x140167655  lea     rcx, [rsp+208h+var_148]; Src
0x14016765d  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x140167662  mov     edx, 104h
0x140167667  lea     rcx, [rsp+208h+var_128]; Src
0x14016766f  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x140167674  lea     rcx, [rsp+208h+Src]
0x14016767c  cmp     qword ptr [rsp+208h+var_158+8], 7
0x140167685  cmova   rcx, [rsp+208h+Src]; pszPath
0x14016768e  call    cs:__imp_PathAddBackslashW
0x140167695  nop     dword ptr [rax+rax+00h]
0x14016769a  test    rax, rax
0x14016769d  jz      loc_140167B16
0x1401676a3  lea     rcx, [rsp+208h+var_148]
0x1401676ab  cmp     qword ptr [rsp+208h+var_138+8], 7
0x1401676b4  cmova   rcx, [rsp+208h+var_148]; pszPath
0x1401676bd  call    cs:__imp_PathAddBackslashW
0x1401676c4  nop     dword ptr [rax+rax+00h]
0x1401676c9  test    rax, rax
0x1401676cc  jz      loc_140167B16
0x1401676d2  lea     rcx, [rsp+208h+var_128]
0x1401676da  cmp     qword ptr [rsp+208h+var_118+8], 7
0x1401676e3  cmova   rcx, [rsp+208h+var_128]; pszPath
0x1401676ec  call    cs:__imp_PathAddBackslashW
0x1401676f3  nop     dword ptr [rax+rax+00h]
0x1401676f8  test    rax, rax
0x1401676fb  jz      loc_140167B16
0x140167701  lea     rax, [rsp+208h+Src]
0x140167709  cmp     qword ptr [rsp+208h+var_158+8], 7
0x140167712  cmova   rax, [rsp+208h+Src]
0x14016771b  mov     rdx, r12
0x14016771e  inc     rdx
0x140167721  cmp     [rax+rdx*2], di
0x140167725  jnz     short loc_14016771E
0x140167727  lea     rcx, [rsp+208h+Src]; Src
0x14016772f  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x140167734  lea     rax, [rsp+208h+var_148]
0x14016773c  cmp     qword ptr [rsp+208h+var_138+8], 7
0x140167745  cmova   rax, [rsp+208h+var_148]
0x14016774e  mov     rdx, r12
0x140167751  inc     rdx
0x140167754  cmp     [rax+rdx*2], di
0x140167758  jnz     short loc_140167751
0x14016775a  lea     rcx, [rsp+208h+var_148]; Src
0x140167762  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x140167767  lea     rax, [rsp+208h+var_128]
0x14016776f  cmp     qword ptr [rsp+208h+var_118+8], 7
0x140167778  cmova   rax, [rsp+208h+var_128]
0x140167781  inc     r12
0x140167784  cmp     [rax+r12*2], di
0x140167789  jnz     short loc_140167781
0x14016778b  mov     rdx, r12
0x14016778e  lea     rcx, [rsp+208h+var_128]; Src
0x140167796  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x14016779b  cmp     dword ptr [rsp+208h+var_70], edi
0x1401677a2  jl      loc_1401678B3
0x1401677a8  lea     rdx, [rsp+208h+Src]
0x1401677b0  cmp     qword ptr [rsp+208h+var_158+8], 7
0x1401677b9  cmova   rdx, [rsp+208h+Src]
0x1401677c2  lea     rcx, [rsp+208h+pszPath]
0x1401677ca  cmp     qword ptr [rsp+208h+var_A0+8], 7
0x1401677d3  cmova   rcx, [rsp+208h+pszPath]
0x1401677dc  call    cs:__imp__o__wcsicmp
0x1401677e3  nop     dword ptr [rax+rax+00h]
0x1401677e8  test    eax, eax
0x1401677ea  jz      loc_1401678B3
0x1401677f0  lea     rdx, [rsp+208h+Src]
0x1401677f8  mov     rcx, r15; struct IVmWmiClientContext *
0x1401677fb  call    CheckTargetDataPaths
0x140167800  mov     r12d, eax
0x140167803  mov     dword ptr [rsp+208h+var_70], eax
0x14016780a  test    eax, eax
0x14016780c  jns     loc_1401678B3
0x140167812  mov     esi, edi
0x140167814  mov     [rsp+208h+var_1B8], edi
0x140167818  xorps   xmm0, xmm0
0x14016781b  movups  xmmword ptr [rsp+208h+var_90], xmm0
0x140167823  movdqu  [rsp+208h+var_80], xmm6
0x14016782c  mov     word ptr [rsp+208h+var_90], di
  ... truncated ...
```
