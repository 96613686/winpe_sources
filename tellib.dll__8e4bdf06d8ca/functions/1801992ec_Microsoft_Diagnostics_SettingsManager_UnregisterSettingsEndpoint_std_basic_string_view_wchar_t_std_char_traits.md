# Microsoft::Diagnostics::SettingsManager::UnregisterSettingsEndpoint(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,bool,Microsoft::Diagnostics::EndpointUnregistrationReason)

- ea: `0x1801992ec`
- end: `0x1801999c3`
- name: `?UnregisterSettingsEndpoint@SettingsManager@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@_NVEndpointUnregistrationReason@23@@Z`
- size: `1751`
- prototype: ``
- caller_count: `4`
- callee_count: `35`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18018d830`
- `0x180192aa8`
- `0x180199220`
- `0x1802ac480`

## callees

- `0x180001d28`
- `0x1800021e4`
- `0x180002b94`
- `0x18001cf30`
- `0x18001d160`
- `0x18001d200`
- `0x18001e638`
- `0x18001ee94`
- `0x180020fbc`
- `0x1800333b0`
- `0x180035698`
- `0x18003fd8c`
- `0x180048ff4`
- `0x18005491c`
- `0x180057f58`
- `0x18005b974`
- `0x18005d050`
- `0x180065dec`
- `0x180098d5c`
- `0x1800a60e4`
- `0x1800a8e5c`
- `0x1800a9344`
- `0x1800af5f0`
- `0x1800f76bc`
- `0x18012de40`
- `0x180161298`
- `0x180173794`
- `0x18018875c`
- `0x180189b24`
- `0x180189d4c`
- `0x180194d60`
- `0x1801992ec`
- `0x18019a440`
- `0x18019a500`
- `0x18019a848`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801998dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801998dd`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180199716`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180199716`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1801998c5`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1801998c5`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1801997c9`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1801997c9`

## string_xrefs

- `0x180199734`: `onecore\base\telemetry\utc\service\engine\settingsmanager.cpp`
- `0x1801997e7`: `onecore\base\telemetry\utc\service\engine\settingsmanager.cpp`
- `0x1801998ee`: `onecore\base\telemetry\utc\service\engine\settingsmanager.cpp`
- `0x18019988f`: `.json`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=1
void __fastcall Microsoft::Diagnostics::SettingsManager::UnregisterSettingsEndpoint(
        __int64 a1,
        _QWORD *a2,
        char a3,
        int a4)
{
  __int64 v7; // rax
  int v8; // ecx
  int v9; // r8d
  int v10; // r9d
  __int64 v11; // r13
  unsigned __int64 v12; // rax
  unsigned __int64 v13; // r15
  __m128i v14; // xmm6
  __m128i v15; // xmm7
  __int64 v16; // rax
  int v17; // ecx
  int v18; // r8d
  __int64 v19; // r9
  __int64 v20; // rcx
  unsigned __int64 v21; // r15
  __int64 v22; // rdx
  __int64 v23; // r14
  char v24; // bl
  _QWORD *v25; // rax
  const WCHAR *v26; // rdx
  unsigned int v27; // eax
  const WCHAR *v28; // rdx
  unsigned int v29; // eax
  wchar_t **v30; // rdx
  void *appended; // rax
  void *v32; // rax
  void *v33; // rax
  const WCHAR *v34; // rcx
  const char *v35; // r9
  __int64 v36; // rax
  int v37; // ecx
  int v38; // r8d
  int v39; // r9d
  unsigned int v40; // [rsp+20h] [rbp-608h]
  unsigned int v41; // [rsp+20h] [rbp-608h]
  __m128i v43; // [rsp+50h] [rbp-5D8h] BYREF
  HKEY hKey[2]; // [rsp+60h] [rbp-5C8h] BYREF
  HKEY v45; // [rsp+70h] [rbp-5B8h] BYREF
  _QWORD v46[2]; // [rsp+78h] [rbp-5B0h] BYREF
  _BYTE v47[16]; // [rsp+88h] [rbp-5A0h] BYREF
  LPCWSTR lpSubKey[4]; // [rsp+98h] [rbp-590h] BYREF
  LPCWSTR lpValueName[4]; // [rsp+B8h] [rbp-570h] BYREF
  WCHAR Src[16]; // [rsp+D8h] [rbp-550h] BYREF
  LPCWSTR lpFileName[7]; // [rsp+F8h] [rbp-530h] BYREF
  _BYTE v52[1128]; // [rsp+130h] [rbp-4F8h] BYREF
  _BYTE v53[56]; // [rsp+598h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+628h] [rbp+0h]

  if ( (unsigned int)dword_18042D328 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 512) )
  {
    v7 = _tlgWrapBinary<wchar_t,2>(&v43, *a2, *((unsigned int *)a2 + 2));
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperArray<1>>(
      v8,
      (unsigned int)&unk_1803C3091,
      v9,
      v10,
      v7);
  }
  std::wstring::wstring((__int64)lpSubKey, a2);
  v11 = a2[1];
  v12 = std::_Traits_find_ch<std::char_traits<wchar_t>>(*a2, v11, 0, 46);
  v13 = v12;
  if ( v12 - 1 > 0xFFFFFFFFFFFFFFFDuLL || v12 >= v11 - 1 )
  {
    if ( (unsigned int)dword_18042D328 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 512) )
    {
      v36 = _tlgWrapBinary<wchar_t,2>(v47, *a2, (unsigned int)v11);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperArray<1>>(
        v37,
        (unsigned int)&unk_1803C2FB1,
        v38,
        v39,
        v36);
    }
    goto LABEL_10;
  }
  std::wstring_view::substr(a2, hKey, 0, v12);
  v46[0] = v13 + 1;
  std::wstring_view::substr(a2, &v43, v13 + 1, -1);
  v14 = v43;
  v15 = *(__m128i *)hKey;
  if ( !(unsigned __int8)Microsoft::Diagnostics::SettingsEndpoint::PartnerAndFeatureAreValid(hKey, &v43) )
  {
    if ( (unsigned int)dword_18042D328 > 2 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_18042D328, 512) )
      {
        _tlgWrapBinary<wchar_t,2>(&v43, v14.m128i_i64[0], _mm_srli_si128(v14, 8).m128i_u32[0]);
        v16 = _tlgWrapBinary<wchar_t,2>(v46, v15.m128i_i64[0], _mm_srli_si128(v15, 8).m128i_u32[0]);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperArray<1>,_tlgWrapperArray<1>>(
          v17,
          (unsigned int)&unk_1803C2F5F,
          v18,
          v19,
          v16,
          v19);
      }
    }
