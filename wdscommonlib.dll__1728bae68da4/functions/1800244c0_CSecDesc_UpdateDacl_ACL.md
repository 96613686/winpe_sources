# CSecDesc::UpdateDacl(_ACL *)

- ea: `0x1800244c0`
- end: `0x1800246f9`
- name: `?UpdateDacl@CSecDesc@@QEAAKPEAU_ACL@@@Z`
- size: `569`
- prototype: `unsigned int __fastcall(void **this, PACL pDacl)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x18000214c`
- `0x180024310`
- `0x1800244c0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180024682`
- `msvcrt!??3@YAXPEAX@Z` at `0x180024696`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800246aa`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800246be`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800246d2`
- `msvcrt!??3@YAXPEAX@Z` at `0x180024682`
- `msvcrt!??3@YAXPEAX@Z` at `0x180024696`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800246aa`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800246be`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800246d2`
- `KERNEL32!GetLastError` at `0x180024547`
- `KERNEL32!GetLastError` at `0x180024647`
- `KERNEL32!GetLastError` at `0x180024547`
- `KERNEL32!GetLastError` at `0x180024647`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180024662`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180024662`
- `ADVAPI32!MakeAbsoluteSD` at `0x180024534`
- `ADVAPI32!MakeAbsoluteSD` at `0x180024637`
- `ADVAPI32!MakeAbsoluteSD` at `0x180024534`
- `ADVAPI32!MakeAbsoluteSD` at `0x180024637`

## pseudocode

```c
__int64 __fastcall CSecDesc::UpdateDacl(void **this, PACL pDacl)
{
  void *v4; // rcx
  struct _ACL *v5; // r12
  struct _ACL *pSacl; // r15
  void *pOwner; // r14
  void *pPrimaryGroup; // rdi
  unsigned int v9; // ebx
  void *v10; // rsi
  DWORD LastError; // eax
  DWORD dwDaclSize; // [rsp+60h] [rbp-10h] BYREF
  DWORD dwAbsoluteSecurityDescriptorSize[3]; // [rsp+64h] [rbp-Ch] BYREF
  DWORD dwPrimaryGroupSize; // [rsp+B0h] [rbp+40h] BYREF
  DWORD dwOwnerSize; // [rsp+C0h] [rbp+50h] BYREF
  DWORD dwSaclSize; // [rsp+C8h] [rbp+58h] BYREF

  v4 = *this;
  v5 = 0;
  dwAbsoluteSecurityDescriptorSize[0] = 0;
  pSacl = 0;
  dwDaclSize = 0;
  pOwner = 0;
  dwSaclSize = 0;
  pPrimaryGroup = 0;
  dwOwnerSize = 0;
  dwPrimaryGroupSize = 0;
  MakeAbsoluteSD(
    v4,
    0,
    dwAbsoluteSecurityDescriptorSize,
    0,
    &dwDaclSize,
    0,
    &dwSaclSize,
    0,
    &dwOwnerSize,
    0,
    &dwPrimaryGroupSize);
  if ( dwAbsoluteSecurityDescriptorSize[0] )
  {
    v10 = operator new[](dwAbsoluteSecurityDescriptorSize[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v10 )
    {
      if ( dwDaclSize
        && (v5 = (struct _ACL *)operator new[](dwDaclSize, (const struct std::nothrow_t *)&std::nothrow)) == 0
        || dwSaclSize
        && (pSacl = (struct _ACL *)operator new[](dwSaclSize, (const struct std::nothrow_t *)&std::nothrow)) == 0
        || dwOwnerSize && (pOwner = operator new[](dwOwnerSize, (const struct std::nothrow_t *)&std::nothrow)) == 0
        || dwPrimaryGroupSize
        && (pPrimaryGroup = operator new[](dwPrimaryGroupSize, (const struct std::nothrow_t *)&std::nothrow)) == 0 )
      {
        v9 = 8;
      }
      else
      {
        if ( MakeAbsoluteSD(
               *this,
               v10,
               dwAbsoluteSecurityDescriptorSize,
               v5,
               &dwDaclSize,
               pSacl,
               &dwSaclSize,
               pOwner,
               &dwOwnerSize,
               pPrimaryGroup,
               &dwPrimaryGroupSize)
          && SetSecurityDescriptorDacl(v10, 1, pDacl, 0) )
        {
          LastError = CSecDesc::Initialize(this, v10);
        }
        else
        {
          LastError = GetLastError();
        }
        v9 = LastError;
      }
      operator delete(v10);
      if ( v5 )
        operator delete(v5);
      if ( pSacl )
        operator delete(pSacl);
      if ( pOwner )
        operator delete(pOwner);
      if ( pPrimaryGroup )
        operator delete(pPrimaryGroup);
    }
    else
    {
      return 8;
    }
  }
  else
  {
    return GetLastError();
  }
  return v9;
}

```

