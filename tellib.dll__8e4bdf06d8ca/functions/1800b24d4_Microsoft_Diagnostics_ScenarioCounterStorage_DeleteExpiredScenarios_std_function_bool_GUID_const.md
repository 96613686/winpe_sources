# Microsoft::Diagnostics::ScenarioCounterStorage::DeleteExpiredScenarios(std::function<bool (_GUID const &)>)

- ea: `0x1800b24d4`
- end: `0x1800b2a34`
- name: `?DeleteExpiredScenarios@ScenarioCounterStorage@Diagnostics@Microsoft@@QEAAXV?$function@$$A6A_NAEBU_GUID@@@Z@std@@@Z`
- size: `1376`
- prototype: ``
- caller_count: `1`
- callee_count: `26`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18021239c`

## callees

- `0x18001cf30`
- `0x18001d160`
- `0x180020fbc`
- `0x180024ee0`
- `0x180026ecc`
- `0x180026ef4`
- `0x180027be0`
- `0x180032718`
- `0x180035698`
- `0x18003fd8c`
- `0x18004ab70`
- `0x1800558c0`
- `0x180089d50`
- `0x1800aac70`
- `0x1800b24d4`
- `0x1800b2a3c`
- `0x1800b2ccc`
- `0x1800b2cf4`
- `0x1800bc2e0`
- `0x1800d0d9c`
- `0x1800dff54`
- `0x1800f5954`
- `0x18011cb34`
- `0x18012de40`
- `0x18021d18c`
- `0x180346010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1800b2954`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1800b2954`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800b2568`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800b2568`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800b2653`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800b2653`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800b2984`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800b2984`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800b25d6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800b25d6`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800b2693`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800b2693`

## string_xrefs

- `0x1800b258e`: `onecore\base\telemetry\utc\service\scenarios\base\scenariocounterstorage.cpp`
- `0x1800b25e9`: `onecore\base\telemetry\utc\service\scenarios\base\scenariocounterstorage.cpp`
- `0x1800b28b6`: `onecore\base\telemetry\utc\service\scenarios\tracing\snapshotmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall Microsoft::Diagnostics::ScenarioCounterStorage::DeleteExpiredScenarios(HKEY *a1, __int64 a2)
{
  int v4; // eax
  HRESULT v5; // eax
  DWORD i; // r14d
  WCHAR *v7; // r8
  int v8; // eax
  wil::details::in1diag3 *v9; // rcx
  const OLECHAR *v10; // rcx
  __int64 v11; // rcx
  int Qword; // eax
  LPWSTR *v13; // rdx
  int v14; // eax
  int String; // eax
  __int64 v16; // rcx
  int v17; // eax
  LPCWSTR v18; // rbx
  LPCWSTR v19; // r14
  const WCHAR *v20; // rdx
  int v21; // eax
  __int64 result; // rax
  __int64 v23; // rdx
  __int64 v24; // rcx
  int lpcSubKeys; // [rsp+20h] [rbp-E0h]
  int lpcSubKeysa; // [rsp+20h] [rbp-E0h]
  DWORD cbMaxSubKeyLen; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cSubKeys; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD cchName; // [rsp+68h] [rbp-98h] BYREF
  LPVOID ppv; // [rsp+70h] [rbp-90h] BYREF
  __int64 v31; // [rsp+78h] [rbp-88h] BYREF
  __int128 v32; // [rsp+80h] [rbp-80h] BYREF
  LPCWSTR lpSubKey[4]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v34[4]; // [rsp+B0h] [rbp-50h] BYREF
  __m128i v35; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v36[16]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v37[16]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v38[16]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v39[16]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v40[16]; // [rsp+120h] [rbp+20h] BYREF
  LPWSTR lpName[2]; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int64 v42; // [rsp+148h] [rbp+48h]
  GUID pclsid; // [rsp+150h] [rbp+50h] BYREF
  _OWORD v44[2]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE Src[32]; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v46[32]; // [rsp+1A0h] [rbp+A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+F8h]

  v34[2] = a2;
  std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(v36, a1 + 1);
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  v4 = RegQueryInfoKeyW(*a1, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
  if ( v4 > 0 )
    v4 = (unsigned __int16)v4 | 0x80070000;
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1D0,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\scenariocounterstorage.cpp",
      (const char *)(unsigned int)v4,
      lpcSubKeys);
  std::wstring::wstring(lpName, cbMaxSubKeyLen + 1, 0);
  ppv = 0;
  v5 = CoCreateInstance(&CLSID_FlightClientAPI, 0, 1u, &GUID_79588f37_5be1_4a35_b23d_29832257cada, &ppv);
  if ( v5 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1DB,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\scenariocounterstorage.cpp",
      (const char *)(unsigned int)v5,
      lpcSubKeysa);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioStateMapEntry>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioStateMapEntry>>>>>>(lpSubKey);
  for ( i = 0; i < cSubKeys; ++i )
  {
    cchName = cbMaxSubKeyLen + 1;
    v7 = (WCHAR *)lpName;
    if ( v42 > 7 )
      v7 = lpName[0];
    v8 = RegEnumKeyExW(*a1, i, v7, &cchName, 0, 0, 0, 0);
    if ( v8 > 0 )
      v8 = (unsigned __int16)v8 | 0x80070000;
    v9 = retaddr;
    if ( v8 < 0 )
      goto LABEL_38;
    pclsid = 0;
    v10 = (const OLECHAR *)lpName;
    if ( v42 > 7 )
      v10 = lpName[0];
    if ( CLSIDFromString(v10, &pclsid) < 0 )
      goto LABEL_18;
    v11 = *(_QWORD *)(a2 + 56);
    if ( !v11 )
    {
      std::_Xbad_function_call();
      __debugbreak();
LABEL_38:
      wil::details::in1diag3::Throw_Hr(
        v9,
        (void *)0x1EB,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\scenariocounterstorage.cpp",
        (const char *)(unsigned int)v8,
        lpcSubKeysa);
    }
    if ( !(*(unsigned __int8 (__fastcall **)(__int64, GUID *))(*(_QWORD *)v11 + 16LL))(v11, &pclsid) )
    {
LABEL_18:
      std::wstring::wstring(v44);
      std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(lpSubKey, v44);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v44);
      v32 = *(_OWORD *)std::_Tree<std::_Tmap_traits<_GUID,std::shared_ptr<Microsoft::Diagnostics::EscalationWorkItem>,LessGuid,std::allocator<std::pair<_GUID const,std::shared_ptr<Microsoft::Diagnostics::EscalationWorkItem>>>,0>>::_Eqrange<_GUID>(
                         a1 + 11,
                         v37,
                         &pclsid);
      std::_Tree<std::_Tmap_traits<_GUID,Microsoft::Diagnostics::ScenarioCounters,LessGuid,std::allocator<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioCounters>>,0>>::_Erase(
        a1 + 11,
        &v32);
      v31 = 0;
      std::wstring::wstring((__int64)Src, &off_18034A860);
      std::wstring::_Append<wchar_t>(Src);
      std::wstring::_Append<wchar_t>(Src);
      v32 = *(_OWORD *)&off_18034AC30;
      v44[0] = *(_OWORD *)std::wstring::operator std::wstring_view(Src, v38);
      Qword = Microsoft::Diagnostics::Utils::Registry::GetQword(-2147483646, v44, &v32, &v31);
      if ( Qword < 0 )
      {
        if ( Qword != -2147024894 )
          wil::details::in1diag3::Log_Hr(
            retaddr,
            (void *)0x21A,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\scenariocounterstorage.cpp",
            (const char *)(unsigned int)Qword,
            lpcSubKeysa);
      }
      else if ( ppv )
      {
        v13 = lpName;
        if ( v42 > 7 )
          LODWORD(v13) = lpName[0];
        lpcSubKeysa = (int)v13;
        v14 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)ppv + 24LL))(ppv, 4, v31);
        if ( v14 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x215,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\scenariocounterstorage.cpp",
            (const char *)(unsigned int)v14,
            lpcSubKeysa);
      }
      std::wstring::wstring(v46);
      v44[0] = *(_OWORD *)&off_180348B58;
      v32 = *(_OWORD *)std::wstring::operator std::wstring_view(Src, v39);
      String = Microsoft::Diagnostics::Utils::Registry::GetString(-2147483646, &v32, v44, v46);
      if ( String < 0 )
      {
        if ( String != -2147024894 )
          wil::details::in1diag3::Log_Hr(
            retaddr,
            (void *)0x22E,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\scenariocounterstorage.cpp",
            (const char *)(unsigned int)String,
            lpcSubKeysa);
      }
      else
      {
        Microsoft::Diagnostics::LifetimeManager::GetEscalationEngine((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
        v35 = *(__m128i *)std::wstring::operator std::wstring_view(v46, v40);
        if ( _mm_srli_si128(v35, 8).m128i_u64[0] )
        {
          v34[0] = 1;
          v34[1] = &v35;
          v17 = Microsoft::Diagnostics::SnapshotManager::ConfigureHeapSnapshotByProcessName(v16, v34, 0);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x15A,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\tracing\\snapshotmanager.cpp",
            (const char *)0x80070057LL,
            lpcSubKeysa);
          v17 = -2147024809;
        }
        if ( v17 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x22A,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\scenariocounterstorage.cpp",
            (const char *)(unsigned int)v17,
            lpcSubKeysa);
      }
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v46);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
    }
  }
  v18 = lpSubKey[0];
  v19 = lpSubKey[1];
  while ( v18 != v19 )
  {
    if ( *((_QWORD *)v18 + 3) <= 7u )
      v20 = v18;
    else
      v20 = *(const WCHAR **)v18;
    v21 = RegDeleteTreeW(*a1, v20);
    if ( v21 > 0 )
      v21 = (unsigned __int16)v21 | 0x80070000;
    if ( v21 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x236,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\scenariocounterstorage.cpp",
        (const char *)(unsigned int)v21,
        lpcSubKeysa);
    v18 += 16;
  }
  std::vector<std::wstring>::_Tidy(lpSubKey);
  wil::com_ptr_t<IFlightData,wil::err_exception_policy>::~com_ptr_t<IFlightData,wil::err_exception_policy>(&ppv);
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpName);
  result = std::unique_lock<std::mutex>::~unique_lock<std::mutex>(v36);
  v24 = *(_QWORD *)(a2 + 56);
  if ( v24 )
  {
    LOBYTE(v23) = v24 != a2;
    result = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v24 + 32LL))(v24, v23);
    *(_QWORD *)(a2 + 56) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800b24d4  mov     [rsp-8+arg_10], rbx