LABEL_10:
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpSubKey);
    return;
  }
  std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(&v43, a1 + 632);
  v21 = std::_Uhash_compare<std::wstring,Microsoft::Diagnostics::Utils::Hash::CaseInsensitiveHashPredicate,Microsoft::Diagnostics::Utils::String::CaseInsensitiveEqualToPredicate>::operator()<std::wstring>(
          v20,
          lpSubKey);
  v22 = std::_Hash<std::_Umap_traits<std::wstring,unsigned __int64,std::_Uhash_compare<std::wstring,Microsoft::Diagnostics::Utils::Hash::CaseInsensitiveHashPredicate,Microsoft::Diagnostics::Utils::String::CaseInsensitiveEqualToPredicate>,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::_Find_last<std::wstring>(
          (_QWORD *)(a1 + 792),
          hKey,
          (__int64)lpSubKey,
          v21)[1];
  if ( v22 )
  {
    std::_Hash<std::_Umap_traits<Microsoft::Diagnostics::ScenarioDbLookupPair,Microsoft::Diagnostics::ScenarioObjectCache::ScenarioObjectMapValue,std::_Uhash_compare<Microsoft::Diagnostics::ScenarioDbLookupPair,std::hash<Microsoft::Diagnostics::ScenarioDbLookupPair>,Microsoft::Diagnostics::ScenarioDbLookupPairEqualsPred>,std::allocator<std::pair<Microsoft::Diagnostics::ScenarioDbLookupPair const,Microsoft::Diagnostics::ScenarioObjectCache::ScenarioObjectMapValue>>,0>>::_Erase_bucket(
      a1 + 792,
      v22,
      v21 & *(_QWORD *)(a1 + 840));
    std::list<std::pair<std::wstring const,std::unique_ptr<Microsoft::Diagnostics::SettingsEndpoint>>>::_Unchecked_erase(a1 + 800);
    v23 = 1;
  }
  else
  {
    v23 = 0;
  }
  std::unique_lock<std::mutex>::~unique_lock<std::mutex>(&v43);
  if ( v23 && std::_Traits_find<std::char_traits<wchar_t>>(*a2, v11, 0, (unsigned int)L"P-", 2) != -1 )
  {
    hKey[0] = (HKEY)L"SettingsManager_TenantEndpointUnregistered_0";
    hKey[1] = (HKEY)44;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AsimovSyntheticEvent(
      (unsigned int)v52,
      (unsigned int)hKey,
      0x1000000,
      0,
      0,
      0,
      0);
    hKey[0] = (HKEY)L"Endpoint";
    hKey[1] = (HKEY)8;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring_view>((unsigned int)v52, (unsigned int)v53);
    LODWORD(hKey[0]) = a4;
    v43.m128i_i64[0] = (__int64)L"Reason";
    v43.m128i_i64[1] = 6;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned long>((unsigned int)v52, (unsigned int)v53);
    v43 = 0;
    Microsoft::Diagnostics::Utils::Enum::MakeEnumSet<Microsoft::Diagnostics::PersistSyntheticOptions>(hKey, &v43);
    Microsoft::Diagnostics::AsimovEventSerializer::PersistSyntheticEvent((Microsoft::Diagnostics::IAsimovEvent *)v52);
    Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v52);
  }
  v24 = a3;
  if ( !a3 )
  {
    v25 = (_QWORD *)std::wstring_view::substr(a2, &v43, v46[0], -1);
    std::wstring::wstring((__int64)lpValueName, v25);
    std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(v46, a1 + 232);
    v43 = *(__m128i *)std::_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,std::less<void>,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::_Eqrange<std::wstring>(
                        a1 + 56,
                        v47,
                        lpValueName);
    std::_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,std::less<void>,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::_Erase(
      a1 + 56,
      &v43);
    std::unique_lock<std::mutex>::~unique_lock<std::mutex>(v46);
    hKey[0] = 0;
    v43 = *(__m128i *)&off_18035EF90;
    if ( (int)Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY_LOCAL_MACHINE, 0xF003Fu, 0) >= 0 && hKey[0] )
    {
      v26 = (const WCHAR *)lpValueName;
      if ( lpValueName[3] > (LPCWSTR)7 )
        v26 = lpValueName[0];
      v27 = RegDeleteValueW(hKey[0], v26);
      if ( (v27 & 0xFFFFFFFD) != 0 )
        wil::details::in1diag3::Log_Win32(
          retaddr,
          (void *)0xF75,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsmanager.cpp",
          (const char *)v27,
          v40);
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hKey);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpValueName);
    v24 = a3;
  }
  v45 = 0;
  v43 = *(__m128i *)&off_180349EF8;
  if ( (int)Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY_LOCAL_MACHINE, 0xF003Fu, 0) >= 0 && v45 )
  {
    v28 = (const WCHAR *)lpSubKey;
    if ( lpSubKey[3] > (LPCWSTR)7 )
      v28 = lpSubKey[0];
    v29 = RegDeleteKeyW(v45, v28);
    if ( (v29 & 0xFFFFFFFD) != 0 )
      wil::details::in1diag3::Log_Win32(
        retaddr,
        (void *)0xF82,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsmanager.cpp",
        (const char *)v29,
        v41);
  }
  v30 = &off_18035F270;
  if ( !v24 )
    v30 = &off_18035F280;
  std::wstring::wstring((__int64)Src, v30);
  Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(Src);
  Microsoft::Diagnostics::WideStringStream::WideStringStream((Microsoft::Diagnostics::WideStringStream *)lpFileName);
  v43 = *(__m128i *)std::wstring::operator std::wstring_view(Src, v47);
  appended = (void *)Microsoft::Diagnostics::WideStringStream::AppendString(lpFileName);
  v32 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(appended);
  v43 = *(__m128i *)a2;
  v33 = (void *)Microsoft::Diagnostics::WideStringStream::AppendString(v32);
  Microsoft::Diagnostics::WideStringStream::operator<<(v33);
  v34 = (const WCHAR *)lpFileName;
  if ( lpFileName[3] > (LPCWSTR)7 )
    v34 = lpFileName[0];
  if ( !DeleteFileW(v34) && GetLastError() != 2 )
    wil::details::in1diag3::_Log_GetLastError(
      retaddr,
      (void *)0xF8E,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsmanager.cpp",
      v35);
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpFileName);
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v45);
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpSubKey);
}

