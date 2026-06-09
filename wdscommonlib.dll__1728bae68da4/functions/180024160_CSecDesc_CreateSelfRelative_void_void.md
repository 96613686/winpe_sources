# CSecDesc::CreateSelfRelative(void *,void * *)

- ea: `0x180024160`
- end: `0x18002428b`
- name: `?CreateSelfRelative@CSecDesc@@SAKPEAXPEAPEAX@Z`
- size: `299`
- prototype: `unsigned int __fastcall(void *Src, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180024310`

## callees

- `0x18000214c`
- `0x1800024b2`
- `0x180024160`
- `0x180024420`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180024240`
- `msvcrt!??3@YAXPEAX@Z` at `0x180024240`
- `KERNEL32!GetLastError` at `0x180024226`
- `KERNEL32!GetLastError` at `0x180024226`
- `ADVAPI32!GetSecurityDescriptorControl` at `0x1800241b4`
- `ADVAPI32!GetSecurityDescriptorControl` at `0x1800241b4`
- `ADVAPI32!MakeSelfRelativeSD` at `0x1800241dc`
- `ADVAPI32!MakeSelfRelativeSD` at `0x180024216`
- `ADVAPI32!MakeSelfRelativeSD` at `0x1800241dc`
- `ADVAPI32!MakeSelfRelativeSD` at `0x180024216`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x18002419a`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x18002419a`

## pseudocode

```c
__int64 __fastcall CSecDesc::CreateSelfRelative(void *Src, void **a2)
{
  void *v3; // rdi
  DWORD IsValid; // ebx
  void *v6; // rax
  void *v7; // rax
  DWORD dwRevision[4]; // [rsp+20h] [rbp-10h] BYREF
  WORD pControl; // [rsp+70h] [rbp+40h] BYREF
  DWORD dwBufferLength; // [rsp+78h] [rbp+48h] BYREF

  dwRevision[0] = 0;
  v3 = 0;
  pControl = 0;
  IsValid = CSecDesc::IsValid(Src);
  if ( IsValid )
    return IsValid;
  dwBufferLength = GetSecurityDescriptorLength(Src);
  if ( GetSecurityDescriptorControl(Src, &pControl, dwRevision) )
  {
    if ( (pControl & 0x8000u) != 0 )
    {
      v7 = operator new[](dwBufferLength, (const struct std::nothrow_t *)&std::nothrow);
      v3 = v7;
      if ( !v7 )
        return 8;
      memmove_0(v7, Src, dwBufferLength);
    }
    else
    {
      dwBufferLength = 0;
      MakeSelfRelativeSD(Src, 0, &dwBufferLength);
      if ( !dwBufferLength )
        goto LABEL_8;
      v6 = operator new[](dwBufferLength, (const struct std::nothrow_t *)&std::nothrow);
      v3 = v6;
      if ( !v6 )
        return 8;
      if ( !MakeSelfRelativeSD(Src, v6, &dwBufferLength) )
        goto LABEL_8;
    }
    *a2 = v3;
    return IsValid;
  }
LABEL_8:
  IsValid = GetLastError();
  if ( IsValid && v3 )
    operator delete(v3);
  return IsValid;
}

```

## disassembly

```asm
0x180024160  mov     [rsp-28h+arg_0], rbx
0x180024165  push    rbp
0x180024166  push    rsi
0x180024167  push    rdi
0x180024168  push    r14
0x18002416a  push    r15
0x18002416c  mov     rbp, rsp
0x18002416f  sub     rsp, 30h
0x180024173  xor     r15d, r15d
0x180024176  mov     r14, rdx
0x180024179  mov     [rbp+dwRevision], r15d
0x18002417d  mov     edi, r15d
0x180024180  mov     [rbp+pControl], r15w
0x180024185  mov     rsi, rcx
0x180024188  call    ?IsValid@CSecDesc@@SAKPEAX@Z; CSecDesc::IsValid(void *)
0x18002418d  mov     ebx, eax
0x18002418f  test    eax, eax
0x180024191  jnz     loc_180024277
0x180024197  mov     rcx, rsi; pSecurityDescriptor
0x18002419a  call    cs:__imp_GetSecurityDescriptorLength
0x1800241a1  nop     dword ptr [rax+rax+00h]
0x1800241a6  lea     r8, [rbp+dwRevision]; lpdwRevision
0x1800241aa  mov     rcx, rsi; pSecurityDescriptor
0x1800241ad  lea     rdx, [rbp+pControl]; pControl
0x1800241b1  mov     [rbp+dwBufferLength], eax
0x1800241b4  call    cs:__imp_GetSecurityDescriptorControl
0x1800241bb  nop     dword ptr [rax+rax+00h]
0x1800241c0  test    eax, eax
0x1800241c2  jz      short loc_180024226
0x1800241c4  mov     eax, 8000h
0x1800241c9  test    [rbp+pControl], ax
0x1800241cd  jnz     short loc_18002424E
0x1800241cf  lea     r8, [rbp+dwBufferLength]; lpdwBufferLength
0x1800241d3  mov     [rbp+dwBufferLength], r15d
0x1800241d7  xor     edx, edx; pSelfRelativeSecurityDescriptor
0x1800241d9  mov     rcx, rsi; pAbsoluteSecurityDescriptor
0x1800241dc  call    cs:__imp_MakeSelfRelativeSD
0x1800241e3  nop     dword ptr [rax+rax+00h]
0x1800241e8  mov     eax, [rbp+dwBufferLength]
0x1800241eb  test    eax, eax
0x1800241ed  jz      short loc_180024226
0x1800241ef  mov     ecx, eax; unsigned __int64
0x1800241f1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800241f8  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800241fd  mov     rdi, rax
0x180024200  test    rax, rax
0x180024203  jnz     short loc_18002420C
0x180024205  mov     ebx, 8
0x18002420a  jmp     short loc_180024277
0x18002420c  lea     r8, [rbp+dwBufferLength]; lpdwBufferLength
0x180024210  mov     rdx, rax; pSelfRelativeSecurityDescriptor
0x180024213  mov     rcx, rsi; pAbsoluteSecurityDescriptor
0x180024216  call    cs:__imp_MakeSelfRelativeSD
0x18002421d  nop     dword ptr [rax+rax+00h]
0x180024222  test    eax, eax
0x180024224  jnz     short loc_180024274
0x180024226  call    cs:__imp_GetLastError
0x18002422d  nop     dword ptr [rax+rax+00h]
0x180024232  mov     ebx, eax
0x180024234  test    eax, eax
0x180024236  jz      short loc_180024277
0x180024238  test    rdi, rdi
0x18002423b  jz      short loc_180024277
0x18002423d  mov     rcx, rdi
0x180024240  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180024247  nop     dword ptr [rax+rax+00h]
0x18002424c  jmp     short loc_180024277
0x18002424e  mov     ecx, [rbp+dwBufferLength]; unsigned __int64
0x180024251  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180024258  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18002425d  mov     rdi, rax
0x180024260  test    rax, rax
0x180024263  jz      short loc_180024205
0x180024265  mov     r8d, [rbp+dwBufferLength]; Size
0x180024269  mov     rdx, rsi; Src
0x18002426c  mov     rcx, rax; void *
0x18002426f  call    memmove_0
0x180024274  mov     [r14], rdi
0x180024277  mov     eax, ebx
0x180024279  mov     rbx, [rsp+30h+arg_0]
0x18002427e  add     rsp, 30h
0x180024282  pop     r15
0x180024284  pop     r14
0x180024286  pop     rdi
0x180024287  pop     rsi
0x180024288  pop     rbp
0x180024289  retn
```
