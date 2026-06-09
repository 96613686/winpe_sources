# CPrintSecurity::SetSecurity(ulong,void *)

- ea: `0x180008950`
- end: `0x180008bd6`
- name: `?SetSecurity@CPrintSecurity@@UEAAJKPEAX@Z`
- size: `646`
- prototype: `__int64 __fastcall(CPrintSecurity *this, unsigned int, _OWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800085c0`
- `0x180008950`
- `0x18000c740`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008a8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008a8e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008ba1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008baf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008ba1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008baf`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800089e3`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800089e3`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x1800089bd`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x1800089bd`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180008a84`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180008a84`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x180008b4e`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x180008b4e`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x180008b25`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x180008b25`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x180008b0f`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x180008b0f`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x180008af4`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x180008af4`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180008b77`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180008b77`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180008ab3`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180008ab3`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x180008ade`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x180008ade`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x180008a29`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x180008a29`

## pseudocode

```c
__int64 __fastcall CPrintSecurity::SetSecurity(CPrintSecurity *this, unsigned int a2, _OWORD *a3)
{
  _OWORD *v3; // rbx
  struct _ACL *v6; // rdi
  PSID v7; // rsi
  int v9; // eax
  int v10; // eax
  signed int LastError; // eax
  unsigned int v12; // ebx
  WINBOOL bDaclPresent; // [rsp+20h] [rbp-50h] BYREF
  DWORD dwRevision; // [rsp+24h] [rbp-4Ch] BYREF
  PSID pOwner; // [rsp+28h] [rbp-48h] BYREF
  PACL pSacl; // [rsp+30h] [rbp-40h] BYREF
  PACL pDacl; // [rsp+38h] [rbp-38h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+40h] [rbp-30h] BYREF
  __int64 v19; // [rsp+60h] [rbp-10h]
  struct _ACL *pControl; // [rsp+C0h] [rbp+50h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+C8h] [rbp+58h] BYREF

  pDacl = 0;
  pSacl = 0;
  v3 = a3;
  pControl = 0;
  pOwner = 0;
  bDaclPresent = 0;
  v6 = 0;
  bDaclDefaulted = 0;
  v7 = 0;
  v19 = 0;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  if ( !a3 )
    return 2147500035LL;
  if ( !a2 || !IsValidSecurityDescriptor(a3) )
    return 2147942487LL;
  if ( (a2 & 4) != 0 )
  {
    if ( GetSecurityDescriptorDacl(v3, &bDaclPresent, &pDacl, &bDaclDefaulted) )
    {
      if ( bDaclPresent )
      {
        v9 = MungeAclForPrinter(pDacl, &pControl);
        v6 = pControl;
        if ( v9 )
        {
          if ( pControl )
            pDacl = pControl;
        }
      }
    }
  }
  if ( (a2 & 8) != 0 )
  {
    if ( GetSecurityDescriptorSacl(v3, &bDaclPresent, &pSacl, &bDaclDefaulted) )
    {
      if ( bDaclPresent )
      {
        v10 = MungeAclForPrinter(pSacl, (struct _ACL **)&pOwner);
        v7 = pOwner;
        if ( v10 )
        {
          if ( pOwner )
            pSacl = (PACL)pOwner;
        }
      }
    }
  }
  if ( v6 || v7 )
  {
    pOwner = 0;
    LOWORD(pControl) = 0;
    dwRevision = 0;
    if ( !GetSecurityDescriptorControl(v3, (PSECURITY_DESCRIPTOR_CONTROL)&pControl, &dwRevision)
      || !InitializeSecurityDescriptor(pSecurityDescriptor, dwRevision)
      || (WORD1(pSecurityDescriptor[0]) = (unsigned __int16)pControl & 0x7FFF, (a2 & 1) != 0)
      && GetSecurityDescriptorOwner(v3, &pOwner, &bDaclDefaulted)
      && !SetSecurityDescriptorOwner(pSecurityDescriptor, pOwner, bDaclDefaulted)
      || (a2 & 2) != 0
      && GetSecurityDescriptorGroup(v3, &pOwner, &bDaclDefaulted)
      && !SetSecurityDescriptorGroup(pSecurityDescriptor, pOwner, bDaclDefaulted)
      || (a2 & 8) != 0
      && !SetSecurityDescriptorSacl(
            pSecurityDescriptor,
            (unsigned __int8)pControl & 0x10,
            pSacl,
            (unsigned __int8)pControl & 0x20)
      || (a2 & 4) != 0
      && !SetSecurityDescriptorDacl(
            pSecurityDescriptor,
            (unsigned __int8)pControl & 4,
            pDacl,
            (unsigned __int8)pControl & 8) )
    {
      LastError = GetLastError();
      v12 = LastError;
      if ( LastError > 0 )
        v12 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_35;
    }
    v3 = pSecurityDescriptor;
  }
  v12 = CSecurityInformation::SetSecurity(this, a2, v3);
LABEL_35:
  if ( v6 )
    LocalFree(v6);
  if ( v7 )
    LocalFree(v7);
  return v12;
}

