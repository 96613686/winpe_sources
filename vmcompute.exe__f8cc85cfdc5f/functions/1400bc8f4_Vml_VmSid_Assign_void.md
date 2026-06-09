# Vml::VmSid::Assign(void *)

- ea: `0x1400bc8f4`
- end: `0x1400bc995`
- name: `?Assign@VmSid@Vml@@QEAAXPEAX@Z`
- size: `161`
- prototype: `void __fastcall(Vml::VmSid *__hidden this, PSID pSourceSid)`
- caller_count: `5`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140040fe8`
- `0x140041ad8`
- `0x140043c30`
- `0x1400bd0b8`
- `0x1400bdc70`

## callees

- `0x140080180`
- `0x1400bc8f4`
- `0x1400bc99c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1400bc95a`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1400bc95a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1400bc90e`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1400bc90e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400bc921`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400bc921`

## string_xrefs

- `0x1400bc93f`: `onecore\vm\common\vml\VmSecurity.h`
- `0x1400bc96f`: `onecore\vm\common\vml\VmSecurity.h`

## pseudocode

```c
void __fastcall Vml::VmSid::Assign(Vml::VmSid *this, PSID pSourceSid)
{
  void *v4; // rbx
  DWORD LengthSid; // r14d
  HLOCAL v6; // rax
  const char *v7; // r9
  const char *v8; // r9
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  HLOCAL v10; // [rsp+58h] [rbp+10h]

  v4 = 0;
  if ( pSourceSid )
  {
    LengthSid = GetLengthSid(pSourceSid);
    v6 = LocalAlloc(0, LengthSid);
    v4 = v6;
    if ( !v6 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x1540,
        (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
        v7);
    if ( !CopySid(LengthSid, v6, pSourceSid) )
    {
      try
      {
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x1545,
          (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
          v8);
      }
      catch ( ... )
      {
        LocalFree(v10);
        throw;
      }
    }
  }
  Vml::VmSid::Reset(this, v4);
}

```

## disassembly

```asm
0x1400bc8f4  push    rbx
0x1400bc8f6  push    rsi
0x1400bc8f7  push    rdi
0x1400bc8f8  push    r14
0x1400bc8fa  sub     rsp, 28h
0x1400bc8fe  mov     rdi, rdx
0x1400bc901  mov     rsi, rcx
0x1400bc904  xor     ebx, ebx
0x1400bc906  test    rdx, rdx
0x1400bc909  jz      short loc_1400BC981
0x1400bc90b  mov     rcx, rdx; pSid
0x1400bc90e  call    cs:__imp_GetLengthSid
0x1400bc915  nop     dword ptr [rax+rax+00h]
0x1400bc91a  mov     r14d, eax
0x1400bc91d  mov     edx, eax; uBytes
0x1400bc91f  xor     ecx, ecx; uFlags
0x1400bc921  call    cs:__imp_LocalAlloc
0x1400bc928  nop     dword ptr [rax+rax+00h]
0x1400bc92d  mov     rbx, rax
0x1400bc930  mov     [rsp+48h+arg_8], rax
0x1400bc935  test    rax, rax
0x1400bc938  jnz     short loc_1400BC951
0x1400bc93a  mov     rcx, [rsp+48h]; this
0x1400bc93f  lea     r8, aOnecoreVmCommo_54; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x1400bc946  mov     edx, 1540h; void *
0x1400bc94b  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400bc951  mov     r8, rdi; pSourceSid
0x1400bc954  mov     rdx, rax; pDestinationSid
0x1400bc957  mov     ecx, r14d; nDestinationSidLength
0x1400bc95a  call    cs:__imp_CopySid
0x1400bc961  nop     dword ptr [rax+rax+00h]
0x1400bc966  mov     rcx, [rsp+48h]; this
0x1400bc96b  test    eax, eax
0x1400bc96d  jnz     short loc_1400BC981
0x1400bc96f  lea     r8, aOnecoreVmCommo_54; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x1400bc976  mov     edx, 1545h; void *
0x1400bc97b  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400bc981  mov     rdx, rbx; void *
0x1400bc984  mov     rcx, rsi; this
0x1400bc987  add     rsp, 28h
0x1400bc98b  pop     r14
0x1400bc98d  pop     rdi
0x1400bc98e  pop     rsi
0x1400bc98f  pop     rbx
0x1400bc990  jmp     ?Reset@VmSid@Vml@@QEAAXPEAX@Z; Vml::VmSid::Reset(void *)
```