```

## disassembly

```asm
0x1801992ec  mov     rax, rsp
0x1801992ef  mov     [rax+18h], rbx
0x1801992f3  push    rsi
0x1801992f4  push    r12
0x1801992f6  push    r13
0x1801992f8  push    r14
0x1801992fa  push    r15
0x1801992fc  sub     rsp, 600h
0x180199303  movaps  xmmword ptr [rax-38h], xmm6
0x180199307  movaps  xmmword ptr [rax-48h], xmm7
0x18019930b  mov     rax, cs:__security_cookie
0x180199312  xor     rax, rsp
0x180199315  mov     [rsp+628h+var_58], rax
0x18019931d  mov     ebx, r9d
0x180199320  mov     [rsp+628h+var_5E8], r8b
0x180199325  mov     rsi, rdx
0x180199328  mov     r12, rcx
0x18019932b  mov     eax, cs:dword_18042D328
0x180199331  mov     r14d, 200h
0x180199337  cmp     eax, 4
0x18019933a  jbe     short loc_180199371
0x18019933c  mov     edx, r14d
0x18019933f  lea     rcx, dword_18042D328
0x180199346  call    _tlgKeywordOn
0x18019934b  test    al, al
0x18019934d  jz      short loc_180199371
0x18019934f  mov     r8d, [rsi+8]
0x180199353  mov     rdx, [rsi]
0x180199356  lea     rcx, [rsp+628h+var_5D8]
0x18019935b  call    ??$_tlgWrapBinary@_W$01@@YA?AU?$_tlgWrapperArray@$00@@PEB_W_K@Z; _tlgWrapBinary<wchar_t,2>(wchar_t const *,unsigned __int64)
0x180199360  mov     qword ptr [rsp+628h+var_608], rax
0x180199365  lea     rdx, unk_1803C3091
0x18019936c  call    ??$Write@U?$_tlgWrapperArray@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperArray@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperArray<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperArray<1> const &)
0x180199371  mov     rdx, rsi
0x180199374  lea     rcx, [rsp+628h+lpSubKey]
0x18019937c  call    ??$?0V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_zstring_view@_W@wil@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wil::basic_zstring_view<wchar_t> const &,std::allocator<wchar_t> const &)
0x180199381  nop
0x180199382  mov     r13, [rsi+8]
0x180199386  mov     r9d, 2Eh ; '.'
0x18019938c  xor     r8d, r8d
0x18019938f  mov     rdx, r13
0x180199392  mov     rcx, [rsi]
0x180199395  call    ??$_Traits_find_ch@U?$char_traits@_W@std@@@std@@YA_KQEB_W_K1_W@Z; std::_Traits_find_ch<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,unsigned __int64,wchar_t)
0x18019939a  mov     r15, rax
0x18019939d  lea     rcx, [rax-1]
0x1801993a1  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1801993a5  ja      loc_18019996C
0x1801993ab  lea     rcx, [r13-1]
0x1801993af  cmp     rax, rcx
0x1801993b2  jnb     loc_18019996C
0x1801993b8  mov     r9, rax
0x1801993bb  xor     r8d, r8d
0x1801993be  lea     rdx, [rsp+628h+hKey]
0x1801993c3  mov     rcx, rsi
0x1801993c6  call    ?substr@?$basic_string_view@_WU?$char_traits@_W@std@@@std@@QEBA?AV12@_K_K@Z; std::wstring_view::substr(unsigned __int64,unsigned __int64)
0x1801993cb  lea     rax, [r15+1]
0x1801993cf  mov     [rsp+628h+var_5B0], rax
0x1801993d4  or      r9, 0FFFFFFFFFFFFFFFFh
0x1801993d8  mov     r8, rax
0x1801993db  lea     rdx, [rsp+628h+var_5D8]
0x1801993e0  mov     rcx, rsi
0x1801993e3  call    ?substr@?$basic_string_view@_WU?$char_traits@_W@std@@@std@@QEBA?AV12@_K_K@Z; std::wstring_view::substr(unsigned __int64,unsigned __int64)
0x1801993e8  movaps  xmm6, [rsp+628h+var_5D8]
0x1801993ed  movdqa  [rsp+628h+var_5D8], xmm6
0x1801993f3  movaps  xmm7, xmmword ptr [rsp+628h+hKey]
0x1801993f8  movdqa  xmmword ptr [rsp+628h+hKey], xmm7
0x1801993fe  lea     rdx, [rsp+628h+var_5D8]
0x180199403  lea     rcx, [rsp+628h+hKey]
0x180199408  call    ?PartnerAndFeatureAreValid@SettingsEndpoint@Diagnostics@Microsoft@@SA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Microsoft::Diagnostics::SettingsEndpoint::PartnerAndFeatureAreValid(std::wstring_view,std::wstring_view)
0x18019940d  test    al, al
0x18019940f  jnz     loc_18019949F
0x180199415  mov     eax, cs:dword_18042D328
0x18019941b  cmp     eax, 2
0x18019941e  jbe     short loc_18019948D
0x180199420  mov     rdx, r14
0x180199423  lea     rcx, dword_18042D328
0x18019942a  call    _tlgKeywordOn
0x18019942f  test    al, al
0x180199431  jz      short loc_18019948D
0x180199433  movdqa  xmm0, xmm6
0x180199437  psrldq  xmm0, 8
0x18019943c  movq    r8, xmm0
0x180199441  mov     r8d, r8d
0x180199444  movq    rdx, xmm6
0x180199449  lea     rcx, [rsp+628h+var_5D8]
0x18019944e  call    ??$_tlgWrapBinary@_W$01@@YA?AU?$_tlgWrapperArray@$00@@PEB_W_K@Z; _tlgWrapBinary<wchar_t,2>(wchar_t const *,unsigned __int64)
0x180199453  mov     r9, rax
0x180199456  movdqa  xmm0, xmm7
0x18019945a  psrldq  xmm0, 8
0x18019945f  movq    r8, xmm0
0x180199464  mov     r8d, r8d
0x180199467  movq    rdx, xmm7
0x18019946c  lea     rcx, [rsp+628h+var_5B0]
0x180199471  call    ??$_tlgWrapBinary@_W$01@@YA?AU?$_tlgWrapperArray@$00@@PEB_W_K@Z; _tlgWrapBinary<wchar_t,2>(wchar_t const *,unsigned __int64)
0x180199476  mov     qword ptr [rsp+628h+var_600], r9
0x18019947b  mov     qword ptr [rsp+628h+var_608], rax
0x180199480  lea     rdx, unk_1803C2F5F
0x180199487  call    ??$Write@U?$_tlgWrapperArray@$00@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperArray@$00@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperArray<1>,_tlgWrapperArray<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperArray<1> const &,_tlgWrapperArray<1> const &)
0x18019948c  nop
0x18019948d  lea     rcx, [rsp+628h+lpSubKey]; this
0x180199495  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18019949a  jmp     loc_180199938
0x18019949f  lea     rdx, [r12+278h]
0x1801994a7  lea     rcx, [rsp+628h+var_5D8]
0x1801994ac  call    ??0?$unique_lock@Vrecursive_mutex@std@@@std@@QEAA@AEAVrecursive_mutex@1@@Z; std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(std::recursive_mutex &)
0x1801994b1  lea     r14, [r12+318h]
0x1801994b9  lea     rdx, [rsp+628h+lpSubKey]
0x1801994c1  call    ??$?RV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UCaseInsensitiveHashPredicate@Hash@Utils@Diagnostics@Microsoft@@UCaseInsensitiveEqualToPredicate@String@567@@std@@QEBA_KAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Uhash_compare<std::wstring,Microsoft::Diagnostics::Utils::Hash::CaseInsensitiveHashPredicate,Microsoft::Diagnostics::Utils::String::CaseInsensitiveEqualToPredicate>::operator()<std::wstring>(std::wstring const &)
0x1801994c6  mov     r15, rax
0x1801994c9  mov     r9, rax
0x1801994cc  lea     r8, [rsp+628h+lpSubKey]
0x1801994d4  lea     rdx, [rsp+628h+hKey]
0x1801994d9  mov     rcx, r14
0x1801994dc  call    ??$_Find_last@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_KV?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UCaseInsensitiveHashPredicate@Hash@Utils@Diagnostics@Microsoft@@UCaseInsensitiveEqualToPredicate@String@567@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_K@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_K@std@@PEAX@std@@@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@_K@Z; std::_Hash<std::_Umap_traits<std::wstring,unsigned __int64,std::_Uhash_compare<std::wstring,Microsoft::Diagnostics::Utils::Hash::CaseInsensitiveHashPredicate,Microsoft::Diagnostics::Utils::String::CaseInsensitiveEqualToPredicate>,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x1801994e1  mov     rdx, [rax+8]
0x1801994e5  test    rdx, rdx
0x1801994e8  jz      short loc_18019950A
0x1801994ea  mov     r8, [r14+30h]
0x1801994ee  and     r8, r15
0x1801994f1  mov     rcx, r14
0x1801994f4  call    ?_Erase_bucket@?$_Hash@V?$_Umap_traits@UScenarioDbLookupPair@Diagnostics@Microsoft@@UScenarioObjectMapValue@ScenarioObjectCache@23@V?$_Uhash_compare@UScenarioDbLookupPair@Diagnostics@Microsoft@@U?$hash@UScenarioDbLookupPair@Diagnostics@Microsoft@@@std@@UScenarioDbLookupPairEqualsPred@23@@std@@V?$allocator@U?$pair@$$CBUScenarioDbLookupPair@Diagnostics@Microsoft@@UScenarioObjectMapValue@ScenarioObjectCache@23@@std@@@7@$0A@@std@@@std@@IEAAXPEAU?$_List_node@U?$pair@$$CBUScenarioDbLookupPair@Diagnostics@Microsoft@@UScenarioObjectMapValue@ScenarioObjectCache@23@@std@@PEAX@2@_K@Z; std::_Hash<std::_Umap_traits<Microsoft::Diagnostics::ScenarioDbLookupPair,Microsoft::Diagnostics::ScenarioObjectCache::ScenarioObjectMapValue,std::_Uhash_compare<Microsoft::Diagnostics::ScenarioDbLookupPair,std::hash<Microsoft::Diagnostics::ScenarioDbLookupPair>,Microsoft::Diagnostics::ScenarioDbLookupPairEqualsPred>,std::allocator<std::pair<Microsoft::Diagnostics::ScenarioDbLookupPair const,Microsoft::Diagnostics::ScenarioObjectCache::ScenarioObjectMapValue>>,0>>::_Erase_bucket(std::_List_node<std::pair<Microsoft::Diagnostics::ScenarioDbLookupPair const,Microsoft::Diagnostics::ScenarioObjectCache::ScenarioObjectMapValue>,void *> *,unsigned __int64)
0x1801994f9  lea     rcx, [r14+8]
0x1801994fd  call    ?_Unchecked_erase@?$list@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@VSettingsEndpoint@Diagnostics@Microsoft@@U?$default_delete@VSettingsEndpoint@Diagnostics@Microsoft@@@std@@@2@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@VSettingsEndpoint@Diagnostics@Microsoft@@U?$default_delete@VSettingsEndpoint@Diagnostics@Microsoft@@@std@@@2@@std@@@2@@std@@AEAAPEAU?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@VSettingsEndpoint@Diagnostics@Microsoft@@U?$default_delete@VSettingsEndpoint@Diagnostics@Microsoft@@@std@@@2@@std@@PEAX@2@QEAU32@@Z; std::list<std::pair<std::wstring const,std::unique_ptr<Microsoft::Diagnostics::SettingsEndpoint>>>::_Unchecked_erase(std::_List_node<std::pair<std::wstring const,std::unique_ptr<Microsoft::Diagnostics::SettingsEndpoint>>,void *> * const)
0x180199502  mov     r14d, 1
0x180199508  jmp     short loc_18019950D
0x18019950a  xor     r14d, r14d
0x18019950d  lea     rcx, [rsp+628h+var_5D8]
0x180199512  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x180199517  test    r14, r14
0x18019951a  jz      loc_18019962E
0x180199520  mov     qword ptr [rsp+628h+var_608], 2
0x180199529  mov     r9, cs:off_18035EF80; "P-"
0x180199530  xor     r8d, r8d
0x180199533  mov     rdx, r13
0x180199536  mov     rcx, [rsi]
0x180199539  call    ??$_Traits_find@U?$char_traits@_W@std@@@std@@YA_KQEB_W_K101@Z; std::_Traits_find<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,unsigned __int64,wchar_t const * const,unsigned __int64)
0x18019953e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180199542  jz      loc_18019962E
0x180199548  lea     rax, aSettingsmanage_2; "SettingsManager_TenantEndpointUnregiste"...
0x18019954f  mov     [rsp+628h+hKey], rax
0x180199554  mov     [rsp+628h+hKey+8], 2Ch ; ','
0x18019955d  mov     r8d, 1000000h
0x180199563  mov     [rsp+628h+var_5F8], 0
0x180199568  mov     byte ptr [rsp+628h+var_600], 0
0x18019956d  mov     byte ptr [rsp+628h+var_608], 0
0x180199572  mov     r9, 400000000000h
0x18019957c  lea     rdx, [rsp+628h+hKey]
0x180199581  lea     rcx, [rsp+628h+var_4F8]
0x180199589  call    ??0AsimovSyntheticEvent@Diagnostics@Microsoft@@QEAA@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@UPrivacyDataType@@_KVTriggerPersistence@12@VTriggerLatency@12@_N@Z; Microsoft::Diagnostics::AsimovSyntheticEvent::AsimovSyntheticEvent(std::wstring_view,PrivacyDataType,unsigned __int64,Microsoft::Diagnostics::TriggerPersistence,Microsoft::Diagnostics::TriggerLatency,bool)
0x18019958e  nop
0x18019958f  lea     rax, aEndpoint_1; "Endpoint"
0x180199596  mov     [rsp+628h+hKey], rax
0x18019959b  mov     [rsp+628h+hKey+8], 8
0x1801995a4  mov     r9, rsi
0x1801995a7  lea     r8, [rsp+628h+hKey]
0x1801995ac  lea     rdx, [rsp+628h+var_90]
0x1801995b4  lea     rcx, [rsp+628h+var_4F8]
0x1801995bc  call    ??$AddField@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@AsimovSyntheticEvent@Diagnostics@Microsoft@@QEAAXAEAUObjectIterator@012@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEBV45@@Z; Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring_view>(Microsoft::Diagnostics::AsimovSyntheticEvent::ObjectIterator &,std::wstring_view,std::wstring_view const &)
0x1801995c1  mov     dword ptr [rsp+628h+hKey], ebx
0x1801995c5  lea     rax, aReason; "Reason"
0x1801995cc  mov     qword ptr [rsp+628h+var_5D8], rax
0x1801995d1  mov     qword ptr [rsp+628h+var_5D8+8], 6
0x1801995da  lea     r9, [rsp+628h+hKey]
0x1801995df  lea     r8, [rsp+628h+var_5D8]
0x1801995e4  lea     rdx, [rsp+628h+var_90]
0x1801995ec  lea     rcx, [rsp+628h+var_4F8]
0x1801995f4  call    ??$AddField@K@AsimovSyntheticEvent@Diagnostics@Microsoft@@QEAAXAEAUObjectIterator@012@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEBK@Z; Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<ulong>(Microsoft::Diagnostics::AsimovSyntheticEvent::ObjectIterator &,std::wstring_view,ulong const &)
0x1801995f9  xorps   xmm0, xmm0
0x1801995fc  movdqa  [rsp+628h+var_5D8], xmm0
0x180199602  lea     rdx, [rsp+628h+var_5D8]
0x180199607  lea     rcx, [rsp+628h+hKey]
0x18019960c  call    ??$MakeEnumSet@VPersistSyntheticOptions@Diagnostics@Microsoft@@@Enum@Utils@Diagnostics@Microsoft@@SA?AV?$bitset@$01@std@@V?$initializer_list@VPersistSyntheticOptions@Diagnostics@Microsoft@@@5@@Z; Microsoft::Diagnostics::Utils::Enum::MakeEnumSet<Microsoft::Diagnostics::PersistSyntheticOptions>(std::initializer_list<Microsoft::Diagnostics::PersistSyntheticOptions>)
0x180199611  mov     edx, [rax]
0x180199613  lea     rcx, [rsp+628h+var_4F8]; this
0x18019961b  call    ?PersistSyntheticEvent@AsimovEventSerializer@Diagnostics@Microsoft@@SAJAEAVAsimovSyntheticEvent@23@V?$bitset@$01@std@@@Z; Microsoft::Diagnostics::AsimovEventSerializer::PersistSyntheticEvent(Microsoft::Diagnostics::AsimovSyntheticEvent &,std::bitset<2>)
0x180199620  nop
0x180199621  lea     rcx, [rsp+628h+var_4F8]; this
0x180199629  call    ??1AsimovSyntheticEvent@Diagnostics@Microsoft@@UEAA@XZ; Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent(void)
0x18019962e  mov     bl, [rsp+628h+var_5E8]
0x180199632  test    bl, bl
0x180199634  jnz     loc_180199762
0x18019963a  or      r9, 0FFFFFFFFFFFFFFFFh
0x18019963e  mov     r8, [rsp+628h+var_5B0]
0x180199643  lea     rdx, [rsp+628h+var_5D8]
0x180199648  mov     rcx, rsi
0x18019964b  call    ?substr@?$basic_string_view@_WU?$char_traits@_W@std@@@std@@QEBA?AV12@_K_K@Z; std::wstring_view::substr(unsigned __int64,unsigned __int64)
0x180199650  mov     rdx, rax
0x180199653  lea     rcx, [rsp+628h+lpValueName]
0x18019965b  call    ??$?0V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_zstring_view@_W@wil@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wil::basic_zstring_view<wchar_t> const &,std::allocator<wchar_t> const &)
0x180199660  nop
0x180199661  lea     rdx, [r12+0E8h]
0x180199669  lea     rcx, [rsp+628h+var_5B0]
0x18019966e  call    ??0?$unique_lock@Vrecursive_mutex@std@@@std@@QEAA@AEAVrecursive_mutex@1@@Z; std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(std::recursive_mutex &)
0x180199673  lea     r8, [rsp+628h+lpValueName]
0x18019967b  lea     rdx, [rsp+628h+var_5A0]
0x180199683  lea     rcx, [r12+38h]
0x180199688  call    ??$_Eqrange@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_KU?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_K@std@@@2@$0A@@std@@@std@@IEBA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_K@std@@PEAX@std@@PEAU12@@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,std::less<void>,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::_Eqrange<std::wstring>(std::wstring const &)
0x18019968d  movups  xmm0, xmmword ptr [rax]
0x180199690  movdqu  [rsp+628h+var_5D8], xmm0
0x180199696  lea     rdx, [rsp+628h+var_5D8]
0x18019969b  lea     rcx, [r12+38h]
0x1801996a0  call    ?_Erase@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_KU?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_K@std@@@2@$0A@@std@@@std@@AEAA_KU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_K@std@@PEAX@std@@PEAU12@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,std::less<void>,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::_Erase(std::pair<std::_Tree_node<std::pair<std::wstring const,unsigned __int64>,void *> *,std::_Tree_node<std::pair<std::wstring const,unsigned __int64>,void *> *>)
0x1801996a5  lea     rcx, [rsp+628h+var_5B0]
0x1801996aa  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x1801996af  mov     [rsp+628h+hKey], 0
0x1801996b8  movups  xmm0, xmmword ptr cs:off_18035EF90; "%DiagtrackRegistryRoot%\\TelemetryNames"...
0x1801996bf  movdqu  [rsp+628h+var_5D8], xmm0
0x1801996c5  mov     [rsp+628h+var_600], 0; DWORD
0x1801996cd  mov     [rsp+628h+var_608], 0F003Fh; unsigned int
0x1801996d5  xor     r9d, r9d
0x1801996d8  lea     r8, [rsp+628h+hKey]
0x1801996dd  lea     rdx, [rsp+628h+var_5D8]
0x1801996e2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1801996e9  call    ?CreateKey@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAU_SECURITY_ATTRIBUTES@@KK@Z; Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY__ *,std::wstring_view,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x1801996ee  test    eax, eax
0x1801996f0  js      short loc_180199746
0x1801996f2  mov     rcx, [rsp+628h+hKey]; hKey
0x1801996f7  test    rcx, rcx
0x1801996fa  jz      short loc_180199746
0x1801996fc  lea     rdx, [rsp+628h+lpValueName]
0x180199704  cmp     [rsp+628h+var_558], 7
0x18019970d  cmova   rdx, [rsp+628h+lpValueName]; lpValueName
0x180199716  call    cs:__imp_RegDeleteValueW
0x18019971d  nop     dword ptr [rax+rax+00h]
0x180199722  test    eax, 0FFFFFFFDh
0x180199727  jz      short loc_180199746
0x180199729  mov     rcx, [rsp+628h]; this
0x180199731  mov     r9d, eax; char *
0x180199734  lea     r8, aOnecoreBaseTel_84; "onecore\\base\\telemetry\\utc\\service"...
0x18019973b  mov     edx, 0F75h; void *
0x180199740  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x180199745  nop
0x180199746  lea     rcx, [rsp+628h+hKey]
0x18019974b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180199750  nop
0x180199751  lea     rcx, [rsp+628h+lpValueName]; this
0x180199759  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18019975e  mov     bl, [rsp+628h+var_5E8]
0x180199762  mov     [rsp+628h+var_5B8], 0
0x18019976b  movups  xmm0, xmmword ptr cs:off_180349EF8; "%DiagtrackRegistryRoot%\\SettingsReques"...
0x180199772  movdqu  [rsp+628h+var_5D8], xmm0
0x180199778  mov     [rsp+628h+var_600], 0; DWORD
0x180199780  mov     [rsp+628h+var_608], 0F003Fh; unsigned int
0x180199788  xor     r9d, r9d
0x18019978b  lea     r8, [rsp+628h+var_5B8]
0x180199790  lea     rdx, [rsp+628h+var_5D8]
0x180199795  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18019979c  call    ?CreateKey@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAU_SECURITY_ATTRIBUTES@@KK@Z; Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY__ *,std::wstring_view,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x1801997a1  test    eax, eax
0x1801997a3  js      short loc_1801997F8
0x1801997a5  mov     rcx, [rsp+628h+var_5B8]; hKey
0x1801997aa  test    rcx, rcx
0x1801997ad  jz      short loc_1801997F8
0x1801997af  lea     rdx, [rsp+628h+lpSubKey]
0x1801997b7  cmp     [rsp+628h+var_578], 7
0x1801997c0  cmova   rdx, [rsp+628h+lpSubKey]; lpSubKey
0x1801997c9  call    cs:__imp_RegDeleteKeyW
0x1801997d0  nop     dword ptr [rax+rax+00h]
0x1801997d5  test    eax, 0FFFFFFFDh
0x1801997da  jz      short loc_1801997F8
0x1801997dc  mov     rcx, [rsp+628h]; this
0x1801997e4  mov     r9d, eax; char *
0x1801997e7  lea     r8, aOnecoreBaseTel_84; "onecore\\base\\telemetry\\utc\\service"...
0x1801997ee  mov     edx, 0F82h; void *
0x1801997f3  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x1801997f8  lea     rax, off_18035F280; "%DiagtrackStorageRoot%\\DownloadedSetti"...
0x1801997ff  lea     rdx, off_18035F270; "%DiagtrackStorageRoot%\\DownloadedScena"...
0x180199806  test    bl, bl
0x180199808  cmovz   rdx, rax
0x18019980c  lea     rcx, [rsp+628h+Src]
0x180199814  call    ??$?0V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_zstring_view@_W@wil@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wil::basic_zstring_view<wchar_t> const &,std::allocator<wchar_t> const &)
0x180199819  nop
0x18019981a  xor     r8d, r8d
0x18019981d  mov     dl, 1
0x18019981f  lea     rcx, [rsp+628h+Src]; lpSrc
0x180199827  call    ?ExpandEnvironmentStringsInString@String@Utils@Diagnostics@Microsoft@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_NPEAX@Z; Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(std::wstring &,bool,void *)
0x18019982c  lea     rcx, [rsp+628h+lpFileName]; this
0x180199834  call    ??0WideStringStream@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::WideStringStream::WideStringStream(void)
0x180199839  nop
0x18019983a  lea     rdx, [rsp+628h+var_5A0]
0x180199842  lea     rcx, [rsp+628h+Src]
0x18019984a  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18019984f  movups  xmm0, xmmword ptr [rax]
0x180199852  movdqu  [rsp+628h+var_5D8], xmm0
0x180199858  lea     rdx, [rsp+628h+var_5D8]
0x18019985d  lea     rcx, [rsp+628h+lpFileName]; Src
0x180199865  call    ?AppendString@WideStringStream@Diagnostics@Microsoft@@AEAAAEAV123@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::WideStringStream::AppendString(std::wstring_view)
0x18019986a  lea     rdx, asc_1803772C8; "\\"
0x180199871  mov     rcx, rax; Src
0x180199874  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x180199879  movups  xmm0, xmmword ptr [rsi]
0x18019987c  movdqu  [rsp+628h+var_5D8], xmm0
0x180199882  lea     rdx, [rsp+628h+var_5D8]
0x180199887  mov     rcx, rax; Src
0x18019988a  call    ?AppendString@WideStringStream@Diagnostics@Microsoft@@AEAAAEAV123@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::WideStringStream::AppendString(std::wstring_view)
0x18019988f  lea     rcx, aJson_0; ".json"
0x180199896  lea     rdx, aXml; ".xml"
0x18019989d  test    bl, bl
0x18019989f  cmovz   rdx, rcx
0x1801998a3  mov     rcx, rax; Src
  ... truncated ...
```
