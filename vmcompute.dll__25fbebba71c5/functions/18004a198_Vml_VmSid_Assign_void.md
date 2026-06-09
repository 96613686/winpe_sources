# Vml::VmSid::Assign(void *)

- ea: `0x18004a198`
- end: `0x18004a27f`
- name: `?Assign@VmSid@Vml@@QEAAXPEAX@Z`
- size: `231`
- prototype: `void(Vml::VmSid *__hidden this, void *)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18004a43c`
- `0x18004a688`
- `0x18004aa68`

## callees

- `0x18000d0ec`
- `0x18004a198`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004a207`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004a207`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18004a1b2`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18004a1b2`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18004a1e7`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18004a1e7`
- `KERNELBASE!LocalAlloc` at `0x18004a1c5`
- `KERNELBASE!LocalAlloc` at `0x18004a1c5`

## string_xrefs

- `0x18004a25a`: `onecore\vm\common\vml\VmSecurity.h`
- `0x18004a26c`: `onecore\vm\common\vml\VmSecurity.h`

## pseudocode

```c
void __fastcall Vml::VmSid::Assign(Vml::VmSid *this, void *a2)
{
  HLOCAL v4; // rdi
  DWORD LengthSid; // r14d
  HLOCAL v6; // rax
  const char *v7; // r9
  const char *v8; // r9
  void *v9; // rcx
  _QWORD *v10; // rcx
  _QWORD *v11; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  HLOCAL v13; // [rsp+58h] [rbp+10h]

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
        LocalFree(v13);
        throw;
      }
    }
  }
  v9 = *(void **)this;
  *(_QWORD *)this = v4;
  if ( v9 )
    LocalFree(v9);
  *((_DWORD *)this + 2) = 7;
  v10 = (_QWORD *)((char *)this + 48);
  *((_QWORD *)this + 8) = 0;
  if ( *((_QWORD *)this + 9) > 7u )
    v10 = (_QWORD *)*v10;
  *(_WORD *)v10 = 0;
  v11 = (_QWORD *)((char *)this + 16);
  *((_QWORD *)this + 4) = 0;
  if ( *((_QWORD *)this + 5) > 7u )
    v11 = (_QWORD *)*v11;
  *(_WORD *)v11 = 0;
}

```

## disassembly

```asm
0x18004a198  push    rbx
0x18004a19a  push    rsi
0x18004a19b  push    rdi
0x18004a19c  push    r14
0x18004a19e  sub     rsp, 28h
0x18004a1a2  mov     rsi, rdx
0x18004a1a5  mov     rbx, rcx
0x18004a1a8  xor     edi, edi
0x18004a1aa  test    rdx, rdx
0x18004a1ad  jz      short loc_18004A1FC
0x18004a1af  mov     rcx, rdx; pSid
0x18004a1b2  call    cs:__imp_GetLengthSid
0x18004a1b9  nop     dword ptr [rax+rax+00h]
0x18004a1be  mov     r14d, eax
0x18004a1c1  mov     edx, eax; uBytes
0x18004a1c3  xor     ecx, ecx; uFlags
0x18004a1c5  call    cs:__imp_LocalAlloc
0x18004a1cc  nop     dword ptr [rax+rax+00h]
0x18004a1d1  mov     rdi, rax
0x18004a1d4  mov     [rsp+48h+arg_8], rax
0x18004a1d9  test    rax, rax
0x18004a1dc  jz      short loc_18004A255
0x18004a1de  mov     r8, rsi; pSourceSid
0x18004a1e1  mov     rdx, rax; pDestinationSid
0x18004a1e4  mov     ecx, r14d; nDestinationSidLength
0x18004a1e7  call    cs:__imp_CopySid
0x18004a1ee  nop     dword ptr [rax+rax+00h]
0x18004a1f3  mov     rcx, [rsp+48h]; this
0x18004a1f8  test    eax, eax
0x18004a1fa  jz      short loc_18004A26C
0x18004a1fc  mov     rcx, [rbx]; hMem
0x18004a1ff  mov     [rbx], rdi
0x18004a202  test    rcx, rcx
0x18004a205  jz      short loc_18004A213
0x18004a207  call    cs:__imp_LocalFree
0x18004a20e  nop     dword ptr [rax+rax+00h]
0x18004a213  mov     dword ptr [rbx+8], 7
0x18004a21a  lea     rcx, [rbx+30h]
0x18004a21e  mov     qword ptr [rcx+10h], 0
0x18004a226  cmp     qword ptr [rcx+18h], 7
0x18004a22b  jbe     short loc_18004A230
0x18004a22d  mov     rcx, [rcx]
0x18004a230  xor     eax, eax
0x18004a232  mov     [rcx], ax
0x18004a235  lea     rcx, [rbx+10h]
0x18004a239  mov     [rcx+10h], rax
0x18004a23d  cmp     qword ptr [rcx+18h], 7
0x18004a242  jbe     short loc_18004A247
0x18004a244  mov     rcx, [rcx]
0x18004a247  mov     [rcx], ax
0x18004a24a  add     rsp, 28h
0x18004a24e  pop     r14
0x18004a250  pop     rdi
0x18004a251  pop     rsi
0x18004a252  pop     rbx
0x18004a253  retn
0x18004a255  mov     rcx, [rsp+48h]; this
0x18004a25a  lea     r8, aOnecoreVmCommo_13; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x18004a261  mov     edx, 1540h; void *
0x18004a266  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18004a26c  lea     r8, aOnecoreVmCommo_13; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x18004a273  mov     edx, 1545h; void *
0x18004a278  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
