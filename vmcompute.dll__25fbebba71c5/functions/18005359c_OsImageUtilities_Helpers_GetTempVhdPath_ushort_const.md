# OsImageUtilities::Helpers::GetTempVhdPath(ushort const *)

- ea: `0x18005359c`
- end: `0x180053771`
- name: `?GetTempVhdPath@Helpers@OsImageUtilities@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z`
- size: `469`
- prototype: `_QWORD *__fastcall(_QWORD *Src, PCWSTR pszPath)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180034e10`
- `0x180034f50`

## callees

- `0x180002f50`
- `0x180006660`
- `0x18000d0ec`
- `0x18000d108`
- `0x18000ec20`
- `0x180014870`
- `0x18001ab14`
- `0x18005359c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800536e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800536e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18005368b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18005368b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005367d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005367d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800536d7`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800536d7`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x18005363d`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x18005363d`
- `api-ms-win-core-path-l1-1-0!PathCchFindExtension` at `0x1800535f4`
- `api-ms-win-core-path-l1-1-0!PathCchFindExtension` at `0x1800535f4`

## string_xrefs

- `0x180053735`: `onecore\vm\compute\dll\lib\storage\osimageutilities.cpp`
- `0x18005374a`: `onecore\vm\compute\dll\lib\storage\osimageutilities.cpp`
- `0x18005375f`: `onecore\vm\compute\dll\lib\storage\osimageutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall OsImageUtilities::Helpers::GetTempVhdPath(_QWORD *Src, PCWSTR pszPath)
{
  __int64 v4; // rdi
  __int64 v5; // rbx
  HRESULT Extension; // eax
  WCHAR *v7; // rcx
  HRESULT v8; // eax
  PWSTR *v9; // rax
  char v10; // bl
  const WCHAR *v11; // rcx
  const char *v12; // r9
  int v14; // [rsp+20h] [rbp-50h]
  PCWSTR ppszExt; // [rsp+40h] [rbp-30h] BYREF
  PWSTR pszPatha[2]; // [rsp+48h] [rbp-28h] BYREF
  __int128 v17; // [rsp+58h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  v4 = -1;
  v5 = -1;
  do
    ++v5;
  while ( pszPath[v5] );
  ppszExt = 0;
  Extension = PathCchFindExtension(pszPath, v5 + 1, &ppszExt);
  if ( Extension < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x61,
      (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\osimageutilities.cpp",
      (const char *)(unsigned int)Extension,
      v14);
  *(_OWORD *)pszPatha = 0;
  v17 = 0;
  std::wstring::_Construct<1,unsigned short const *>(pszPatha, pszPath, v5);
  v7 = (WCHAR *)pszPatha;
  if ( *((_QWORD *)&v17 + 1) > 7u )
    v7 = pszPatha[0];
  v8 = PathCchRemoveFileSpec(v7, v5 + 1);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x64,
      (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\osimageutilities.cpp",
      (const char *)(unsigned int)v8,
      v14);
  v9 = pszPatha;
  if ( *((_QWORD *)&v17 + 1) > 7u )
    v9 = (PWSTR *)pszPatha[0];
  do
    ++v4;
  while ( *((_WORD *)v9 + v4) );
  std::wstring::resize(pszPatha);
  GetCurrentThreadId();
  GetCurrentProcessId();
  Vml::FormatString(Src, (wchar_t *)L"%s\\%d.%d%s");
  v10 = 1;
  if ( Src[3] <= 7u )
    v11 = (const WCHAR *)Src;
  else
    v11 = (const WCHAR *)*Src;
  if ( DeleteFileW(v11) || GetLastError() == 2 )
    v10 = 0;
  if ( v10 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x68,
      (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\osimageutilities.cpp",
      v12);
  std::wstring::~wstring(pszPatha);
  return Src;
}

```

## disassembly

```asm
0x18005359c  mov     [rsp-28h+arg_10], rbx
0x1800535a1  mov     [rsp-28h+arg_18], rsi
0x1800535a6  push    rbp
0x1800535a7  push    rdi
0x1800535a8  push    r12
0x1800535aa  push    r14
0x1800535ac  push    r15
0x1800535ae  mov     rbp, rsp
0x1800535b1  sub     rsp, 70h
0x1800535b5  mov     rax, cs:__security_cookie
0x1800535bc  xor     rax, rsp
0x1800535bf  mov     [rbp+var_8], rax
0x1800535c3  mov     r14, rdx
0x1800535c6  mov     rsi, rcx
0x1800535c9  mov     [rbp+var_38], rcx
0x1800535cd  xor     r12d, r12d
0x1800535d0  mov     [rbp+var_40], r12d
0x1800535d4  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800535d8  mov     rbx, rdi
0x1800535db  inc     rbx
0x1800535de  cmp     [rdx+rbx*2], r12w
0x1800535e3  jnz     short loc_1800535DB
0x1800535e5  mov     [rbp+ppszExt], r12
0x1800535e9  lea     r8, [rbp+ppszExt]; ppszExt
0x1800535ed  lea     rdx, [rbx+1]; cchPath
0x1800535f1  mov     rcx, r14; pszPath
0x1800535f4  call    cs:__imp_PathCchFindExtension
0x1800535fb  nop     dword ptr [rax+rax+00h]
0x180053600  mov     rcx, [rbp+28h]; this
0x180053604  test    eax, eax
0x180053606  js      loc_180053747
0x18005360c  xorps   xmm0, xmm0
0x18005360f  movups  xmmword ptr [rbp+pszPath], xmm0
0x180053613  xorps   xmm1, xmm1
0x180053616  movdqu  [rbp+var_18], xmm1
0x18005361b  mov     r8, rbx
0x18005361e  mov     rdx, r14
0x180053621  lea     rcx, [rbp+pszPath]
0x180053625  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18005362a  nop
0x18005362b  lea     rcx, [rbp+pszPath]
0x18005362f  cmp     qword ptr [rbp+var_18+8], 7
0x180053634  cmova   rcx, [rbp+pszPath]; pszPath
0x180053639  lea     rdx, [rbx+1]; cchPath
0x18005363d  call    cs:__imp_PathCchRemoveFileSpec
0x180053644  nop     dword ptr [rax+rax+00h]
0x180053649  mov     rcx, [rbp+28h]; this
0x18005364d  test    eax, eax
0x18005364f  js      loc_18005375C
0x180053655  lea     rax, [rbp+pszPath]
0x180053659  cmp     qword ptr [rbp+var_18+8], 7
0x18005365e  cmova   rax, [rbp+pszPath]
0x180053663  inc     rdi
0x180053666  cmp     [rax+rdi*2], r12w
0x18005366b  jnz     short loc_180053663
0x18005366d  mov     rdx, rdi
0x180053670  lea     rcx, [rbp+pszPath]; Src
0x180053674  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180053679  mov     rdi, [rbp+ppszExt]
0x18005367d  call    cs:__imp_GetCurrentThreadId
0x180053684  nop     dword ptr [rax+rax+00h]
0x180053689  mov     ebx, eax
0x18005368b  call    cs:__imp_GetCurrentProcessId
0x180053692  nop     dword ptr [rax+rax+00h]
0x180053697  lea     r8, [rbp+pszPath]
0x18005369b  cmp     qword ptr [rbp+var_18+8], 7
0x1800536a0  cmova   r8, [rbp+pszPath]
0x1800536a5  mov     [rsp+70h+var_48], rdi
0x1800536aa  mov     [rsp+70h+var_50], ebx
0x1800536ae  mov     r9d, eax
0x1800536b1  lea     rdx, aSDDS; "%s\\%d.%d%s"
0x1800536b8  mov     rcx, rsi; Src
0x1800536bb  call    ?FormatString@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; Vml::FormatString(ushort const *,...)
0x1800536c0  mov     ebx, 1
0x1800536c5  mov     [rbp+var_40], ebx
0x1800536c8  cmp     qword ptr [rsi+18h], 7
0x1800536cd  jbe     short loc_1800536D4
0x1800536cf  mov     rcx, [rsi]
0x1800536d2  jmp     short loc_1800536D7
0x1800536d4  mov     rcx, rsi; lpFileName
0x1800536d7  call    cs:__imp_DeleteFileW
0x1800536de  nop     dword ptr [rax+rax+00h]
0x1800536e3  test    eax, eax
0x1800536e5  jnz     short loc_1800536F8
0x1800536e7  call    cs:__imp_GetLastError
0x1800536ee  nop     dword ptr [rax+rax+00h]
0x1800536f3  cmp     eax, 2
0x1800536f6  jnz     short loc_1800536FB
0x1800536f8  mov     bl, r12b
0x1800536fb  mov     rcx, [rbp+28h]; this
0x1800536ff  test    bl, bl
0x180053701  jnz     short loc_180053735
0x180053703  lea     rcx, [rbp+pszPath]
0x180053707  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005370c  mov     rax, rsi
0x18005370f  mov     rcx, [rbp+var_8]
0x180053713  xor     rcx, rsp; StackCookie
0x180053716  call    __security_check_cookie
0x18005371b  lea     r11, [rsp+70h+var_s0]
0x180053720  mov     rbx, [r11+40h]
0x180053724  mov     rsi, [r11+48h]
0x180053728  mov     rsp, r11
0x18005372b  pop     r15
0x18005372d  pop     r14
0x18005372f  pop     r12
0x180053731  pop     rdi
0x180053732  pop     rbp
0x180053733  retn
0x180053735  lea     r8, aOnecoreVmCompu_3; "onecore\\vm\\compute\\dll\\lib\\storage"...
0x18005373c  mov     edx, 68h ; 'h'; void *
0x180053741  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180053747  mov     r9d, eax; char *
0x18005374a  lea     r8, aOnecoreVmCompu_3; "onecore\\vm\\compute\\dll\\lib\\storage"...
0x180053751  mov     edx, 61h ; 'a'; void *
0x180053756  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005375c  mov     r9d, eax; char *
0x18005375f  lea     r8, aOnecoreVmCompu_3; "onecore\\vm\\compute\\dll\\lib\\storage"...
0x180053766  mov     edx, 64h ; 'd'; void *
0x18005376b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
