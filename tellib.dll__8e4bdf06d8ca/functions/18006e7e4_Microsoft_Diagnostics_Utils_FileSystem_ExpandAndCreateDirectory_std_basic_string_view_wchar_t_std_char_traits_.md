# Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,bool,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>)

- ea: `0x18006e7e4`
- end: `0x18006ec77`
- name: `?ExpandAndCreateDirectory@FileSystem@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@_N0@Z`
- size: `1171`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `17`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18006de80`
- `0x18006e038`
- `0x18006f9f0`
- `0x1800705e4`
- `0x180086440`
- `0x1800f71d4`
- `0x1800f888c`
- `0x1801817c4`
- `0x1801cbb28`
- `0x1801e0f90`
- `0x1801e1cd0`
- `0x1801e58a0`
- `0x1801ef158`
- `0x1801ef780`
- `0x18022dd54`
- `0x180260350`
- `0x1802efaf0`

## callees

- `0x180001d28`
- `0x1800044d4`
- `0x18000459c`
- `0x18001d160`
- `0x180035698`
- `0x180048ff4`
- `0x18005a764`
- `0x18005d050`
- `0x18006dd98`
- `0x18006e7e4`
- `0x18006f334`
- `0x18006f66c`
- `0x18008bd1c`
- `0x18012de40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e902`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e939`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ead2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006eb07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e902`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e939`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ead2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006eb07`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18006e8ee`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18006eabe`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18006e8ee`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18006eabe`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(
        _QWORD *a1,
        char a2,
        __int128 *a3)
{
  __int64 v5; // rbx
  __int64 *v6; // rdi
  const WCHAR *v7; // rcx
  const char *v8; // r9
  LPCWSTR *v9; // rax
  __int64 v10; // rax
  int v11; // r8d
  int v12; // r9d
  unsigned int v13; // ebx
  unsigned __int64 i; // rbx
  LPCWSTR *v16; // r14
  LPCWSTR *v17; // rax
  const WCHAR *v18; // rcx
  const char *v19; // r9
  LPCWSTR *v20; // rax
  __int64 v21; // rax
  int v22; // r8d
  int v23; // r9d
  unsigned int LastError; // ebx
  LPCWSTR *v25; // rax
  __int64 v26; // rax
  int v27; // r8d
  int v28; // r9d
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+40h] [rbp-98h] BYREF
  __int64 v30; // [rsp+48h] [rbp-90h] BYREF
  __int128 v31; // [rsp+50h] [rbp-88h] BYREF
  __int128 v32; // [rsp+60h] [rbp-78h] BYREF
  __int64 v33; // [rsp+70h] [rbp-68h]
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+78h] [rbp-60h] BYREF
  LPCWSTR lpPathName[2]; // [rsp+90h] [rbp-48h] BYREF
  unsigned __int64 v36; // [rsp+A0h] [rbp-38h]
  unsigned __int64 v37; // [rsp+A8h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  v5 = 0;
  v30 = 0;
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  if ( *((_QWORD *)a3 + 1) )
  {
    v31 = *a3;
    v6 = (__int64 *)Microsoft::Diagnostics::Utils::Os::CreateSecurityDecriptorFromSddl(&SecurityDescriptor);
    if ( &v30 != v6 )
    {
      wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::reset(
        &v30,
        *v6);
      *v6 = 0;
      v5 = v30;
    }
    wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&SecurityDescriptor);
    *(_QWORD *)&v32 = 24;
    *((_QWORD *)&v32 + 1) = v5;
    v33 = 0;
    *(_OWORD *)&SecurityAttributes.nLength = v32;
    *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
  }
  std::wstring::wstring((__int64)lpPathName, a1);
  Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(lpPathName, 1, 0);
  v7 = (const WCHAR *)lpPathName;
  if ( a2 )
  {
    if ( v37 > 7 )
      v7 = lpPathName[0];
    if ( v7[v36 - 1] != 92 )
      std::wstring::push_back(lpPathName, 92);
    for ( i = 0; i < v36; ++i )
    {
      v16 = lpPathName;
      if ( v37 > 7 )
        v16 = (LPCWSTR *)lpPathName[0];
      if ( *((_WORD *)v16 + i) == 92 )
      {
        if ( !i )
          goto LABEL_49;
        v17 = lpPathName;
        if ( v37 > 7 )
          v17 = (LPCWSTR *)lpPathName[0];
        if ( *((_WORD *)v17 + i - 1) == 58 )
        {
LABEL_49:
          if ( (unsigned int)dword_18042D328 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 0x20000) )
          {
            *(_QWORD *)&v31 = i;
            v25 = lpPathName;
            if ( v37 > 7 )
              v25 = (LPCWSTR *)lpPathName[0];
            SecurityDescriptor = v25;
            v26 = _tlgWrapBinary<wchar_t,2>(&v32, *a1, *((unsigned int *)a1 + 2));
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperArray<1>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<8>>(
              (unsigned int)&SecurityDescriptor,
              (unsigned int)&unk_1803C26E8,
              v27,
              v28,
              v26,
              (__int64)&SecurityDescriptor,
              (__int64)&v31);
          }
        }
        else
        {
          *((_WORD *)v16 + i) = 0;
          v18 = (const WCHAR *)lpPathName;
          if ( v37 > 7 )
            v18 = lpPathName[0];
          if ( !CreateDirectoryW(v18, &SecurityAttributes) && GetLastError() != 183 )
          {
            if ( (unsigned int)dword_18042D328 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 0x20000) )
            {
              LODWORD(SecurityDescriptor) = GetLastError();
              v20 = lpPathName;
              if ( v37 > 7 )
                v20 = (LPCWSTR *)lpPathName[0];
              *(_QWORD *)&v31 = v20;
              v21 = _tlgWrapBinary<wchar_t,2>(&v32, *a1, *((unsigned int *)a1 + 2));
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperArray<1>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
                (unsigned int)&v31,
                (unsigned int)&unk_1803C27AA,
                v22,
                v23,
                v21,
                (__int64)&v31,
                (__int64)&SecurityDescriptor);
            }
            LastError = wil::details::in1diag3::Return_GetLastError(
                          retaddr,
                          (void *)0x5C4,
                          (unsigned int)"onecore\\base\\telemetry\\utc\\include\\FileSystemUtils.h",
                          v19);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpPathName);
            wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&v30);
            return LastError;
          }
          *((_WORD *)v16 + i) = 92;
        }
      }
    }
    goto LABEL_46;
  }
  if ( v37 > 7 )
    v7 = lpPathName[0];
  if ( CreateDirectoryW(v7, &SecurityAttributes) || GetLastError() == 183 )
  {
LABEL_46:
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpPathName);
    wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&v30);
    return 0;
  }
  if ( (unsigned int)dword_18042D328 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 0x20000) )
  {
    LODWORD(SecurityDescriptor) = GetLastError();
    v9 = lpPathName;
    if ( v37 > 7 )
      v9 = (LPCWSTR *)lpPathName[0];
    *(_QWORD *)&v31 = v9;
    v10 = _tlgWrapBinary<wchar_t,2>(&v32, *a1, *((unsigned int *)a1 + 2));
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperArray<1>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
      (unsigned int)&v31,
      (unsigned int)&unk_1803C2756,
      v11,
      v12,
      v10,
      (__int64)&v31,
      (__int64)&SecurityDescriptor);
  }
  v13 = wil::details::in1diag3::Return_GetLastError(
          retaddr,
          (void *)0x59C,
          (unsigned int)"onecore\\base\\telemetry\\utc\\include\\FileSystemUtils.h",
          v8);
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpPathName);
  wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&v30);
  return v13;
}

```

