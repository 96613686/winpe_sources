# WpSecurity::AllocateVirtualMachineGroupSid(void)

- ea: `0x180049ef0`
- end: `0x18004a00c`
- name: `?AllocateVirtualMachineGroupSid@WpSecurity@@YAPEAXXZ`
- size: `284`
- prototype: `void *__fastcall(WpSecurity *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004a688`

## callees

- `0x18000d0ec`
- `0x18000d108`
- `0x180049ef0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180049f85`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180049f9f`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180049f85`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180049f9f`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x180049f11`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x180049f4a`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x180049f11`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x180049f4a`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x180049f70`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x180049f70`
- `KERNELBASE!LocalAlloc` at `0x180049f26`
- `KERNELBASE!LocalAlloc` at `0x180049f26`

## string_xrefs

- `0x180049fc5`: `onecore\vm\inc\WpSecurity.h`
- `0x180049ff7`: `onecore\vm\inc\WpSecurity.h`
- `0x180049fdf`: `onecore\vm\common\vml\VmMemory.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void *__fastcall WpSecurity::AllocateVirtualMachineGroupSid(WpSecurity *this)
{
  DWORD SidLengthRequired; // edi
  HLOCAL v2; // rax
  const char *v3; // r9
  void *v4; // rbx
  const char *v5; // r9
  int v7; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  SidLengthRequired = GetSidLengthRequired(2u);
  v2 = LocalAlloc(0x40u, SidLengthRequired);
  v4 = v2;
  if ( !v2 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x355,
      (unsigned int)"onecore\\vm\\common\\vml\\VmMemory.h",
      v3);
  v7 = (int)v2;
  if ( GetSidLengthRequired(2u) > SidLengthRequired )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xAB,
      (unsigned int)"onecore\\vm\\inc\\WpSecurity.h",
      (const char *)0x8007007ALL,
      v7);
  if ( !InitializeSid(v4, (PSID_IDENTIFIER_AUTHORITY)&pIdentifierAuthority, 2u) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xB8,
      (unsigned int)"onecore\\vm\\inc\\WpSecurity.h",
      v5);
  *GetSidSubAuthority(v4, 0) = 83;
  *GetSidSubAuthority(v4, 1u) = 0;
  return v4;
}

```

## disassembly

```asm
0x180049ef0  mov     rax, rsp
0x180049ef3  mov     [rax+8], rbx
0x180049ef7  mov     [rax+10h], rsi
0x180049efb  push    rdi
0x180049efc  sub     rsp, 30h
0x180049f00  xorps   xmm0, xmm0
0x180049f03  movups  xmmword ptr [rax-18h], xmm0
0x180049f07  mov     qword ptr [rax-18h], 0
0x180049f0f  mov     cl, 2; nSubAuthorityCount
0x180049f11  call    cs:__imp_GetSidLengthRequired
0x180049f18  nop     dword ptr [rax+rax+00h]
0x180049f1d  mov     edi, eax
0x180049f1f  mov     edx, eax; uBytes
0x180049f21  mov     ecx, 40h ; '@'; uFlags
0x180049f26  call    cs:__imp_LocalAlloc
0x180049f2d  nop     dword ptr [rax+rax+00h]
0x180049f32  mov     rbx, rax
0x180049f35  test    rax, rax
0x180049f38  jz      loc_180049FDA
0x180049f3e  mov     qword ptr [rsp+38h+var_18], rax; int
0x180049f43  mov     rsi, [rsp+38h]
0x180049f48  mov     cl, 2; nSubAuthorityCount
0x180049f4a  call    cs:__imp_GetSidLengthRequired
0x180049f51  nop     dword ptr [rax+rax+00h]
0x180049f56  cmp     eax, edi
0x180049f58  ja      loc_180049FF1
0x180049f5e  mov     rdi, [rsp+38h]
0x180049f63  mov     r8b, 2; nSubAuthorityCount
0x180049f66  lea     rdx, pIdentifierAuthority; pIdentifierAuthority
0x180049f6d  mov     rcx, rbx; Sid
0x180049f70  call    cs:__imp_InitializeSid
0x180049f77  nop     dword ptr [rax+rax+00h]
0x180049f7c  test    eax, eax
0x180049f7e  jz      short loc_180049FC5
0x180049f80  xor     edx, edx; nSubAuthority
0x180049f82  mov     rcx, rbx; pSid
0x180049f85  call    cs:__imp_GetSidSubAuthority
0x180049f8c  nop     dword ptr [rax+rax+00h]
0x180049f91  mov     dword ptr [rax], 53h ; 'S'
0x180049f97  mov     edx, 1; nSubAuthority
0x180049f9c  mov     rcx, rbx; pSid
0x180049f9f  call    cs:__imp_GetSidSubAuthority
0x180049fa6  nop     dword ptr [rax+rax+00h]
0x180049fab  mov     dword ptr [rax], 0
0x180049fb1  mov     rax, rbx
0x180049fb4  mov     rbx, [rsp+38h+arg_0]
0x180049fb9  mov     rsi, [rsp+38h+arg_8]
0x180049fbe  add     rsp, 30h
0x180049fc2  pop     rdi
0x180049fc3  retn
0x180049fc5  lea     r8, aOnecoreVmIncWp; "onecore\\vm\\inc\\WpSecurity.h"
0x180049fcc  mov     edx, 0B8h; void *
0x180049fd1  mov     rcx, rdi; this
0x180049fd4  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180049fda  mov     rcx, [rsp+38h]; this
0x180049fdf  lea     r8, aOnecoreVmCommo_5; "onecore\\vm\\common\\vml\\VmMemory.h"
0x180049fe6  mov     edx, 355h; void *
0x180049feb  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180049ff1  mov     r9d, 8007007Ah; char *
0x180049ff7  lea     r8, aOnecoreVmIncWp; "onecore\\vm\\inc\\WpSecurity.h"
0x180049ffe  mov     edx, 0ABh; void *
0x18004a003  mov     rcx, rsi; this
0x18004a006  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
