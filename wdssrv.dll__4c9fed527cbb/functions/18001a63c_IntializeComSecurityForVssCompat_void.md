# IntializeComSecurityForVssCompat(void)

- ea: `0x18001a63c`
- end: `0x18001a8fe`
- name: `?IntializeComSecurityForVssCompat@@YAKXZ`
- size: `706`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001ad9c`

## callees

- `0x18001a63c`
- `0x18001ae58`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001a69f`
- `KERNEL32!GetLastError` at `0x18001a706`
- `KERNEL32!GetLastError` at `0x18001a69f`
- `KERNEL32!GetLastError` at `0x18001a706`
- `KERNEL32!LocalAlloc` at `0x18001a71c`
- `KERNEL32!LocalAlloc` at `0x18001a730`
- `KERNEL32!LocalAlloc` at `0x18001a744`
- `KERNEL32!LocalAlloc` at `0x18001a758`
- `KERNEL32!LocalAlloc` at `0x18001a76c`
- `KERNEL32!LocalAlloc` at `0x18001a71c`
- `KERNEL32!LocalAlloc` at `0x18001a730`
- `KERNEL32!LocalAlloc` at `0x18001a744`
- `KERNEL32!LocalAlloc` at `0x18001a758`
- `KERNEL32!LocalAlloc` at `0x18001a76c`
- `KERNEL32!LocalFree` at `0x18001a862`
- `KERNEL32!LocalFree` at `0x18001a87a`
- `KERNEL32!LocalFree` at `0x18001a88e`
- `KERNEL32!LocalFree` at `0x18001a8a2`
- `KERNEL32!LocalFree` at `0x18001a8b6`
- `KERNEL32!LocalFree` at `0x18001a8ca`
- `KERNEL32!LocalFree` at `0x18001a862`
- `KERNEL32!LocalFree` at `0x18001a87a`
- `KERNEL32!LocalFree` at `0x18001a88e`
- `KERNEL32!LocalFree` at `0x18001a8a2`
- `KERNEL32!LocalFree` at `0x18001a8b6`
- `KERNEL32!LocalFree` at `0x18001a8ca`
- `ADVAPI32!MakeAbsoluteSD` at `0x18001a6f2`
- `ADVAPI32!MakeAbsoluteSD` at `0x18001a7e9`
- `ADVAPI32!MakeAbsoluteSD` at `0x18001a6f2`
- `ADVAPI32!MakeAbsoluteSD` at `0x18001a7e9`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001a68f`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001a68f`
- `ole32!CoInitializeSecurity` at `0x18001a825`
- `ole32!CoInitializeSecurity` at `0x18001a825`
- `WdsServerCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x18001a848`
- `WdsServerCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x18001a848`

## pseudocode

