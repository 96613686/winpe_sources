# Vml::VmSid::Assign(void *)

- ea: `0x1400c40ec`
- end: `0x1400c41b6`
- name: `?Assign@VmSid@Vml@@QEAAXPEAX@Z`
- size: `202`
- prototype: `void(Vml::VmSid *__hidden this, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400c3aa0`

## callees

- `0x14005b648`
- `0x1400c40ec`
- `0x14013fef8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400c4184`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400c4184`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400c4119`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400c4119`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1400c4152`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1400c4152`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1400c4106`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1400c4106`

## string_xrefs

- `0x1400c4137`: `onecore\vm\common\vml\VmSecurity.h`
- `0x1400c4167`: `onecore\vm\common\vml\VmSecurity.h`

## pseudocode

```c
void __fastcall Vml::VmSid::Assign(Vml::VmSid *this, void *a2)
{
  HLOCAL v4; // rdi
  SIZE_T LengthSid; // r14
  HLOCAL v6; // rax
  const char *v7; // r9
  const char *v8; // r9
  void *v9; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  HLOCAL v11; // [rsp+58h] [rbp+10h]

  v4 = 0;
  if ( a2 )
  {
    LengthSid = GetLengthSid(a2);
    v6 = LocalAlloc(0, LengthSid);
    v4 = v6;
    if ( !v6 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x1540,
        (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
        v7);
    if ( !CopySid(LengthSid, v6, a2) )
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
        LocalFree(v11);
        throw;
      }
    }
  }
  v9 = *(void **)this;
  *(_QWORD *)this = v4;
  if ( v9 )
    LocalFree(v9);
  *((_DWORD *)this + 2) = 7;
  std::wstring::erase((char *)this + 48, 0);
  std::wstring::erase((char *)this + 16, 0);
}

```

## disassembly

```asm
0x1400c40ec  push    rbx
0x1400c40ee  push    rsi
0x1400c40ef  push    rdi
0x1400c40f0  push    r14
0x1400c40f2  sub     rsp, 28h
0x1400c40f6  mov     rsi, rdx
0x1400c40f9  mov     rbx, rcx
0x1400c40fc  xor     edi, edi
0x1400c40fe  test    rdx, rdx
0x1400c4101  jz      short loc_1400C4179
0x1400c4103  mov     rcx, rdx; pSid
0x1400c4106  call    cs:__imp_GetLengthSid
0x1400c410d  nop     dword ptr [rax+rax+00h]
0x1400c4112  mov     r14d, eax
0x1400c4115  mov     edx, eax; uBytes
0x1400c4117  xor     ecx, ecx; uFlags
0x1400c4119  call    cs:__imp_LocalAlloc
0x1400c4120  nop     dword ptr [rax+rax+00h]
0x1400c4125  mov     rdi, rax
0x1400c4128  mov     [rsp+48h+arg_8], rax
0x1400c412d  test    rax, rax
0x1400c4130  jnz     short loc_1400C4149
0x1400c4132  mov     rcx, [rsp+48h]; this
0x1400c4137  lea     r8, aOnecoreVmCommo_90; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x1400c413e  mov     edx, 1540h; void *
0x1400c4143  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400c4149  mov     r8, rsi; pSourceSid
0x1400c414c  mov     rdx, rax; pDestinationSid
0x1400c414f  mov     ecx, r14d; nDestinationSidLength
0x1400c4152  call    cs:__imp_CopySid
0x1400c4159  nop     dword ptr [rax+rax+00h]
0x1400c415e  mov     rcx, [rsp+48h]; this
0x1400c4163  test    eax, eax
0x1400c4165  jnz     short loc_1400C4179
0x1400c4167  lea     r8, aOnecoreVmCommo_90; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x1400c416e  mov     edx, 1545h; void *
0x1400c4173  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400c4179  mov     rcx, [rbx]; hMem
0x1400c417c  mov     [rbx], rdi
0x1400c417f  test    rcx, rcx
0x1400c4182  jz      short loc_1400C4190
0x1400c4184  call    cs:__imp_LocalFree
0x1400c418b  nop     dword ptr [rax+rax+00h]
0x1400c4190  mov     dword ptr [rbx+8], 7
0x1400c4197  lea     rcx, [rbx+30h]
0x1400c419b  xor     edx, edx
0x1400c419d  call    ?erase@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_K@Z; std::wstring::erase(unsigned __int64)
0x1400c41a2  lea     rcx, [rbx+10h]
0x1400c41a6  xor     edx, edx
0x1400c41a8  add     rsp, 28h
0x1400c41ac  pop     r14
0x1400c41ae  pop     rdi
0x1400c41af  pop     rsi
0x1400c41b0  pop     rbx
0x1400c41b1  jmp     ?erase@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_K@Z; std::wstring::erase(unsigned __int64)
```
