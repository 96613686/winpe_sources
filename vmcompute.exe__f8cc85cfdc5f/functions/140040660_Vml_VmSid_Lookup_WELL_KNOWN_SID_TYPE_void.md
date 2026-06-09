# Vml::VmSid::Lookup(WELL_KNOWN_SID_TYPE,void *)

- ea: `0x140040660`
- end: `0x140040741`
- name: `?Lookup@VmSid@Vml@@QEAAXW4WELL_KNOWN_SID_TYPE@@PEAX@Z`
- size: `225`
- prototype: `void __fastcall(Vml::VmSid *__hidden this, WELL_KNOWN_SID_TYPE WellKnownSidType, PSID DomainSid)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400412a0`

## callees

- `0x140040660`
- `0x140080180`
- `0x1400bc99c`
- `0x1401332f0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CopySid` at `0x140040708`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x140040708`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x14004069e`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x14004069e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400406ce`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400406ce`

## string_xrefs

- `0x1400406b6`: `onecore\vm\common\vml\VmSecurity.h`
- `0x1400406ea`: `onecore\vm\common\vml\VmSecurity.h`

## pseudocode

```c
void __fastcall Vml::VmSid::Lookup(Vml::VmSid *this, WELL_KNOWN_SID_TYPE WellKnownSidType, PSID DomainSid)
{
  const char *v4; // r9
  HLOCAL v5; // rax
  const char *v6; // r9
  void *v7; // rbx
  DWORD cbSid[4]; // [rsp+20h] [rbp-78h] BYREF
  _BYTE pSid[80]; // [rsp+30h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  cbSid[0] = 68;
  if ( !CreateWellKnownSid(WellKnownSidType, DomainSid, pSid, cbSid) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1469,
      (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
      v4);
  v5 = LocalAlloc(0, cbSid[0]);
  v7 = v5;
  if ( !v5 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x146F,
      (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
      v6);
  CopySid(cbSid[0], v5, pSid);
  Vml::VmSid::Reset(this, v7);
}

```

## disassembly

```asm
0x140040660  mov     [rsp+arg_18], rbx
0x140040665  push    rdi
0x140040666  sub     rsp, 90h
0x14004066d  mov     rax, cs:__security_cookie
0x140040674  xor     rax, rsp
0x140040677  mov     [rsp+98h+var_18], rax
0x14004067f  mov     r10, r8
0x140040682  mov     [rsp+98h+cbSid], 44h ; 'D'
0x14004068a  mov     eax, edx
0x14004068c  lea     r9, [rsp+98h+cbSid]; cbSid
0x140040691  mov     rdi, rcx
0x140040694  lea     r8, [rsp+98h+pSid]; pSid
0x140040699  mov     rdx, r10; DomainSid
0x14004069c  mov     ecx, eax; WellKnownSidType
0x14004069e  call    cs:__imp_CreateWellKnownSid
0x1400406a5  nop     dword ptr [rax+rax+00h]
0x1400406aa  test    eax, eax
0x1400406ac  jnz     short loc_1400406C8
0x1400406ae  mov     rcx, [rsp+98h]; this
0x1400406b6  lea     r8, aOnecoreVmCommo_54; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x1400406bd  mov     edx, 1469h; void *
0x1400406c2  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400406c8  mov     edx, [rsp+98h+cbSid]; uBytes
0x1400406cc  xor     ecx, ecx; uFlags
0x1400406ce  call    cs:__imp_LocalAlloc
0x1400406d5  nop     dword ptr [rax+rax+00h]
0x1400406da  mov     rbx, rax
0x1400406dd  test    rax, rax
0x1400406e0  jnz     short loc_1400406FC
0x1400406e2  mov     rcx, [rsp+98h]; this
0x1400406ea  lea     r8, aOnecoreVmCommo_54; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x1400406f1  mov     edx, 146Fh; void *
0x1400406f6  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400406fc  mov     ecx, [rsp+98h+cbSid]; nDestinationSidLength
0x140040700  lea     r8, [rsp+98h+pSid]; pSourceSid
0x140040705  mov     rdx, rbx; pDestinationSid
0x140040708  call    cs:__imp_CopySid
0x14004070f  nop     dword ptr [rax+rax+00h]
0x140040714  mov     rdx, rbx; void *
0x140040717  mov     rcx, rdi; this
0x14004071a  call    ?Reset@VmSid@Vml@@QEAAXPEAX@Z; Vml::VmSid::Reset(void *)
0x14004071f  mov     rcx, [rsp+98h+var_18]
0x140040727  xor     rcx, rsp; StackCookie
0x14004072a  call    __security_check_cookie
0x14004072f  mov     rbx, [rsp+98h+arg_18]
0x140040737  add     rsp, 90h
0x14004073e  pop     rdi
0x14004073f  retn
```
