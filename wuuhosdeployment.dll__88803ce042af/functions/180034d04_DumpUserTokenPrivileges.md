# DumpUserTokenPrivileges

- ea: `0x180034d04`
- end: `0x180035082`
- name: `DumpUserTokenPrivileges`
- size: `894`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003543c`

## callees

- `0x180001e8c`
- `0x180003950`
- `0x180003974`
- `0x18000956c`
- `0x180009e38`
- `0x180034d04`
- `0x180036960`
- `0x180042630`
- `0x180043160`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034ea7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034f1e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034f73`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034fed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003504b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180035069`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034ea7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034f1e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034f73`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034fed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003504b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180035069`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034eb5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034f2c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034f81`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034ffb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180035059`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180035077`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034eb5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034f2c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034f81`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034ffb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180035059`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180035077`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034e29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034e29`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeNameW` at `0x180034e1b`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeNameW` at `0x180034e81`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeNameW` at `0x180034e1b`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeNameW` at `0x180034e81`

## string_xrefs

- `0x180034d6c`: `User token has no privileges.`
- `0x180034f4d`: `User token has %lu privileges: %ws`

## pseudocode

```c
__int64 __fastcall DumpUserTokenPrivileges(__int64 a1)
{
  int token_information; // eax
  _DWORD *v2; // rbx
  int LastError; // r15d
  unsigned __int64 v4; // rax
  void *v5; // rsi
  int v6; // r13d
  LPWSTR v7; // rdi
  const char *v8; // r9
  LPWSTR v9; // r14
  const char *v10; // r9
  HANDLE v11; // rax
  __int64 v12; // rdx
  HANDLE v13; // rax
  HANDLE ProcessHeap; // rax
  HANDLE v16; // rax
  __int64 v17; // rdx
  HANDLE v18; // rax
  HANDLE v19; // rax
  int v20; // [rsp+20h] [rbp-50h]
  bool v21; // [rsp+40h] [rbp-30h]
  bool v22; // [rsp+41h] [rbp-2Fh]
  LPVOID lpMem; // [rsp+48h] [rbp-28h] BYREF
  LPWSTR lpName; // [rsp+50h] [rbp-20h] BYREF
  unsigned __int64 v25; // [rsp+58h] [rbp-18h]
  DWORD cchName; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  lpMem = 0;
  token_information = wil::get_token_information_nothrow<_TOKEN_PRIVILEGES,0>(&lpMem, a1);
  v2 = lpMem;
  LastError = token_information;
  if ( token_information < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x29,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\shared\\RemoteUHProcessHostWrapper.cpp",
      (const char *)(unsigned int)token_information,
      v20);
    goto LABEL_29;
  }
  if ( !*(_DWORD *)lpMem )
  {
    WUTrace(0, 0, 4096, 5);
LABEL_28:
    LastError = 0;
    goto LABEL_29;
  }
  v4 = (unsigned int)(42 * *(_DWORD *)lpMem);
  lpMem = 0;
  v25 = v4;
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(
    &lpMem,
    0,
    (unsigned int)v4);
  v5 = lpMem;
  v22 = lpMem != 0;
  LOBYTE(lpMem) = lpMem != 0;
  if ( !(_BYTE)lpMem )
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)(unsigned int)((_DWORD)v5 + 52),
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\shared\\RemoteUHProcessHostWrapper.cpp",
      (const char *)0x8007000ELL,
      v20);
    goto LABEL_41;
  }
  v6 = 0;
  if ( !*v2 )
  {
LABEL_26:
    WUTrace(0, 0, 4096, 4);
    if ( v22 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v5);
    }
    goto LABEL_28;
  }
  while ( 1 )
  {
    v7 = 0;
    if ( !&v2[2 * v6 + 1 + v6] )
    {
      LastError = -2147024809;
      v17 = 21;
      goto LABEL_37;
    }
    cchName = 0;
    if ( LookupPrivilegeNameW(0, (PLUID)&v2[2 * v6 + 1 + v6], 0, &cchName) )
    {
      LastError = -2145112065;
      v17 = 26;
LABEL_37:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v17,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\shared\\RemoteUHProcessHostWrapper.cpp",
        (const char *)(unsigned int)LastError,
        v20);
      goto LABEL_38;
    }
    if ( GetLastError() != 122 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x1B,
                    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\shared\\RemoteUHProcessHostWrapper.cpp",
                    v8);
      goto LABEL_16;
    }
    lpName = 0;
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(
      &lpName,
      0,
      cchName);
    v9 = lpName;
    v21 = lpName != 0;
    if ( !lpName )
      break;
    if ( LookupPrivilegeNameW(0, (PLUID)&v2[2 * v6 + 1 + v6], lpName, &cchName) )
    {
      v7 = v9;
      goto LABEL_19;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x1F,
                  (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\shared\\RemoteUHProcessHostWrapper.cpp",
                  v10);
    if ( v21 )
    {
      v11 = GetProcessHeap();
      HeapFree(v11, 0, v9);
    }
LABEL_16:
    if ( LastError < 0 )
      goto LABEL_38;
LABEL_19:
    if ( v6 )
    {
      v20 = (int)v7;
      LastError = StringCchPrintfW((wchar_t *)v5, v25, L"%ws, %ws", v5);
      if ( LastError < 0 )
      {
        v12 = 64;
        goto LABEL_39;
      }
    }
    else
    {
      LastError = StringCchPrintfW((wchar_t *)v5, v25, L"%ws", v7);
      if ( LastError < 0 )
      {
        v12 = 59;
        goto LABEL_39;
      }
    }
    if ( v7 )
    {
      v13 = GetProcessHeap();
      HeapFree(v13, 0, v7);
    }
    if ( (unsigned int)++v6 >= *v2 )
      goto LABEL_26;
  }
  LastError = -2147024882;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1E,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\shared\\RemoteUHProcessHostWrapper.cpp",
    (const char *)0x8007000ELL,
    v20);
  if ( v21 )
  {
    v16 = GetProcessHeap();
    HeapFree(v16, 0, 0);
  }
LABEL_38:
  v12 = 56;
LABEL_39:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v12,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\shared\\RemoteUHProcessHostWrapper.cpp",
    (const char *)(unsigned int)LastError,
    v20);
  if ( v7 )
  {
    v18 = GetProcessHeap();
    HeapFree(v18, 0, v7);
  }
LABEL_41:
  if ( (_BYTE)lpMem )
  {
    v19 = GetProcessHeap();
    HeapFree(v19, 0, v5);
  }
LABEL_29:
  if ( v2 )
    operator delete(v2);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180034d04  mov     [rsp-28h+arg_8], rbx
0x180034d09  mov     [rsp-28h+arg_10], rsi
0x180034d0e  push    rbp
0x180034d0f  push    rdi
0x180034d10  push    r13
0x180034d12  push    r14
0x180034d14  push    r15
0x180034d16  mov     rbp, rsp
0x180034d19  sub     rsp, 70h
0x180034d1d  mov     rax, cs:__security_cookie
0x180034d24  xor     rax, rsp
0x180034d27  mov     [rbp+var_8], rax
0x180034d2b  mov     rdx, rcx
0x180034d2e  xor     r14d, r14d
0x180034d31  lea     rcx, [rbp+lpMem]
0x180034d35  mov     [rbp+lpMem], r14
0x180034d39  call    ??$get_token_information_nothrow@U_TOKEN_PRIVILEGES@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_PRIVILEGES@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_PRIVILEGES,0>(wistd::unique_ptr<_TOKEN_PRIVILEGES,wil::details::token_info_deleter> &,void *)
0x180034d3e  mov     rbx, [rbp+lpMem]
0x180034d42  mov     r15d, eax
0x180034d45  test    eax, eax
0x180034d47  jns     short loc_180034D65
0x180034d49  mov     rcx, [rbp+28h]; this
0x180034d4d  lea     r8, aCW1SSrcClientE_8; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x180034d54  mov     r9d, eax; char *
0x180034d57  lea     edx, [r14+29h]; void *
0x180034d5b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034d60  jmp     loc_180034F8A
0x180034d65  xor     edx, edx
0x180034d67  cmp     [rbx], r14d
0x180034d6a  jnz     short loc_180034D93
0x180034d6c  lea     rax, aUserTokenHasNo; "User token has no privileges."
0x180034d73  xor     ecx, ecx
0x180034d75  mov     [rsp+70h+var_48], rax
0x180034d7a  lea     r9d, [rdx+5]
0x180034d7e  mov     r8d, 1000h
0x180034d84  mov     [rsp+70h+var_50], r14
0x180034d89  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180034d8e  jmp     loc_180034F87
0x180034d93  imul    eax, [rbx], 2Ah ; '*'
0x180034d96  lea     rcx, [rbp+lpMem]
0x180034d9a  mov     [rbp+lpMem], r14
0x180034d9e  mov     r8d, eax
0x180034da1  mov     [rbp+var_18], rax
0x180034da5  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(wchar_t const *,unsigned __int64)
0x180034daa  mov     rsi, [rbp+lpMem]
0x180034dae  test    rsi, rsi
0x180034db1  setnz   al
0x180034db4  mov     [rbp+var_2F], al
0x180034db7  mov     byte ptr [rbp+lpMem], al
0x180034dba  test    rsi, rsi
0x180034dbd  jnz     short loc_180034DE0
0x180034dbf  mov     rcx, [rbp+28h]; this
0x180034dc3  lea     r8, aCW1SSrcClientE_8; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x180034dca  mov     r15d, 8007000Eh
0x180034dd0  lea     edx, [rsi+34h]; void *
0x180034dd3  mov     r9d, r15d; char *
0x180034dd6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034ddb  jmp     loc_18003505F
0x180034de0  mov     eax, [rbx]
0x180034de2  mov     r13d, r14d
0x180034de5  test    eax, eax
0x180034de7  jz      loc_180034F40
0x180034ded  mov     eax, r13d
0x180034df0  mov     rdi, r14
0x180034df3  lea     r15, ds:1[rax*2]
0x180034dfb  add     r15, rax
0x180034dfe  lea     r15, [rbx+r15*4]
0x180034e02  test    r15, r15
0x180034e05  jz      loc_180035010
0x180034e0b  lea     r9, [rbp+cchName]; cchName
0x180034e0f  mov     [rbp+cchName], r14d
0x180034e13  xor     r8d, r8d; lpName
0x180034e16  mov     rdx, r15; lpLuid
0x180034e19  xor     ecx, ecx; lpSystemName
0x180034e1b  call    cs:__imp_LookupPrivilegeNameW
0x180034e21  test    eax, eax
0x180034e23  jnz     loc_180035003
0x180034e29  call    cs:__imp_GetLastError
0x180034e2f  cmp     eax, 7Ah ; 'z'
0x180034e32  jz      short loc_180034E4E
0x180034e34  mov     rcx, [rbp+28h]; this
0x180034e38  lea     r8, aCW1SSrcClientE_8; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x180034e3f  mov     edx, 1Bh; void *
0x180034e44  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180034e49  mov     r15d, eax
0x180034e4c  jmp     short loc_180034EBE
0x180034e4e  mov     r8d, [rbp+cchName]
0x180034e52  lea     rcx, [rbp+lpName]
0x180034e56  xor     edx, edx
0x180034e58  mov     [rbp+lpName], r14
0x180034e5c  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(wchar_t const *,unsigned __int64)
0x180034e61  mov     r14, [rbp+lpName]
0x180034e65  test    r14, r14
0x180034e68  setnz   [rbp+var_30]
0x180034e6c  test    r14, r14
0x180034e6f  jz      loc_180034FC6
0x180034e75  lea     r9, [rbp+cchName]; cchName
0x180034e79  mov     r8, r14; lpName
0x180034e7c  mov     rdx, r15; lpLuid
0x180034e7f  xor     ecx, ecx; lpSystemName
0x180034e81  call    cs:__imp_LookupPrivilegeNameW
0x180034e87  test    eax, eax
0x180034e89  jnz     short loc_180034EC9
0x180034e8b  mov     rcx, [rbp+28h]; this
0x180034e8f  lea     r8, aCW1SSrcClientE_8; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x180034e96  lea     edx, [rax+1Fh]; void *
0x180034e99  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180034e9e  cmp     [rbp+var_30], 0
0x180034ea2  mov     r15d, eax
0x180034ea5  jz      short loc_180034EBB
0x180034ea7  call    cs:__imp_GetProcessHeap
0x180034ead  mov     r8, r14; lpMem
0x180034eb0  xor     edx, edx; dwFlags
0x180034eb2  mov     rcx, rax; hHeap
0x180034eb5  call    cs:__imp_HeapFree
0x180034ebb  xor     r14d, r14d
0x180034ebe  test    r15d, r15d
0x180034ec1  js      loc_18003502E
0x180034ec7  jmp     short loc_180034ECF
0x180034ec9  mov     rdi, r14
0x180034ecc  xor     r14d, r14d
0x180034ecf  mov     rdx, [rbp+var_18]; unsigned __int64
0x180034ed3  mov     rcx, rsi; Buffer
0x180034ed6  test    r13d, r13d
0x180034ed9  jnz     short loc_180034EFA
0x180034edb  mov     r9, rdi
0x180034ede  lea     r8, aWs; "%ws"
0x180034ee5  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180034eea  mov     r15d, eax
0x180034eed  test    eax, eax
0x180034eef  jns     short loc_180034F19
0x180034ef1  lea     edx, [r13+3Bh]
0x180034ef5  jmp     loc_180035033
0x180034efa  mov     r9, rsi
0x180034efd  mov     [rsp+70h+var_50], rdi
0x180034f02  lea     r8, aWsWs; "%ws, %ws"
0x180034f09  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180034f0e  mov     r15d, eax
0x180034f11  test    eax, eax
0x180034f13  js      loc_180034FBF
0x180034f19  test    rdi, rdi
0x180034f1c  jz      short loc_180034F32
0x180034f1e  call    cs:__imp_GetProcessHeap
0x180034f24  mov     r8, rdi; lpMem
0x180034f27  xor     edx, edx; dwFlags
0x180034f29  mov     rcx, rax; hHeap
0x180034f2c  call    cs:__imp_HeapFree
0x180034f32  mov     eax, [rbx]
0x180034f34  inc     r13d
0x180034f37  cmp     r13d, eax
0x180034f3a  jb      loc_180034DED
0x180034f40  mov     [rsp+70h+var_38], rsi
0x180034f45  xor     edx, edx
0x180034f47  mov     [rsp+70h+var_40], eax
0x180034f4b  xor     ecx, ecx
0x180034f4d  lea     rax, aUserTokenHasLu; "User token has %lu privileges: %ws"
0x180034f54  mov     r8d, 1000h
0x180034f5a  mov     [rsp+70h+var_48], rax
0x180034f5f  lea     r9d, [rdx+4]
0x180034f63  mov     [rsp+70h+var_50], r14
0x180034f68  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180034f6d  cmp     [rbp+var_2F], r14b
0x180034f71  jz      short loc_180034F87
0x180034f73  call    cs:__imp_GetProcessHeap
0x180034f79  mov     r8, rsi; lpMem
0x180034f7c  xor     edx, edx; dwFlags
0x180034f7e  mov     rcx, rax; hHeap
0x180034f81  call    cs:__imp_HeapFree
0x180034f87  mov     r15d, r14d
0x180034f8a  test    rbx, rbx
0x180034f8d  jz      short loc_180034F97
0x180034f8f  mov     rcx, rbx; Block
0x180034f92  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180034f97  mov     eax, r15d
0x180034f9a  mov     rcx, [rbp+var_8]
0x180034f9e  xor     rcx, rsp; StackCookie
0x180034fa1  call    __security_check_cookie
0x180034fa6  lea     r11, [rsp+70h+var_s0]
0x180034fab  mov     rbx, [r11+38h]
0x180034faf  mov     rsi, [r11+40h]
0x180034fb3  mov     rsp, r11
0x180034fb6  pop     r15
0x180034fb8  pop     r14
0x180034fba  pop     r13
0x180034fbc  pop     rdi
0x180034fbd  pop     rbp
0x180034fbe  retn
0x180034fbf  mov     edx, 40h ; '@'
0x180034fc4  jmp     short loc_180035033
0x180034fc6  mov     rcx, [rbp+28h]; this
0x180034fca  lea     r8, aCW1SSrcClientE_8; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x180034fd1  mov     r15d, 8007000Eh
0x180034fd7  mov     edx, 1Eh; void *
0x180034fdc  mov     r9d, r15d; char *
0x180034fdf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034fe4  xor     r14d, r14d
0x180034fe7  cmp     [rbp+var_30], r14b
0x180034feb  jz      short loc_18003502E
0x180034fed  call    cs:__imp_GetProcessHeap
0x180034ff3  xor     r8d, r8d; lpMem
0x180034ff6  xor     edx, edx; dwFlags
0x180034ff8  mov     rcx, rax; hHeap
0x180034ffb  call    cs:__imp_HeapFree
0x180035001  jmp     short loc_18003502E
0x180035003  mov     r15d, 80242FFFh
0x180035009  mov     edx, 1Ah
0x18003500e  jmp     short loc_18003501B
0x180035010  mov     r15d, 80070057h
0x180035016  mov     edx, 15h; void *
0x18003501b  mov     rcx, [rbp+28h]; this
0x18003501f  lea     r8, aCW1SSrcClientE_8; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x180035026  mov     r9d, r15d; char *
0x180035029  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003502e  mov     edx, 38h ; '8'; void *
0x180035033  mov     rcx, [rbp+28h]; this
0x180035037  lea     r8, aCW1SSrcClientE_8; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18003503e  mov     r9d, r15d; char *
0x180035041  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035046  test    rdi, rdi
0x180035049  jz      short loc_18003505F
0x18003504b  call    cs:__imp_GetProcessHeap
0x180035051  mov     r8, rdi; lpMem
0x180035054  xor     edx, edx; dwFlags
0x180035056  mov     rcx, rax; hHeap
0x180035059  call    cs:__imp_HeapFree
0x18003505f  cmp     byte ptr [rbp+lpMem], r14b
0x180035063  jz      loc_180034F8A
0x180035069  call    cs:__imp_GetProcessHeap
0x18003506f  mov     r8, rsi; lpMem
0x180035072  xor     edx, edx; dwFlags
0x180035074  mov     rcx, rax; hHeap
0x180035077  call    cs:__imp_HeapFree
0x18003507d  jmp     loc_180034F8A
```
