# WpSecurity::AllocateVirtualMachineSid(_GUID const &)

- ea: `0x18004a014`
- end: `0x18004a192`
- name: `?AllocateVirtualMachineSid@WpSecurity@@YAPEAXAEBU_GUID@@@Z`
- size: `382`
- prototype: `void *__fastcall(WpSecurity *__hidden this, const struct _GUID *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004a43c`
- `0x18004aa68`

## callees

- `0x18000d0ec`
- `0x18000d108`
- `0x18004a014`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18004a0ac`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18004a0c8`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18004a0e1`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18004a0fb`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18004a115`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18004a12f`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18004a0ac`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18004a0c8`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18004a0e1`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18004a0fb`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18004a115`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18004a12f`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x18004a034`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x18004a06d`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x18004a034`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x18004a06d`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x18004a093`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x18004a093`
- `KERNELBASE!LocalAlloc` at `0x18004a049`
- `KERNELBASE!LocalAlloc` at `0x18004a049`

## string_xrefs

- `0x18004a14b`: `onecore\vm\inc\WpSecurity.h`
- `0x18004a17d`: `onecore\vm\inc\WpSecurity.h`
- `0x18004a165`: `onecore\vm\common\vml\VmMemory.h`

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
  if ( !InitializeSid(v6, (PSID_IDENTIFIER_AUTHORITY)&pIdentifierAuthority, 6u) )
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
0x18004a014  push    rbx
0x18004a016  push    rsi
0x18004a017  push    rdi
0x18004a018  push    r14
0x18004a01a  sub     rsp, 38h
0x18004a01e  mov     r14, rcx
0x18004a021  xorps   xmm0, xmm0
0x18004a024  movups  xmmword ptr [rsp+58h+var_38], xmm0
0x18004a029  mov     qword ptr [rsp+58h+var_38], 0
0x18004a032  mov     cl, 6; nSubAuthorityCount
0x18004a034  call    cs:__imp_GetSidLengthRequired
0x18004a03b  nop     dword ptr [rax+rax+00h]
0x18004a040  mov     ebx, eax
0x18004a042  mov     edx, eax; uBytes
0x18004a044  mov     ecx, 40h ; '@'; uFlags
0x18004a049  call    cs:__imp_LocalAlloc
0x18004a050  nop     dword ptr [rax+rax+00h]
0x18004a055  mov     rdi, rax
0x18004a058  test    rax, rax
0x18004a05b  jz      loc_18004A160
0x18004a061  mov     qword ptr [rsp+58h+var_38], rax; int
0x18004a066  mov     rsi, [rsp+58h]
0x18004a06b  mov     cl, 6; nSubAuthorityCount
0x18004a06d  call    cs:__imp_GetSidLengthRequired
0x18004a074  nop     dword ptr [rax+rax+00h]
0x18004a079  cmp     eax, ebx
0x18004a07b  ja      loc_18004A177
0x18004a081  mov     rbx, [rsp+58h]
0x18004a086  mov     r8b, 6; nSubAuthorityCount
0x18004a089  lea     rdx, pIdentifierAuthority; pIdentifierAuthority
0x18004a090  mov     rcx, rdi; Sid
0x18004a093  call    cs:__imp_InitializeSid
0x18004a09a  nop     dword ptr [rax+rax+00h]
0x18004a09f  test    eax, eax
0x18004a0a1  jz      loc_18004A14B
0x18004a0a7  xor     edx, edx; nSubAuthority
0x18004a0a9  mov     rcx, rdi; pSid
0x18004a0ac  call    cs:__imp_GetSidSubAuthority
0x18004a0b3  nop     dword ptr [rax+rax+00h]
0x18004a0b8  mov     dword ptr [rax], 53h ; 'S'
0x18004a0be  mov     ebx, 1
0x18004a0c3  mov     edx, ebx; nSubAuthority
0x18004a0c5  mov     rcx, rdi; pSid
0x18004a0c8  call    cs:__imp_GetSidSubAuthority
0x18004a0cf  nop     dword ptr [rax+rax+00h]
0x18004a0d4  mov     [rax], ebx
0x18004a0d6  mov     ebx, [r14]
0x18004a0d9  mov     edx, 2; nSubAuthority
0x18004a0de  mov     rcx, rdi; pSid
0x18004a0e1  call    cs:__imp_GetSidSubAuthority
0x18004a0e8  nop     dword ptr [rax+rax+00h]
0x18004a0ed  mov     [rax], ebx
0x18004a0ef  mov     ebx, [r14+4]
0x18004a0f3  mov     edx, 3; nSubAuthority
0x18004a0f8  mov     rcx, rdi; pSid
0x18004a0fb  call    cs:__imp_GetSidSubAuthority
0x18004a102  nop     dword ptr [rax+rax+00h]
0x18004a107  mov     [rax], ebx
0x18004a109  mov     ebx, [r14+8]
0x18004a10d  mov     edx, 4; nSubAuthority
0x18004a112  mov     rcx, rdi; pSid
0x18004a115  call    cs:__imp_GetSidSubAuthority
0x18004a11c  nop     dword ptr [rax+rax+00h]
0x18004a121  mov     [rax], ebx
0x18004a123  mov     ebx, [r14+0Ch]
0x18004a127  mov     edx, 5; nSubAuthority
0x18004a12c  mov     rcx, rdi; pSid
0x18004a12f  call    cs:__imp_GetSidSubAuthority
0x18004a136  nop     dword ptr [rax+rax+00h]
0x18004a13b  mov     [rax], ebx
0x18004a13d  mov     rax, rdi
0x18004a140  add     rsp, 38h
0x18004a144  pop     r14
0x18004a146  pop     rdi
0x18004a147  pop     rsi
0x18004a148  pop     rbx
0x18004a149  retn
0x18004a14b  lea     r8, aOnecoreVmIncWp; "onecore\\vm\\inc\\WpSecurity.h"
0x18004a152  mov     edx, 119h; void *
0x18004a157  mov     rcx, rbx; this
0x18004a15a  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18004a160  mov     rcx, [rsp+58h]; this
0x18004a165  lea     r8, aOnecoreVmCommo_5; "onecore\\vm\\common\\vml\\VmMemory.h"
0x18004a16c  mov     edx, 355h; void *
0x18004a171  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18004a177  mov     r9d, 8007007Ah; char *
0x18004a17d  lea     r8, aOnecoreVmIncWp; "onecore\\vm\\inc\\WpSecurity.h"
0x18004a184  mov     edx, 10Bh; void *
0x18004a189  mov     rcx, rsi; this
0x18004a18c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