## disassembly

```asm
0x1800244c0  mov     r11, rsp
0x1800244c3  mov     [r11+10h], rbx
0x1800244c7  push    rbp
0x1800244c8  push    rsi
0x1800244c9  push    rdi
0x1800244ca  push    r12
0x1800244cc  push    r13
0x1800244ce  push    r14
0x1800244d0  push    r15
0x1800244d2  mov     rbp, rsp
0x1800244d5  sub     rsp, 70h
0x1800244d9  xor     esi, esi
0x1800244db  lea     rax, [rbp+dwPrimaryGroupSize]
0x1800244df  mov     [r11-58h], rax
0x1800244e3  lea     r8, [rbp+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x1800244e7  mov     [r11-60h], rsi
0x1800244eb  lea     rax, [rbp+dwOwnerSize]
0x1800244ef  mov     [r11-68h], rax
0x1800244f3  mov     r13, rdx
0x1800244f6  mov     [r11-70h], rsi
0x1800244fa  lea     rax, [rbp+dwSaclSize]
0x1800244fe  mov     [r11-78h], rax
0x180024502  mov     rbx, rcx
0x180024505  mov     rcx, [rcx]; pSelfRelativeSecurityDescriptor
0x180024508  lea     rax, [rbp+dwDaclSize]
0x18002450c  mov     [r11-80h], rsi
0x180024510  xor     r9d, r9d; pDacl
0x180024513  xor     edx, edx; pAbsoluteSecurityDescriptor
0x180024515  mov     [rsp+70h+lpdwDaclSize], rax; lpdwDaclSize
0x18002451a  mov     r12d, esi
0x18002451d  mov     [rbp+dwAbsoluteSecurityDescriptorSize], esi
0x180024520  mov     r15d, esi
0x180024523  mov     [rbp+dwDaclSize], esi
0x180024526  mov     r14d, esi
0x180024529  mov     [rbp+dwSaclSize], esi
0x18002452c  mov     edi, esi
0x18002452e  mov     [rbp+dwOwnerSize], esi
0x180024531  mov     [rbp+dwPrimaryGroupSize], esi
0x180024534  call    cs:__imp_MakeAbsoluteSD
0x18002453b  nop     dword ptr [rax+rax+00h]
0x180024540  mov     eax, [rbp+dwAbsoluteSecurityDescriptorSize]
0x180024543  test    eax, eax
0x180024545  jnz     short loc_18002455A
0x180024547  call    cs:__imp_GetLastError
0x18002454e  nop     dword ptr [rax+rax+00h]
0x180024553  mov     ebx, eax
0x180024555  jmp     loc_1800246DE
0x18002455a  mov     rcx, rax; unsigned __int64
0x18002455d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180024564  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180024569  mov     rsi, rax
0x18002456c  test    rax, rax
0x18002456f  jnz     short loc_180024579
0x180024571  lea     ebx, [rax+8]
0x180024574  jmp     loc_1800246DE
0x180024579  mov     eax, [rbp+dwDaclSize]
0x18002457c  test    eax, eax
0x18002457e  jz      short loc_1800245A0
0x180024580  mov     ecx, eax; unsigned __int64
0x180024582  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180024589  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18002458e  mov     r12, rax
0x180024591  test    rax, rax
0x180024594  jnz     short loc_1800245A0
0x180024596  mov     ebx, 8
0x18002459b  jmp     loc_18002467F
0x1800245a0  mov     eax, [rbp+dwSaclSize]
0x1800245a3  test    eax, eax
0x1800245a5  jz      short loc_1800245BD
0x1800245a7  mov     ecx, eax; unsigned __int64
0x1800245a9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800245b0  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800245b5  mov     r15, rax
0x1800245b8  test    rax, rax
0x1800245bb  jz      short loc_180024596
0x1800245bd  mov     eax, [rbp+dwOwnerSize]
0x1800245c0  test    eax, eax
0x1800245c2  jz      short loc_1800245DA
0x1800245c4  mov     ecx, eax; unsigned __int64
0x1800245c6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800245cd  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800245d2  mov     r14, rax
0x1800245d5  test    rax, rax
0x1800245d8  jz      short loc_180024596
0x1800245da  mov     eax, [rbp+dwPrimaryGroupSize]
0x1800245dd  test    eax, eax
0x1800245df  jz      short loc_1800245F7
0x1800245e1  mov     ecx, eax; unsigned __int64
0x1800245e3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800245ea  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800245ef  mov     rdi, rax
0x1800245f2  test    rax, rax
0x1800245f5  jz      short loc_180024596
0x1800245f7  mov     rcx, [rbx]; pSelfRelativeSecurityDescriptor
0x1800245fa  lea     rax, [rbp+dwPrimaryGroupSize]
0x1800245fe  mov     [rsp+70h+lpdwPrimaryGroupSize], rax; lpdwPrimaryGroupSize
0x180024603  lea     r8, [rbp+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x180024607  mov     [rsp+70h+pPrimaryGroup], rdi; pPrimaryGroup
0x18002460c  lea     rax, [rbp+dwOwnerSize]
0x180024610  mov     [rsp+70h+lpdwOwnerSize], rax; lpdwOwnerSize
0x180024615  mov     r9, r12; pDacl
0x180024618  mov     [rsp+70h+pOwner], r14; pOwner
0x18002461d  lea     rax, [rbp+dwSaclSize]
0x180024621  mov     [rsp+70h+lpdwSaclSize], rax; lpdwSaclSize
0x180024626  mov     rdx, rsi; pAbsoluteSecurityDescriptor
0x180024629  lea     rax, [rbp+dwDaclSize]
0x18002462d  mov     [rsp+70h+pSacl], r15; pSacl
0x180024632  mov     [rsp+70h+lpdwDaclSize], rax; lpdwDaclSize
0x180024637  call    cs:__imp_MakeAbsoluteSD
0x18002463e  nop     dword ptr [rax+rax+00h]
0x180024643  test    eax, eax
0x180024645  jnz     short loc_180024655
0x180024647  call    cs:__imp_GetLastError
0x18002464e  nop     dword ptr [rax+rax+00h]
0x180024653  jmp     short loc_18002467D
0x180024655  xor     r9d, r9d; bDaclDefaulted
0x180024658  mov     r8, r13; pDacl
0x18002465b  mov     rcx, rsi; pSecurityDescriptor
0x18002465e  lea     edx, [r9+1]; bDaclPresent
0x180024662  call    cs:__imp_SetSecurityDescriptorDacl
0x180024669  nop     dword ptr [rax+rax+00h]
0x18002466e  test    eax, eax
0x180024670  jz      short loc_180024647
0x180024672  mov     rdx, rsi; Src
0x180024675  mov     rcx, rbx; this
0x180024678  call    ?Initialize@CSecDesc@@QEAAKPEAX@Z; CSecDesc::Initialize(void *)
0x18002467d  mov     ebx, eax
0x18002467f  mov     rcx, rsi
0x180024682  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180024689  nop     dword ptr [rax+rax+00h]
0x18002468e  test    r12, r12
0x180024691  jz      short loc_1800246A2
0x180024693  mov     rcx, r12
0x180024696  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002469d  nop     dword ptr [rax+rax+00h]
0x1800246a2  test    r15, r15
0x1800246a5  jz      short loc_1800246B6
0x1800246a7  mov     rcx, r15
0x1800246aa  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800246b1  nop     dword ptr [rax+rax+00h]
0x1800246b6  test    r14, r14
0x1800246b9  jz      short loc_1800246CA
0x1800246bb  mov     rcx, r14
0x1800246be  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800246c5  nop     dword ptr [rax+rax+00h]
0x1800246ca  test    rdi, rdi
0x1800246cd  jz      short loc_1800246DE
0x1800246cf  mov     rcx, rdi
0x1800246d2  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800246d9  nop     dword ptr [rax+rax+00h]
0x1800246de  mov     eax, ebx
0x1800246e0  mov     rbx, [rsp+70h+arg_8]
0x1800246e8  add     rsp, 70h
0x1800246ec  pop     r15
0x1800246ee  pop     r14
0x1800246f0  pop     r13
0x1800246f2  pop     r12
0x1800246f4  pop     rdi
0x1800246f5  pop     rsi
0x1800246f6  pop     rbp
0x1800246f7  retn
```
