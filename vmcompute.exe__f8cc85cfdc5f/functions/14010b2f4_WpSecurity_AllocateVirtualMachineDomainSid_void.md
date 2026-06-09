# WpSecurity::AllocateVirtualMachineDomainSid(void)

- ea: `0x14010b2f4`
- end: `0x14010b3ec`
- name: `?AllocateVirtualMachineDomainSid@WpSecurity@@YAPEAXXZ`
- size: `248`
- prototype: `void *__fastcall(WpSecurity *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400bed64`

## callees

- `0x140080180`
- `0x1400c40e0`
- `0x14010b2f4`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x14010b39e`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x14010b39e`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x14010b315`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x14010b361`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x14010b315`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x14010b361`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x14010b3c6`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x14010b3c6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14010b32a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14010b32a`

## string_xrefs

- `0x14010b377`: `onecore\vm\inc\WpSecurity.h`
- `0x14010b3ae`: `onecore\vm\inc\WpSecurity.h`
- `0x14010b343`: `onecore\vm\common\vml\VmMemory.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void *__fastcall WpSecurity::AllocateVirtualMachineDomainSid(WpSecurity *this)
{
  DWORD SidLengthRequired; // edi
  HLOCAL v2; // rax
  const char *v3; // r9
  void *v4; // rbx
  const char *v5; // r9
  int v7; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  SidLengthRequired = GetSidLengthRequired(1u);
  v2 = LocalAlloc(0x40u, SidLengthRequired);
  v4 = v2;
  if ( !v2 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x355,
      (unsigned int)"onecore\\vm\\common\\vml\\VmMemory.h",
      v3);
  v7 = (int)v2;
  if ( GetSidLengthRequired(1u) > SidLengthRequired )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x52,
      (unsigned int)"onecore\\vm\\inc\\WpSecurity.h",
      (const char *)0x8007007ALL,
      v7);
  if ( !InitializeSid(v4, (PSID_IDENTIFIER_AUTHORITY)&pIdentifierAuthority, 1u) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x5F,
      (unsigned int)"onecore\\vm\\inc\\WpSecurity.h",
      v5);
  *GetSidSubAuthority(v4, 0) = 83;
  return v4;
}

```

## disassembly

```asm
0x14010b2f4  mov     rax, rsp
0x14010b2f7  mov     [rax+8], rbx
0x14010b2fb  mov     [rax+10h], rsi
0x14010b2ff  push    rdi
0x14010b300  sub     rsp, 30h
0x14010b304  xorps   xmm0, xmm0
0x14010b307  movups  xmmword ptr [rax-18h], xmm0
0x14010b30b  mov     qword ptr [rax-18h], 0
0x14010b313  mov     cl, 1; nSubAuthorityCount
0x14010b315  call    cs:__imp_GetSidLengthRequired
0x14010b31c  nop     dword ptr [rax+rax+00h]
0x14010b321  mov     edi, eax
0x14010b323  mov     edx, eax; uBytes
0x14010b325  mov     ecx, 40h ; '@'; uFlags
0x14010b32a  call    cs:__imp_LocalAlloc
0x14010b331  nop     dword ptr [rax+rax+00h]
0x14010b336  mov     rbx, rax
0x14010b339  test    rax, rax
0x14010b33c  jnz     short loc_14010B355
0x14010b33e  mov     rcx, [rsp+38h]; this
0x14010b343  lea     r8, aOnecoreVmCommo_21; "onecore\\vm\\common\\vml\\VmMemory.h"
0x14010b34a  mov     edx, 355h; void *
0x14010b34f  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14010b355  mov     qword ptr [rsp+38h+var_18], rbx; int
0x14010b35a  mov     rsi, [rsp+38h]
0x14010b35f  mov     cl, 1; nSubAuthorityCount
0x14010b361  call    cs:__imp_GetSidLengthRequired
0x14010b368  nop     dword ptr [rax+rax+00h]
0x14010b36d  cmp     eax, edi
0x14010b36f  jbe     short loc_14010B38C
0x14010b371  mov     r9d, 8007007Ah; char *
0x14010b377  lea     r8, aOnecoreVmIncWp; "onecore\\vm\\inc\\WpSecurity.h"
0x14010b37e  mov     edx, 52h ; 'R'; void *
0x14010b383  mov     rcx, rsi; this
0x14010b386  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14010b38c  mov     rdi, [rsp+38h]
0x14010b391  mov     r8b, 1; nSubAuthorityCount
0x14010b394  lea     rdx, pIdentifierAuthority; pIdentifierAuthority
0x14010b39b  mov     rcx, rbx; Sid
0x14010b39e  call    cs:__imp_InitializeSid
0x14010b3a5  nop     dword ptr [rax+rax+00h]
0x14010b3aa  test    eax, eax
0x14010b3ac  jnz     short loc_14010B3C1
0x14010b3ae  lea     r8, aOnecoreVmIncWp; "onecore\\vm\\inc\\WpSecurity.h"
0x14010b3b5  lea     edx, [rax+5Fh]; void *
0x14010b3b8  mov     rcx, rdi; this
0x14010b3bb  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14010b3c1  xor     edx, edx; nSubAuthority
0x14010b3c3  mov     rcx, rbx; pSid
0x14010b3c6  call    cs:__imp_GetSidSubAuthority
0x14010b3cd  nop     dword ptr [rax+rax+00h]
0x14010b3d2  mov     dword ptr [rax], 53h ; 'S'
0x14010b3d8  mov     rax, rbx
0x14010b3db  mov     rbx, [rsp+38h+arg_0]
0x14010b3e0  mov     rsi, [rsp+38h+arg_8]
0x14010b3e5  add     rsp, 30h
0x14010b3e9  pop     rdi
0x14010b3ea  retn
```
