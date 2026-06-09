# DataPersistence::CDataPersistence::GetRegKey(ushort const *,ushort const *,bool,HKEY__ * *)

- ea: `0x18005e928`
- end: `0x18005f2ca`
- name: `?GetRegKey@CDataPersistence@DataPersistence@@AEAAJPEBG0_NPEAPEAUHKEY__@@@Z`
- size: `2466`
- prototype: `int(DataPersistence::CDataPersistence *__hidden this, const unsigned __int16 *, const unsigned __int16 *, bool, HKEY *)`
- caller_count: `9`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18005e3a0`
- `0x18005e530`
- `0x18005e5c0`
- `0x18005e6c8`
- `0x18005e820`
- `0x1800fc4c0`
- `0x1801d9e78`
- `0x1801da030`
- `0x1801da220`

## callees

- `0x18003c5e4`
- `0x180047224`
- `0x18005e928`
- `0x18005f2f8`
- `0x18008943c`
- `0x1800a663c`
- `0x1800a665c`
- `0x1800ead54`
- `0x1801045d4`
- `0x18010701c`
- `0x18013d330`
- `0x18013df8c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18005e9c8`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18005e9c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ebbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ebbf`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005ed95`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005ef6a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005f223`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005f2b2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005ed95`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005ef6a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005f223`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005f2b2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005ed04`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005ed14`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005ed46`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005edca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005edda`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005ee3a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005eec5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005eed9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005efa6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005efe9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005f018`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005f196`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005f1b8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005ed04`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005ed14`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005ed46`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005edca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005edda`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005ee3a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005eec5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005eed9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005efa6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005efe9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005f018`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005f196`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005f1b8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005ec3c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005ec7f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005ecb9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005ee66`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005eea1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005ec3c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005ec7f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005ecb9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005ee66`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005eea1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005ea2b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005ed27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005eded`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005eee7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005ef1c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005effc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005f023`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005f0fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005f17e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005f278`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005ea2b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005ed27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005eded`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005eee7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005ef1c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005effc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005f023`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005f0fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005f17e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005f278`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005eaeb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005ebd9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005eaeb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005ebd9`
- `api-ms-win-appmodel-state-l1-2-0!OpenStateExplicit` at `0x18005eb8b`
- `api-ms-win-appmodel-state-l1-2-0!OpenStateExplicit` at `0x18005eb8b`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x18005ebb1`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x18005ec0a`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x18005ebb1`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x18005ec0a`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x18005ed30`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x18005edf6`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x18005f005`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x18005ed30`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x18005edf6`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x18005f005`

## pseudocode

```c
__int64 __fastcall DataPersistence::CDataPersistence::GetRegKey(
        DataPersistence::CDataPersistence *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        char a4,
        PHKEY a5)
{
  wchar_t *v5; // rax
  __int64 v7; // rbx
  const unsigned __int16 *v9; // r8
  __int64 v10; // rcx
  __int64 v11; // rdx
  wchar_t *v12; // rcx
  wchar_t *v13; // rax
  unsigned int LastError; // edi
  _WORD *v15; // rbx
  _WORD *v17; // r8
  __int64 v18; // rdx
  __int64 v19; // r9
  wchar_t *v20; // rcx
  __int64 v21; // rax
  _WORD *v22; // r10
  _WORD *v23; // rcx
  unsigned __int64 v24; // r14
  unsigned __int64 v25; // rsi
  __int64 v26; // r8
  __int64 v27; // r9
  _WORD *v28; // rcx
  unsigned __int64 v29; // rdx
  _WORD *v30; // rax
  _WORD *v31; // rcx
  __int64 v32; // rax
  const char *v33; // r9
  __int64 v34; // rdi
  __int64 v35; // rsi
  _WORD *v36; // r14
  const char *v37; // r9
  int v38; // esi
  bool v39; // sf
  LSTATUS v40; // eax
  bool v41; // sf
  LSTATUS v42; // eax
  bool v43; // sf
  char v44; // si
  HKEY v45; // rsi
  unsigned int v46; // eax
  __int64 v47; // rdx
  LSTATUS v48; // eax
  bool v49; // sf
  LSTATUS v50; // eax
  bool v51; // sf
  HKEY v52; // rsi
  unsigned int v53; // eax
  unsigned __int64 v54; // rsi
  bool v55; // cf
  int Error; // eax
  __int64 v57; // rdx
  unsigned int Key; // eax
  int phkResult; // [rsp+20h] [rbp-E0h]
  int phkResulta; // [rsp+20h] [rbp-E0h]
  unsigned int phkResultb; // [rsp+20h] [rbp-E0h]
  unsigned int phkResultc; // [rsp+20h] [rbp-E0h]
  unsigned int phkResultd; // [rsp+20h] [rbp-E0h]
  HKEY v65; // [rsp+58h] [rbp-A8h] BYREF
  HKEY v66; // [rsp+60h] [rbp-A0h] BYREF
  HKEY v67; // [rsp+68h] [rbp-98h] BYREF
  HKEY v68; // [rsp+70h] [rbp-90h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-88h] BYREF
  __int64 v70; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v71; // [rsp+88h] [rbp-78h] BYREF
  _WORD v72[72]; // [rsp+90h] [rbp-70h] BYREF
  wchar_t Str[136]; // [rsp+120h] [rbp+20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  v5 = Str;
  v72[0] = 0;
  v7 = 2147483646;
  v9 = a2;
  *a5 = 0;
  v10 = 2147483646;
  v11 = 130;
  do
  {
    if ( !v10 )
      break;
    if ( !*v9 )
      break;
    *v5++ = *v9++;
    --v10;
    --v11;
  }
  while ( v11 );
  v12 = v5 - 1;
  if ( v11 )
    v12 = v5;
  *v12 = 0;
  if ( !v11 || (v13 = wcsrchr(Str, 0x21u), Str[0] == 33) || !v13 || (v17 = v13 + 1, !v13[1]) )
  {
    LastError = -2147024809;
LABEL_10:
    v15 = 0;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDD,
      (unsigned int)"shell\\twinui\\datapersistence\\lib\\datapersistence.cpp",
      (const char *)LastError,
      phkResult);
LABEL_12:
    if ( v15 )
      CoTaskMemFree(v15);
    return LastError;
  }
  v18 = 65;
  *v13 = 0;
  v19 = 65;
  v20 = Str;
  v21 = 2147483646;
  v22 = v72;
  do
  {
    if ( !v21 )
      break;
    if ( !*v20 )
      break;
    *v22++ = *v20++;
    --v21;
    --v19;
  }
  while ( v19 );
  v23 = v22 - 1;
  LastError = v19 == 0 ? 0x8007007A : 0;
  if ( v19 )
    v23 = v22;
  *v23 = 0;
  if ( v19 )
  {
    do
    {
      if ( !v7 )
        break;
      if ( !*v17 )
        break;
      ++v17;
      --v7;
      --v18;
    }
    while ( v18 );
    LastError = v18 == 0 ? 0x8007007A : 0;
  }
  if ( (LastError & 0x80000000) != 0 )
    goto LABEL_10;
  v24 = -1;
  do
    ++v24;
  while ( v72[v24] );
  v25 = v24 + 1;
  if ( v24 + 1 < v24 || (v70 = 0, !is_mul_ok(v25, 2u)) )
  {
    LastError = -2147024362;
    goto LABEL_10;
  }
  v15 = CoTaskMemAlloc(2 * v25);
  LastError = v15 == 0 ? 0x8007000E : 0;
  if ( !v15 )
    goto LABEL_11;
  if ( v25 > 0x7FFFFFFF )
  {
LABEL_113:
    *v15 = 0;
    goto LABEL_40;
  }
  if ( v24 >= 0x7FFFFFFF )
  {
    if ( v24 == -1 )
      goto LABEL_40;
    goto LABEL_113;
  }
  v28 = v72;
  v29 = v24 + 1;
  v30 = v15;
  v26 = 0;
  do
  {
    if ( !v24 )
      break;
    if ( !*v28 )
      break;
    *v30++ = *v28++;
    --v24;
    ++v26;
    --v29;
  }
  while ( v29 );
  v31 = v30 - 1;
  v27 = v26 - 1;
  if ( v29 )
  {
    v31 = v30;
    v27 = v26;
  }
  *v31 = 0;
  if ( v29 )
  {
    v55 = v25 == v27;
    v54 = v25 - v27;
    if ( !v55 && v54 != 1 )
    {
      v26 = 2 * v54;
      if ( 2 * v54 > 2 )
        memset_0(&v15[v27 + 1], 0, v26 - 2);
    }
  }