```c
__int64 IntializeComSecurityForVssCompat(void)
{
  DWORD LastError; // ebx
  HLOCAL v1; // r12
  struct _ACL *v2; // rsi
  struct _ACL *pSacl; // rdi
  HLOCAL pOwner; // r15
  void *v5; // r14
  HLOCAL pPrimaryGroup; // rax
  unsigned int v7; // r13d
  __int64 v8; // rdx
  __int64 v9; // r8
  DWORD dwAbsoluteSecurityDescriptorSize; // [rsp+60h] [rbp-18h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+68h] [rbp-10h] BYREF
  DWORD dwPrimaryGroupSize; // [rsp+C0h] [rbp+48h] BYREF
  DWORD dwOwnerSize; // [rsp+C8h] [rbp+50h] BYREF
  DWORD dwSaclSize; // [rsp+D0h] [rbp+58h] BYREF
  DWORD dwDaclSize; // [rsp+D8h] [rbp+60h] BYREF

  SecurityDescriptor = 0;
  dwAbsoluteSecurityDescriptorSize = 0;
  LastError = 0;
  dwDaclSize = 0;
  dwSaclSize = 0;
  v1 = 0;
  dwOwnerSize = 0;
  v2 = 0;
  dwPrimaryGroupSize = 0;
  pSacl = 0;
  pOwner = 0;
  v5 = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"O:SYG:SYD:(A;;0x3;;;SY)(A;;0x3;;;BA)(A;;0x3;;;BO)(A;;0x3;;;S-1-5-80-1688844526-3235337491-1375791646-891369040-3692469510)",
          1u,
          &SecurityDescriptor,
          0) )
    goto LABEL_2;
  if ( MakeAbsoluteSD(
         SecurityDescriptor,
         0,
         &dwAbsoluteSecurityDescriptorSize,
         0,
         &dwDaclSize,
         0,
         &dwSaclSize,
         0,
         &dwOwnerSize,
         0,
         &dwPrimaryGroupSize) )
  {
    LastError = 13;
  }
  else
  {
    if ( GetLastError() != 122 )
      goto LABEL_2;
    v1 = LocalAlloc(0, dwAbsoluteSecurityDescriptorSize);
    v2 = (struct _ACL *)LocalAlloc(0, dwDaclSize);
    pSacl = (struct _ACL *)LocalAlloc(0, dwSaclSize);
    pOwner = LocalAlloc(0, dwOwnerSize);
    pPrimaryGroup = LocalAlloc(0, dwPrimaryGroupSize);
    v5 = pPrimaryGroup;
    if ( !v1 || !v2 || !pSacl || !pOwner || !pPrimaryGroup )
    {
      LastError = 14;
      goto LABEL_13;
    }
    if ( !MakeAbsoluteSD(
            SecurityDescriptor,
            v1,
            &dwAbsoluteSecurityDescriptorSize,
            v2,
            &dwDaclSize,
            pSacl,
            &dwSaclSize,
            pOwner,
            &dwOwnerSize,
            pPrimaryGroup,
            &dwPrimaryGroupSize) )
    {
LABEL_2:
      LastError = GetLastError();
      goto LABEL_13;
    }
    v7 = CoInitializeSecurity(v1, -1, 0, 0, 2u, 2u, 0, 0, 0);
    if ( (int)ElValidateHr(v7, v8, v9, 462) < 0 )
      LastError = WIN32_FROM_HRESULT(v7);
  }
LABEL_13:
  if ( SecurityDescriptor )
  {
    LocalFree(SecurityDescriptor);
    SecurityDescriptor = 0;
  }
  if ( v1 )
    LocalFree(v1);
  if ( pOwner )
    LocalFree(pOwner);
  if ( v5 )
    LocalFree(v5);
  if ( v2 )
    LocalFree(v2);
  if ( pSacl )
    LocalFree(pSacl);
  return LastError;
}

```

## disassembly

