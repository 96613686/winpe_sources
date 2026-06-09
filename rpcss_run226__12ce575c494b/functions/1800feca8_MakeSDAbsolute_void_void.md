# MakeSDAbsolute(void *,void * *)

- ea: `0x1800feca8`
- end: `0x1800feec8`
- name: `?MakeSDAbsolute@@YAKPEAXPEAPEAX@Z`
- size: `544`
- prototype: `unsigned int __fastcall(PSECURITY_DESCRIPTOR pSelfRelativeSecurityDescriptor, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18009617c`

## callees

- `0x1800b3128`
- `0x1800f6eac`
- `0x1800feca8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fed0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fee3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fed0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fee3a`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x1800fed03`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x1800fed03`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x1800fed68`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x1800fed68`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x1800fed8a`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x1800fed8a`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800fed3d`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800fed3d`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x1800fedf5`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x1800fee91`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x1800fedf5`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x1800fee91`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800fed76`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800fed9c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800fed76`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800fed9c`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800fee30`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800fee30`
- `KERNELBASE!LocalAlloc` at `0x1800fee00`
- `KERNELBASE!LocalAlloc` at `0x1800fee00`

## pseudocode

```c
DWORD __fastcall MakeSDAbsolute(PSECURITY_DESCRIPTOR pSelfRelativeSecurityDescriptor, void **a2)
{
  HLOCAL v5; // rax
  void *v6; // rbx
  DWORD LastError; // ebx
  WINBOOL bSaclDefaulted; // [rsp+60h] [rbp+7h] BYREF
  DWORD dwPrimaryGroupSize; // [rsp+64h] [rbp+Bh] BYREF
  DWORD dwOwnerSize; // [rsp+68h] [rbp+Fh] BYREF
  DWORD dwSaclSize; // [rsp+6Ch] [rbp+13h] BYREF
  DWORD dwDaclSize; // [rsp+70h] [rbp+17h] BYREF
  PSID pGroup; // [rsp+78h] [rbp+1Fh] BYREF
  PSID pOwner; // [rsp+80h] [rbp+27h] BYREF
  PACL pSacl; // [rsp+88h] [rbp+2Fh] BYREF
  PACL pDacl; // [rsp+90h] [rbp+37h] BYREF
  HLOCAL v17; // [rsp+98h] [rbp+3Fh] BYREF
  DWORD dwAbsoluteSecurityDescriptorSize; // [rsp+D0h] [rbp+77h] BYREF
  WINBOOL bSaclPresent; // [rsp+D8h] [rbp+7Fh] BYREF

  dwAbsoluteSecurityDescriptorSize = 0;
  dwDaclSize = 0;
  dwSaclSize = 0;
  dwOwnerSize = 0;
  dwPrimaryGroupSize = 0;
  pDacl = 0;
  pSacl = 0;
  pOwner = 0;
  pGroup = 0;
  bSaclPresent = 0;
  bSaclDefaulted = 0;
  if ( !GetSecurityDescriptorSacl(pSelfRelativeSecurityDescriptor, &bSaclPresent, &pSacl, &bSaclDefaulted) )
    return GetLastError();
  if ( pSacl && bSaclPresent )
    dwSaclSize = pSacl->AclSize;
  if ( !GetSecurityDescriptorDacl(pSelfRelativeSecurityDescriptor, &bSaclPresent, &pDacl, &bSaclDefaulted) )
    return GetLastError();
  if ( pDacl && bSaclPresent )
    dwDaclSize = pDacl->AclSize;
  if ( !GetSecurityDescriptorOwner(pSelfRelativeSecurityDescriptor, &pOwner, &bSaclDefaulted) )
    return GetLastError();
  dwOwnerSize = GetLengthSid(pOwner);
  if ( !GetSecurityDescriptorGroup(pSelfRelativeSecurityDescriptor, &pGroup, &bSaclDefaulted) )
    return GetLastError();
  dwPrimaryGroupSize = GetLengthSid(pGroup);
  dwAbsoluteSecurityDescriptorSize = 0;
  MakeAbsoluteSD(
    pSelfRelativeSecurityDescriptor,
    0,
    &dwAbsoluteSecurityDescriptorSize,
    pDacl,
    &dwDaclSize,
    pSacl,
    &dwSaclSize,
    pOwner,
    &dwOwnerSize,
    pGroup,
    &dwPrimaryGroupSize);
  v5 = LocalAlloc(0, dwAbsoluteSecurityDescriptorSize);
  v17 = v5;
  v6 = v5;
  if ( v5 )
  {
    memset_0(v5, 0, dwAbsoluteSecurityDescriptorSize);
    if ( InitializeSecurityDescriptor(v6, 1u)
      && MakeAbsoluteSD(
           pSelfRelativeSecurityDescriptor,
           v6,
           &dwAbsoluteSecurityDescriptorSize,
           pDacl,
           &dwDaclSize,
           pSacl,
           &dwSaclSize,
           pOwner,
           &dwOwnerSize,
           pGroup,
           &dwPrimaryGroupSize) )
    {
      *a2 = v6;
      LastError = 0;
      v17 = 0;
    }
    else
    {
      LastError = GetLastError();
    }
  }
  else
  {
    LastError = 14;
  }
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_DestroyPrivateObjectSecurity_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v17);
  return LastError;
}