LABEL_40:
  v32 = OpenStateExplicit(-4, v15, v26, v27);
  v70 = v32;
  v34 = v32;
  if ( !v32 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xE0,
                  (unsigned int)"shell\\twinui\\datapersistence\\lib\\datapersistence.cpp",
                  v33);
    goto LABEL_12;
  }
  v71 = 0;
  if ( (unsigned int)GetSystemAppDataKey(v32, 0, 0, &v71) )
  {
    LastError = -2147418113;
    v47 = 228;
    goto LABEL_78;
  }
  if ( GetLastError() != 122 )
  {
    Error = ResultFromKnownLastError();
    v38 = Error;
    if ( Error < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE7,
        (unsigned int)"shell\\twinui\\datapersistence\\lib\\datapersistence.cpp",
        (const char *)(unsigned int)Error,
        phkResult);
LABEL_118:
      wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v70);
LABEL_76:
      CoTaskMemFree(v15);
      return (unsigned int)v38;
    }
  }
  v35 = v71;
  v36 = CoTaskMemAlloc(2LL * v71 + 2);
  if ( !v36 )
  {
    LastError = -2147024882;
    v47 = 236;
LABEL_78:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v47,
      (unsigned int)"shell\\twinui\\datapersistence\\lib\\datapersistence.cpp",
      (const char *)LastError,
      phkResult);
