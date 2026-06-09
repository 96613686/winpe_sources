# Vml::TemporaryPrivilege::TemporaryPrivilege(long)

- ea: `0x140041b14`
- end: `0x140041c48`
- name: `??0TemporaryPrivilege@Vml@@QEAA@J@Z`
- size: `308`
- prototype: `_QWORD(Vml::TemporaryPrivilege *__hidden this, int)`
- caller_count: `5`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14004218c`
- `0x14008c5c0`
- `0x1400a63d4`
- `0x1400d3588`
- `0x1400d3e5c`

## callees

- `0x1400083b0`
- `0x140009f8c`
- `0x14000ddac`
- `0x1400341ac`
- `0x140041b14`
- `0x1400420e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140041b70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140041bb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140041b70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140041bb6`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x140041b86`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x140041b86`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x140041bbe`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x140041bbe`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140041b66`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140041bac`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140041b66`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140041bac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140041b53`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140041b99`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140041b53`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140041b99`

## string_xrefs

- `0x140041bd0`: `onecore\vm\common\vml\VmSecurity.h`
- `0x140041c24`: `onecore\vm\common\vml\VmSecurity.h`
- `0x140041c36`: `onecore\vm\common\vml\VmSecurity.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
Vml::TemporaryPrivilege *__fastcall Vml::TemporaryPrivilege::TemporaryPrivilege(Vml::TemporaryPrivilege *this, int a2)
{
  void **v3; // rdi
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  const char *v6; // r9
  HANDLE v7; // rax
  DWORD v8; // ebx
  unsigned int v9; // eax
  const char *v10; // r9
  unsigned int v12; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v3 = (void **)((char *)this + 8);
  *((_QWORD *)this + 1) = 0;
  *((_DWORD *)this + 4) = 0;
  *((_BYTE *)this + 20) = 0;
  *(_QWORD *)this = a2;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0x28u, 0, v3) )
  {
    LastError = GetLastError();
    if ( LastError != 1008 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x1DD7,
        (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
        (const char *)LastError,
        v12);
    if ( !ImpersonateSelf(SecurityImpersonation) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x1DDA,
        (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
        v6);
    v7 = GetCurrentThread();
    if ( !OpenThreadToken(v7, 0x28u, 0, v3) )
    {
      v8 = GetLastError();
      v9 = RevertToSelf();
      if ( (unsigned __int8)wil::verify_bool<int,0>(v9) )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x1DDF,
          (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
          (const char *)v8,
          v12);
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x1DDE,
        (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
        v10);
    }
    *((_BYTE *)this + 20) = 1;
  }
  *((_DWORD *)this + 4) = Vml::VmAccessToken::EnablePrivilege((Vml::VmAccessToken *)v3, (const struct _LUID *)this, 1);
  return this;
}

```

## disassembly

```asm
0x140041b14  mov     [rsp+arg_8], rbx
0x140041b19  mov     [rsp+arg_0], rcx
0x140041b1e  push    rdi; unsigned int
0x140041b1f  sub     rsp, 20h
0x140041b23  mov     rbx, rcx
0x140041b26  lea     rdi, [rcx+8]
0x140041b2a  mov     qword ptr [rdi], 0
0x140041b31  mov     dword ptr [rcx+10h], 0
0x140041b38  mov     byte ptr [rcx+14h], 0
0x140041b3c  movsxd  rax, edx
0x140041b3f  mov     dword ptr [rsp+28h+arg_10], eax
0x140041b43  shr     rax, 20h
0x140041b47  mov     dword ptr [rsp+28h+arg_10+4], eax
0x140041b4b  mov     rax, [rsp+28h+arg_10]
0x140041b50  mov     [rcx], rax
0x140041b53  call    cs:__imp_GetCurrentThread
0x140041b59  mov     r9, rdi; TokenHandle
0x140041b5c  xor     r8d, r8d; OpenAsSelf
0x140041b5f  lea     edx, [r8+28h]; DesiredAccess
0x140041b63  mov     rcx, rax; ThreadHandle
0x140041b66  call    cs:__imp_OpenThreadToken
0x140041b6c  test    eax, eax
0x140041b6e  jnz     short loc_140041BE1
0x140041b70  call    cs:__imp_GetLastError
0x140041b76  cmp     eax, 3F0h
0x140041b7b  jnz     loc_140041C1C
0x140041b81  mov     ecx, 2; ImpersonationLevel
0x140041b86  call    cs:__imp_ImpersonateSelf
0x140041b8c  mov     rcx, [rsp+28h]; this
0x140041b91  test    eax, eax
0x140041b93  jz      loc_140041C36
0x140041b99  call    cs:__imp_GetCurrentThread
0x140041b9f  mov     r9, rdi; TokenHandle
0x140041ba2  xor     r8d, r8d; OpenAsSelf
0x140041ba5  lea     edx, [r8+28h]; DesiredAccess
0x140041ba9  mov     rcx, rax; ThreadHandle
0x140041bac  call    cs:__imp_OpenThreadToken
0x140041bb2  test    eax, eax
0x140041bb4  jnz     short loc_140041BDD
0x140041bb6  call    cs:__imp_GetLastError
0x140041bbc  mov     ebx, eax
0x140041bbe  call    cs:__imp_RevertToSelf
0x140041bc4  mov     ecx, eax
0x140041bc6  call    ??$verify_bool@H$0A@@wil@@YA_NH@Z; wil::verify_bool<int,0>(int)
0x140041bcb  mov     rcx, [rsp+28h]; this
0x140041bd0  lea     r8, aOnecoreVmCommo_12; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x140041bd7  test    al, al
0x140041bd9  jz      short loc_140041C11
0x140041bdb  jmp     short loc_140041C03
0x140041bdd  mov     byte ptr [rbx+14h], 1
0x140041be1  mov     r8d, 1; int
0x140041be7  mov     rdx, rbx; struct _LUID *
0x140041bea  mov     rcx, rdi; this
0x140041bed  call    ?EnablePrivilege@VmAccessToken@Vml@@QEAAHAEBU_LUID@@H@Z; Vml::VmAccessToken::EnablePrivilege(_LUID const &,int)
0x140041bf2  mov     [rbx+10h], eax
0x140041bf5  mov     rax, rbx
0x140041bf8  mov     rbx, [rsp+28h+arg_8]
0x140041bfd  add     rsp, 20h
0x140041c01  pop     rdi
0x140041c02  retn
0x140041c03  mov     r9d, ebx; char *
0x140041c06  mov     edx, 1DDFh; void *
0x140041c0b  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x140041c11  mov     edx, 1DDEh; void *
0x140041c16  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x140041c1c  mov     rcx, [rsp+28h]; this
0x140041c21  mov     r9d, eax; char *
0x140041c24  lea     r8, aOnecoreVmCommo_12; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x140041c2b  mov     edx, 1DD7h; void *
0x140041c30  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x140041c36  lea     r8, aOnecoreVmCommo_12; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x140041c3d  mov     edx, 1DDAh; void *
0x140041c42  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