```

## disassembly

```asm
0x1800feca8  mov     [rsp-8+arg_0], rbx
0x1800fecad  mov     [rsp-8+arg_8], rsi
0x1800fecb2  push    rbp
0x1800fecb3  push    rdi
0x1800fecb4  push    r14
0x1800fecb6  lea     rbp, [rsp-47h]
0x1800fecbb  sub     rsp, 0A0h
0x1800fecc2  xor     r14d, r14d
0x1800fecc5  lea     r9, [rbp+57h+bSaclDefaulted]; lpbSaclDefaulted
0x1800fecc9  mov     rsi, rdx
0x1800feccc  mov     [rbp+57h+dwAbsoluteSecurityDescriptorSize], r14d
0x1800fecd0  lea     rdx, [rbp+57h+bSaclPresent]; lpbSaclPresent
0x1800fecd4  mov     [rbp+57h+dwDaclSize], r14d
0x1800fecd8  lea     r8, [rbp+57h+pSacl]; pSacl
0x1800fecdc  mov     [rbp+57h+dwSaclSize], r14d
0x1800fece0  mov     [rbp+57h+dwOwnerSize], r14d
0x1800fece4  mov     rdi, rcx
0x1800fece7  mov     [rbp+57h+dwPrimaryGroupSize], r14d
0x1800feceb  mov     [rbp+57h+pDacl], r14
0x1800fecef  mov     [rbp+57h+pSacl], r14
0x1800fecf3  mov     [rbp+57h+pOwner], r14
0x1800fecf7  mov     [rbp+57h+pGroup], r14
0x1800fecfb  mov     [rbp+57h+bSaclPresent], r14d
0x1800fecff  mov     [rbp+57h+bSaclDefaulted], r14d
0x1800fed03  call    cs:__imp_GetSecurityDescriptorSacl
0x1800fed09  test    eax, eax
0x1800fed0b  jnz     short loc_1800FED18
0x1800fed0d  call    cs:__imp_GetLastError
0x1800fed13  jmp     loc_1800FEEB0
0x1800fed18  mov     rax, [rbp+57h+pSacl]
0x1800fed1c  test    rax, rax
0x1800fed1f  jz      short loc_1800FED2E
0x1800fed21  cmp     [rbp+57h+bSaclPresent], r14d
0x1800fed25  jz      short loc_1800FED2E
0x1800fed27  movzx   eax, word ptr [rax+2]
0x1800fed2b  mov     [rbp+57h+dwSaclSize], eax
0x1800fed2e  lea     r9, [rbp+57h+bSaclDefaulted]; lpbDaclDefaulted
0x1800fed32  mov     rcx, rdi; pSecurityDescriptor
0x1800fed35  lea     r8, [rbp+57h+pDacl]; pDacl
0x1800fed39  lea     rdx, [rbp+57h+bSaclPresent]; lpbDaclPresent
0x1800fed3d  call    cs:__imp_GetSecurityDescriptorDacl
0x1800fed43  test    eax, eax
0x1800fed45  jz      short loc_1800FED0D
0x1800fed47  mov     rax, [rbp+57h+pDacl]
0x1800fed4b  test    rax, rax
0x1800fed4e  jz      short loc_1800FED5D
0x1800fed50  cmp     [rbp+57h+bSaclPresent], r14d
0x1800fed54  jz      short loc_1800FED5D
0x1800fed56  movzx   eax, word ptr [rax+2]
0x1800fed5a  mov     [rbp+57h+dwDaclSize], eax
0x1800fed5d  lea     r8, [rbp+57h+bSaclDefaulted]; lpbOwnerDefaulted
0x1800fed61  mov     rcx, rdi; pSecurityDescriptor
0x1800fed64  lea     rdx, [rbp+57h+pOwner]; pOwner
0x1800fed68  call    cs:__imp_GetSecurityDescriptorOwner
0x1800fed6e  test    eax, eax
0x1800fed70  jz      short loc_1800FED0D
0x1800fed72  mov     rcx, [rbp+57h+pOwner]; pSid
0x1800fed76  call    cs:__imp_GetLengthSid
0x1800fed7c  lea     r8, [rbp+57h+bSaclDefaulted]; lpbGroupDefaulted
0x1800fed80  mov     rcx, rdi; pSecurityDescriptor
0x1800fed83  lea     rdx, [rbp+57h+pGroup]; pGroup
0x1800fed87  mov     [rbp+57h+dwOwnerSize], eax
0x1800fed8a  call    cs:__imp_GetSecurityDescriptorGroup
0x1800fed90  test    eax, eax
0x1800fed92  jz      loc_1800FED0D
0x1800fed98  mov     rcx, [rbp+57h+pGroup]; pSid
0x1800fed9c  call    cs:__imp_GetLengthSid
0x1800feda2  mov     r9, [rbp+57h+pDacl]; pDacl
0x1800feda6  lea     r8, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x1800fedaa  mov     [rbp+57h+dwPrimaryGroupSize], eax
0x1800fedad  xor     edx, edx; pAbsoluteSecurityDescriptor
0x1800fedaf  lea     rax, [rbp+57h+dwPrimaryGroupSize]
0x1800fedb3  mov     [rbp+57h+dwAbsoluteSecurityDescriptorSize], r14d
0x1800fedb7  mov     [rsp+0B0h+lpdwPrimaryGroupSize], rax; lpdwPrimaryGroupSize
0x1800fedbc  mov     rcx, rdi; pSelfRelativeSecurityDescriptor
0x1800fedbf  mov     rax, [rbp+57h+pGroup]
0x1800fedc3  mov     [rsp+0B0h+pPrimaryGroup], rax; pPrimaryGroup
0x1800fedc8  lea     rax, [rbp+57h+dwOwnerSize]
0x1800fedcc  mov     [rsp+0B0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x1800fedd1  mov     rax, [rbp+57h+pOwner]
0x1800fedd5  mov     [rsp+0B0h+var_78], rax; pOwner
0x1800fedda  lea     rax, [rbp+57h+dwSaclSize]
0x1800fedde  mov     [rsp+0B0h+lpdwSaclSize], rax; lpdwSaclSize
0x1800fede3  mov     rax, [rbp+57h+pSacl]
0x1800fede7  mov     [rsp+0B0h+var_88], rax; pSacl
0x1800fedec  lea     rax, [rbp+57h+dwDaclSize]
0x1800fedf0  mov     [rsp+0B0h+lpdwDaclSize], rax; lpdwDaclSize
0x1800fedf5  call    cs:__imp_MakeAbsoluteSD
0x1800fedfb  mov     edx, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; uBytes
0x1800fedfe  xor     ecx, ecx; uFlags
0x1800fee00  call    cs:__imp_LocalAlloc
0x1800fee06  mov     [rbp+57h+var_18], rax
0x1800fee0a  mov     rbx, rax
0x1800fee0d  test    rax, rax
0x1800fee10  jnz     short loc_1800FEE1A
0x1800fee12  lea     ebx, [rax+0Eh]
0x1800fee15  jmp     loc_1800FEEA5
0x1800fee1a  mov     r8d, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; Size
0x1800fee1e  xor     edx, edx; Val
0x1800fee20  mov     rcx, rbx; void *
0x1800fee23  call    memset_0
0x1800fee28  mov     edx, 1; dwRevision
0x1800fee2d  mov     rcx, rbx; pSecurityDescriptor
0x1800fee30  call    cs:__imp_InitializeSecurityDescriptor
0x1800fee36  test    eax, eax
0x1800fee38  jnz     short loc_1800FEE44
0x1800fee3a  call    cs:__imp_GetLastError
0x1800fee40  mov     ebx, eax
0x1800fee42  jmp     short loc_1800FEEA5
0x1800fee44  mov     rax, [rbp+57h+pGroup]
0x1800fee48  lea     r8, [rbp+57h+dwPrimaryGroupSize]
0x1800fee4c  mov     rcx, [rbp+57h+pOwner]
0x1800fee50  mov     rdx, [rbp+57h+pSacl]
0x1800fee54  mov     r9, [rbp+57h+pDacl]; pDacl
0x1800fee58  mov     [rsp+0B0h+lpdwPrimaryGroupSize], r8; lpdwPrimaryGroupSize
0x1800fee5d  lea     r8, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x1800fee61  mov     [rsp+0B0h+pPrimaryGroup], rax; pPrimaryGroup
0x1800fee66  lea     rax, [rbp+57h+dwOwnerSize]
0x1800fee6a  mov     [rsp+0B0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x1800fee6f  lea     rax, [rbp+57h+dwSaclSize]
0x1800fee73  mov     [rsp+0B0h+var_78], rcx; pOwner
0x1800fee78  mov     rcx, rdi; pSelfRelativeSecurityDescriptor
0x1800fee7b  mov     [rsp+0B0h+lpdwSaclSize], rax; lpdwSaclSize
0x1800fee80  lea     rax, [rbp+57h+dwDaclSize]
0x1800fee84  mov     [rsp+0B0h+var_88], rdx; pSacl
0x1800fee89  mov     rdx, rbx; pAbsoluteSecurityDescriptor
0x1800fee8c  mov     [rsp+0B0h+lpdwDaclSize], rax; lpdwDaclSize
0x1800fee91  call    cs:__imp_MakeAbsoluteSD
0x1800fee97  test    eax, eax
0x1800fee99  jz      short loc_1800FEE3A
0x1800fee9b  mov     [rsi], rbx
0x1800fee9e  mov     ebx, r14d
0x1800feea1  mov     [rbp+57h+var_18], r14
0x1800feea5  lea     rcx, [rbp+57h+var_18]
0x1800feea9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?DestroyPrivateObjectSecurity@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800feeae  mov     eax, ebx
0x1800feeb0  lea     r11, [rsp+0B0h+var_10]
0x1800feeb8  mov     rbx, [r11+20h]
0x1800feebc  mov     rsi, [r11+28h]
0x1800feec0  mov     rsp, r11
0x1800feec3  pop     r14
0x1800feec5  pop     rdi
0x1800feec6  pop     rbp
0x1800feec7  retn
```