LABEL_79:
    wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v70);
    goto LABEL_12;
  }
  *v36 = 0;
  v36[v35] = 0;
  hKey = 0;
  if ( !(unsigned int)GetSystemAppDataKey(v34, &hKey, v36, &v71) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xF0,
                  (unsigned int)"shell\\twinui\\datapersistence\\lib\\datapersistence.cpp",
                  v37);
LABEL_121:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    CoTaskMemFree(v36);
    goto LABEL_79;
  }
  v68 = 0;
  v38 = RegOpenKeyExW(hKey, v36, 0, 0xF003Fu, &v68);
  v39 = v38 < 0;
  if ( v38 > 0 )
  {
    v38 = (unsigned __int16)v38 | 0x80070000;
    v39 = v38 < 0;
  }
  if ( !v39 )
  {
    v67 = 0;
    v40 = RegOpenKeyExW(v68, L"ApplicationFrame", 0, 0xF003Fu, &v67);
    v41 = v40 < 0;
    if ( v40 > 0 )
      v41 = 1;
    if ( v41 )
    {
      v45 = v67;
      if ( v67 )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v65);
        RegCloseKey(v45);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v65);
      }
      v67 = 0;
      v46 = RegCreateKeyExW(v68, L"ApplicationFrame", 0, 0, 0, 0xF003Fu, 0, &v67, 0);
      if ( v46 )
      {
        v38 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x100,
                (unsigned int)"shell\\twinui\\datapersistence\\lib\\datapersistence.cpp",
                (const char *)v46,
                phkResultb);
