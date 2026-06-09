# WpSecurity::AllocateVirtualMachineSid(_GUID const &)

- ea: `0x1400e91a8`
- end: `0x1400e931a`
- name: `?AllocateVirtualMachineSid@WpSecurity@@YAPEAXAEBU_GUID@@@Z`
- size: `370`
- prototype: `void *__fastcall(WpSecurity *__hidden this, const struct _GUID *)`
- caller_count: `7`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14003f93c`
- `0x140040fe8`
- `0x140041ad8`
- `0x140043c30`
- `0x1400b1df4`
- `0x1400b5024`
- `0x1400b9e34`

## callees

- `0x140080180`
- `0x1400c40e0`
- `0x1400e91a8`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x1400e9251`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x1400e9251`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x1400e91c8`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x1400e9214`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x1400e91c8`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x1400e9214`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1400e927b`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1400e9297`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1400e92b0`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1400e92ca`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1400e92e4`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1400e92fe`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1400e927b`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1400e9297`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1400e92b0`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1400e92ca`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1400e92e4`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1400e92fe`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400e91dd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400e91dd`

## string_xrefs

- `0x1400e922a`: `onecore\vm\inc\WpSecurity.h`
- `0x1400e9261`: `onecore\vm\inc\WpSecurity.h`
- `0x1400e91f6`: `onecore\vm\common\vml\VmMemory.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void *__fastcall WpSecurity::AllocateVirtualMachineSid(DWORD *this, const struct _GUID *a2)
{
  DWORD SidLengthRequired; // ebx
  HLOCAL v4; // rax
  const char *v5; // r9
  void *v6; // rdi
  const char *v7; // r9
  DWORD v8; // ebx
  DWORD v9; // ebx
  DWORD v10; // ebx
  DWORD v11; // ebx
  int v13; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  SidLengthRequired = GetSidLengthRequired(6u);
  v4 = LocalAlloc(0x40u, SidLengthRequired);
  v6 = v4;
  if ( !v4 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x355,
      (unsigned int)"onecore\\vm\\common\\vml\\VmMemory.h",
      v5);
  v13 = (int)v4;
  if ( GetSidLengthRequired(6u) > SidLengthRequired )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x10B,
      (unsigned int)"onecore\\vm\\inc\\WpSecurity.h",
      (const char *)0x8007007ALL,
      v13);
  if ( !InitializeSid(v6, (PSID_IDENTIFIER_AUTHORITY)&stru_140304F08, 6u) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x119,
      (unsigned int)"onecore\\vm\\inc\\WpSecurity.h",
      v7);
  *GetSidSubAuthority(v6, 0) = 83;
  *GetSidSubAuthority(v6, 1u) = 1;
  v8 = *this;
  *GetSidSubAuthority(v6, 2u) = v8;
  v9 = this[1];
  *GetSidSubAuthority(v6, 3u) = v9;
  v10 = this[2];
  *GetSidSubAuthority(v6, 4u) = v10;
  v11 = this[3];
  *GetSidSubAuthority(v6, 5u) = v11;
  return v6;
}

```

## disassembly

