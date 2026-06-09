# ResolveAccountSid(void *,ushort * *,ushort * *,ushort * *)

- ea: `0x180012b30`
- end: `0x180012d6d`
- name: `?ResolveAccountSid@@YAKPEAXPEAPEAG11@Z`
- size: `573`
- prototype: `unsigned int __fastcall(PSID Sid, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180012150`

## callees

- `0x18000179c`
- `0x180005830`
- `0x180012b30`
- `0x18002e468`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180012bb2`
- `KERNEL32!GetLastError` at `0x180012c5d`
- `KERNEL32!GetLastError` at `0x180012d3e`
- `KERNEL32!GetLastError` at `0x180012bb2`
- `KERNEL32!GetLastError` at `0x180012c5d`
- `KERNEL32!GetLastError` at `0x180012d3e`
- `ADVAPI32!LookupAccountSidW` at `0x180012b8a`
- `ADVAPI32!LookupAccountSidW` at `0x180012c4d`
- `ADVAPI32!LookupAccountSidW` at `0x180012b8a`
- `ADVAPI32!LookupAccountSidW` at `0x180012c4d`

## pseudocode

```c
__int64 __fastcall ResolveAccountSid(PSID Sid, unsigned __int16 **a2, unsigned __int16 **a3, unsigned __int16 **a4)
{
  unsigned __int64 v8; // rax
  WCHAR *v9; // rsi
  signed int LastError; // ebx
  unsigned __int64 v11; // rax
  WCHAR *ReferencedDomainName; // rdi
  __int64 v13; // r8
  __int64 v14; // rcx
  unsigned __int64 v15; // rbx
  unsigned __int64 v16; // rax
  unsigned __int16 *v17; // rax
  DWORD cchReferencedDomainName; // [rsp+40h] [rbp-20h] BYREF
  DWORD cchName; // [rsp+44h] [rbp-1Ch] BYREF
  enum _SID_NAME_USE peUse[6]; // [rsp+48h] [rbp-18h] BYREF

  cchName = 0;
  cchReferencedDomainName = 0;
  peUse[0] = 0;
  if ( LookupAccountSidW(0, Sid, 0, &cchName, 0, &cchReferencedDomainName, peUse)
    || !cchName
    || !cchReferencedDomainName
    || GetLastError() == 1332 )
  {
    return GetLastError();
  }
  v8 = 2LL * cchName;
  if ( !is_mul_ok(cchName, 2u) )
    v8 = -1;
  v9 = (WCHAR *)operator new[](v8, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v9 )
    return 8;
  v11 = 2LL * cchReferencedDomainName;
  if ( !is_mul_ok(cchReferencedDomainName, 2u) )
    v11 = -1;
  ReferencedDomainName = (WCHAR *)operator new[](v11, (const struct std::nothrow_t *)&std::nothrow);
  if ( !ReferencedDomainName )
    goto LABEL_12;
  if ( !LookupAccountSidW(0, Sid, v9, &cchName, ReferencedDomainName, &cchReferencedDomainName, peUse) )
  {
    LastError = GetLastError();
    goto LABEL_33;
  }
  if ( !a4 )
  {
LABEL_28:
    if ( a2 )
    {
      *a2 = v9;
      v9 = 0;
    }
    if ( a3 )
    {
      *a3 = ReferencedDomainName;
      ReferencedDomainName = 0;
    }
    LastError = 0;
    if ( !v9 )
      goto LABEL_34;
    goto LABEL_33;
  }
  v13 = -1;
  do
    ++v13;
  while ( ReferencedDomainName[v13] );
  v14 = -1;
  do
    ++v14;
  while ( v9[v14] );
  v15 = v13 + v14 + 2;
  v16 = 2 * v15;
  if ( !is_mul_ok(v15, 2u) )
    v16 = -1;
  v17 = (unsigned __int16 *)operator new[](v16, (const struct std::nothrow_t *)&std::nothrow);
  *a4 = v17;
  if ( v17 )
  {
    LastError = StringCchPrintfW(v17, v15, L"%s\\%s", ReferencedDomainName, v9);
    if ( LastError < 0 )
    {
      if ( *a4 )
      {
        operator delete(*a4);
        *a4 = 0;
      }
      if ( (LastError & 0x1FFF0000) == 0x70000 )
        LastError = (unsigned __int16)LastError;
      goto LABEL_33;
    }
    goto LABEL_28;
  }
LABEL_12:
  LastError = 8;
LABEL_33:
  operator delete(v9);
LABEL_34:
  if ( ReferencedDomainName )
    operator delete(ReferencedDomainName);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180012b30  mov     r11, rsp
0x180012b33  mov     [r11+8], rbx
0x180012b37  mov     [r11+10h], rsi
0x180012b3b  mov     [r11+18h], rdi
0x180012b3f  push    rbp
0x180012b40  push    r12
0x180012b42  push    r13
0x180012b44  push    r14
0x180012b46  push    r15
0x180012b48  mov     rbp, rsp
0x180012b4b  sub     rsp, 60h
0x180012b4f  xor     r13d, r13d
0x180012b52  lea     rax, [rbp+var_18]
0x180012b56  mov     [r11-58h], rax
0x180012b5a  mov     r15, rdx
0x180012b5d  lea     rax, [rbp+var_20]
0x180012b61  mov     [rbp+cchName], r13d
0x180012b65  mov     r14, r9
0x180012b68  mov     [r11-60h], rax
0x180012b6c  mov     r12, r8
0x180012b6f  mov     [r11-68h], r13
0x180012b73  mov     rbx, rcx
0x180012b76  mov     [rbp+var_20], r13d
0x180012b7a  mov     rdx, rcx; Sid
0x180012b7d  mov     [rbp+var_18], r13d
0x180012b81  lea     r9, [rbp+cchName]; cchName
0x180012b85  xor     r8d, r8d; Name
0x180012b88  xor     ecx, ecx; lpSystemName
0x180012b8a  call    cs:__imp_LookupAccountSidW
0x180012b91  nop     dword ptr [rax+rax+00h]
0x180012b96  test    eax, eax
0x180012b98  jnz     loc_180012D3E
0x180012b9e  cmp     [rbp+cchName], r13d
0x180012ba2  jz      loc_180012D3E
0x180012ba8  cmp     [rbp+var_20], r13d
0x180012bac  jz      loc_180012D3E
0x180012bb2  call    cs:__imp_GetLastError
0x180012bb9  nop     dword ptr [rax+rax+00h]
0x180012bbe  cmp     eax, 534h
0x180012bc3  jz      loc_180012D3E
0x180012bc9  mov     ecx, [rbp+cchName]
0x180012bcc  lea     eax, [r13+2]
0x180012bd0  mul     rcx
0x180012bd3  lea     rdi, [r13-1]
0x180012bd7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180012bde  cmovo   rax, rdi
0x180012be2  mov     rcx, rax; unsigned __int64
0x180012be5  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180012bea  mov     rsi, rax
0x180012bed  test    rax, rax
0x180012bf0  jnz     short loc_180012BFA
0x180012bf2  lea     ebx, [rdi+9]
0x180012bf5  jmp     loc_180012D4C
0x180012bfa  mov     ecx, [rbp+var_20]
0x180012bfd  mov     eax, 2
0x180012c02  mul     rcx
0x180012c05  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180012c0c  cmovo   rax, rdi
0x180012c10  mov     rcx, rax; unsigned __int64
0x180012c13  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180012c18  mov     rdi, rax
0x180012c1b  test    rax, rax
0x180012c1e  jnz     short loc_180012C2A
0x180012c20  mov     ebx, 8
0x180012c25  jmp     loc_180012D27
0x180012c2a  lea     rax, [rbp+var_18]
0x180012c2e  mov     r8, rsi; Name
0x180012c31  mov     [rsp+60h+peUse], rax; peUse
0x180012c36  lea     r9, [rbp+cchName]; cchName
0x180012c3a  lea     rax, [rbp+var_20]
0x180012c3e  mov     rdx, rbx; Sid
0x180012c41  mov     [rsp+60h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180012c46  xor     ecx, ecx; lpSystemName
0x180012c48  mov     [rsp+60h+ReferencedDomainName], rdi; ReferencedDomainName
0x180012c4d  call    cs:__imp_LookupAccountSidW
0x180012c54  nop     dword ptr [rax+rax+00h]
0x180012c59  test    eax, eax
0x180012c5b  jnz     short loc_180012C70
0x180012c5d  call    cs:__imp_GetLastError
0x180012c64  nop     dword ptr [rax+rax+00h]
0x180012c69  mov     ebx, eax
0x180012c6b  jmp     loc_180012D27
0x180012c70  test    r14, r14
0x180012c73  jz      loc_180012D08
0x180012c79  or      r9, 0FFFFFFFFFFFFFFFFh
0x180012c7d  mov     r8, r9
0x180012c80  inc     r8
0x180012c83  cmp     [rdi+r8*2], r13w
0x180012c88  jnz     short loc_180012C80
0x180012c8a  mov     rcx, r9
0x180012c8d  inc     rcx
0x180012c90  cmp     [rsi+rcx*2], r13w
0x180012c95  jnz     short loc_180012C8D
0x180012c97  lea     rbx, [rcx+2]
0x180012c9b  mov     eax, 2
0x180012ca0  add     rbx, r8
0x180012ca3  mul     rbx
0x180012ca6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180012cad  cmovo   rax, r9
0x180012cb1  mov     rcx, rax; unsigned __int64
0x180012cb4  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180012cb9  mov     [r14], rax
0x180012cbc  test    rax, rax
0x180012cbf  jz      loc_180012C20
0x180012cc5  mov     r9, rdi
0x180012cc8  mov     [rsp+60h+ReferencedDomainName], rsi
0x180012ccd  lea     r8, aSS; "%s\\%s"
0x180012cd4  mov     rdx, rbx; unsigned __int64
0x180012cd7  mov     rcx, rax; unsigned __int16 *
0x180012cda  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180012cdf  mov     ebx, eax
0x180012ce1  test    eax, eax
0x180012ce3  jns     short loc_180012D08
0x180012ce5  mov     rcx, [r14]; lpMem
0x180012ce8  test    rcx, rcx
0x180012ceb  jz      short loc_180012CF5
0x180012ced  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180012cf2  mov     [r14], r13
0x180012cf5  mov     eax, ebx
0x180012cf7  and     eax, 1FFF0000h
0x180012cfc  cmp     eax, 70000h
0x180012d01  jnz     short loc_180012D27
0x180012d03  movzx   ebx, bx
0x180012d06  jmp     short loc_180012D27
0x180012d08  test    r15, r15
0x180012d0b  jz      short loc_180012D13
0x180012d0d  mov     [r15], rsi
0x180012d10  mov     rsi, r13
0x180012d13  test    r12, r12
0x180012d16  jz      short loc_180012D1F
0x180012d18  mov     [r12], rdi
0x180012d1c  mov     rdi, r13
0x180012d1f  mov     ebx, r13d
0x180012d22  test    rsi, rsi
0x180012d25  jz      short loc_180012D2F
0x180012d27  mov     rcx, rsi; lpMem
0x180012d2a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180012d2f  test    rdi, rdi
0x180012d32  jz      short loc_180012D4C
0x180012d34  mov     rcx, rdi; lpMem
0x180012d37  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180012d3c  jmp     short loc_180012D4C
0x180012d3e  call    cs:__imp_GetLastError
0x180012d45  nop     dword ptr [rax+rax+00h]
0x180012d4a  mov     ebx, eax
0x180012d4c  lea     r11, [rsp+60h+var_s0]
0x180012d51  mov     eax, ebx
0x180012d53  mov     rbx, [r11+30h]
0x180012d57  mov     rsi, [r11+38h]
0x180012d5b  mov     rdi, [r11+40h]
0x180012d5f  mov     rsp, r11
0x180012d62  pop     r15
0x180012d64  pop     r14
0x180012d66  pop     r13
0x180012d68  pop     r12
0x180012d6a  pop     rbp
0x180012d6b  retn
```