LABEL_69:
        if ( v67 )
          RegCloseKey(v67);
        if ( v68 )
          RegCloseKey(v68);
        if ( hKey )
          RegCloseKey(hKey);
        CoTaskMemFree(v36);
        CloseState(v34);
        goto LABEL_76;
      }
    }
    v66 = 0;
    v42 = RegOpenKeyExW(v67, a2, 0, 0xF003Fu, &v66);
    v43 = v42 < 0;
    if ( v42 > 0 )
      v43 = 1;
    if ( v43 )
    {
      v52 = v66;
      if ( v66 )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v65);
        RegCloseKey(v52);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v65);
      }
      v66 = 0;
      v53 = RegCreateKeyExW(v67, a2, 0, 0, 0, 0xF003Fu, 0, &v66, 0);
      if ( v53 )
      {
        v38 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x106,
                (unsigned int)"shell\\twinui\\datapersistence\\lib\\datapersistence.cpp",
                (const char *)v53,
                phkResultc);
        if ( v66 )
          RegCloseKey(v66);
        goto LABEL_69;
      }
    }
    if ( a3 && *a3 )
    {
      v44 = a4;
    }
    else
    {
      v44 = a4;
      if ( !a4 )
      {
        *a5 = v66;
        v66 = 0;
        goto LABEL_57;
      }
    }
    v65 = 0;
    v48 = RegOpenKeyExW(v66, L"ApplicationWindows", 0, 0xF003Fu, &v65);
    v49 = v48 < 0;
    if ( v48 > 0 )
      v49 = 1;
    if ( v49 )
    {
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &v65,
        0);
      Key = RegCreateKeyExW(v66, L"ApplicationWindows", 0, 0, 0, 0xF003Fu, 0, &v65, 0);
      if ( Key )
      {
        v57 = 276;
LABEL_120:
        LastError = wil::details::in1diag3::Return_Win32(
                      retaddr,
                      (void *)v57,
                      (unsigned int)"shell\\twinui\\datapersistence\\lib\\datapersistence.cpp",
                      (const char *)Key,
                      phkResultd);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v65);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v66);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v67);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v68);
        goto LABEL_121;
      }
    }
    if ( v44 )
    {
      *a5 = v65;
      v65 = 0;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v65);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v66);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v67);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v68);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      CoTaskMemFree(v36);
      wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v70);
LABEL_64:
      CoTaskMemFree(v15);
      return 0;
    }
    v50 = RegOpenKeyExW(v65, a3, 0, 0xF003Fu, a5);
    v51 = v50 < 0;
    if ( v50 > 0 )
      v51 = 1;
    if ( v51 )
    {
      Key = RegCreateKeyExW(v65, a3, 0, 0, 0, 0xF003Fu, 0, a5, 0);
      if ( Key )
      {
        v57 = 287;
        goto LABEL_120;
      }
    }
    if ( v65 )
      RegCloseKey(v65);
    if ( v66 )
      RegCloseKey(v66);
LABEL_57:
    if ( v67 )
      RegCloseKey(v67);
    if ( v68 )
      RegCloseKey(v68);
    if ( hKey )
      RegCloseKey(hKey);
    CoTaskMemFree(v36);
    CloseState(v34);
    goto LABEL_64;
  }
  if ( v38 != -2147024894 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFB,
      (unsigned int)"shell\\twinui\\datapersistence\\lib\\datapersistence.cpp",
      (const char *)(unsigned int)v38,
      phkResulta);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v68);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    CoTaskMemFree(v36);
    goto LABEL_118;
  }
  if ( v68 )
    RegCloseKey(v68);
  if ( hKey )
    RegCloseKey(hKey);
  CoTaskMemFree(v36);
  CloseState(v34);
  CoTaskMemFree(v15);
  return 2147942402LL;
}

