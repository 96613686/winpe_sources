# Vml::VmSid::Assign(void *)

- ea: `0x140065d58`
- end: `0x140065e22`
- name: `?Assign@VmSid@Vml@@QEAAXPEAX@Z`
- size: `202`
- prototype: `void(Vml::VmSid *__hidden this, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14006570c`

## callees

- `0x140065d58`
- `0x140083990`
- `0x14012bfd8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140065d85`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140065d85`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140065df0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140065df0`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x140065dbe`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x140065dbe`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140065d72`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140065d72`

## string_xrefs

- `0x140065da3`: `onecore\vm\common\vml\VmSecurity.h`
- `0x140065dd3`: `onecore\vm\common\vml\VmSecurity.h`

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
0x140065d58  push    rbx
0x140065d5a  push    rsi
0x140065d5b  push    rdi
0x140065d5c  push    r14
0x140065d5e  sub     rsp, 28h
0x140065d62  mov     rsi, rdx
0x140065d65  mov     rbx, rcx
0x140065d68  xor     edi, edi
0x140065d6a  test    rdx, rdx
0x140065d6d  jz      short loc_140065DE5
0x140065d6f  mov     rcx, rdx; pSid
0x140065d72  call    cs:__imp_GetLengthSid
0x140065d79  nop     dword ptr [rax+rax+00h]
0x140065d7e  mov     r14d, eax
0x140065d81  mov     edx, eax; uBytes
0x140065d83  xor     ecx, ecx; uFlags
0x140065d85  call    cs:__imp_LocalAlloc
0x140065d8c  nop     dword ptr [rax+rax+00h]
0x140065d91  mov     rdi, rax
0x140065d94  mov     [rsp+48h+arg_8], rax
0x140065d99  test    rax, rax
0x140065d9c  jnz     short loc_140065DB5
0x140065d9e  mov     rcx, [rsp+48h]; this
0x140065da3  lea     r8, aOnecoreVmCommo_90; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x140065daa  mov     edx, 1540h; void *
0x140065daf  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140065db5  mov     r8, rsi; pSourceSid
0x140065db8  mov     rdx, rax; pDestinationSid
0x140065dbb  mov     ecx, r14d; nDestinationSidLength
0x140065dbe  call    cs:__imp_CopySid
0x140065dc5  nop     dword ptr [rax+rax+00h]
0x140065dca  mov     rcx, [rsp+48h]; this
0x140065dcf  test    eax, eax
0x140065dd1  jnz     short loc_140065DE5
0x140065dd3  lea     r8, aOnecoreVmCommo_90; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x140065dda  mov     edx, 1545h; void *
0x140065ddf  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140065de5  mov     rcx, [rbx]; hMem
0x140065de8  mov     [rbx], rdi
0x140065deb  test    rcx, rcx
0x140065dee  jz      short loc_140065DFC
0x140065df0  call    cs:__imp_LocalFree
0x140065df7  nop     dword ptr [rax+rax+00h]
0x140065dfc  mov     dword ptr [rbx+8], 7
0x140065e03  lea     rcx, [rbx+30h]
0x140065e07  xor     edx, edx
0x140065e09  call    ?erase@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_K@Z; std::wstring::erase(unsigned __int64)
0x140065e0e  lea     rcx, [rbx+10h]
0x140065e12  xor     edx, edx
0x140065e14  add     rsp, 28h
0x140065e18  pop     r14
0x140065e1a  pop     rdi
0x140065e1b  pop     rsi
0x140065e1c  pop     rbx
0x140065e1d  jmp     ?erase@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_K@Z; std::wstring::erase(unsigned __int64)
```
