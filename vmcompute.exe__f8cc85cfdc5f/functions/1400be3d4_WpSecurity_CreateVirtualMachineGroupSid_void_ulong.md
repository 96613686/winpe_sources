# WpSecurity::CreateVirtualMachineGroupSid(void *,ulong *)

- ea: `0x1400be3d4`
- end: `0x1400be4d3`
- name: `?CreateVirtualMachineGroupSid@WpSecurity@@YAXPEAXPEAK@Z`
- size: `255`
- prototype: `void __fastcall(PSID pSid, void *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400be354`

## callees

- `0x140080180`
- `0x1400be3d4`
- `0x1400c40e0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x1400be44d`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x1400be44d`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x1400be403`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x1400be403`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1400be479`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1400be493`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1400be479`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1400be493`

## string_xrefs

- `0x1400be423`: `onecore\vm\inc\WpSecurity.h`
- `0x1400be462`: `onecore\vm\inc\WpSecurity.h`
- `0x1400be4bb`: `onecore\vm\inc\WpSecurity.h`

## pseudocode

```c
void __fastcall WpSecurity::CreateVirtualMachineGroupSid(PSID pSid, DWORD *a2, unsigned int *a3)
{
  DWORD v5; // esi
  DWORD SidLengthRequired; // eax
  const char *v7; // r9
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !a2 || (v5 = *a2) != 0 && !pSid )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xA1,
      (unsigned int)"onecore\\vm\\inc\\WpSecurity.h",
      (const char *)0x80070057LL,
      v8);
  SidLengthRequired = GetSidLengthRequired(2u);
  *a2 = SidLengthRequired;
  if ( SidLengthRequired <= v5 )
  {
    if ( pSid )
    {
      if ( !InitializeSid(pSid, (PSID_IDENTIFIER_AUTHORITY)&pIdentifierAuthority, 2u) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0xB8,
          (unsigned int)"onecore\\vm\\inc\\WpSecurity.h",
          v7);
      *GetSidSubAuthority(pSid, 0) = 83;
      *GetSidSubAuthority(pSid, 1u) = 0;
    }
  }
  else if ( pSid )
  {
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xAB,
      (unsigned int)"onecore\\vm\\inc\\WpSecurity.h",
      (const char *)0x8007007ALL,
      v8);
  }
}

```

## disassembly

```asm
0x1400be3d4  mov     [rsp+arg_0], rbx
0x1400be3d9  mov     [rsp+arg_8], rsi
0x1400be3de  push    rdi; int
0x1400be3df  sub     rsp, 20h
0x1400be3e3  mov     rdi, rdx
0x1400be3e6  mov     rbx, rcx
0x1400be3e9  test    rdx, rdx
0x1400be3ec  jz      loc_1400BE4B6
0x1400be3f2  mov     esi, [rdx]
0x1400be3f4  test    esi, esi
0x1400be3f6  jz      short loc_1400BE401
0x1400be3f8  test    rcx, rcx
0x1400be3fb  jz      loc_1400BE4B6
0x1400be401  mov     cl, 2; nSubAuthorityCount
0x1400be403  call    cs:__imp_GetSidLengthRequired
0x1400be40a  nop     dword ptr [rax+rax+00h]
0x1400be40f  mov     [rdi], eax
0x1400be411  cmp     eax, esi
0x1400be413  jbe     short loc_1400BE43B
0x1400be415  test    rbx, rbx
0x1400be418  jz      loc_1400BE4A5
0x1400be41e  mov     rcx, [rsp+28h]; this
0x1400be423  lea     r8, aOnecoreVmIncWp; "onecore\\vm\\inc\\WpSecurity.h"
0x1400be42a  mov     r9d, 8007007Ah; char *
0x1400be430  mov     edx, 0ABh; void *
0x1400be435  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400be43b  test    rbx, rbx
0x1400be43e  jz      short loc_1400BE4A5
0x1400be440  mov     r8b, 2; nSubAuthorityCount
0x1400be443  lea     rdx, pIdentifierAuthority; pIdentifierAuthority
0x1400be44a  mov     rcx, rbx; Sid
0x1400be44d  call    cs:__imp_InitializeSid
0x1400be454  nop     dword ptr [rax+rax+00h]
0x1400be459  test    eax, eax
0x1400be45b  jnz     short loc_1400BE474
0x1400be45d  mov     rcx, [rsp+28h]; this
0x1400be462  lea     r8, aOnecoreVmIncWp; "onecore\\vm\\inc\\WpSecurity.h"
0x1400be469  mov     edx, 0B8h; void *
0x1400be46e  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400be474  xor     edx, edx; nSubAuthority
0x1400be476  mov     rcx, rbx; pSid
0x1400be479  call    cs:__imp_GetSidSubAuthority
0x1400be480  nop     dword ptr [rax+rax+00h]
0x1400be485  mov     edx, 1; nSubAuthority
0x1400be48a  mov     rcx, rbx; pSid
0x1400be48d  mov     dword ptr [rax], 53h ; 'S'
0x1400be493  call    cs:__imp_GetSidSubAuthority
0x1400be49a  nop     dword ptr [rax+rax+00h]
0x1400be49f  mov     dword ptr [rax], 0
0x1400be4a5  mov     rbx, [rsp+28h+arg_0]
0x1400be4aa  mov     rsi, [rsp+28h+arg_8]
0x1400be4af  add     rsp, 20h
0x1400be4b3  pop     rdi
0x1400be4b4  retn
0x1400be4b6  mov     rcx, [rsp+28h]; this
0x1400be4bb  lea     r8, aOnecoreVmIncWp; "onecore\\vm\\inc\\WpSecurity.h"
0x1400be4c2  mov     r9d, 80070057h; char *
0x1400be4c8  mov     edx, 0A1h; void *
0x1400be4cd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