```

## disassembly

```asm
0x18005e928  mov     [rsp-8+arg_0], rbx
0x18005e92d  push    rbp
0x18005e92e  push    rsi
0x18005e92f  push    rdi
0x18005e930  push    r12
0x18005e932  push    r13
0x18005e934  push    r14
0x18005e936  push    r15
0x18005e938  lea     rbp, [rsp-140h]
0x18005e940  sub     rsp, 240h
0x18005e947  mov     rax, cs:__security_cookie
0x18005e94e  xor     rax, rsp
0x18005e951  mov     [rbp+170h+var_40], rax
0x18005e958  mov     r15, [rbp+170h+arg_20]
0x18005e95f  lea     rax, [rbp+170h+Str]
0x18005e963  xor     r14d, r14d
0x18005e966  mov     [rsp+270h+var_220], r9b
0x18005e96b  mov     r12, r8
0x18005e96e  mov     [rbp+170h+var_1E0], r14w
0x18005e973  mov     ebx, 7FFFFFFEh
0x18005e978  mov     r13, rdx
0x18005e97b  mov     r8, rdx
0x18005e97e  mov     [r15], r14
0x18005e981  mov     ecx, ebx
0x18005e983  mov     edx, 82h
0x18005e988  test    rcx, rcx
0x18005e98b  jz      short loc_18005E9AC
0x18005e98d  movzx   r9d, word ptr [r8]
0x18005e991  test    r9w, r9w
0x18005e995  jz      short loc_18005E9AC
0x18005e997  mov     [rax], r9w
0x18005e99b  add     r8, 2
0x18005e99f  add     rax, 2
0x18005e9a3  dec     rcx
0x18005e9a6  sub     rdx, 1
0x18005e9aa  jnz     short loc_18005E988
0x18005e9ac  test    rdx, rdx
0x18005e9af  lea     rcx, [rax-2]
0x18005e9b3  cmovnz  rcx, rax
0x18005e9b7  mov     [rcx], r14w
0x18005e9bb  jz      short loc_18005E9D4
0x18005e9bd  mov     edi, 21h ; '!'
0x18005e9c2  lea     rcx, [rbp+170h+Str]; Str
0x18005e9c6  mov     edx, edi; Ch
0x18005e9c8  call    cs:__imp_wcsrchr
0x18005e9ce  cmp     di, [rbp+170h+Str]
0x18005e9d2  jnz     short loc_18005EA33
0x18005e9d4  mov     edi, 80070057h
0x18005e9d9  mov     rbx, r14
0x18005e9dc  mov     rcx, [rbp+178h]; this
0x18005e9e3  lea     r8, aShellTwinuiDat; "shell\\twinui\\datapersistence\\lib\\da"...
0x18005e9ea  mov     r9d, edi; char *
0x18005e9ed  mov     edx, 0DDh; void *
0x18005e9f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005e9f7  test    rbx, rbx
0x18005e9fa  jnz     short loc_18005EA28
0x18005e9fc  mov     eax, edi
0x18005e9fe  mov     rcx, [rbp+170h+var_40]
0x18005ea05  xor     rcx, rsp; StackCookie
0x18005ea08  call    __security_check_cookie
0x18005ea0d  mov     rbx, [rsp+270h+arg_0]
0x18005ea15  add     rsp, 240h
0x18005ea1c  pop     r15
0x18005ea1e  pop     r14
0x18005ea20  pop     r13
0x18005ea22  pop     r12
0x18005ea24  pop     rdi
0x18005ea25  pop     rsi
0x18005ea26  pop     rbp
0x18005ea27  retn
0x18005ea28  mov     rcx, rbx; pv
0x18005ea2b  call    cs:__imp_CoTaskMemFree
0x18005ea31  jmp     short loc_18005E9FC
0x18005ea33  test    rax, rax
0x18005ea36  jz      short loc_18005E9D4
0x18005ea38  lea     r8, [rax+2]
0x18005ea3c  cmp     r14w, [r8]
0x18005ea40  jz      short loc_18005E9D4
0x18005ea42  mov     edx, 41h ; 'A'
0x18005ea47  mov     [rax], r14w
0x18005ea4b  mov     r9d, edx
0x18005ea4e  lea     rcx, [rbp+170h+Str]
0x18005ea52  mov     rax, rbx
0x18005ea55  lea     r10, [rbp+170h+var_1E0]
0x18005ea59  test    rax, rax
0x18005ea5c  jz      short loc_18005EA7D
0x18005ea5e  movzx   r11d, word ptr [rcx]
0x18005ea62  test    r11w, r11w
0x18005ea66  jz      short loc_18005EA7D
0x18005ea68  mov     [r10], r11w
0x18005ea6c  add     rcx, 2
0x18005ea70  add     r10, 2
0x18005ea74  dec     rax
0x18005ea77  sub     r9, 1
0x18005ea7b  jnz     short loc_18005EA59
0x18005ea7d  mov     rax, r9
0x18005ea80  lea     rcx, [r10-2]
0x18005ea84  neg     rax
0x18005ea87  mov     r11d, 8007007Ah
0x18005ea8d  sbb     edi, edi
0x18005ea8f  not     edi
0x18005ea91  and     edi, r11d
0x18005ea94  test    r9, r9
0x18005ea97  cmovnz  rcx, r10
0x18005ea9b  mov     [rcx], r14w
0x18005ea9f  jnz     loc_18005EEF2
0x18005eaa5  test    edi, edi
0x18005eaa7  js      loc_18005E9D9
0x18005eaad  or      r14, 0FFFFFFFFFFFFFFFFh
0x18005eab1  lea     rax, [rbp+170h+var_1E0]
0x18005eab5  xor     ecx, ecx
0x18005eab7  inc     r14
0x18005eaba  cmp     [rax+r14*2], cx
0x18005eabf  jnz     short loc_18005EAB7
0x18005eac1  lea     rsi, [r14+1]
0x18005eac5  cmp     rsi, r14
0x18005eac8  jb      short loc_18005EADB
0x18005eaca  mov     eax, 2
0x18005eacf  mov     [rbp+170h+var_1F0], rcx
0x18005ead3  mul     rsi
0x18005ead6  test    rdx, rdx
0x18005ead9  jz      short loc_18005EAE8
0x18005eadb  xor     r14d, r14d
0x18005eade  mov     edi, 80070216h
0x18005eae3  jmp     loc_18005E9D9
0x18005eae8  mov     rcx, rax; cb
0x18005eaeb  call    cs:__imp_CoTaskMemAlloc
0x18005eaf1  mov     rbx, rax
0x18005eaf4  neg     rax
0x18005eaf7  sbb     edi, edi
0x18005eaf9  xor     r10d, r10d
0x18005eafc  not     edi
0x18005eafe  and     edi, 8007000Eh
0x18005eb04  test    rbx, rbx
0x18005eb07  jz      loc_18005F02B
0x18005eb0d  mov     eax, 7FFFFFFFh
0x18005eb12  cmp     rsi, rax
0x18005eb15  ja      loc_18005F03B
0x18005eb1b  cmp     r14, rax
0x18005eb1e  jnb     loc_18005F07A
0x18005eb24  test    rsi, rsi
0x18005eb27  jz      loc_18005F040
0x18005eb2d  lea     rcx, [rbp+170h+var_1E0]
0x18005eb31  mov     rdx, rsi
0x18005eb34  mov     rax, rbx
0x18005eb37  mov     r8d, r10d
0x18005eb3a  test    r14, r14
0x18005eb3d  jz      short loc_18005EB61
0x18005eb3f  movzx   r9d, word ptr [rcx]
0x18005eb43  test    r9w, r9w
0x18005eb47  jz      short loc_18005EB61
0x18005eb49  mov     [rax], r9w
0x18005eb4d  add     rcx, 2
0x18005eb51  add     rax, 2
0x18005eb55  dec     r14
0x18005eb58  inc     r8
0x18005eb5b  sub     rdx, 1
0x18005eb5f  jnz     short loc_18005EB3A
0x18005eb61  xor     r14d, r14d
0x18005eb64  lea     rcx, [rax-2]
0x18005eb68  test    rdx, rdx
0x18005eb6b  lea     r9, [r8-1]
0x18005eb6f  cmovnz  rcx, rax
0x18005eb73  cmovnz  r9, r8
0x18005eb77  mov     [rcx], r14w
0x18005eb7b  jnz     loc_18005F048
0x18005eb81  mov     rdx, rbx
0x18005eb84  mov     rcx, 0FFFFFFFFFFFFFFFCh
0x18005eb8b  call    cs:__imp_OpenStateExplicit
0x18005eb91  mov     [rbp+170h+var_1F0], rax
0x18005eb95  mov     rdi, rax
0x18005eb98  test    rax, rax
0x18005eb9b  jz      loc_18005EFB1
0x18005eba1  lea     r9, [rbp+170h+var_1E8]
0x18005eba5  mov     [rbp+170h+var_1E8], r14d
0x18005eba9  xor     r8d, r8d
0x18005ebac  xor     edx, edx
0x18005ebae  mov     rcx, rax
0x18005ebb1  call    cs:__imp_GetSystemAppDataKey
0x18005ebb7  test    eax, eax
0x18005ebb9  jnz     loc_18005F08F
0x18005ebbf  call    cs:__imp_GetLastError
0x18005ebc5  cmp     eax, 7Ah ; 'z'
0x18005ebc8  jnz     loc_18005F09E
0x18005ebce  mov     esi, [rbp+170h+var_1E8]
0x18005ebd1  lea     rcx, ds:2[rsi*2]; cb
0x18005ebd9  call    cs:__imp_CoTaskMemAlloc
0x18005ebdf  mov     r14, rax
0x18005ebe2  xor     eax, eax
0x18005ebe4  test    r14, r14
0x18005ebe7  jz      loc_18005EE0C
0x18005ebed  mov     [r14], ax
0x18005ebf1  lea     r9, [rbp+170h+var_1E8]
0x18005ebf5  mov     [r14+rsi*2], ax
0x18005ebfa  lea     rdx, [rsp+270h+hKey]
0x18005ebff  mov     r8, r14
0x18005ec02  mov     [rsp+270h+hKey], rax
0x18005ec07  mov     rcx, rdi
0x18005ec0a  call    cs:__imp_GetSystemAppDataKey
0x18005ec10  test    eax, eax
0x18005ec12  jz      loc_18005F110
0x18005ec18  mov     rcx, [rsp+270h+hKey]; hKey
0x18005ec1d  lea     rax, [rsp+270h+var_200]
0x18005ec22  mov     r9d, 0F003Fh; samDesired
0x18005ec28  mov     [rsp+270h+phkResult], rax; int
0x18005ec2d  xor     r8d, r8d; ulOptions
0x18005ec30  mov     [rsp+270h+var_200], 0
0x18005ec39  mov     rdx, r14; lpSubKey
0x18005ec3c  call    cs:__imp_RegOpenKeyExW
0x18005ec42  mov     esi, eax
0x18005ec44  test    eax, eax
0x18005ec46  jle     short loc_18005EC53
0x18005ec48  movzx   esi, si
0x18005ec4b  or      esi, 80070000h
0x18005ec51  test    esi, esi
0x18005ec53  js      loc_18005EFD0
0x18005ec59  mov     rcx, [rsp+270h+var_200]; hKey
0x18005ec5e  lea     rax, [rsp+270h+var_208]
0x18005ec63  xor     esi, esi
0x18005ec65  mov     [rsp+270h+phkResult], rax; phkResult
0x18005ec6a  mov     r9d, 0F003Fh; samDesired
0x18005ec70  mov     [rsp+270h+var_208], rsi
0x18005ec75  xor     r8d, r8d; ulOptions
0x18005ec78  lea     rdx, aApplicationfra; "ApplicationFrame"
0x18005ec7f  call    cs:__imp_RegOpenKeyExW
0x18005ec85  test    eax, eax
0x18005ec87  jle     short loc_18005EC93
0x18005ec89  movzx   eax, ax
0x18005ec8c  or      eax, 80070000h
0x18005ec91  test    eax, eax
0x18005ec93  js      loc_18005ED4E
0x18005ec99  mov     rcx, [rsp+270h+var_208]; hKey
0x18005ec9e  lea     rax, [rsp+270h+var_210]
0x18005eca3  mov     r9d, 0F003Fh; samDesired
0x18005eca9  mov     [rsp+270h+phkResult], rax; phkResult
0x18005ecae  xor     r8d, r8d; ulOptions
0x18005ecb1  mov     [rsp+270h+var_210], rsi
0x18005ecb6  mov     rdx, r13; lpSubKey
0x18005ecb9  call    cs:__imp_RegOpenKeyExW
0x18005ecbf  test    eax, eax
0x18005ecc1  jle     short loc_18005ECCD
0x18005ecc3  movzx   eax, ax
0x18005ecc6  or      eax, 80070000h
0x18005eccb  test    eax, eax
0x18005eccd  js      loc_18005EF27
0x18005ecd3  xor     r13d, r13d
0x18005ecd6  test    r12, r12
0x18005ecd9  jnz     loc_18005F1CF
0x18005ecdf  mov     sil, [rsp+270h+var_220]
0x18005ece4  test    sil, sil
0x18005ece7  jnz     loc_18005EE42
0x18005eced  mov     rax, [rsp+270h+var_210]
0x18005ecf2  mov     [r15], rax
0x18005ecf5  mov     [rsp+270h+var_210], r13
0x18005ecfa  mov     rcx, [rsp+270h+var_208]; hKey
0x18005ecff  test    rcx, rcx
0x18005ed02  jz      short loc_18005ED0A
0x18005ed04  call    cs:__imp_RegCloseKey
0x18005ed0a  mov     rcx, [rsp+270h+var_200]; hKey
0x18005ed0f  test    rcx, rcx
0x18005ed12  jz      short loc_18005ED1A
0x18005ed14  call    cs:__imp_RegCloseKey
0x18005ed1a  mov     rcx, [rsp+270h+hKey]; hKey
0x18005ed1f  test    rcx, rcx
0x18005ed22  jnz     short loc_18005ED46
0x18005ed24  mov     rcx, r14; pv
0x18005ed27  call    cs:__imp_CoTaskMemFree
0x18005ed2d  mov     rcx, rdi
0x18005ed30  call    cs:__imp_CloseState
0x18005ed36  test    rbx, rbx
0x18005ed39  jnz     loc_18005EEE4
0x18005ed3f  xor     eax, eax
0x18005ed41  jmp     loc_18005E9FE
0x18005ed46  call    cs:__imp_RegCloseKey
0x18005ed4c  jmp     short loc_18005ED24
0x18005ed4e  mov     rsi, [rsp+270h+var_208]
0x18005ed53  test    rsi, rsi
0x18005ed56  jnz     loc_18005F189
0x18005ed5c  mov     rcx, [rsp+270h+var_200]; hKey
0x18005ed61  lea     rax, [rsp+270h+var_208]
0x18005ed66  xor     esi, esi
0x18005ed68  lea     rdx, aApplicationfra; "ApplicationFrame"
0x18005ed6f  mov     [rsp+270h+lpdwDisposition], rsi; lpdwDisposition
0x18005ed74  xor     r9d, r9d; lpClass
0x18005ed77  mov     [rsp+270h+var_238], rax; phkResult
0x18005ed7c  xor     r8d, r8d; Reserved
0x18005ed7f  mov     [rsp+270h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x18005ed84  mov     [rsp+270h+samDesired], 0F003Fh; samDesired
0x18005ed8c  mov     dword ptr [rsp+270h+phkResult], esi; unsigned int
0x18005ed90  mov     [rsp+270h+var_208], rsi
0x18005ed95  call    cs:__imp_RegCreateKeyExW
0x18005ed9b  test    eax, eax
0x18005ed9d  jz      loc_18005EC99
0x18005eda3  mov     rcx, [rbp+178h]; this
0x18005edaa  lea     r8, aShellTwinuiDat; "shell\\twinui\\datapersistence\\lib\\da"...
0x18005edb1  mov     r9d, eax; char *
0x18005edb4  mov     edx, 100h; void *
0x18005edb9  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18005edbe  mov     esi, eax
0x18005edc0  mov     rcx, [rsp+270h+var_208]; hKey
  ... truncated ...
```
