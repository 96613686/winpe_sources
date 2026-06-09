# CRevertToSelf::MakePrivileged(void)

- ea: `0x180147ee8`
- end: `0x180147fdd`
- name: `?MakePrivileged@CRevertToSelf@@AEAAXXZ`
- size: `245`
- prototype: `void(CRevertToSelf *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1801a40bc`

## callees

- `0x180038f08`
- `0x180147ee8`
- `0x1801480fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180147f24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180147f85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180147fa6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180147f24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180147f85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180147fa6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180147f04`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180147f04`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180147f1a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180147f1a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180147f79`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180147f79`

## string_xrefs

- `0x180147f8b`: `[UtilSecurity] RevertToSelf() failed. 0x%08x`
- `0x180147f3a`: `[UtilSecurity] OpenThreadToken() failed with error 0x%08x.`

## pseudocode

```c
void __fastcall CRevertToSelf::MakePrivileged(CRevertToSelf *this)
{
  HANDLE CurrentThread; // rax
  DWORD v3; // eax
  signed int v4; // ebx
  BOOL v5; // eax
  DWORD LastError; // eax
  signed int v7; // eax
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( ((*((_QWORD *)this + 1) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) != 0
    || (CurrentThread = GetCurrentThread(), OpenThreadToken(CurrentThread, 0xEu, 1, (PHANDLE)this + 1)) )
  {
    v5 = RevertToSelf();
    *(_DWORD *)this = v5;
    if ( !v5 )
    {
      LastError = GetLastError();
      SearchIndexerTrace::Error(
        (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\tquery\\\\fteutil\\\\secutil.cxx\"",
        (const wchar_t *)0x53,
        (unsigned int)L"[UtilSecurity] RevertToSelf() failed. 0x%08x",
        (const wchar_t *)LastError);
      v7 = GetLastError();
      if ( v7 > 0 )
        v7 = (unsigned __int16)v7 | 0x80070000;
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x54,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\fteutil\\secutil.cxx",
        (const char *)(unsigned int)v7,
        v8);
    }
  }
  else
  {
    v3 = GetLastError();
    v4 = v3;
    if ( v3 != 1008 )
    {
      SearchIndexerTrace::Error(
        (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\tquery\\\\fteutil\\\\secutil.cxx\"",
        (const wchar_t *)0x4A,
        (unsigned int)L"[UtilSecurity] OpenThreadToken() failed with error 0x%08x.",
        (const wchar_t *)v3);
      if ( v4 > 0 )
        v4 = (unsigned __int16)v4 | 0x80070000;
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4B,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\fteutil\\secutil.cxx",
        (const char *)(unsigned int)v4,
        v8);
    }
  }
}

```

## disassembly

```asm
0x180147ee8  mov     [rsp+arg_0], rbx
0x180147eed  push    rdi; int
0x180147eee  sub     rsp, 20h
0x180147ef2  mov     rax, [rcx+8]
0x180147ef6  mov     rbx, rcx
0x180147ef9  inc     rax
0x180147efc  test    rax, 0FFFFFFFFFFFFFFFEh
0x180147f02  jnz     short loc_180147F79
0x180147f04  call    cs:__imp_GetCurrentThread
0x180147f0a  mov     edx, 0Eh; DesiredAccess
0x180147f0f  lea     r9, [rbx+8]; TokenHandle
0x180147f13  mov     rcx, rax; ThreadHandle
0x180147f16  lea     r8d, [rdx-0Dh]; OpenAsSelf
0x180147f1a  call    cs:__imp_OpenThreadToken
0x180147f20  test    eax, eax
0x180147f22  jnz     short loc_180147F79
0x180147f24  call    cs:__imp_GetLastError
0x180147f2a  mov     ebx, eax
0x180147f2c  cmp     eax, 3F0h
0x180147f31  jz      loc_180147FD2
0x180147f37  mov     r9d, eax; wchar_t *
0x180147f3a  lea     r8, aUtilsecurityOp; "[UtilSecurity] OpenThreadToken() failed"...
0x180147f41  mov     edx, 4Ah ; 'J'; wchar_t *
0x180147f46  lea     rcx, aOnecoreuapBase_159; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x180147f4d  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x180147f52  test    ebx, ebx
0x180147f54  jle     short loc_180147F5F
0x180147f56  movzx   ebx, bx
0x180147f59  or      ebx, 80070000h
0x180147f5f  mov     rcx, [rsp+28h]; this
0x180147f64  lea     r8, aOnecoreuapBase_58; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x180147f6b  mov     r9d, ebx; char *
0x180147f6e  mov     edx, 4Bh ; 'K'; void *
0x180147f73  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180147f79  call    cs:__imp_RevertToSelf
0x180147f7f  mov     [rbx], eax
0x180147f81  test    eax, eax
0x180147f83  jnz     short loc_180147FD2
0x180147f85  call    cs:__imp_GetLastError
0x180147f8b  lea     r8, aUtilsecurityRe; "[UtilSecurity] RevertToSelf() failed. 0"...
0x180147f92  mov     edx, 53h ; 'S'; wchar_t *
0x180147f97  mov     r9d, eax; wchar_t *
0x180147f9a  lea     rcx, aOnecoreuapBase_159; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x180147fa1  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x180147fa6  call    cs:__imp_GetLastError
0x180147fac  test    eax, eax
0x180147fae  jle     short loc_180147FB8
0x180147fb0  movzx   eax, ax
0x180147fb3  or      eax, 80070000h
0x180147fb8  mov     rcx, [rsp+28h]; this
0x180147fbd  lea     r8, aOnecoreuapBase_58; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x180147fc4  mov     r9d, eax; char *
0x180147fc7  mov     edx, 54h ; 'T'; void *
0x180147fcc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180147fd2  mov     rbx, [rsp+28h+arg_0]
0x180147fd7  add     rsp, 20h
0x180147fdb  pop     rdi
0x180147fdc  retn
```