0x1800b24d9  mov     [rsp-8+arg_18], rsi
0x1800b24de  push    rbp
0x1800b24df  push    rdi
0x1800b24e0  push    r12
0x1800b24e2  push    r14
0x1800b24e4  push    r15
0x1800b24e6  lea     rbp, [rsp-0D0h]
0x1800b24ee  sub     rsp, 1D0h
0x1800b24f5  mov     rax, cs:__security_cookie
0x1800b24fc  xor     rax, rsp
0x1800b24ff  mov     [rbp+0F0h+var_30], rax
0x1800b2506  mov     rsi, rdx
0x1800b2509  mov     r15, rcx
0x1800b250c  mov     [rbp+0F0h+var_130], rdx
0x1800b2510  lea     rdx, [rcx+8]
0x1800b2514  lea     rcx, [rbp+0F0h+var_110]
0x1800b2518  call    ??0?$unique_lock@Vrecursive_mutex@std@@@std@@QEAA@AEAVrecursive_mutex@1@@Z; std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(std::recursive_mutex &)
0x1800b251d  nop
0x1800b251e  xor     r12d, r12d
0x1800b2521  mov     [rsp+1F0h+cSubKeys], r12d
0x1800b2526  mov     [rsp+1F0h+cbMaxSubKeyLen], r12d
0x1800b252b  mov     [rsp+1F0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x1800b2530  mov     [rsp+1F0h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x1800b2535  mov     [rsp+1F0h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x1800b253a  mov     [rsp+1F0h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x1800b253f  mov     [rsp+1F0h+lpcValues], r12; lpcValues
0x1800b2544  mov     [rsp+1F0h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x1800b2549  lea     rax, [rsp+1F0h+cbMaxSubKeyLen]
0x1800b254e  mov     [rsp+1F0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x1800b2553  lea     rax, [rsp+1F0h+cSubKeys]
0x1800b2558  mov     [rsp+1F0h+lpcSubKeys], rax; int
0x1800b255d  xor     r9d, r9d; lpReserved
0x1800b2560  xor     r8d, r8d; lpcchClass
0x1800b2563  xor     edx, edx; lpClass
0x1800b2565  mov     rcx, [r15]; hKey
0x1800b2568  call    cs:__imp_RegQueryInfoKeyW
0x1800b256f  nop     dword ptr [rax+rax+00h]
0x1800b2574  test    eax, eax
0x1800b2576  jle     short loc_1800B2580
0x1800b2578  movzx   eax, ax
0x1800b257b  or      eax, 80070000h
0x1800b2580  mov     rcx, [rbp+0F8h]; this
0x1800b2587  test    eax, eax
0x1800b2589  jns     short loc_1800B25A0
0x1800b258b  mov     r9d, eax; char *
0x1800b258e  lea     r8, aOnecoreBaseTel_150; "onecore\\base\\telemetry\\utc\\service"...
0x1800b2595  mov     edx, 1D0h; void *
0x1800b259a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b25a0  xor     r8d, r8d
0x1800b25a3  mov     edx, [rsp+1F0h+cbMaxSubKeyLen]
0x1800b25a7  inc     edx
0x1800b25a9  lea     rcx, [rbp+0F0h+lpName]
0x1800b25ad  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@_K_W@Z; std::wstring::wstring(unsigned __int64,wchar_t)
0x1800b25b2  nop
0x1800b25b3  mov     [rsp+1F0h+ppv], r12
0x1800b25b8  lea     rax, [rsp+1F0h+ppv]
0x1800b25bd  mov     [rsp+1F0h+lpcSubKeys], rax; int
0x1800b25c2  lea     r9, _GUID_79588f37_5be1_4a35_b23d_29832257cada; riid
0x1800b25c9  xor     edx, edx; pUnkOuter
0x1800b25cb  lea     r8d, [rdx+1]; dwClsContext
0x1800b25cf  lea     rcx, CLSID_FlightClientAPI; rclsid
0x1800b25d6  call    cs:__imp_CoCreateInstance
0x1800b25dd  nop     dword ptr [rax+rax+00h]
0x1800b25e2  mov     rcx, [rbp+0F8h]; this
0x1800b25e9  lea     rdi, aOnecoreBaseTel_150; "onecore\\base\\telemetry\\utc\\service"...
0x1800b25f0  test    eax, eax
0x1800b25f2  jns     short loc_1800B2604
0x1800b25f4  mov     r9d, eax; char *
0x1800b25f7  mov     r8, rdi; unsigned int
0x1800b25fa  mov     edx, 1DBh; void *
0x1800b25ff  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800b2604  lea     rcx, [rbp+0F0h+lpSubKey]; void *
0x1800b2608  call    ??$?0AEBV?$allocator@U?$pair@$$CBU_GUID@@UScenarioStateMapEntry@Diagnostics@Microsoft@@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@UScenarioStateMapEntry@Diagnostics@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBU_GUID@@UScenarioStateMapEntry@Diagnostics@Microsoft@@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioStateMapEntry>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioStateMapEntry>>>>>>(std::allocator<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioStateMapEntry>> const &)
0x1800b260d  nop
0x1800b260e  mov     r14d, r12d
0x1800b2611  cmp     [rsp+1F0h+cSubKeys], r12d
0x1800b2616  jbe     loc_1800B294A
0x1800b261c  mov     eax, [rsp+1F0h+cbMaxSubKeyLen]
0x1800b2620  inc     eax
0x1800b2622  mov     [rsp+1F0h+cchName], eax
0x1800b2626  lea     r8, [rbp+0F0h+lpName]
0x1800b262a  cmp     [rbp+0F0h+var_A8], 7
0x1800b262f  cmova   r8, [rbp+0F0h+lpName]; lpName
0x1800b2634  mov     [rsp+1F0h+lpcValues], r12; lpftLastWriteTime
0x1800b2639  mov     [rsp+1F0h+lpcbMaxClassLen], r12; lpcchClass
0x1800b263e  mov     [rsp+1F0h+lpcbMaxSubKeyLen], r12; lpClass
0x1800b2643  mov     [rsp+1F0h+lpcSubKeys], r12; int
0x1800b2648  lea     r9, [rsp+1F0h+cchName]; lpcchName
0x1800b264d  mov     edx, r14d; dwIndex
0x1800b2650  mov     rcx, [r15]; hKey
0x1800b2653  call    cs:__imp_RegEnumKeyExW
0x1800b265a  nop     dword ptr [rax+rax+00h]
0x1800b265f  test    eax, eax
0x1800b2661  jle     short loc_1800B266B
0x1800b2663  movzx   eax, ax
0x1800b2666  or      eax, 80070000h
0x1800b266b  mov     rcx, [rbp+0F8h]
0x1800b2672  test    eax, eax
0x1800b2674  js      loc_1800B2961
0x1800b267a  xorps   xmm0, xmm0
0x1800b267d  movups  xmmword ptr [rbp+0F0h+pclsid.Data1], xmm0
0x1800b2681  lea     rcx, [rbp+0F0h+lpName]
0x1800b2685  cmp     [rbp+0F0h+var_A8], 7
0x1800b268a  cmova   rcx, [rbp+0F0h+lpName]; lpsz
0x1800b268f  lea     rdx, [rbp+0F0h+pclsid]; pclsid
0x1800b2693  call    cs:__imp_CLSIDFromString
0x1800b269a  nop     dword ptr [rax+rax+00h]
0x1800b269f  test    eax, eax
0x1800b26a1  js      short loc_1800B26C8
0x1800b26a3  mov     rcx, [rsi+38h]
0x1800b26a7  test    rcx, rcx
0x1800b26aa  jz      loc_1800B2954
0x1800b26b0  mov     rax, [rcx]
0x1800b26b3  lea     rdx, [rbp+0F0h+pclsid]
0x1800b26b7  mov     rax, [rax+10h]
0x1800b26bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b26c0  test    al, al
0x1800b26c2  jnz     loc_1800B293C
0x1800b26c8  lea     rdx, [rbp+0F0h+lpName]
0x1800b26cc  cmp     [rbp+0F0h+var_A8], 7
0x1800b26d1  cmova   rdx, [rbp+0F0h+lpName]
0x1800b26d6  lea     rcx, [rbp+0F0h+var_90]
0x1800b26da  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800b26df  nop
0x1800b26e0  lea     rdx, [rbp+0F0h+var_90]
0x1800b26e4  lea     rcx, [rbp+0F0h+lpSubKey]
0x1800b26e8  call    ??$_Emplace_one_at_back@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(std::wstring &&)
0x1800b26ed  nop
0x1800b26ee  lea     rcx, [rbp+0F0h+var_90]; this
0x1800b26f2  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1800b26f7  lea     r8, [rbp+0F0h+pclsid]
0x1800b26fb  lea     rdx, [rbp+0F0h+var_100]
0x1800b26ff  lea     rcx, [r15+58h]
0x1800b2703  call    ??$_Eqrange@U_GUID@@@?$_Tree@V?$_Tmap_traits@U_GUID@@V?$shared_ptr@VEscalationWorkItem@Diagnostics@Microsoft@@@std@@ULessGuid@@V?$allocator@U?$pair@$$CBU_GUID@@V?$shared_ptr@VEscalationWorkItem@Diagnostics@Microsoft@@@std@@@std@@@3@$0A@@std@@@std@@IEBA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$shared_ptr@VEscalationWorkItem@Diagnostics@Microsoft@@@std@@@std@@PEAX@std@@PEAU12@@1@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,std::shared_ptr<Microsoft::Diagnostics::EscalationWorkItem>,LessGuid,std::allocator<std::pair<_GUID const,std::shared_ptr<Microsoft::Diagnostics::EscalationWorkItem>>>,0>>::_Eqrange<_GUID>(_GUID const &)
0x1800b2708  movups  xmm0, xmmword ptr [rax]
0x1800b270b  movdqu  [rbp+0F0h+var_170], xmm0
0x1800b2710  lea     rdx, [rbp+0F0h+var_170]
0x1800b2714  lea     rcx, [r15+58h]
0x1800b2718  call    ?_Erase@?$_Tree@V?$_Tmap_traits@U_GUID@@UScenarioCounters@Diagnostics@Microsoft@@ULessGuid@@V?$allocator@U?$pair@$$CBU_GUID@@UScenarioCounters@Diagnostics@Microsoft@@@std@@@std@@$0A@@std@@@std@@AEAA_KU?$pair@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@UScenarioCounters@Diagnostics@Microsoft@@@std@@PEAX@std@@PEAU12@@2@@Z; std::_Tree<std::_Tmap_traits<_GUID,Microsoft::Diagnostics::ScenarioCounters,LessGuid,std::allocator<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioCounters>>,0>>::_Erase(std::pair<std::_Tree_node<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioCounters>,void *> *,std::_Tree_node<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioCounters>,void *> *>)
0x1800b271d  mov     [rsp+1F0h+var_178], r12
0x1800b2722  lea     rdx, off_18034A860; "%DiagtrackRegistryRoot%\\Scenarios"
0x1800b2729  lea     rcx, [rbp+0F0h+Src]
0x1800b2730  call    ??$?0V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_zstring_view@_W@wil@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wil::basic_zstring_view<wchar_t> const &,std::allocator<wchar_t> const &)
0x1800b2735  nop
0x1800b2736  mov     r8d, 1
0x1800b273c  lea     rdx, asc_1803772C8; "\\"
0x1800b2743  lea     rcx, [rbp+0F0h+Src]; Src
0x1800b274a  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x1800b274f  lea     rdx, [rbp+0F0h+lpName]
0x1800b2753  cmp     [rbp+0F0h+var_A8], 7
0x1800b2758  cmova   rdx, [rbp+0F0h+lpName]
0x1800b275d  mov     r8, [rbp+0F0h+var_B0]
0x1800b2761  lea     rcx, [rbp+0F0h+Src]; Src
0x1800b2768  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x1800b276d  movups  xmm0, xmmword ptr cs:off_18034AC30; "FlightId"
0x1800b2774  movdqu  [rbp+0F0h+var_170], xmm0
0x1800b2779  lea     rdx, [rbp+0F0h+var_F0]
0x1800b277d  lea     rcx, [rbp+0F0h+Src]
0x1800b2784  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1800b2789  movups  xmm0, xmmword ptr [rax]
0x1800b278c  movdqu  [rbp+0F0h+var_90], xmm0
0x1800b2791  lea     r9, [rsp+1F0h+var_178]
0x1800b2796  lea     r8, [rbp+0F0h+var_170]
0x1800b279a  lea     rdx, [rbp+0F0h+var_90]
0x1800b279e  mov     rcx, 0FFFFFFFF80000002h
0x1800b27a5  call    ?GetQword@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@1AEA_K@Z; Microsoft::Diagnostics::Utils::Registry::GetQword(HKEY__ *,std::wstring_view,std::wstring_view,unsigned __int64 &)
0x1800b27aa  test    eax, eax
0x1800b27ac  js      short loc_1800B2803
0x1800b27ae  mov     rcx, [rsp+1F0h+ppv]
0x1800b27b3  test    rcx, rcx
0x1800b27b6  jz      short loc_1800B2821
0x1800b27b8  mov     rax, [rcx]
0x1800b27bb  lea     rdx, [rbp+0F0h+lpName]
0x1800b27bf  cmp     [rbp+0F0h+var_A8], 7
0x1800b27c4  cmova   rdx, [rbp+0F0h+lpName]
0x1800b27c9  mov     [rsp+1F0h+lpcSubKeys], rdx; int
0x1800b27ce  mov     r9d, 3
0x1800b27d4  mov     r8, [rsp+1F0h+var_178]
0x1800b27d9  lea     edx, [r9+1]
0x1800b27dd  mov     rax, [rax+18h]
0x1800b27e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b27e6  mov     rcx, [rbp+0F8h]; this
0x1800b27ed  test    eax, eax
0x1800b27ef  jns     short loc_1800B2821
0x1800b27f1  mov     r9d, eax; char *
0x1800b27f4  mov     r8, rdi; unsigned int
0x1800b27f7  mov     edx, 215h; void *
0x1800b27fc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800b2801  jmp     short loc_1800B2821
0x1800b2803  cmp     eax, 80070002h
0x1800b2808  jz      short loc_1800B2821
0x1800b280a  mov     rcx, [rbp+0F8h]; this
0x1800b2811  mov     r9d, eax; char *
0x1800b2814  mov     r8, rdi; unsigned int
0x1800b2817  mov     edx, 21Ah; void *
0x1800b281c  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1800b2821  lea     rcx, [rbp+0F0h+var_50]; void *
0x1800b2828  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800b282d  nop
0x1800b282e  movups  xmm0, xmmword ptr cs:off_180348B58; "HeapSnapshotProcessName"
0x1800b2835  movdqu  [rbp+0F0h+var_90], xmm0
0x1800b283a  lea     rdx, [rbp+0F0h+var_E0]
0x1800b283e  lea     rcx, [rbp+0F0h+Src]
0x1800b2845  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1800b284a  movups  xmm0, xmmword ptr [rax]
0x1800b284d  movdqu  [rbp+0F0h+var_170], xmm0
0x1800b2852  lea     r9, [rbp+0F0h+var_50]
0x1800b2859  lea     r8, [rbp+0F0h+var_90]
0x1800b285d  lea     rdx, [rbp+0F0h+var_170]
0x1800b2861  mov     rcx, 0FFFFFFFF80000002h
0x1800b2868  call    ?GetString@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@1AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@7@@Z; Microsoft::Diagnostics::Utils::Registry::GetString(HKEY__ *,std::wstring_view,std::wstring_view,std::wstring &)
0x1800b286d  test    eax, eax
0x1800b286f  js      loc_1800B2904
0x1800b2875  lea     rcx, ?gs_lifetimeManager@@3VLifetimeManager@Diagnostics@Microsoft@@A; this
0x1800b287c  call    ?GetEscalationEngine@LifetimeManager@Diagnostics@Microsoft@@QEAAAEAVEscalationEngine@23@XZ; Microsoft::Diagnostics::LifetimeManager::GetEscalationEngine(void)
0x1800b2881  lea     rdx, [rbp+0F0h+var_D0]
0x1800b2885  lea     rcx, [rbp+0F0h+var_50]
0x1800b288c  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1800b2891  movups  xmm0, xmmword ptr [rax]
0x1800b2894  movaps  [rbp+0F0h+var_120], xmm0
0x1800b2898  psrldq  xmm0, 8
0x1800b289d  movq    rax, xmm0
0x1800b28a2  test    rax, rax
0x1800b28a5  jnz     short loc_1800B28CB
0x1800b28a7  mov     rcx, [rbp+0F8h]; this
0x1800b28ae  mov     ebx, 80070057h
0x1800b28b3  mov     r9d, ebx; char *
0x1800b28b6  lea     r8, aOnecoreBaseTel_206; "onecore\\base\\telemetry\\utc\\service"...
0x1800b28bd  mov     edx, 15Ah; void *
0x1800b28c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b28c7  mov     eax, ebx
0x1800b28c9  jmp     short loc_1800B28E7
0x1800b28cb  mov     [rbp+0F0h+var_140], 1
0x1800b28d3  lea     rax, [rbp+0F0h+var_120]
0x1800b28d7  mov     [rbp+0F0h+var_138], rax
0x1800b28db  xor     r8d, r8d
0x1800b28de  lea     rdx, [rbp+0F0h+var_140]
0x1800b28e2  call    ?ConfigureHeapSnapshotByProcessName@SnapshotManager@Diagnostics@Microsoft@@AEBAJV?$span@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@$0?0@gsl@@_N@Z; Microsoft::Diagnostics::SnapshotManager::ConfigureHeapSnapshotByProcessName(gsl::span<std::wstring_view,-1>,bool)
0x1800b28e7  mov     rcx, [rbp+0F8h]; this
0x1800b28ee  test    eax, eax
0x1800b28f0  jns     short loc_1800B2923
0x1800b28f2  mov     r9d, eax; char *
0x1800b28f5  mov     r8, rdi; unsigned int
0x1800b28f8  mov     edx, 22Ah; void *
0x1800b28fd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800b2902  jmp     short loc_1800B2923
0x1800b2904  cmp     eax, 80070002h
0x1800b2909  jz      short loc_1800B2923
0x1800b290b  mov     rcx, [rbp+0F8h]; this
0x1800b2912  mov     r9d, eax; char *
0x1800b2915  mov     r8, rdi; unsigned int
0x1800b2918  mov     edx, 22Eh; void *
0x1800b291d  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1800b2922  nop
0x1800b2923  lea     rcx, [rbp+0F0h+var_50]; this
0x1800b292a  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1800b292f  nop
0x1800b2930  lea     rcx, [rbp+0F0h+Src]; this
0x1800b2937  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1800b293c  inc     r14d
0x1800b293f  cmp     r14d, [rsp+1F0h+cSubKeys]
0x1800b2944  jb      loc_1800B261C
0x1800b294a  mov     rbx, [rbp+0F0h+lpSubKey]
0x1800b294e  mov     r14, [rbp+0F0h+var_158]
0x1800b2952  jmp     short loc_1800B29BB
0x1800b2954  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x1800b295b  nop     dword ptr [rax+rax+00h]
0x1800b2960  int     3; Trap to Debugger
0x1800b2961  mov     r9d, eax; char *
0x1800b2964  mov     r8, rdi; unsigned int
0x1800b2967  mov     edx, 1EBh; void *
0x1800b296c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b2972  cmp     qword ptr [rbx+18h], 7
0x1800b2977  jbe     short loc_1800B297E
0x1800b2979  mov     rdx, [rbx]
0x1800b297c  jmp     short loc_1800B2981
0x1800b297e  mov     rdx, rbx; lpSubKey
0x1800b2981  mov     rcx, [r15]; hKey
0x1800b2984  call    cs:__imp_RegDeleteTreeW
0x1800b298b  nop     dword ptr [rax+rax+00h]
0x1800b2990  test    eax, eax
0x1800b2992  jle     short loc_1800B299C
0x1800b2994  movzx   eax, ax
0x1800b2997  or      eax, 80070000h
0x1800b299c  mov     rcx, [rbp+0F8h]; this
0x1800b29a3  test    eax, eax
0x1800b29a5  jns     short loc_1800B29B7
0x1800b29a7  mov     r9d, eax; char *
0x1800b29aa  mov     r8, rdi; unsigned int
0x1800b29ad  mov     edx, 236h; void *
0x1800b29b2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800b29b7  add     rbx, 20h ; ' '
0x1800b29bb  cmp     rbx, r14
0x1800b29be  jnz     short loc_1800B2972
0x1800b29c0  lea     rcx, [rbp+0F0h+lpSubKey]
0x1800b29c4  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800b29c9  nop
0x1800b29ca  lea     rcx, [rsp+1F0h+ppv]
0x1800b29cf  call    ??1?$com_ptr_t@UIFlightData@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFlightData,wil::err_exception_policy>::~com_ptr_t<IFlightData,wil::err_exception_policy>(void)
  ... truncated ...
```
