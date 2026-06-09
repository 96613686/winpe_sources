# Microsoft::Diagnostics::LifetimeManager::EnsureAclsOnFolder(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>)

- ea: `0x18017e554`
- end: `0x18017ea78`
- name: `?EnsureAclsOnFolder@LifetimeManager@Diagnostics@Microsoft@@AEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z`
- size: `1316`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18006e038`
- `0x1801817c4`

## callees

- `0x180001bf4`
- `0x180001d28`
- `0x180002b94`
- `0x1800035ec`
- `0x18001d160`
- `0x180035698`
- `0x180053a84`
- `0x18005d050`
- `0x18006dd98`
- `0x18006f66c`
- `0x1800827b8`
- `0x1800a1e24`
- `0x1800bc2e0`
- `0x18012de40`
- `0x18017e554`
- `0x180346010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18017e6b0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18017e6b0`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18017e60b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18017e60b`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18017e696`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18017e6f3`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18017e696`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18017e6f3`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x18017e866`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x18017e866`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18017e828`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18017e828`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x18017e735`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x18017e735`

## string_xrefs

- `0x18017ea1b`: `onecore\base\telemetry\utc\service\engine\lifetimemanager.cpp`
- `0x18017ea30`: `onecore\base\telemetry\utc\service\engine\lifetimemanager.cpp`
- `0x18017ea42`: `onecore\base\telemetry\utc\service\engine\lifetimemanager.cpp`
- `0x18017ea54`: `onecore\base\telemetry\utc\service\engine\lifetimemanager.cpp`
- `0x18017ea65`: `onecore\base\telemetry\utc\service\engine\lifetimemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall Microsoft::Diagnostics::LifetimeManager::EnsureAclsOnFolder(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  __int64 v5; // rax
  int v6; // ecx
  int v7; // r8d
  int v8; // r9d
  const WCHAR *v9; // rcx
  const WCHAR *v10; // rcx
  HLOCAL v11; // rbx
  const WCHAR *v12; // rcx
  const char *v13; // r9
  const char *v14; // r9
  __int64 v15; // rax
  const WCHAR *v16; // rcx
  const char *v17; // r9
  const WCHAR *v18; // rcx
  const char *v19; // r9
  __int64 (__fastcall ***v20)(); // rdx
  int v21; // r8d
  int v22; // r9d
  int v23; // eax
  int lpnLengthNeeded; // [rsp+20h] [rbp-1D8h]
  int lpnLengthNeededa; // [rsp+20h] [rbp-1D8h]
  DWORD nLengthNeeded; // [rsp+30h] [rbp-1C8h] BYREF
  int v27; // [rsp+34h] [rbp-1C4h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+38h] [rbp-1C0h] BYREF
  LPWSTR StringSecurityDescriptor[2]; // [rsp+40h] [rbp-1B8h] BYREF
  const WCHAR *v30; // [rsp+50h] [rbp-1A8h] BYREF
  __int64 v31; // [rsp+58h] [rbp-1A0h]
  _QWORD v32[2]; // [rsp+60h] [rbp-198h] BYREF
  __int128 v33; // [rsp+70h] [rbp-188h] BYREF
  _OWORD *v34; // [rsp+80h] [rbp-178h]
  _OWORD v35[2]; // [rsp+90h] [rbp-168h] BYREF
  _BYTE v36[72]; // [rsp+B0h] [rbp-148h] BYREF
  _BYTE v37[72]; // [rsp+F8h] [rbp-100h] BYREF
  LPCWSTR lpFileName[3]; // [rsp+140h] [rbp-B8h] BYREF
  unsigned __int64 v39; // [rsp+158h] [rbp-A0h]
  LPCWSTR v40[4]; // [rsp+160h] [rbp-98h] BYREF
  __int64 (__fastcall **v41)(); // [rsp+180h] [rbp-78h] BYREF
  int v42; // [rsp+188h] [rbp-70h]
  int v43; // [rsp+18Ch] [rbp-6Ch]
  PSECURITY_DESCRIPTOR *p_SecurityDescriptor; // [rsp+190h] [rbp-68h]
  int *v45; // [rsp+198h] [rbp-60h]
  __int64 (__fastcall ***v46)(); // [rsp+1B8h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+0h]

  v34 = a2;
  if ( (unsigned int)dword_18042D328 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 16) )
  {
    v5 = _tlgWrapBinary<wchar_t,2>(v35, *a2, *((unsigned int *)a2 + 2));
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperArray<1>>(
      v6,
      (unsigned int)&unk_1803C1EF7,
      v7,
      v8,
      v5);
  }
  try
  {
    std::wstring::wstring((__int64)lpFileName, a2);
    v9 = (const WCHAR *)lpFileName;
    if ( v39 > 7 )
      v9 = lpFileName[0];
    if ( GetFileAttributesW(v9) == -1 )
    {
      if ( (unsigned int)dword_18042D328 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 16) )
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
          &dword_18042D328,
          &unk_1803C1E78);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpFileName);
    }
    else
    {
      nLengthNeeded = 0;
      v10 = (const WCHAR *)lpFileName;
      if ( v39 > 7 )
        v10 = lpFileName[0];
      if ( GetFileSecurityW(v10, 5u, 0, 0, &nLengthNeeded) )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x9A6,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
          (const char *)0x8000FFFFLL,
          lpnLengthNeededa);
      v11 = LocalAlloc(0, nLengthNeeded);
      v32[0] = v11;
      v12 = (const WCHAR *)lpFileName;
      if ( v39 > 7 )
        v12 = lpFileName[0];
      if ( !GetFileSecurityW(v12, 5u, v11, nLengthNeeded, &nLengthNeeded) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x9AE,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
          v13);
      StringSecurityDescriptor[0] = 0;
      wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::reset(
        StringSecurityDescriptor,
        0);
      if ( !ConvertSecurityDescriptorToStringSecurityDescriptorW(v11, 1u, 5u, StringSecurityDescriptor, 0) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x9B6,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
          v14);
      v15 = -1;
      do
        ++v15;
      while ( StringSecurityDescriptor[0][v15] );
      v33 = *(_OWORD *)a3;
      v30 = StringSecurityDescriptor[0];
      v31 = v15;
      if ( (unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v30, &v33) )
      {
        std::wstring::wstring((__int64)v40, a3);
        SecurityDescriptor = 0;
        wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::reset(
          &SecurityDescriptor,
          0);
        v16 = (const WCHAR *)v40;
        if ( v40[3] > (LPCWSTR)7 )
          v16 = v40[0];
        if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(v16, 1u, &SecurityDescriptor, 0) )
          wil::details::in1diag3::Throw_GetLastError(
            retaddr,
            (void *)0x9CA,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
            v17);
        v18 = (const WCHAR *)lpFileName;
        if ( v39 > 7 )
          v18 = lpFileName[0];
        if ( !SetFileSecurityW(v18, 5u, SecurityDescriptor) )
          wil::details::in1diag3::Throw_GetLastError(
            retaddr,
            (void *)0x9CF,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
            v19);
        v27 = 0;
        v36[64] = 0;
        v37[64] = 0;
        v41 = off_180355B18;
        v42 = 5;
        v43 = DWORD1(v35[0]);
        p_SecurityDescriptor = &SecurityDescriptor;
        v45 = &v27;
        v46 = &v41;
        v30 = L"*";
        v31 = 1;
        *(_QWORD *)&v33 = L"*";
        *((_QWORD *)&v33 + 1) = 1;
        v35[0] = *(_OWORD *)a2;
        Microsoft::Diagnostics::Utils::FileSystem::DoForEachFileAndDirectoryRecursivelyInPattern(
          (unsigned int)v35,
          (unsigned int)&v33,
          (unsigned int)&v30,
          (unsigned int)&v41,
          (__int64)v37,
          (__int64)v36);
        if ( v46 )
        {
          v20 = &v41;
          LOBYTE(v20) = v46 != &v41;
          ((void (__fastcall *)(__int64 (__fastcall ***)(), __int64 (__fastcall ***)()))(*v46)[4])(v46, v20);
        }
        if ( (unsigned int)dword_18042D328 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 16) )
        {
          LODWORD(v30) = v27;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (unsigned int)&dword_18042D328,
            (unsigned int)&unk_1803C1E2B,
            v21,
            v22,
            (__int64)&v30);
        }
        wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&SecurityDescriptor);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v40);
        wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(StringSecurityDescriptor);
        wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(v32);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpFileName);
      }
      else
      {
        if ( (unsigned int)dword_18042D328 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 16) )
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
            &dword_18042D328,
            &unk_1803C1EB9);
        wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(StringSecurityDescriptor);
        wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(v32);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpFileName);
      }
    }
  }
  catch ( ... )
  {
    v35[0] = *v34;
    v23 = Microsoft::Diagnostics::Utils::FileSystem::RecursivelyDeleteDirectory();
    if ( v23 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x9E9,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
        (const char *)(unsigned int)v23,
        lpnLengthNeeded);
  }
}

```

