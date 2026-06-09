# Vml::TemporaryPrivilege::TemporaryPrivilege(long)

- ea: `0x140087ef4`
- end: `0x14008804c`
- name: `??0TemporaryPrivilege@Vml@@QEAA@J@Z`
- size: `344`
- prototype: `__int64 __fastcall(struct _LUID *this, int)`
- caller_count: `7`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140041ad8`
- `0x140087820`
- `0x140087ba0`
- `0x140088438`
- `0x140089600`
- `0x1400aca18`
- `0x140215160`

## callees

- `0x140069590`
- `0x140080180`
- `0x140087500`
- `0x140087ef4`
- `0x1400c4154`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x140087f92`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x140087f92`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x140087ff0`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x140087ff0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140087f60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140087fe2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140087f60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140087fe2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140087f4c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140087fd2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140087f4c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140087fd2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140087f33`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140087fb9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140087f33`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140087fb9`

## string_xrefs

- `0x140087f7b`: `onecore\vm\common\vml\vmsecurity.h`
- `0x140087fa7`: `onecore\vm\common\vml\vmsecurity.h`
- `0x140088001`: `onecore\vm\common\vml\vmsecurity.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct _LUID *__fastcall Vml::TemporaryPrivilege::TemporaryPrivilege(struct _LUID *this, int a2)
{
  void **v3; // rdi
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  const char *v6; // r9
  HANDLE v7; // rax
  DWORD v8; // ebx
  const char *v9; // r9
  unsigned int v11; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v3 = (void **)&this[1];
  this[1] = 0;
  this[2].LowPart = 0;
  LOBYTE(this[2].HighPart) = 0;
  *this = (struct _LUID)a2;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0x28u, 0, v3) )
  {
    LastError = GetLastError();
    if ( LastError != 1008 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x1DD7,
        (unsigned int)"onecore\\vm\\common\\vml\\vmsecurity.h",
        (const char *)LastError,
        v11);
    if ( !ImpersonateSelf(SecurityImpersonation) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x1DDA,
        (unsigned int)"onecore\\vm\\common\\vml\\vmsecurity.h",
        v6);
    v7 = GetCurrentThread();
    if ( !OpenThreadToken(v7, 0x28u, 0, v3) )
    {
      v8 = GetLastError();
      if ( !RevertToSelf() )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x1DDE,
          (unsigned int)"onecore\\vm\\common\\vml\\vmsecurity.h",
          v9);
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x1DDF,
        (unsigned int)"onecore\\vm\\common\\vml\\vmsecurity.h",
        (const char *)v8,
        v11);
    }
    LOBYTE(this[2].HighPart) = 1;
  }
  this[2].LowPart = Vml::VmAccessToken::EnablePrivilege((Vml::VmAccessToken *)v3, this, 1);
  return this;
}

```

## disassembly

```asm
0x140087ef4  mov     [rsp+arg_8], rbx
0x140087ef9  mov     [rsp+arg_0], rcx
0x140087efe  push    rdi; unsigned int
0x140087eff  sub     rsp, 20h
0x140087f03  mov     rbx, rcx
0x140087f06  lea     rdi, [rcx+8]
0x140087f0a  mov     qword ptr [rdi], 0
0x140087f11  mov     dword ptr [rcx+10h], 0
0x140087f18  mov     byte ptr [rcx+14h], 0
0x140087f1c  movsxd  rax, edx
0x140087f1f  mov     dword ptr [rsp+28h+arg_10], eax
0x140087f23  shr     rax, 20h
0x140087f27  mov     dword ptr [rsp+28h+arg_10+4], eax
0x140087f2b  mov     rax, [rsp+28h+arg_10]
0x140087f30  mov     [rcx], rax
0x140087f33  call    cs:__imp_GetCurrentThread
0x140087f3a  nop     dword ptr [rax+rax+00h]
0x140087f3f  mov     r9, rdi; TokenHandle
0x140087f42  xor     r8d, r8d; OpenAsSelf
0x140087f45  lea     edx, [r8+28h]; DesiredAccess
0x140087f49  mov     rcx, rax; ThreadHandle
0x140087f4c  call    cs:__imp_OpenThreadToken
0x140087f53  nop     dword ptr [rax+rax+00h]
0x140087f58  test    eax, eax
0x140087f5a  jnz     loc_140088029
0x140087f60  call    cs:__imp_GetLastError
0x140087f67  nop     dword ptr [rax+rax+00h]
0x140087f6c  cmp     eax, 3F0h
0x140087f71  jz      short loc_140087F8D
0x140087f73  mov     rcx, [rsp+28h]; this
0x140087f78  mov     r9d, eax; char *
0x140087f7b  lea     r8, aOnecoreVmCommo_46; "onecore\\vm\\common\\vml\\vmsecurity.h"
0x140087f82  mov     edx, 1DD7h; void *
0x140087f87  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x140087f8d  mov     ecx, 2; ImpersonationLevel
0x140087f92  call    cs:__imp_ImpersonateSelf
0x140087f99  nop     dword ptr [rax+rax+00h]
0x140087f9e  mov     rcx, [rsp+28h]; this
0x140087fa3  test    eax, eax
0x140087fa5  jnz     short loc_140087FB9
0x140087fa7  lea     r8, aOnecoreVmCommo_46; "onecore\\vm\\common\\vml\\vmsecurity.h"
0x140087fae  mov     edx, 1DDAh; void *
0x140087fb3  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140087fb9  call    cs:__imp_GetCurrentThread
0x140087fc0  nop     dword ptr [rax+rax+00h]
0x140087fc5  mov     r9, rdi; TokenHandle
0x140087fc8  xor     r8d, r8d; OpenAsSelf
0x140087fcb  lea     edx, [r8+28h]; DesiredAccess
0x140087fcf  mov     rcx, rax; ThreadHandle
0x140087fd2  call    cs:__imp_OpenThreadToken
0x140087fd9  nop     dword ptr [rax+rax+00h]
0x140087fde  test    eax, eax
0x140087fe0  jnz     short loc_140088025
0x140087fe2  call    cs:__imp_GetLastError
0x140087fe9  nop     dword ptr [rax+rax+00h]
0x140087fee  mov     ebx, eax
0x140087ff0  call    cs:__imp_RevertToSelf
0x140087ff7  nop     dword ptr [rax+rax+00h]
0x140087ffc  mov     rcx, [rsp+28h]; this
0x140088001  lea     r8, aOnecoreVmCommo_46; "onecore\\vm\\common\\vml\\vmsecurity.h"
0x140088008  test    eax, eax
0x14008800a  jnz     short loc_140088017
0x14008800c  mov     edx, 1DDEh; void *
0x140088011  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x140088017  mov     r9d, ebx; char *
0x14008801a  mov     edx, 1DDFh; void *
0x14008801f  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x140088025  mov     byte ptr [rbx+14h], 1
0x140088029  mov     r8d, 1; int
0x14008802f  mov     rdx, rbx; struct _LUID *
0x140088032  mov     rcx, rdi; this
0x140088035  call    ?EnablePrivilege@VmAccessToken@Vml@@QEAAHAEBU_LUID@@H@Z; Vml::VmAccessToken::EnablePrivilege(_LUID const &,int)
0x14008803a  mov     [rbx+10h], eax
0x14008803d  mov     rax, rbx
0x140088040  mov     rbx, [rsp+28h+arg_8]
0x140088045  add     rsp, 20h
0x140088049  pop     rdi
0x14008804a  retn
```
