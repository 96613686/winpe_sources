# Vml::TemporaryPrivilege::TemporaryPrivilege(long)

- ea: `0x18002e454`
- end: `0x18002e5bd`
- name: `??0TemporaryPrivilege@Vml@@QEAA@J@Z`
- size: `361`
- prototype: `_QWORD(Vml::TemporaryPrivilege *__hidden this, int)`
- caller_count: `8`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180035d90`
- `0x1800362d0`
- `0x1800520b0`
- `0x18005340c`
- `0x180053778`
- `0x1800542e4`
- `0x18005c148`
- `0x18005d664`

## callees

- `0x180006148`
- `0x180008c34`
- `0x18000d0ec`
- `0x180022d10`
- `0x18002e454`
- `0x180030078`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e4c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e51e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e4c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e51e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002e493`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002e4f5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002e493`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002e4f5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002e4ac`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002e50e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002e4ac`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002e50e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002e52c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002e52c`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x18002e4dc`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x18002e4dc`

## string_xrefs

- `0x18002e544`: `onecore\vm\common\vml\VmSecurity.h`
- `0x18002e599`: `onecore\vm\common\vml\VmSecurity.h`
- `0x18002e5ab`: `onecore\vm\common\vml\VmSecurity.h`

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
0x18002e454  mov     [rsp+arg_8], rbx
0x18002e459  mov     [rsp+arg_0], rcx
0x18002e45e  push    rdi; unsigned int
0x18002e45f  sub     rsp, 20h
0x18002e463  mov     rbx, rcx
0x18002e466  lea     rdi, [rcx+8]
0x18002e46a  mov     qword ptr [rdi], 0
0x18002e471  mov     dword ptr [rcx+10h], 0
0x18002e478  mov     byte ptr [rcx+14h], 0
0x18002e47c  movsxd  rax, edx
0x18002e47f  mov     dword ptr [rsp+28h+arg_10], eax
0x18002e483  shr     rax, 20h
0x18002e487  mov     dword ptr [rsp+28h+arg_10+4], eax
0x18002e48b  mov     rax, [rsp+28h+arg_10]
0x18002e490  mov     [rcx], rax
0x18002e493  call    cs:__imp_GetCurrentThread
0x18002e49a  nop     dword ptr [rax+rax+00h]
0x18002e49f  mov     r9, rdi; TokenHandle
0x18002e4a2  xor     r8d, r8d; OpenAsSelf
0x18002e4a5  lea     edx, [r8+28h]; DesiredAccess
0x18002e4a9  mov     rcx, rax; ThreadHandle
0x18002e4ac  call    cs:__imp_OpenThreadToken
0x18002e4b3  nop     dword ptr [rax+rax+00h]
0x18002e4b8  test    eax, eax
0x18002e4ba  jnz     loc_18002E555
0x18002e4c0  call    cs:__imp_GetLastError
0x18002e4c7  nop     dword ptr [rax+rax+00h]
0x18002e4cc  cmp     eax, 3F0h
0x18002e4d1  jnz     loc_18002E591
0x18002e4d7  mov     ecx, 2; ImpersonationLevel
0x18002e4dc  call    cs:__imp_ImpersonateSelf
0x18002e4e3  nop     dword ptr [rax+rax+00h]
0x18002e4e8  mov     rcx, [rsp+28h]; this
0x18002e4ed  test    eax, eax
0x18002e4ef  jz      loc_18002E5AB
0x18002e4f5  call    cs:__imp_GetCurrentThread
0x18002e4fc  nop     dword ptr [rax+rax+00h]
0x18002e501  mov     r9, rdi; TokenHandle
0x18002e504  xor     r8d, r8d; OpenAsSelf
0x18002e507  lea     edx, [r8+28h]; DesiredAccess
0x18002e50b  mov     rcx, rax; ThreadHandle
0x18002e50e  call    cs:__imp_OpenThreadToken
0x18002e515  nop     dword ptr [rax+rax+00h]
0x18002e51a  test    eax, eax
0x18002e51c  jnz     short loc_18002E551
0x18002e51e  call    cs:__imp_GetLastError
0x18002e525  nop     dword ptr [rax+rax+00h]
0x18002e52a  mov     ebx, eax
0x18002e52c  call    cs:__imp_RevertToSelf
0x18002e533  nop     dword ptr [rax+rax+00h]
0x18002e538  mov     ecx, eax
0x18002e53a  call    ??$verify_bool@H$0A@@wil@@YA_NH@Z; wil::verify_bool<int,0>(int)
0x18002e53f  mov     rcx, [rsp+28h]; this
0x18002e544  lea     r8, aOnecoreVmCommo_13; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x18002e54b  test    al, al
0x18002e54d  jz      short loc_18002E586
0x18002e54f  jmp     short loc_18002E578
0x18002e551  mov     byte ptr [rbx+14h], 1
0x18002e555  mov     r8d, 1; int
0x18002e55b  mov     rdx, rbx; struct _LUID *
0x18002e55e  mov     rcx, rdi; this
0x18002e561  call    ?EnablePrivilege@VmAccessToken@Vml@@QEAAHAEBU_LUID@@H@Z; Vml::VmAccessToken::EnablePrivilege(_LUID const &,int)
0x18002e566  mov     [rbx+10h], eax
0x18002e569  mov     rax, rbx
0x18002e56c  mov     rbx, [rsp+28h+arg_8]
0x18002e571  add     rsp, 20h
0x18002e575  pop     rdi
0x18002e576  retn
0x18002e578  mov     r9d, ebx; char *
0x18002e57b  mov     edx, 1DDFh; void *
0x18002e580  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18002e586  mov     edx, 1DDEh; void *
0x18002e58b  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18002e591  mov     rcx, [rsp+28h]; this
0x18002e596  mov     r9d, eax; char *
0x18002e599  lea     r8, aOnecoreVmCommo_13; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x18002e5a0  mov     edx, 1DD7h; void *
0x18002e5a5  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18002e5ab  lea     r8, aOnecoreVmCommo_13; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x18002e5b2  mov     edx, 1DDAh; void *
0x18002e5b7  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