```

## disassembly

```asm
0x180008950  mov     [rsp-38h+arg_0], rbx
0x180008955  push    rbp
0x180008956  push    rsi
0x180008957  push    rdi
0x180008958  push    r12
0x18000895a  push    r13
0x18000895c  push    r14
0x18000895e  push    r15
0x180008960  mov     rbp, rsp
0x180008963  sub     rsp, 70h
0x180008967  xor     r15d, r15d
0x18000896a  xor     eax, eax
0x18000896c  mov     [rbp+pDacl], r15
0x180008970  xorps   xmm0, xmm0
0x180008973  mov     [rbp+pSacl], r15
0x180008977  mov     rbx, r8
0x18000897a  mov     [rbp+pControl], r15
0x18000897e  mov     r14d, edx
0x180008981  mov     [rbp+pOwner], r15
0x180008985  mov     r13, rcx
0x180008988  mov     [rbp+bDaclPresent], r15d
0x18000898c  mov     edi, r15d
0x18000898f  mov     [rbp+bDaclDefaulted], r15d
0x180008993  mov     esi, r15d
0x180008996  mov     [rbp+var_10], rax
0x18000899a  movups  [rbp+pSecurityDescriptor], xmm0
0x18000899e  movups  [rbp+var_20], xmm0
0x1800089a2  test    r8, r8
0x1800089a5  jnz     short loc_1800089B1
0x1800089a7  mov     eax, 80004003h
0x1800089ac  jmp     loc_180008BBE
0x1800089b1  test    r14d, r14d
0x1800089b4  jz      loc_180008BB9
0x1800089ba  mov     rcx, rbx; pSecurityDescriptor
0x1800089bd  call    cs:__imp_IsValidSecurityDescriptor
0x1800089c3  test    eax, eax
0x1800089c5  jz      loc_180008BB9
0x1800089cb  mov     r12d, r14d
0x1800089ce  and     r12d, 4
0x1800089d2  jz      short loc_180008A11
0x1800089d4  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x1800089d8  mov     rcx, rbx; pSecurityDescriptor
0x1800089db  lea     r8, [rbp+pDacl]; pDacl
0x1800089df  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x1800089e3  call    cs:__imp_GetSecurityDescriptorDacl
0x1800089e9  test    eax, eax
0x1800089eb  jz      short loc_180008A11
0x1800089ed  cmp     [rbp+bDaclPresent], r15d
0x1800089f1  jz      short loc_180008A11
0x1800089f3  mov     rcx, [rbp+pDacl]; Src
0x1800089f7  lea     rdx, [rbp+pControl]; struct _ACL **
0x1800089fb  call    ?MungeAclForPrinter@@YAHPEAU_ACL@@PEAPEAU1@@Z; MungeAclForPrinter(_ACL *,_ACL * *)
0x180008a00  mov     rdi, [rbp+pControl]
0x180008a04  test    eax, eax
0x180008a06  jz      short loc_180008A11
0x180008a08  test    rdi, rdi
0x180008a0b  jz      short loc_180008A11
0x180008a0d  mov     [rbp+pDacl], rdi
0x180008a11  mov     r15d, r14d
0x180008a14  and     r15d, 8
0x180008a18  jz      short loc_180008A56
0x180008a1a  lea     r9, [rbp+bDaclDefaulted]; lpbSaclDefaulted
0x180008a1e  mov     rcx, rbx; pSecurityDescriptor
0x180008a21  lea     r8, [rbp+pSacl]; pSacl
0x180008a25  lea     rdx, [rbp+bDaclPresent]; lpbSaclPresent
0x180008a29  call    cs:__imp_GetSecurityDescriptorSacl
0x180008a2f  test    eax, eax
0x180008a31  jz      short loc_180008A56
0x180008a33  cmp     [rbp+bDaclPresent], esi
0x180008a36  jz      short loc_180008A56
0x180008a38  mov     rcx, [rbp+pSacl]; Src
0x180008a3c  lea     rdx, [rbp+pOwner]; struct _ACL **
0x180008a40  call    ?MungeAclForPrinter@@YAHPEAU_ACL@@PEAPEAU1@@Z; MungeAclForPrinter(_ACL *,_ACL * *)
0x180008a45  mov     rsi, [rbp+pOwner]
0x180008a49  test    eax, eax
0x180008a4b  jz      short loc_180008A56
0x180008a4d  test    rsi, rsi
0x180008a50  jz      short loc_180008A56
0x180008a52  mov     [rbp+pSacl], rsi
0x180008a56  test    rdi, rdi
0x180008a59  jnz     short loc_180008A64
0x180008a5b  test    rsi, rsi
0x180008a5e  jz      loc_180008B89
0x180008a64  xor     eax, eax
0x180008a66  mov     [rbp+pOwner], 0
0x180008a6e  lea     r8, [rbp+dwRevision]; lpdwRevision
0x180008a72  mov     word ptr [rbp+pControl], ax
0x180008a76  lea     rdx, [rbp+pControl]; pControl
0x180008a7a  mov     [rbp+dwRevision], 0
0x180008a81  mov     rcx, rbx; pSecurityDescriptor
0x180008a84  call    cs:__imp_GetSecurityDescriptorControl
0x180008a8a  test    eax, eax
0x180008a8c  jnz     short loc_180008AAC
0x180008a8e  call    cs:__imp_GetLastError
0x180008a94  mov     ebx, eax
0x180008a96  test    eax, eax
0x180008a98  jle     loc_180008B99
0x180008a9e  movzx   ebx, ax
0x180008aa1  or      ebx, 80070000h
0x180008aa7  jmp     loc_180008B99
0x180008aac  mov     edx, [rbp+dwRevision]; dwRevision
0x180008aaf  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x180008ab3  call    cs:__imp_InitializeSecurityDescriptor
0x180008ab9  test    eax, eax
0x180008abb  jz      short loc_180008A8E
0x180008abd  movzx   eax, word ptr [rbp+pControl]
0x180008ac1  mov     ecx, 7FFFh
0x180008ac6  and     ax, cx
0x180008ac9  mov     word ptr [rbp+pSecurityDescriptor+2], ax
0x180008acd  test    r14b, 1
0x180008ad1  jz      short loc_180008AFE
0x180008ad3  lea     r8, [rbp+bDaclDefaulted]; lpbOwnerDefaulted
0x180008ad7  mov     rcx, rbx; pSecurityDescriptor
0x180008ada  lea     rdx, [rbp+pOwner]; pOwner
0x180008ade  call    cs:__imp_GetSecurityDescriptorOwner
0x180008ae4  test    eax, eax
0x180008ae6  jz      short loc_180008AFE
0x180008ae8  mov     r8d, [rbp+bDaclDefaulted]; bOwnerDefaulted
0x180008aec  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x180008af0  mov     rdx, [rbp+pOwner]; pOwner
0x180008af4  call    cs:__imp_SetSecurityDescriptorOwner
0x180008afa  test    eax, eax
0x180008afc  jz      short loc_180008A8E
0x180008afe  test    r14b, 2
0x180008b02  jz      short loc_180008B33
0x180008b04  lea     r8, [rbp+bDaclDefaulted]; lpbGroupDefaulted
0x180008b08  mov     rcx, rbx; pSecurityDescriptor
0x180008b0b  lea     rdx, [rbp+pOwner]; pGroup
0x180008b0f  call    cs:__imp_GetSecurityDescriptorGroup
0x180008b15  test    eax, eax
0x180008b17  jz      short loc_180008B33
0x180008b19  mov     r8d, [rbp+bDaclDefaulted]; bGroupDefaulted
0x180008b1d  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x180008b21  mov     rdx, [rbp+pOwner]; pGroup
0x180008b25  call    cs:__imp_SetSecurityDescriptorGroup
0x180008b2b  test    eax, eax
0x180008b2d  jz      loc_180008A8E
0x180008b33  test    r15d, r15d
0x180008b36  jz      short loc_180008B5C
0x180008b38  movzx   edx, word ptr [rbp+pControl]
0x180008b3c  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x180008b40  mov     r8, [rbp+pSacl]; pSacl
0x180008b44  mov     r9d, edx
0x180008b47  and     r9d, 20h; bSaclDefaulted
0x180008b4b  and     edx, 10h; bSaclPresent
0x180008b4e  call    cs:__imp_SetSecurityDescriptorSacl
0x180008b54  test    eax, eax
0x180008b56  jz      loc_180008A8E
0x180008b5c  test    r12d, r12d
0x180008b5f  jz      short loc_180008B85
0x180008b61  movzx   edx, word ptr [rbp+pControl]
0x180008b65  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x180008b69  mov     r8, [rbp+pDacl]; pDacl
0x180008b6d  mov     r9d, edx
0x180008b70  and     r9d, 8; bDaclDefaulted
0x180008b74  and     edx, 4; bDaclPresent
0x180008b77  call    cs:__imp_SetSecurityDescriptorDacl
0x180008b7d  test    eax, eax
0x180008b7f  jz      loc_180008A8E
0x180008b85  lea     rbx, [rbp+pSecurityDescriptor]
0x180008b89  mov     r8, rbx; void *
0x180008b8c  mov     edx, r14d; unsigned int
0x180008b8f  mov     rcx, r13; this
0x180008b92  call    ?SetSecurity@CSecurityInformation@@UEAAJKPEAX@Z; CSecurityInformation::SetSecurity(ulong,void *)
0x180008b97  mov     ebx, eax
0x180008b99  test    rdi, rdi
0x180008b9c  jz      short loc_180008BA7
0x180008b9e  mov     rcx, rdi; hMem
0x180008ba1  call    cs:__imp_LocalFree
0x180008ba7  test    rsi, rsi
0x180008baa  jz      short loc_180008BB5
0x180008bac  mov     rcx, rsi; hMem
0x180008baf  call    cs:__imp_LocalFree
0x180008bb5  mov     eax, ebx
0x180008bb7  jmp     short loc_180008BBE
0x180008bb9  mov     eax, 80070057h
0x180008bbe  mov     rbx, [rsp+70h+arg_0]
0x180008bc6  add     rsp, 70h
0x180008bca  pop     r15
0x180008bcc  pop     r14
0x180008bce  pop     r13
0x180008bd0  pop     r12
0x180008bd2  pop     rdi
0x180008bd3  pop     rsi
0x180008bd4  pop     rbp
0x180008bd5  retn
```