## disassembly

```asm
0x18006e7e4  mov     r11, rsp
0x18006e7e7  mov     [r11+10h], rbx
0x18006e7eb  mov     [r11+20h], rsi
0x18006e7ef  push    rdi
0x18006e7f0  push    r12
0x18006e7f2  push    r14
0x18006e7f4  sub     rsp, 0C0h
0x18006e7fb  mov     rax, cs:__security_cookie
0x18006e802  xor     rax, rsp
0x18006e805  mov     [rsp+0D8h+var_28], rax
0x18006e80d  mov     r14b, dl
0x18006e810  mov     rsi, rcx
0x18006e813  xor     ebx, ebx
0x18006e815  mov     [rsp+0D8h+var_90], rbx
0x18006e81a  xorps   xmm0, xmm0
0x18006e81d  xor     eax, eax
0x18006e81f  movups  xmmword ptr [rsp+0D8h+SecurityAttributes.nLength], xmm0
0x18006e824  mov     [r11-50h], rax
0x18006e828  cmp     [r8+8], rax
0x18006e82c  jz      short loc_18006E8A3
0x18006e82e  movups  xmm0, xmmword ptr [r8]
0x18006e832  movdqu  [rsp+0D8h+var_88], xmm0
0x18006e838  lea     rdx, [rsp+0D8h+var_88]
0x18006e83d  lea     rcx, [rsp+0D8h+SecurityDescriptor]; SecurityDescriptor
0x18006e842  call    ?CreateSecurityDecriptorFromSddl@Os@Utils@Diagnostics@Microsoft@@SA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::Utils::Os::CreateSecurityDecriptorFromSddl(std::wstring_view)
0x18006e847  mov     rdi, rax
0x18006e84a  lea     rax, [rsp+0D8h+var_90]
0x18006e84f  cmp     rax, rdi
0x18006e852  jz      short loc_18006E869
0x18006e854  mov     rdx, [rdi]
0x18006e857  lea     rcx, [rsp+0D8h+var_90]
0x18006e85c  call    ?reset@?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAAXPEA_W@Z; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::reset(wchar_t *)
0x18006e861  mov     [rdi], rbx
0x18006e864  mov     rbx, [rsp+0D8h+var_90]
0x18006e869  lea     rcx, [rsp+0D8h+SecurityDescriptor]
0x18006e86e  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x18006e873  mov     qword ptr [rsp+0D8h+var_78], 18h
0x18006e87c  mov     qword ptr [rsp+0D8h+var_78+8], rbx
0x18006e881  mov     [rsp+0D8h+var_68], 0
0x18006e88a  movups  xmm0, [rsp+0D8h+var_78]
0x18006e88f  movups  xmmword ptr [rsp+0D8h+SecurityAttributes.nLength], xmm0
0x18006e894  movsd   xmm1, [rsp+0D8h+var_68]
0x18006e89a  movsd   qword ptr [rsp+0D8h+SecurityAttributes.bInheritHandle], xmm1
0x18006e8a3  mov     rdx, rsi
0x18006e8a6  lea     rcx, [rsp+0D8h+lpPathName]
0x18006e8ae  call    ??$?0V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_zstring_view@_W@wil@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wil::basic_zstring_view<wchar_t> const &,std::allocator<wchar_t> const &)
0x18006e8b3  nop
0x18006e8b4  xor     r8d, r8d
0x18006e8b7  mov     dl, 1
0x18006e8b9  lea     rcx, [rsp+0D8h+lpPathName]; lpSrc
0x18006e8c1  call    ?ExpandEnvironmentStringsInString@String@Utils@Diagnostics@Microsoft@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_NPEAX@Z; Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(std::wstring &,bool,void *)
0x18006e8c6  lea     rcx, [rsp+0D8h+lpPathName]
0x18006e8ce  test    r14b, r14b
0x18006e8d1  jnz     loc_18006E9F7
0x18006e8d7  cmp     [rsp+0D8h+var_30], 7
0x18006e8e0  cmova   rcx, [rsp+0D8h+lpPathName]; lpPathName
0x18006e8e9  lea     rdx, [rsp+0D8h+SecurityAttributes]; lpSecurityAttributes
0x18006e8ee  call    cs:__imp_CreateDirectoryW
0x18006e8f5  nop     dword ptr [rax+rax+00h]
0x18006e8fa  test    eax, eax
0x18006e8fc  jnz     loc_18006E9D8
0x18006e902  call    cs:__imp_GetLastError
0x18006e909  nop     dword ptr [rax+rax+00h]
0x18006e90e  cmp     eax, 0B7h
0x18006e913  jz      loc_18006E9D8
0x18006e919  mov     eax, cs:dword_18042D328
0x18006e91f  cmp     eax, 2
0x18006e922  jbe     short loc_18006E99E
0x18006e924  mov     edx, 20000h
0x18006e929  lea     rcx, dword_18042D328
0x18006e930  call    _tlgKeywordOn
0x18006e935  test    al, al
0x18006e937  jz      short loc_18006E99E
0x18006e939  call    cs:__imp_GetLastError
0x18006e940  nop     dword ptr [rax+rax+00h]
0x18006e945  mov     dword ptr [rsp+0D8h+SecurityDescriptor], eax
0x18006e949  lea     rax, [rsp+0D8h+lpPathName]
0x18006e951  cmp     [rsp+0D8h+var_30], 7
0x18006e95a  cmova   rax, [rsp+0D8h+lpPathName]
0x18006e963  mov     qword ptr [rsp+0D8h+var_88], rax
0x18006e968  mov     r8d, [rsi+8]
0x18006e96c  mov     rdx, [rsi]
0x18006e96f  lea     rcx, [rsp+0D8h+var_78]
0x18006e974  call    ??$_tlgWrapBinary@_W$01@@YA?AU?$_tlgWrapperArray@$00@@PEB_W_K@Z; _tlgWrapBinary<wchar_t,2>(wchar_t const *,unsigned __int64)
0x18006e979  lea     rcx, [rsp+0D8h+SecurityDescriptor]
0x18006e97e  mov     [rsp+0D8h+var_A8], rcx
0x18006e983  lea     rcx, [rsp+0D8h+var_88]
0x18006e988  mov     [rsp+0D8h+var_B0], rcx
0x18006e98d  mov     [rsp+0D8h+var_B8], rax
0x18006e992  lea     rdx, unk_1803C2756
0x18006e999  call    ??$Write@U?$_tlgWrapperArray@$00@@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperArray@$00@@AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperArray<1>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperArray<1> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x18006e99e  mov     rcx, [rsp+0D8h]; this
0x18006e9a6  lea     r8, aOnecoreBaseTel_0; "onecore\\base\\telemetry\\utc\\include"...
0x18006e9ad  mov     edx, 59Ch; void *
0x18006e9b2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18006e9b7  mov     ebx, eax
0x18006e9b9  lea     rcx, [rsp+0D8h+lpPathName]; this
0x18006e9c1  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18006e9c6  nop
0x18006e9c7  lea     rcx, [rsp+0D8h+var_90]
0x18006e9cc  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x18006e9d1  mov     eax, ebx
0x18006e9d3  jmp     loc_18006EC4D
0x18006e9d8  lea     rcx, [rsp+0D8h+lpPathName]; this
0x18006e9e0  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18006e9e5  nop
0x18006e9e6  lea     rcx, [rsp+0D8h+var_90]
0x18006e9eb  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x18006e9f0  xor     eax, eax
0x18006e9f2  jmp     loc_18006EC4D
0x18006e9f7  cmp     [rsp+0D8h+var_30], 7
0x18006ea00  cmova   rcx, [rsp+0D8h+lpPathName]
0x18006ea09  mov     r12d, 5Ch ; '\'
0x18006ea0f  mov     rax, [rsp+0D8h+var_38]
0x18006ea17  cmp     [rcx+rax*2-2], r12w
0x18006ea1d  jz      short loc_18006EA2F
0x18006ea1f  mov     edx, r12d
0x18006ea22  lea     rcx, [rsp+0D8h+lpPathName]
0x18006ea2a  call    ?push_back@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_W@Z; std::wstring::push_back(wchar_t)
0x18006ea2f  xor     ebx, ebx
0x18006ea31  mov     edi, 20000h
0x18006ea36  cmp     rbx, [rsp+0D8h+var_38]
0x18006ea3e  jnb     loc_18006EC2D
0x18006ea44  lea     r14, [rsp+0D8h+lpPathName]
0x18006ea4c  cmp     [rsp+0D8h+var_30], 7
0x18006ea55  cmova   r14, [rsp+0D8h+lpPathName]
0x18006ea5e  cmp     [r14+rbx*2], r12w
0x18006ea63  jnz     loc_18006EC25
0x18006ea69  test    rbx, rbx
0x18006ea6c  jz      loc_18006EBAD
0x18006ea72  lea     rax, [rsp+0D8h+lpPathName]
0x18006ea7a  cmp     [rsp+0D8h+var_30], 7
0x18006ea83  cmova   rax, [rsp+0D8h+lpPathName]
0x18006ea8c  cmp     word ptr [rax+rbx*2-2], 3Ah ; ':'
0x18006ea92  jz      loc_18006EBAD
0x18006ea98  xor     eax, eax
0x18006ea9a  mov     [r14+rbx*2], ax
0x18006ea9f  lea     rcx, [rsp+0D8h+lpPathName]
0x18006eaa7  cmp     [rsp+0D8h+var_30], 7
0x18006eab0  cmova   rcx, [rsp+0D8h+lpPathName]; lpPathName
0x18006eab9  lea     rdx, [rsp+0D8h+SecurityAttributes]; lpSecurityAttributes
0x18006eabe  call    cs:__imp_CreateDirectoryW
0x18006eac5  nop     dword ptr [rax+rax+00h]
0x18006eaca  test    eax, eax
0x18006eacc  jnz     loc_18006EBA6
0x18006ead2  call    cs:__imp_GetLastError
0x18006ead9  nop     dword ptr [rax+rax+00h]
0x18006eade  cmp     eax, 0B7h
0x18006eae3  jz      loc_18006EBA6
0x18006eae9  mov     eax, cs:dword_18042D328
0x18006eaef  cmp     eax, 2
0x18006eaf2  jbe     short loc_18006EB6C
0x18006eaf4  mov     rdx, rdi
0x18006eaf7  lea     rcx, dword_18042D328
0x18006eafe  call    _tlgKeywordOn
0x18006eb03  test    al, al
0x18006eb05  jz      short loc_18006EB6C
0x18006eb07  call    cs:__imp_GetLastError
0x18006eb0e  nop     dword ptr [rax+rax+00h]
0x18006eb13  mov     dword ptr [rsp+0D8h+SecurityDescriptor], eax
0x18006eb17  lea     rax, [rsp+0D8h+lpPathName]
0x18006eb1f  cmp     [rsp+0D8h+var_30], 7
0x18006eb28  cmova   rax, [rsp+0D8h+lpPathName]
0x18006eb31  mov     qword ptr [rsp+0D8h+var_88], rax
0x18006eb36  mov     r8d, [rsi+8]
0x18006eb3a  mov     rdx, [rsi]
0x18006eb3d  lea     rcx, [rsp+0D8h+var_78]
0x18006eb42  call    ??$_tlgWrapBinary@_W$01@@YA?AU?$_tlgWrapperArray@$00@@PEB_W_K@Z; _tlgWrapBinary<wchar_t,2>(wchar_t const *,unsigned __int64)
0x18006eb47  lea     rcx, [rsp+0D8h+SecurityDescriptor]
0x18006eb4c  mov     [rsp+0D8h+var_A8], rcx
0x18006eb51  lea     rcx, [rsp+0D8h+var_88]
0x18006eb56  mov     [rsp+0D8h+var_B0], rcx
0x18006eb5b  mov     [rsp+0D8h+var_B8], rax
0x18006eb60  lea     rdx, unk_1803C27AA
0x18006eb67  call    ??$Write@U?$_tlgWrapperArray@$00@@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperArray@$00@@AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperArray<1>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperArray<1> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x18006eb6c  mov     rcx, [rsp+0D8h]; this
0x18006eb74  lea     r8, aOnecoreBaseTel_0; "onecore\\base\\telemetry\\utc\\include"...
0x18006eb7b  mov     edx, 5C4h; void *
0x18006eb80  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18006eb85  mov     ebx, eax
0x18006eb87  lea     rcx, [rsp+0D8h+lpPathName]; this
0x18006eb8f  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18006eb94  nop
0x18006eb95  lea     rcx, [rsp+0D8h+var_90]
0x18006eb9a  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x18006eb9f  mov     eax, ebx
0x18006eba1  jmp     loc_18006EC4D
0x18006eba6  mov     [r14+rbx*2], r12w
0x18006ebab  jmp     short loc_18006EC25
0x18006ebad  mov     eax, cs:dword_18042D328
0x18006ebb3  cmp     eax, 5
0x18006ebb6  jbe     short loc_18006EC25
0x18006ebb8  mov     rdx, rdi
0x18006ebbb  lea     rcx, dword_18042D328
0x18006ebc2  call    _tlgKeywordOn
0x18006ebc7  test    al, al
0x18006ebc9  jz      short loc_18006EC25
0x18006ebcb  mov     qword ptr [rsp+0D8h+var_88], rbx
0x18006ebd0  lea     rax, [rsp+0D8h+lpPathName]
0x18006ebd8  cmp     [rsp+0D8h+var_30], 7
0x18006ebe1  cmova   rax, [rsp+0D8h+lpPathName]
0x18006ebea  mov     [rsp+0D8h+SecurityDescriptor], rax
0x18006ebef  mov     r8d, [rsi+8]
0x18006ebf3  mov     rdx, [rsi]
0x18006ebf6  lea     rcx, [rsp+0D8h+var_78]
0x18006ebfb  call    ??$_tlgWrapBinary@_W$01@@YA?AU?$_tlgWrapperArray@$00@@PEB_W_K@Z; _tlgWrapBinary<wchar_t,2>(wchar_t const *,unsigned __int64)
0x18006ec00  lea     rcx, [rsp+0D8h+var_88]
0x18006ec05  mov     [rsp+0D8h+var_A8], rcx
0x18006ec0a  lea     rcx, [rsp+0D8h+SecurityDescriptor]
0x18006ec0f  mov     [rsp+0D8h+var_B0], rcx
0x18006ec14  mov     [rsp+0D8h+var_B8], rax
0x18006ec19  lea     rdx, unk_1803C26E8
0x18006ec20  call    ??$Write@U?$_tlgWrapperArray@$00@@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperArray@$00@@AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperArray<1>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperArray<1> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<8> const &)
0x18006ec25  inc     rbx
0x18006ec28  jmp     loc_18006EA36
0x18006ec2d  lea     rcx, [rsp+0D8h+lpPathName]; this
0x18006ec35  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18006ec3a  nop
0x18006ec3b  lea     rcx, [rsp+0D8h+var_90]
0x18006ec40  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x18006ec45  xor     eax, eax
0x18006ec47  jmp     short loc_18006EC4D
0x18006ec49  mov     eax, dword ptr [rsp+0D8h+SecurityDescriptor]
0x18006ec4d  mov     rcx, [rsp+0D8h+var_28]
0x18006ec55  xor     rcx, rsp; StackCookie
0x18006ec58  call    __security_check_cookie
0x18006ec5d  lea     r11, [rsp+0D8h+var_18]
0x18006ec65  mov     rbx, [r11+28h]
0x18006ec69  mov     rsi, [r11+38h]
0x18006ec6d  mov     rsp, r11
0x18006ec70  pop     r14
0x18006ec72  pop     r12
0x18006ec74  pop     rdi
0x18006ec75  retn
```