```asm
0x1400e91a8  push    rbx
0x1400e91aa  push    rsi
0x1400e91ab  push    rdi
0x1400e91ac  push    r14
0x1400e91ae  sub     rsp, 38h
0x1400e91b2  mov     r14, rcx
0x1400e91b5  xorps   xmm0, xmm0
0x1400e91b8  movups  xmmword ptr [rsp+58h+var_38], xmm0
0x1400e91bd  mov     qword ptr [rsp+58h+var_38], 0
0x1400e91c6  mov     cl, 6; nSubAuthorityCount
0x1400e91c8  call    cs:__imp_GetSidLengthRequired
0x1400e91cf  nop     dword ptr [rax+rax+00h]
0x1400e91d4  mov     ebx, eax
0x1400e91d6  mov     edx, eax; uBytes
0x1400e91d8  mov     ecx, 40h ; '@'; uFlags
0x1400e91dd  call    cs:__imp_LocalAlloc
0x1400e91e4  nop     dword ptr [rax+rax+00h]
0x1400e91e9  mov     rdi, rax
0x1400e91ec  test    rax, rax
0x1400e91ef  jnz     short loc_1400E9208
0x1400e91f1  mov     rcx, [rsp+58h]; this
0x1400e91f6  lea     r8, aOnecoreVmCommo_21; "onecore\\vm\\common\\vml\\VmMemory.h"
0x1400e91fd  mov     edx, 355h; void *
0x1400e9202  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400e9208  mov     qword ptr [rsp+58h+var_38], rdi; int
0x1400e920d  mov     rsi, [rsp+58h]
0x1400e9212  mov     cl, 6; nSubAuthorityCount
0x1400e9214  call    cs:__imp_GetSidLengthRequired
0x1400e921b  nop     dword ptr [rax+rax+00h]
0x1400e9220  cmp     eax, ebx
0x1400e9222  jbe     short loc_1400E923F
0x1400e9224  mov     r9d, 8007007Ah; char *
0x1400e922a  lea     r8, aOnecoreVmIncWp; "onecore\\vm\\inc\\WpSecurity.h"
0x1400e9231  mov     edx, 10Bh; void *
0x1400e9236  mov     rcx, rsi; this
0x1400e9239  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400e923f  mov     rbx, [rsp+58h]
0x1400e9244  mov     r8b, 6; nSubAuthorityCount
0x1400e9247  lea     rdx, stru_140304F08; pIdentifierAuthority
0x1400e924e  mov     rcx, rdi; Sid
0x1400e9251  call    cs:__imp_InitializeSid
0x1400e9258  nop     dword ptr [rax+rax+00h]
0x1400e925d  test    eax, eax
0x1400e925f  jnz     short loc_1400E9276
0x1400e9261  lea     r8, aOnecoreVmIncWp; "onecore\\vm\\inc\\WpSecurity.h"
0x1400e9268  mov     edx, 119h; void *
0x1400e926d  mov     rcx, rbx; this
0x1400e9270  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400e9276  xor     edx, edx; nSubAuthority
0x1400e9278  mov     rcx, rdi; pSid
0x1400e927b  call    cs:__imp_GetSidSubAuthority
0x1400e9282  nop     dword ptr [rax+rax+00h]
0x1400e9287  mov     dword ptr [rax], 53h ; 'S'
0x1400e928d  mov     ebx, 1
0x1400e9292  mov     edx, ebx; nSubAuthority
0x1400e9294  mov     rcx, rdi; pSid
0x1400e9297  call    cs:__imp_GetSidSubAuthority
0x1400e929e  nop     dword ptr [rax+rax+00h]
0x1400e92a3  mov     [rax], ebx
0x1400e92a5  mov     ebx, [r14]
0x1400e92a8  mov     edx, 2; nSubAuthority
0x1400e92ad  mov     rcx, rdi; pSid
0x1400e92b0  call    cs:__imp_GetSidSubAuthority
0x1400e92b7  nop     dword ptr [rax+rax+00h]
0x1400e92bc  mov     [rax], ebx
0x1400e92be  mov     ebx, [r14+4]
0x1400e92c2  mov     edx, 3; nSubAuthority
0x1400e92c7  mov     rcx, rdi; pSid
0x1400e92ca  call    cs:__imp_GetSidSubAuthority
0x1400e92d1  nop     dword ptr [rax+rax+00h]
0x1400e92d6  mov     [rax], ebx
0x1400e92d8  mov     ebx, [r14+8]
0x1400e92dc  mov     edx, 4; nSubAuthority
0x1400e92e1  mov     rcx, rdi; pSid
0x1400e92e4  call    cs:__imp_GetSidSubAuthority
0x1400e92eb  nop     dword ptr [rax+rax+00h]
0x1400e92f0  mov     [rax], ebx
0x1400e92f2  mov     ebx, [r14+0Ch]
0x1400e92f6  mov     edx, 5; nSubAuthority
0x1400e92fb  mov     rcx, rdi; pSid
0x1400e92fe  call    cs:__imp_GetSidSubAuthority
0x1400e9305  nop     dword ptr [rax+rax+00h]
0x1400e930a  mov     [rax], ebx
0x1400e930c  mov     rax, rdi
0x1400e930f  add     rsp, 38h
0x1400e9313  pop     r14
0x1400e9315  pop     rdi
0x1400e9316  pop     rsi
0x1400e9317  pop     rbx
0x1400e9318  retn
```