## disassembly

```asm
0x18017e554  mov     [rsp+arg_0], rbx
0x18017e559  mov     [rsp+arg_18], rsi
0x18017e55e  push    rdi
0x18017e55f  push    r12
0x18017e561  push    r13
0x18017e563  push    r14
0x18017e565  push    r15
0x18017e567  sub     rsp, 1D0h
0x18017e56e  mov     rax, cs:__security_cookie
0x18017e575  xor     rax, rsp
0x18017e578  mov     [rsp+1F8h+var_38], rax
0x18017e580  mov     r12, r8
0x18017e583  mov     r15, rdx
0x18017e586  mov     [rsp+1F8h+var_178], rdx
0x18017e58e  mov     eax, cs:dword_18042D328
0x18017e594  mov     r14d, 10h
0x18017e59a  lea     rsi, dword_18042D328
0x18017e5a1  cmp     eax, 4
0x18017e5a4  jbe     short loc_18017E5DE
0x18017e5a6  mov     edx, r14d
0x18017e5a9  mov     rcx, rsi
0x18017e5ac  call    _tlgKeywordOn
0x18017e5b1  xor     edi, edi
0x18017e5b3  test    al, al
0x18017e5b5  jz      short loc_18017E5E0
0x18017e5b7  mov     r8d, [r15+8]
0x18017e5bb  mov     rdx, [r15]
0x18017e5be  lea     rcx, [rsp+1F8h+var_168]
0x18017e5c6  call    ??$_tlgWrapBinary@_W$01@@YA?AU?$_tlgWrapperArray@$00@@PEB_W_K@Z; _tlgWrapBinary<wchar_t,2>(wchar_t const *,unsigned __int64)
0x18017e5cb  mov     [rsp+1F8h+lpnLengthNeeded], rax
0x18017e5d0  lea     rdx, unk_1803C1EF7
0x18017e5d7  call    ??$Write@U?$_tlgWrapperArray@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperArray@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperArray<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperArray<1> const &)
0x18017e5dc  jmp     short loc_18017E5E0
0x18017e5de  xor     edi, edi
0x18017e5e0  mov     rdx, r15
0x18017e5e3  lea     rcx, [rsp+1F8h+lpFileName]
0x18017e5eb  call    ??$?0V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_zstring_view@_W@wil@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wil::basic_zstring_view<wchar_t> const &,std::allocator<wchar_t> const &)
0x18017e5f0  nop
0x18017e5f1  lea     rcx, [rsp+1F8h+lpFileName]
0x18017e5f9  cmp     [rsp+1F8h+var_A0], 7
0x18017e602  cmova   rcx, [rsp+1F8h+lpFileName]; lpFileName
0x18017e60b  call    cs:__imp_GetFileAttributesW
0x18017e612  nop     dword ptr [rax+rax+00h]
0x18017e617  cmp     eax, 0FFFFFFFFh
0x18017e61a  jnz     short loc_18017E659
0x18017e61c  mov     eax, cs:dword_18042D328
0x18017e622  cmp     eax, 4
0x18017e625  jbe     short loc_18017E646
0x18017e627  mov     rdx, r14
0x18017e62a  mov     rcx, rsi
0x18017e62d  call    _tlgKeywordOn
0x18017e632  test    al, al
0x18017e634  jz      short loc_18017E646
0x18017e636  lea     rdx, unk_1803C1E78
0x18017e63d  mov     rcx, rsi
0x18017e640  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18017e645  nop
0x18017e646  lea     rcx, [rsp+1F8h+lpFileName]; this
0x18017e64e  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18017e653  nop
0x18017e654  jmp     loc_18017E9E7
0x18017e659  mov     [rsp+1F8h+nLengthNeeded], edi
0x18017e65d  lea     rcx, [rsp+1F8h+lpFileName]
0x18017e665  cmp     [rsp+1F8h+var_A0], 7
0x18017e66e  cmova   rcx, [rsp+1F8h+lpFileName]; lpFileName
0x18017e677  mov     rbx, [rsp+1F8h]
0x18017e67f  lea     rax, [rsp+1F8h+nLengthNeeded]
0x18017e684  mov     [rsp+1F8h+lpnLengthNeeded], rax; int
0x18017e689  xor     r9d, r9d; nLength
0x18017e68c  xor     r8d, r8d; pSecurityDescriptor
0x18017e68f  lea     r13d, [r9+5]
0x18017e693  mov     edx, r13d; RequestedInformation
0x18017e696  call    cs:__imp_GetFileSecurityW
0x18017e69d  nop     dword ptr [rax+rax+00h]
0x18017e6a2  test    eax, eax
0x18017e6a4  jnz     loc_18017EA15
0x18017e6aa  mov     edx, [rsp+1F8h+nLengthNeeded]; uBytes
0x18017e6ae  xor     ecx, ecx; uFlags
0x18017e6b0  call    cs:__imp_LocalAlloc
0x18017e6b7  nop     dword ptr [rax+rax+00h]
0x18017e6bc  mov     rbx, rax
0x18017e6bf  mov     [rsp+1F8h+var_198], rax
0x18017e6c4  lea     rcx, [rsp+1F8h+lpFileName]
0x18017e6cc  cmp     [rsp+1F8h+var_A0], 7
0x18017e6d5  cmova   rcx, [rsp+1F8h+lpFileName]; lpFileName
0x18017e6de  lea     rax, [rsp+1F8h+nLengthNeeded]
0x18017e6e3  mov     [rsp+1F8h+lpnLengthNeeded], rax; lpnLengthNeeded
0x18017e6e8  mov     r9d, [rsp+1F8h+nLengthNeeded]; nLength
0x18017e6ed  mov     r8, rbx; pSecurityDescriptor
0x18017e6f0  mov     edx, r13d; RequestedInformation
0x18017e6f3  call    cs:__imp_GetFileSecurityW
0x18017e6fa  nop     dword ptr [rax+rax+00h]
0x18017e6ff  mov     rcx, [rsp+1F8h]; this
0x18017e707  test    eax, eax
0x18017e709  jz      loc_18017EA30
0x18017e70f  mov     [rsp+1F8h+StringSecurityDescriptor], rdi
0x18017e714  xor     edx, edx
0x18017e716  lea     rcx, [rsp+1F8h+StringSecurityDescriptor]
0x18017e71b  call    ?reset@?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAAXPEA_W@Z; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::reset(wchar_t *)
0x18017e720  mov     [rsp+1F8h+lpnLengthNeeded], rdi; StringSecurityDescriptorLen
0x18017e725  lea     r9, [rsp+1F8h+StringSecurityDescriptor]; StringSecurityDescriptor
0x18017e72a  mov     r8d, r13d; SecurityInformation
0x18017e72d  mov     edx, 1; RequestedStringSDRevision
0x18017e732  mov     rcx, rbx; SecurityDescriptor
0x18017e735  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x18017e73c  nop     dword ptr [rax+rax+00h]
0x18017e741  mov     rcx, [rsp+1F8h]; this
0x18017e749  test    eax, eax
0x18017e74b  jz      loc_18017EA42
0x18017e751  mov     rcx, [rsp+1F8h+StringSecurityDescriptor]
0x18017e756  or      rax, 0FFFFFFFFFFFFFFFFh
0x18017e75a  inc     rax
0x18017e75d  cmp     [rcx+rax*2], di
0x18017e761  jnz     short loc_18017E75A
0x18017e763  movups  xmm0, xmmword ptr [r12]
0x18017e768  movdqu  [rsp+1F8h+var_188], xmm0
0x18017e76e  mov     [rsp+1F8h+var_1A8], rcx
0x18017e773  mov     [rsp+1F8h+var_1A0], rax
0x18017e778  lea     rdx, [rsp+1F8h+var_188]
0x18017e77d  lea     rcx, [rsp+1F8h+var_1A8]
0x18017e782  call    ?ICompare@String@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Microsoft::Diagnostics::Utils::String::ICompare(std::wstring_view,std::wstring_view)
0x18017e787  test    eax, eax
0x18017e789  jnz     short loc_18017E7DE
0x18017e78b  mov     eax, cs:dword_18042D328
0x18017e791  cmp     eax, 4
0x18017e794  jbe     short loc_18017E7B5
0x18017e796  mov     rdx, r14
0x18017e799  mov     rcx, rsi
0x18017e79c  call    _tlgKeywordOn
0x18017e7a1  test    al, al
0x18017e7a3  jz      short loc_18017E7B5
0x18017e7a5  lea     rdx, unk_1803C1EB9
0x18017e7ac  mov     rcx, rsi
0x18017e7af  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18017e7b4  nop
0x18017e7b5  lea     rcx, [rsp+1F8h+StringSecurityDescriptor]
0x18017e7ba  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x18017e7bf  nop
0x18017e7c0  lea     rcx, [rsp+1F8h+var_198]
0x18017e7c5  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x18017e7ca  nop
0x18017e7cb  lea     rcx, [rsp+1F8h+lpFileName]; this
0x18017e7d3  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18017e7d8  nop
0x18017e7d9  jmp     loc_18017E9E7
0x18017e7de  mov     rdx, r12
0x18017e7e1  lea     rcx, [rsp+1F8h+var_98]
0x18017e7e9  call    ??$?0V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_zstring_view@_W@wil@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wil::basic_zstring_view<wchar_t> const &,std::allocator<wchar_t> const &)
0x18017e7ee  nop
0x18017e7ef  mov     [rsp+1F8h+SecurityDescriptor], rdi
0x18017e7f4  xor     edx, edx
0x18017e7f6  lea     rcx, [rsp+1F8h+SecurityDescriptor]
0x18017e7fb  call    ?reset@?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAAXPEA_W@Z; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::reset(wchar_t *)
0x18017e800  lea     rcx, [rsp+1F8h+var_98]
0x18017e808  cmp     [rsp+1F8h+var_80], 7
0x18017e811  cmova   rcx, [rsp+1F8h+var_98]; StringSecurityDescriptor
0x18017e81a  xor     r9d, r9d; SecurityDescriptorSize
0x18017e81d  lea     r8, [rsp+1F8h+SecurityDescriptor]; SecurityDescriptor
0x18017e822  lea     ebx, [r9+1]
0x18017e826  mov     edx, ebx; StringSDRevision
0x18017e828  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18017e82f  nop     dword ptr [rax+rax+00h]
0x18017e834  mov     rcx, [rsp+1F8h]; this
0x18017e83c  test    eax, eax
0x18017e83e  jz      loc_18017EA54
0x18017e844  lea     rcx, [rsp+1F8h+lpFileName]
0x18017e84c  cmp     [rsp+1F8h+var_A0], 7
0x18017e855  cmova   rcx, [rsp+1F8h+lpFileName]; lpFileName
0x18017e85e  mov     r8, [rsp+1F8h+SecurityDescriptor]; pSecurityDescriptor
0x18017e863  mov     edx, r13d; SecurityInformation
0x18017e866  call    cs:__imp_SetFileSecurityW
0x18017e86d  nop     dword ptr [rax+rax+00h]
0x18017e872  mov     rcx, [rsp+1F8h]; this
0x18017e87a  test    eax, eax
0x18017e87c  jz      loc_18017EA65
0x18017e882  mov     [rsp+1F8h+var_1C4], edi
0x18017e886  mov     [rsp+1F8h+var_108], dil
0x18017e88e  mov     [rsp+1F8h+var_C0], dil
0x18017e896  lea     rax, off_180355B18
0x18017e89d  mov     [rsp+1F8h+var_78], rax
0x18017e8a5  mov     [rsp+1F8h+var_70], r13d
0x18017e8ad  mov     eax, dword ptr [rsp+1F8h+var_168+4]
0x18017e8b4  mov     [rsp+1F8h+var_6C], eax
0x18017e8bb  lea     rax, [rsp+1F8h+SecurityDescriptor]
0x18017e8c0  mov     [rsp+1F8h+var_68], rax
0x18017e8c8  lea     rax, [rsp+1F8h+var_1C4]
0x18017e8cd  mov     [rsp+1F8h+var_60], rax
0x18017e8d5  lea     rax, [rsp+1F8h+var_78]
0x18017e8dd  mov     [rsp+1F8h+var_40], rax
0x18017e8e5  lea     rax, pszMore; "*"
0x18017e8ec  mov     [rsp+1F8h+var_1A8], rax
0x18017e8f1  mov     [rsp+1F8h+var_1A0], rbx
0x18017e8f6  mov     qword ptr [rsp+1F8h+var_188], rax
0x18017e8fb  mov     qword ptr [rsp+1F8h+var_188+8], rbx
0x18017e900  movups  xmm0, xmmword ptr [r15]
0x18017e904  movdqu  [rsp+1F8h+var_168], xmm0
0x18017e90d  lea     rax, [rsp+1F8h+var_148]
0x18017e915  mov     [rsp+1F8h+var_1D0], rax
0x18017e91a  lea     rax, [rsp+1F8h+var_100]
0x18017e922  mov     [rsp+1F8h+lpnLengthNeeded], rax
0x18017e927  lea     r9, [rsp+1F8h+var_78]
0x18017e92f  lea     r8, [rsp+1F8h+var_1A8]
0x18017e934  lea     rdx, [rsp+1F8h+var_188]
0x18017e939  lea     rcx, [rsp+1F8h+var_168]
0x18017e941  call    ?DoForEachFileAndDirectoryRecursivelyInPattern@FileSystem@Utils@Diagnostics@Microsoft@@SAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@00AEBV?$function@$$A6A_NAEBVAutoFindFile@@@Z@6@V?$optional@V?$function@$$A6AXXZ@std@@@6@V?$optional@V?$function@$$A6A_NJ@Z@std@@@6@@Z; Microsoft::Diagnostics::Utils::FileSystem::DoForEachFileAndDirectoryRecursivelyInPattern(std::wstring_view,std::wstring_view,std::wstring_view,std::function<bool (AutoFindFile const &)> const &,std::optional<std::function<void (void)>>,std::optional<std::function<bool (long)>>)
0x18017e946  nop
0x18017e947  mov     rcx, [rsp+1F8h+var_40]
0x18017e94f  test    rcx, rcx
0x18017e952  jz      short loc_18017E96E
0x18017e954  mov     rax, [rcx]
0x18017e957  lea     rdx, [rsp+1F8h+var_78]
0x18017e95f  cmp     rcx, rdx
0x18017e962  setnz   dl
0x18017e965  mov     rax, [rax+20h]
0x18017e969  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017e96e  mov     eax, cs:dword_18042D328
0x18017e974  cmp     eax, 4
0x18017e977  jbe     short loc_18017E9AA
0x18017e979  mov     rdx, r14
0x18017e97c  mov     rcx, rsi
0x18017e97f  call    _tlgKeywordOn
0x18017e984  test    al, al
0x18017e986  jz      short loc_18017E9AA
0x18017e988  mov     eax, [rsp+1F8h+var_1C4]
0x18017e98c  mov     dword ptr [rsp+1F8h+var_1A8], eax
0x18017e990  lea     rax, [rsp+1F8h+var_1A8]
0x18017e995  mov     [rsp+1F8h+lpnLengthNeeded], rax
0x18017e99a  lea     rdx, unk_1803C1E2B
0x18017e9a1  mov     rcx, rsi
0x18017e9a4  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18017e9a9  nop
0x18017e9aa  lea     rcx, [rsp+1F8h+SecurityDescriptor]
0x18017e9af  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x18017e9b4  nop
0x18017e9b5  lea     rcx, [rsp+1F8h+var_98]; this
0x18017e9bd  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18017e9c2  nop
0x18017e9c3  lea     rcx, [rsp+1F8h+StringSecurityDescriptor]
0x18017e9c8  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x18017e9cd  nop
0x18017e9ce  lea     rcx, [rsp+1F8h+var_198]
0x18017e9d3  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x18017e9d8  nop
0x18017e9d9  lea     rcx, [rsp+1F8h+lpFileName]; this
0x18017e9e1  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18017e9e6  nop
0x18017e9e7  mov     rcx, [rsp+1F8h+var_38]
0x18017e9ef  xor     rcx, rsp; StackCookie
0x18017e9f2  call    __security_check_cookie
0x18017e9f7  lea     r11, [rsp+1F8h+var_28]
0x18017e9ff  mov     rbx, [r11+30h]
0x18017ea03  mov     rsi, [r11+48h]
0x18017ea07  mov     rsp, r11
0x18017ea0a  pop     r15
0x18017ea0c  pop     r14
0x18017ea0e  pop     r13
0x18017ea10  pop     r12
0x18017ea12  pop     rdi
0x18017ea13  retn
0x18017ea15  mov     r9d, 8000FFFFh; char *
0x18017ea1b  lea     r8, aOnecoreBaseTel_210; "onecore\\base\\telemetry\\utc\\service"...
0x18017ea22  mov     edx, 9A6h; void *
0x18017ea27  mov     rcx, rbx; this
0x18017ea2a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18017ea30  lea     r8, aOnecoreBaseTel_210; "onecore\\base\\telemetry\\utc\\service"...
0x18017ea37  mov     edx, 9AEh; void *
0x18017ea3c  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18017ea42  lea     r8, aOnecoreBaseTel_210; "onecore\\base\\telemetry\\utc\\service"...
0x18017ea49  mov     edx, 9B6h; void *
0x18017ea4e  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18017ea54  lea     r8, aOnecoreBaseTel_210; "onecore\\base\\telemetry\\utc\\service"...
0x18017ea5b  mov     edx, 9CAh; void *
0x18017ea60  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18017ea65  lea     r8, aOnecoreBaseTel_210; "onecore\\base\\telemetry\\utc\\service"...
0x18017ea6c  mov     edx, 9CFh; void *
0x18017ea71  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