```asm
0x18001a63c  push    rbp
0x18001a63e  push    rbx
0x18001a63f  push    rsi
0x18001a640  push    rdi
0x18001a641  push    r12
0x18001a643  push    r13
0x18001a645  push    r14
0x18001a647  push    r15
0x18001a649  mov     rbp, rsp
0x18001a64c  sub     rsp, 78h
0x18001a650  xor     r13d, r13d
0x18001a653  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18001a657  xor     r9d, r9d; SecurityDescriptorSize
0x18001a65a  mov     [rbp+SecurityDescriptor], r13
0x18001a65e  lea     rcx, StringSecurityDescriptor; "O:SYG:SYD:(A;;0x3;;;SY)(A;;0x3;;;BA)(A;"...
0x18001a665  mov     [rbp+dwAbsoluteSecurityDescriptorSize], r13d
0x18001a669  mov     ebx, r13d
0x18001a66c  mov     [rbp+dwDaclSize], r13d
0x18001a670  lea     edx, [r13+1]; StringSDRevision
0x18001a674  mov     [rbp+dwSaclSize], r13d
0x18001a678  mov     r12d, r13d
0x18001a67b  mov     [rbp+dwOwnerSize], r13d
0x18001a67f  mov     esi, r13d
0x18001a682  mov     [rbp+dwPrimaryGroupSize], r13d
0x18001a686  mov     edi, r13d
0x18001a689  mov     r15d, r13d
0x18001a68c  mov     r14d, r13d
0x18001a68f  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18001a696  nop     dword ptr [rax+rax+00h]
0x18001a69b  test    eax, eax
0x18001a69d  jnz     short loc_18001A6B2
0x18001a69f  call    cs:__imp_GetLastError
0x18001a6a6  nop     dword ptr [rax+rax+00h]
0x18001a6ab  mov     ebx, eax
0x18001a6ad  jmp     loc_18001A859
0x18001a6b2  mov     rcx, [rbp+SecurityDescriptor]; pSelfRelativeSecurityDescriptor
0x18001a6b6  lea     rax, [rbp+dwPrimaryGroupSize]
0x18001a6ba  mov     [rsp+78h+lpdwPrimaryGroupSize], rax; lpdwPrimaryGroupSize
0x18001a6bf  lea     r8, [rbp+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x18001a6c3  mov     [rsp+78h+pPrimaryGroup], r13; pPrimaryGroup
0x18001a6c8  lea     rax, [rbp+dwOwnerSize]
0x18001a6cc  mov     [rsp+78h+lpdwOwnerSize], rax; lpdwOwnerSize
0x18001a6d1  xor     r9d, r9d; pDacl
0x18001a6d4  mov     [rsp+78h+pOwner], r13; pOwner
0x18001a6d9  lea     rax, [rbp+dwSaclSize]
0x18001a6dd  mov     [rsp+78h+lpdwSaclSize], rax; lpdwSaclSize
0x18001a6e2  xor     edx, edx; pAbsoluteSecurityDescriptor
0x18001a6e4  lea     rax, [rbp+dwDaclSize]
0x18001a6e8  mov     [rsp+78h+pSacl], r13; pSacl
0x18001a6ed  mov     [rsp+78h+lpdwDaclSize], rax; lpdwDaclSize
0x18001a6f2  call    cs:__imp_MakeAbsoluteSD
0x18001a6f9  nop     dword ptr [rax+rax+00h]
0x18001a6fe  test    eax, eax
0x18001a700  jnz     loc_18001A8F4
0x18001a706  call    cs:__imp_GetLastError
0x18001a70d  nop     dword ptr [rax+rax+00h]
0x18001a712  cmp     eax, 7Ah ; 'z'
0x18001a715  jnz     short loc_18001A69F
0x18001a717  mov     edx, [rbp+dwAbsoluteSecurityDescriptorSize]; uBytes
0x18001a71a  xor     ecx, ecx; uFlags
0x18001a71c  call    cs:__imp_LocalAlloc
0x18001a723  nop     dword ptr [rax+rax+00h]
0x18001a728  mov     edx, [rbp+dwDaclSize]; uBytes
0x18001a72b  xor     ecx, ecx; uFlags
0x18001a72d  mov     r12, rax
0x18001a730  call    cs:__imp_LocalAlloc
0x18001a737  nop     dword ptr [rax+rax+00h]
0x18001a73c  mov     edx, [rbp+dwSaclSize]; uBytes
0x18001a73f  xor     ecx, ecx; uFlags
0x18001a741  mov     rsi, rax
0x18001a744  call    cs:__imp_LocalAlloc
0x18001a74b  nop     dword ptr [rax+rax+00h]
0x18001a750  mov     edx, [rbp+dwOwnerSize]; uBytes
0x18001a753  xor     ecx, ecx; uFlags
0x18001a755  mov     rdi, rax
0x18001a758  call    cs:__imp_LocalAlloc
0x18001a75f  nop     dword ptr [rax+rax+00h]
0x18001a764  mov     edx, [rbp+dwPrimaryGroupSize]; uBytes
0x18001a767  xor     ecx, ecx; uFlags
0x18001a769  mov     r15, rax
0x18001a76c  call    cs:__imp_LocalAlloc
0x18001a773  nop     dword ptr [rax+rax+00h]
0x18001a778  mov     r14, rax
0x18001a77b  test    r12, r12
0x18001a77e  jz      loc_18001A8EA
0x18001a784  test    rsi, rsi
0x18001a787  jz      loc_18001A8EA
0x18001a78d  test    rdi, rdi
0x18001a790  jz      loc_18001A8EA
0x18001a796  test    r15, r15
0x18001a799  jz      loc_18001A8EA
0x18001a79f  test    rax, rax
0x18001a7a2  jz      loc_18001A8EA
0x18001a7a8  mov     rcx, [rbp+SecurityDescriptor]; pSelfRelativeSecurityDescriptor
0x18001a7ac  lea     rax, [rbp+dwPrimaryGroupSize]
0x18001a7b0  mov     [rsp+78h+lpdwPrimaryGroupSize], rax; lpdwPrimaryGroupSize
0x18001a7b5  lea     r8, [rbp+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x18001a7b9  mov     [rsp+78h+pPrimaryGroup], r14; pPrimaryGroup
0x18001a7be  lea     rax, [rbp+dwOwnerSize]
0x18001a7c2  mov     [rsp+78h+lpdwOwnerSize], rax; lpdwOwnerSize
0x18001a7c7  mov     r9, rsi; pDacl
0x18001a7ca  mov     [rsp+78h+pOwner], r15; pOwner
0x18001a7cf  lea     rax, [rbp+dwSaclSize]
0x18001a7d3  mov     [rsp+78h+lpdwSaclSize], rax; lpdwSaclSize
0x18001a7d8  mov     rdx, r12; pAbsoluteSecurityDescriptor
0x18001a7db  lea     rax, [rbp+dwDaclSize]
0x18001a7df  mov     [rsp+78h+pSacl], rdi; pSacl
0x18001a7e4  mov     [rsp+78h+lpdwDaclSize], rax; lpdwDaclSize
0x18001a7e9  call    cs:__imp_MakeAbsoluteSD
0x18001a7f0  nop     dword ptr [rax+rax+00h]
0x18001a7f5  test    eax, eax
0x18001a7f7  jz      loc_18001A69F
0x18001a7fd  mov     [rsp+78h+lpdwOwnerSize], r13; pReserved3
0x18001a802  mov     eax, 2
0x18001a807  mov     dword ptr [rsp+78h+pOwner], r13d; dwCapabilities
0x18001a80c  xor     r9d, r9d; pReserved1
0x18001a80f  mov     [rsp+78h+lpdwSaclSize], r13; pAuthList
0x18001a814  xor     r8d, r8d; asAuthSvc
0x18001a817  mov     dword ptr [rsp+78h+pSacl], eax; dwImpLevel
0x18001a81b  or      edx, 0FFFFFFFFh; cAuthSvc
0x18001a81e  mov     rcx, r12; pSecDesc
0x18001a821  mov     dword ptr [rsp+78h+lpdwDaclSize], eax; dwAuthnLevel
0x18001a825  call    cs:__imp_CoInitializeSecurity
0x18001a82c  nop     dword ptr [rax+rax+00h]
0x18001a831  mov     ecx, eax
0x18001a833  mov     r9d, 1CEh
0x18001a839  mov     r13d, eax
0x18001a83c  call    ElValidateHr
0x18001a841  test    eax, eax
0x18001a843  jns     short loc_18001A856
0x18001a845  mov     ecx, r13d
0x18001a848  call    cs:__imp_?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x18001a84f  nop     dword ptr [rax+rax+00h]
0x18001a854  mov     ebx, eax
0x18001a856  xor     r13d, r13d
0x18001a859  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x18001a85d  test    rcx, rcx
0x18001a860  jz      short loc_18001A872
0x18001a862  call    cs:__imp_LocalFree
0x18001a869  nop     dword ptr [rax+rax+00h]
0x18001a86e  mov     [rbp+SecurityDescriptor], r13
0x18001a872  test    r12, r12
0x18001a875  jz      short loc_18001A886
0x18001a877  mov     rcx, r12; hMem
0x18001a87a  call    cs:__imp_LocalFree
0x18001a881  nop     dword ptr [rax+rax+00h]
0x18001a886  test    r15, r15
0x18001a889  jz      short loc_18001A89A
0x18001a88b  mov     rcx, r15; hMem
0x18001a88e  call    cs:__imp_LocalFree
0x18001a895  nop     dword ptr [rax+rax+00h]
0x18001a89a  test    r14, r14
0x18001a89d  jz      short loc_18001A8AE
0x18001a89f  mov     rcx, r14; hMem
0x18001a8a2  call    cs:__imp_LocalFree
0x18001a8a9  nop     dword ptr [rax+rax+00h]
0x18001a8ae  test    rsi, rsi
0x18001a8b1  jz      short loc_18001A8C2
0x18001a8b3  mov     rcx, rsi; hMem
0x18001a8b6  call    cs:__imp_LocalFree
0x18001a8bd  nop     dword ptr [rax+rax+00h]
0x18001a8c2  test    rdi, rdi
0x18001a8c5  jz      short loc_18001A8D6
0x18001a8c7  mov     rcx, rdi; hMem
0x18001a8ca  call    cs:__imp_LocalFree
0x18001a8d1  nop     dword ptr [rax+rax+00h]
0x18001a8d6  mov     eax, ebx
0x18001a8d8  add     rsp, 78h
0x18001a8dc  pop     r15
0x18001a8de  pop     r14
0x18001a8e0  pop     r13
0x18001a8e2  pop     r12
0x18001a8e4  pop     rdi
0x18001a8e5  pop     rsi
0x18001a8e6  pop     rbx
0x18001a8e7  pop     rbp
0x18001a8e8  retn
0x18001a8ea  mov     ebx, 0Eh
0x18001a8ef  jmp     loc_18001A859
0x18001a8f4  mov     ebx, 0Dh
0x18001a8f9  jmp     loc_18001A859
```
