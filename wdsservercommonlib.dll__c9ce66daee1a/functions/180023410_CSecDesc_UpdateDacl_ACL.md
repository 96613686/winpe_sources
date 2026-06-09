# CSecDesc::UpdateDacl(_ACL *)

- ea: `0x180023410`
- end: `0x180023626`
- name: `?UpdateDacl@CSecDesc@@QEAAKPEAU_ACL@@@Z`
- size: `534`
- prototype: `unsigned int __fastcall(void **this, PACL pDacl)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x18000179c`
- `0x180023270`
- `0x180023410`
- `0x18002e468`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180023497`
- `KERNEL32!GetLastError` at `0x180023597`
- `KERNEL32!GetLastError` at `0x180023497`
- `KERNEL32!GetLastError` at `0x180023597`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x1800235b2`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x1800235b2`
- `ADVAPI32!MakeAbsoluteSD` at `0x180023484`
- `ADVAPI32!MakeAbsoluteSD` at `0x180023587`
- `ADVAPI32!MakeAbsoluteSD` at `0x180023484`
- `ADVAPI32!MakeAbsoluteSD` at `0x180023587`

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
0x180023410  mov     r11, rsp
0x180023413  mov     [r11+10h], rbx
0x180023417  push    rbp
0x180023418  push    rsi
0x180023419  push    rdi
0x18002341a  push    r12
0x18002341c  push    r13
0x18002341e  push    r14
0x180023420  push    r15
0x180023422  mov     rbp, rsp
0x180023425  sub     rsp, 70h
0x180023429  xor     esi, esi
0x18002342b  lea     rax, [rbp+dwPrimaryGroupSize]
0x18002342f  mov     [r11-58h], rax
0x180023433  lea     r8, [rbp+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x180023437  mov     [r11-60h], rsi
0x18002343b  lea     rax, [rbp+dwOwnerSize]
0x18002343f  mov     [r11-68h], rax
0x180023443  mov     r13, rdx
0x180023446  mov     [r11-70h], rsi
0x18002344a  lea     rax, [rbp+dwSaclSize]
0x18002344e  mov     [r11-78h], rax
0x180023452  mov     rbx, rcx
0x180023455  mov     rcx, [rcx]; pSelfRelativeSecurityDescriptor
0x180023458  lea     rax, [rbp+dwDaclSize]
0x18002345c  mov     [r11-80h], rsi
0x180023460  xor     r9d, r9d; pDacl
0x180023463  xor     edx, edx; pAbsoluteSecurityDescriptor
0x180023465  mov     [rsp+70h+lpdwDaclSize], rax; lpdwDaclSize
0x18002346a  mov     r12d, esi
0x18002346d  mov     [rbp+dwAbsoluteSecurityDescriptorSize], esi
0x180023470  mov     r15d, esi
0x180023473  mov     [rbp+dwDaclSize], esi
0x180023476  mov     r14d, esi
0x180023479  mov     [rbp+dwSaclSize], esi
0x18002347c  mov     edi, esi
0x18002347e  mov     [rbp+dwOwnerSize], esi
0x180023481  mov     [rbp+dwPrimaryGroupSize], esi
0x180023484  call    cs:__imp_MakeAbsoluteSD
0x18002348b  nop     dword ptr [rax+rax+00h]
0x180023490  mov     eax, [rbp+dwAbsoluteSecurityDescriptorSize]
0x180023493  test    eax, eax
0x180023495  jnz     short loc_1800234AA
0x180023497  call    cs:__imp_GetLastError
0x18002349e  nop     dword ptr [rax+rax+00h]
0x1800234a3  mov     ebx, eax
0x1800234a5  jmp     loc_18002360B
0x1800234aa  mov     rcx, rax; unsigned __int64
0x1800234ad  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800234b4  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800234b9  mov     rsi, rax
0x1800234bc  test    rax, rax
0x1800234bf  jnz     short loc_1800234C9
0x1800234c1  lea     ebx, [rax+8]
0x1800234c4  jmp     loc_18002360B
0x1800234c9  mov     eax, [rbp+dwDaclSize]
0x1800234cc  test    eax, eax
0x1800234ce  jz      short loc_1800234F0
0x1800234d0  mov     ecx, eax; unsigned __int64
0x1800234d2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800234d9  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800234de  mov     r12, rax
0x1800234e1  test    rax, rax
0x1800234e4  jnz     short loc_1800234F0
0x1800234e6  mov     ebx, 8
0x1800234eb  jmp     loc_1800235CF
0x1800234f0  mov     eax, [rbp+dwSaclSize]
0x1800234f3  test    eax, eax
0x1800234f5  jz      short loc_18002350D
0x1800234f7  mov     ecx, eax; unsigned __int64
0x1800234f9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180023500  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180023505  mov     r15, rax
0x180023508  test    rax, rax
0x18002350b  jz      short loc_1800234E6
0x18002350d  mov     eax, [rbp+dwOwnerSize]
0x180023510  test    eax, eax
0x180023512  jz      short loc_18002352A
0x180023514  mov     ecx, eax; unsigned __int64
0x180023516  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002351d  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180023522  mov     r14, rax
0x180023525  test    rax, rax
0x180023528  jz      short loc_1800234E6
0x18002352a  mov     eax, [rbp+dwPrimaryGroupSize]
0x18002352d  test    eax, eax
0x18002352f  jz      short loc_180023547
0x180023531  mov     ecx, eax; unsigned __int64
0x180023533  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002353a  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18002353f  mov     rdi, rax
0x180023542  test    rax, rax
0x180023545  jz      short loc_1800234E6
0x180023547  mov     rcx, [rbx]; pSelfRelativeSecurityDescriptor
0x18002354a  lea     rax, [rbp+dwPrimaryGroupSize]
0x18002354e  mov     [rsp+70h+lpdwPrimaryGroupSize], rax; lpdwPrimaryGroupSize
0x180023553  lea     r8, [rbp+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x180023557  mov     [rsp+70h+pPrimaryGroup], rdi; pPrimaryGroup
0x18002355c  lea     rax, [rbp+dwOwnerSize]
0x180023560  mov     [rsp+70h+lpdwOwnerSize], rax; lpdwOwnerSize
0x180023565  mov     r9, r12; pDacl
0x180023568  mov     [rsp+70h+pOwner], r14; pOwner
0x18002356d  lea     rax, [rbp+dwSaclSize]
0x180023571  mov     [rsp+70h+lpdwSaclSize], rax; lpdwSaclSize
0x180023576  mov     rdx, rsi; pAbsoluteSecurityDescriptor
0x180023579  lea     rax, [rbp+dwDaclSize]
0x18002357d  mov     [rsp+70h+pSacl], r15; pSacl
0x180023582  mov     [rsp+70h+lpdwDaclSize], rax; lpdwDaclSize
0x180023587  call    cs:__imp_MakeAbsoluteSD
0x18002358e  nop     dword ptr [rax+rax+00h]
0x180023593  test    eax, eax
0x180023595  jnz     short loc_1800235A5
0x180023597  call    cs:__imp_GetLastError
0x18002359e  nop     dword ptr [rax+rax+00h]
0x1800235a3  jmp     short loc_1800235CD
0x1800235a5  xor     r9d, r9d; bDaclDefaulted
0x1800235a8  mov     r8, r13; pDacl
0x1800235ab  mov     rcx, rsi; pSecurityDescriptor
0x1800235ae  lea     edx, [r9+1]; bDaclPresent
0x1800235b2  call    cs:__imp_SetSecurityDescriptorDacl
0x1800235b9  nop     dword ptr [rax+rax+00h]
0x1800235be  test    eax, eax
0x1800235c0  jz      short loc_180023597
0x1800235c2  mov     rdx, rsi; Src
0x1800235c5  mov     rcx, rbx; this
0x1800235c8  call    ?Initialize@CSecDesc@@QEAAKPEAX@Z; CSecDesc::Initialize(void *)
0x1800235cd  mov     ebx, eax
0x1800235cf  mov     rcx, rsi; lpMem
0x1800235d2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800235d7  test    r12, r12
0x1800235da  jz      short loc_1800235E4
0x1800235dc  mov     rcx, r12; lpMem
0x1800235df  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800235e4  test    r15, r15
0x1800235e7  jz      short loc_1800235F1
0x1800235e9  mov     rcx, r15; lpMem
0x1800235ec  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800235f1  test    r14, r14
0x1800235f4  jz      short loc_1800235FE
0x1800235f6  mov     rcx, r14; lpMem
0x1800235f9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800235fe  test    rdi, rdi
0x180023601  jz      short loc_18002360B
0x180023603  mov     rcx, rdi; lpMem
0x180023606  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002360b  mov     eax, ebx
0x18002360d  mov     rbx, [rsp+70h+arg_8]
0x180023615  add     rsp, 70h
0x180023619  pop     r15
0x18002361b  pop     r14
0x18002361d  pop     r13
0x18002361f  pop     r12
0x180023621  pop     rdi
0x180023622  pop     rsi
0x180023623  pop     rbp
0x180023624  retn
```
