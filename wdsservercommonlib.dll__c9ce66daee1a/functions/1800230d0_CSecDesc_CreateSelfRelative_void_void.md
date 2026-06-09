# CSecDesc::CreateSelfRelative(void *,void * *)

- ea: `0x1800230d0`
- end: `0x1800231f4`
- name: `?CreateSelfRelative@CSecDesc@@SAKPEAXPEAPEAX@Z`
- size: `292`
- prototype: `unsigned int __fastcall(void *Src, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180023270`

## callees

- `0x18000179c`
- `0x1800230d0`
- `0x180023380`
- `0x18002e468`
- `0x18002f3ae`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180023196`
- `KERNEL32!GetLastError` at `0x180023196`
- `ADVAPI32!MakeSelfRelativeSD` at `0x18002314c`
- `ADVAPI32!MakeSelfRelativeSD` at `0x180023186`
- `ADVAPI32!MakeSelfRelativeSD` at `0x18002314c`
- `ADVAPI32!MakeSelfRelativeSD` at `0x180023186`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x18002310a`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x18002310a`
- `ADVAPI32!GetSecurityDescriptorControl` at `0x180023124`
- `ADVAPI32!GetSecurityDescriptorControl` at `0x180023124`

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
0x1800230d0  mov     [rsp-28h+arg_0], rbx
0x1800230d5  push    rbp
0x1800230d6  push    rsi
0x1800230d7  push    rdi
0x1800230d8  push    r14
0x1800230da  push    r15
0x1800230dc  mov     rbp, rsp
0x1800230df  sub     rsp, 30h
0x1800230e3  xor     r15d, r15d
0x1800230e6  mov     r14, rdx
0x1800230e9  mov     [rbp+dwRevision], r15d
0x1800230ed  mov     edi, r15d
0x1800230f0  mov     [rbp+pControl], r15w
0x1800230f5  mov     rsi, rcx
0x1800230f8  call    ?IsValid@CSecDesc@@SAKPEAX@Z; CSecDesc::IsValid(void *)
0x1800230fd  mov     ebx, eax
0x1800230ff  test    eax, eax
0x180023101  jnz     loc_1800231E0
0x180023107  mov     rcx, rsi; pSecurityDescriptor
0x18002310a  call    cs:__imp_GetSecurityDescriptorLength
0x180023111  nop     dword ptr [rax+rax+00h]
0x180023116  lea     r8, [rbp+dwRevision]; lpdwRevision
0x18002311a  mov     rcx, rsi; pSecurityDescriptor
0x18002311d  lea     rdx, [rbp+pControl]; pControl
0x180023121  mov     [rbp+dwBufferLength], eax
0x180023124  call    cs:__imp_GetSecurityDescriptorControl
0x18002312b  nop     dword ptr [rax+rax+00h]
0x180023130  test    eax, eax
0x180023132  jz      short loc_180023196
0x180023134  mov     eax, 8000h
0x180023139  test    [rbp+pControl], ax
0x18002313d  jnz     short loc_1800231B7
0x18002313f  lea     r8, [rbp+dwBufferLength]; lpdwBufferLength
0x180023143  mov     [rbp+dwBufferLength], r15d
0x180023147  xor     edx, edx; pSelfRelativeSecurityDescriptor
0x180023149  mov     rcx, rsi; pAbsoluteSecurityDescriptor
0x18002314c  call    cs:__imp_MakeSelfRelativeSD
0x180023153  nop     dword ptr [rax+rax+00h]
0x180023158  mov     eax, [rbp+dwBufferLength]
0x18002315b  test    eax, eax
0x18002315d  jz      short loc_180023196
0x18002315f  mov     ecx, eax; unsigned __int64
0x180023161  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180023168  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18002316d  mov     rdi, rax
0x180023170  test    rax, rax
0x180023173  jnz     short loc_18002317C
0x180023175  mov     ebx, 8
0x18002317a  jmp     short loc_1800231E0
0x18002317c  lea     r8, [rbp+dwBufferLength]; lpdwBufferLength
0x180023180  mov     rdx, rax; pSelfRelativeSecurityDescriptor
0x180023183  mov     rcx, rsi; pAbsoluteSecurityDescriptor
0x180023186  call    cs:__imp_MakeSelfRelativeSD
0x18002318d  nop     dword ptr [rax+rax+00h]
0x180023192  test    eax, eax
0x180023194  jnz     short loc_1800231DD
0x180023196  call    cs:__imp_GetLastError
0x18002319d  nop     dword ptr [rax+rax+00h]
0x1800231a2  mov     ebx, eax
0x1800231a4  test    eax, eax
0x1800231a6  jz      short loc_1800231E0
0x1800231a8  test    rdi, rdi
0x1800231ab  jz      short loc_1800231E0
0x1800231ad  mov     rcx, rdi; lpMem
0x1800231b0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800231b5  jmp     short loc_1800231E0
0x1800231b7  mov     ecx, [rbp+dwBufferLength]; unsigned __int64
0x1800231ba  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800231c1  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800231c6  mov     rdi, rax
0x1800231c9  test    rax, rax
0x1800231cc  jz      short loc_180023175
0x1800231ce  mov     r8d, [rbp+dwBufferLength]; Size
0x1800231d2  mov     rdx, rsi; Src
0x1800231d5  mov     rcx, rax; void *
0x1800231d8  call    memmove_0
0x1800231dd  mov     [r14], rdi
0x1800231e0  mov     eax, ebx
0x1800231e2  mov     rbx, [rsp+30h+arg_0]
0x1800231e7  add     rsp, 30h
0x1800231eb  pop     r15
0x1800231ed  pop     r14
0x1800231ef  pop     rdi
0x1800231f0  pop     rsi
0x1800231f1  pop     rbp
0x1800231f2  retn
```
