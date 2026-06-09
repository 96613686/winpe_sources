# BfspSetSecurityDescriptor

- ea: `0x180036dd4`
- end: `0x18003704f`
- name: `BfspSetSecurityDescriptor`
- size: `635`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, LPCWSTR StringSecurityDescriptor)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180032518`
- `0x180036ca8`

## callees

- `0x180031b50`
- `0x1800366b8`
- `0x180036dd4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180037030`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180037030`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036e4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036e7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036eaa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036ed9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036e4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036e7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036eaa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036ed9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180037024`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180037024`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x180036f1c`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x180036f1c`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180036f00`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180036f00`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x180036ecd`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x180036ecd`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180036e6f`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180036e6f`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x180036e9e`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x180036e9e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180036e40`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180036e40`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x180036f60`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x180036fe3`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x180036f60`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x180036fe3`

## string_xrefs

- `0x180036e54`: `ConvertStringSecurityDescriptorToSecurityDescriptor failed! Error code = %#x`
- `0x180036eb2`: `GetSecurityDescriptorOwner failed! Error code = %#x`
- `0x180036e83`: `GetSecurityDescriptorControl failed! Error code = %#x`
- `0x180036f6f`: `SetNamedSecurityInfo failed! Error code = %#x`
- `0x18003700a`: `SetNamedSecurityInfo failed! Error code = %#x`
- `0x180036ee1`: `GetSecurityDescriptorGroup failed! Error code = %#x`

## pseudocode

```c
__int64 __fastcall BfspSetSecurityDescriptor(WCHAR *lpFileName, LPCWSTR StringSecurityDescriptor)
{
  unsigned int SecurityDescriptorControl; // edi
  __int64 LastError; // rbx
  const wchar_t *v5; // rdx
  __int64 v6; // r8
  SECURITY_INFORMATION v7; // r8d
  DWORD v8; // eax
  __int64 v9; // rcx
  SECURITY_INFORMATION v10; // r8d
  DWORD v11; // eax
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+40h] [rbp-19h] BYREF
  WINBOOL bSaclPresent; // [rsp+48h] [rbp-11h] BYREF
  ULONG SecurityDescriptorSize; // [rsp+4Ch] [rbp-Dh] BYREF
  DWORD dwRevision; // [rsp+50h] [rbp-9h] BYREF
  WINBOOL bOwnerDefaulted; // [rsp+54h] [rbp-5h] BYREF
  WINBOOL bGroupDefaulted; // [rsp+58h] [rbp-1h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+5Ch] [rbp+3h] BYREF
  WINBOOL bSaclDefaulted; // [rsp+60h] [rbp+7h] BYREF
  PSID pOwner; // [rsp+68h] [rbp+Fh] BYREF
  PSID pGroup; // [rsp+70h] [rbp+17h] BYREF
  PACL pSacl; // [rsp+78h] [rbp+1Fh] BYREF
  PACL pDacl; // [rsp+80h] [rbp+27h] BYREF
  WORD pControl; // [rsp+D0h] [rbp+77h] BYREF
  WINBOOL bDaclPresent; // [rsp+D8h] [rbp+7Fh] BYREF

  pDacl = 0;
  bDaclPresent = 0;
  bDaclDefaulted = 0;
  pGroup = 0;
  bGroupDefaulted = 0;
  pOwner = 0;
  bOwnerDefaulted = 0;
  pSacl = 0;
  bSaclPresent = 0;
  bSaclDefaulted = 0;
  pControl = 0;
  dwRevision = 0;
  SecurityDescriptorSize = 0;
  SecurityDescriptor = 0;
  SecurityDescriptorControl = ConvertStringSecurityDescriptorToSecurityDescriptorW(
                                StringSecurityDescriptor,
                                1u,
                                &SecurityDescriptor,
                                &SecurityDescriptorSize);
  if ( !SecurityDescriptorControl )
  {
    LastError = GetLastError();
    v5 = L"ConvertStringSecurityDescriptorToSecurityDescriptor failed! Error code = %#x";
    v6 = LastError;
LABEL_28:
    v9 = 4;
    goto LABEL_29;
  }
  SecurityDescriptorControl = GetSecurityDescriptorControl(SecurityDescriptor, &pControl, &dwRevision);
  if ( !SecurityDescriptorControl )
  {
    LastError = GetLastError();
    v5 = L"GetSecurityDescriptorControl failed! Error code = %#x";
    v6 = LastError;
    goto LABEL_28;
  }
  SecurityDescriptorControl = GetSecurityDescriptorOwner(SecurityDescriptor, &pOwner, &bOwnerDefaulted);
  if ( !SecurityDescriptorControl )
  {
    LastError = GetLastError();
    v5 = L"GetSecurityDescriptorOwner failed! Error code = %#x";
    v6 = LastError;
    goto LABEL_28;
  }
  SecurityDescriptorControl = GetSecurityDescriptorGroup(SecurityDescriptor, &pGroup, &bGroupDefaulted);
  if ( !SecurityDescriptorControl
    || (SecurityDescriptorControl = GetSecurityDescriptorDacl(
                                      SecurityDescriptor,
                                      &bDaclPresent,
                                      &pDacl,
                                      &bDaclDefaulted)) == 0
    || (SecurityDescriptorControl = GetSecurityDescriptorSacl(
                                      SecurityDescriptor,
                                      &bSaclPresent,
                                      &pSacl,
                                      &bSaclDefaulted)) == 0 )
  {
    LastError = GetLastError();
    v5 = L"GetSecurityDescriptorGroup failed! Error code = %#x";
    v6 = LastError;
    goto LABEL_28;
  }
  LODWORD(LastError) = 0;
  v7 = pOwner != 0;
  if ( pGroup )
    v7 |= 2u;
  if ( v7 )
  {
    v8 = SetNamedSecurityInfoW(lpFileName, SE_FILE_OBJECT, v7, pOwner, pGroup, 0, 0);
    LODWORD(LastError) = v8;
    if ( v8 )
    {
      SecurityDescriptorControl = 0;
      v5 = L"SetNamedSecurityInfo failed! Error code = %#x";
      v6 = v8;
      v9 = 2;
LABEL_29:
      BfspLogMessage(v9, v5, v6);
      goto LABEL_30;
    }
  }
  v10 = 0;
  if ( bDaclPresent )
  {
    v10 = 4;
    if ( (pControl & 0x1000) != 0 )
      v10 = -2147483644;
  }
  if ( bSaclPresent )
  {
    v10 |= 8u;
    if ( (pControl & 0x2000) != 0 )
      v10 |= 0x40000000u;
  }
  if ( v10 )
  {
    v11 = SetNamedSecurityInfoW(lpFileName, SE_FILE_OBJECT, v10, 0, 0, pDacl, pSacl);
    LODWORD(LastError) = v11;
    if ( v11 )
    {
      SecurityDescriptorControl = 0;
      if ( v11 == 5 || v11 - 32 <= 1 )
        BfspPrintFileOwnerProcess(lpFileName);
      v6 = (unsigned int)LastError;
      v5 = L"SetNamedSecurityInfo failed! Error code = %#x";
      goto LABEL_28;
    }
  }
LABEL_30:
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  if ( !SecurityDescriptorControl )
    SetLastError(LastError);
  return SecurityDescriptorControl;
}

```

## disassembly

```asm
0x180036dd4  mov     [rsp-8+arg_0], rbx
0x180036dd9  push    rbp
0x180036dda  push    rsi
0x180036ddb  push    rdi
0x180036ddc  push    r14
0x180036dde  push    r15
0x180036de0  lea     rbp, [rsp-37h]
0x180036de5  sub     rsp, 90h
0x180036dec  xor     r14d, r14d
0x180036def  lea     r9, [rbp+57h+SecurityDescriptorSize]; SecurityDescriptorSize
0x180036df3  mov     r10, rdx
0x180036df6  mov     [rbp+57h+pDacl], r14
0x180036dfa  mov     rsi, rcx
0x180036dfd  mov     [rbp+57h+bDaclPresent], r14d
0x180036e01  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x180036e05  mov     [rbp+57h+bDaclDefaulted], r14d
0x180036e09  lea     r15d, [r14+1]
0x180036e0d  mov     [rbp+57h+pGroup], r14
0x180036e11  mov     edx, r15d; StringSDRevision
0x180036e14  mov     [rbp+57h+bGroupDefaulted], r14d
0x180036e18  mov     rcx, r10; StringSecurityDescriptor
0x180036e1b  mov     [rbp+57h+pOwner], r14
0x180036e1f  mov     [rbp+57h+bOwnerDefaulted], r14d
0x180036e23  mov     [rbp+57h+pSacl], r14
0x180036e27  mov     [rbp+57h+bSaclPresent], r14d
0x180036e2b  mov     [rbp+57h+bSaclDefaulted], r14d
0x180036e2f  mov     [rbp+57h+pControl], r14w
0x180036e34  mov     [rbp+57h+dwRevision], r14d
0x180036e38  mov     [rbp+57h+SecurityDescriptorSize], r14d
0x180036e3c  mov     [rbp+57h+SecurityDescriptor], r14
0x180036e40  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180036e46  mov     edi, eax
0x180036e48  test    eax, eax
0x180036e4a  jnz     short loc_180036E63
0x180036e4c  call    cs:__imp_GetLastError
0x180036e52  mov     ebx, eax
0x180036e54  lea     rdx, aConvertstrings; "ConvertStringSecurityDescriptorToSecuri"...
0x180036e5b  mov     r8d, eax
0x180036e5e  jmp     loc_180037011
0x180036e63  mov     rcx, [rbp+57h+SecurityDescriptor]; pSecurityDescriptor
0x180036e67  lea     r8, [rbp+57h+dwRevision]; lpdwRevision
0x180036e6b  lea     rdx, [rbp+57h+pControl]; pControl
0x180036e6f  call    cs:__imp_GetSecurityDescriptorControl
0x180036e75  mov     edi, eax
0x180036e77  test    eax, eax
0x180036e79  jnz     short loc_180036E92
0x180036e7b  call    cs:__imp_GetLastError
0x180036e81  mov     ebx, eax
0x180036e83  lea     rdx, aGetsecuritydes_1; "GetSecurityDescriptorControl failed! Er"...
0x180036e8a  mov     r8d, eax
0x180036e8d  jmp     loc_180037011
0x180036e92  mov     rcx, [rbp+57h+SecurityDescriptor]; pSecurityDescriptor
0x180036e96  lea     r8, [rbp+57h+bOwnerDefaulted]; lpbOwnerDefaulted
0x180036e9a  lea     rdx, [rbp+57h+pOwner]; pOwner
0x180036e9e  call    cs:__imp_GetSecurityDescriptorOwner
0x180036ea4  mov     edi, eax
0x180036ea6  test    eax, eax
0x180036ea8  jnz     short loc_180036EC1
0x180036eaa  call    cs:__imp_GetLastError
0x180036eb0  mov     ebx, eax
0x180036eb2  lea     rdx, aGetsecuritydes_0; "GetSecurityDescriptorOwner failed! Erro"...
0x180036eb9  mov     r8d, eax
0x180036ebc  jmp     loc_180037011
0x180036ec1  mov     rcx, [rbp+57h+SecurityDescriptor]; pSecurityDescriptor
0x180036ec5  lea     r8, [rbp+57h+bGroupDefaulted]; lpbGroupDefaulted
0x180036ec9  lea     rdx, [rbp+57h+pGroup]; pGroup
0x180036ecd  call    cs:__imp_GetSecurityDescriptorGroup
0x180036ed3  mov     edi, eax
0x180036ed5  test    eax, eax
0x180036ed7  jnz     short loc_180036EF0
0x180036ed9  call    cs:__imp_GetLastError
0x180036edf  mov     ebx, eax
0x180036ee1  lea     rdx, aGetsecuritydes; "GetSecurityDescriptorGroup failed! Erro"...
0x180036ee8  mov     r8d, eax
0x180036eeb  jmp     loc_180037011
0x180036ef0  mov     rcx, [rbp+57h+SecurityDescriptor]; pSecurityDescriptor
0x180036ef4  lea     r9, [rbp+57h+bDaclDefaulted]; lpbDaclDefaulted
0x180036ef8  lea     r8, [rbp+57h+pDacl]; pDacl
0x180036efc  lea     rdx, [rbp+57h+bDaclPresent]; lpbDaclPresent
0x180036f00  call    cs:__imp_GetSecurityDescriptorDacl
0x180036f06  mov     edi, eax
0x180036f08  test    eax, eax
0x180036f0a  jz      short loc_180036ED9
0x180036f0c  mov     rcx, [rbp+57h+SecurityDescriptor]; pSecurityDescriptor
0x180036f10  lea     r9, [rbp+57h+bSaclDefaulted]; lpbSaclDefaulted
0x180036f14  lea     r8, [rbp+57h+pSacl]; pSacl
0x180036f18  lea     rdx, [rbp+57h+bSaclPresent]; lpbSaclPresent
0x180036f1c  call    cs:__imp_GetSecurityDescriptorSacl
0x180036f22  mov     edi, eax
0x180036f24  test    eax, eax
0x180036f26  jz      short loc_180036ED9
0x180036f28  mov     r9, [rbp+57h+pOwner]; psidOwner
0x180036f2c  mov     r8d, r14d
0x180036f2f  mov     rax, [rbp+57h+pGroup]
0x180036f33  test    r9, r9
0x180036f36  mov     ebx, r14d
0x180036f39  cmovnz  r8d, r15d
0x180036f3d  test    rax, rax
0x180036f40  jz      short loc_180036F46
0x180036f42  or      r8d, 2; SecurityInfo
0x180036f46  test    r8d, r8d
0x180036f49  jz      short loc_180036F83
0x180036f4b  mov     [rsp+0B0h+var_80], r14; pSacl
0x180036f50  mov     edx, r15d; ObjectType
0x180036f53  mov     [rsp+0B0h+var_88], r14; pDacl
0x180036f58  mov     rcx, rsi; pObjectName
0x180036f5b  mov     [rsp+0B0h+psidGroup], rax; psidGroup
0x180036f60  call    cs:__imp_SetNamedSecurityInfoW
0x180036f66  mov     ebx, eax
0x180036f68  test    eax, eax
0x180036f6a  jz      short loc_180036F83
0x180036f6c  mov     edi, r14d
0x180036f6f  lea     rdx, aSetnamedsecuri; "SetNamedSecurityInfo failed! Error code"...
0x180036f76  mov     r8d, eax
0x180036f79  mov     ecx, 2
0x180036f7e  jmp     loc_180037016
0x180036f83  mov     r8d, r14d
0x180036f86  cmp     [rbp+57h+bDaclPresent], r14d
0x180036f8a  jz      short loc_180036FA4
0x180036f8c  mov     eax, 1000h
0x180036f91  mov     r8d, 4
0x180036f97  test    [rbp+57h+pControl], ax
0x180036f9b  mov     eax, 80000004h
0x180036fa0  cmovnz  r8d, eax
0x180036fa4  cmp     [rbp+57h+bSaclPresent], r14d
0x180036fa8  jz      short loc_180036FBE
0x180036faa  or      r8d, 8
0x180036fae  mov     eax, 2000h
0x180036fb3  test    [rbp+57h+pControl], ax
0x180036fb7  jz      short loc_180036FBE
0x180036fb9  bts     r8d, 1Eh; SecurityInfo
0x180036fbe  test    r8d, r8d
0x180036fc1  jz      short loc_18003701B
0x180036fc3  mov     rax, [rbp+57h+pSacl]
0x180036fc7  xor     r9d, r9d; psidOwner
0x180036fca  mov     [rsp+0B0h+var_80], rax; pSacl
0x180036fcf  mov     edx, r15d; ObjectType
0x180036fd2  mov     rax, [rbp+57h+pDacl]
0x180036fd6  mov     rcx, rsi; pObjectName
0x180036fd9  mov     [rsp+0B0h+var_88], rax; pDacl
0x180036fde  mov     [rsp+0B0h+psidGroup], r14; psidGroup
0x180036fe3  call    cs:__imp_SetNamedSecurityInfoW
0x180036fe9  mov     ebx, eax
0x180036feb  test    eax, eax
0x180036fed  jz      short loc_18003701B
0x180036fef  mov     edi, r14d
0x180036ff2  cmp     eax, 5
0x180036ff5  jz      short loc_180036FFF
0x180036ff7  add     eax, 0FFFFFFE0h
0x180036ffa  cmp     eax, r15d
0x180036ffd  ja      short loc_180037007
0x180036fff  mov     rcx, rsi; lpFileName
0x180037002  call    BfspPrintFileOwnerProcess
0x180037007  mov     r8d, ebx
0x18003700a  lea     rdx, aSetnamedsecuri; "SetNamedSecurityInfo failed! Error code"...
0x180037011  mov     ecx, 4
0x180037016  call    BfspLogMessage
0x18003701b  mov     rcx, [rbp+57h+SecurityDescriptor]; hMem
0x18003701f  test    rcx, rcx
0x180037022  jz      short loc_18003702A
0x180037024  call    cs:__imp_LocalFree
0x18003702a  test    edi, edi
0x18003702c  jnz     short loc_180037036
0x18003702e  mov     ecx, ebx; dwErrCode
0x180037030  call    cs:__imp_SetLastError
0x180037036  mov     rbx, [rsp+0B0h+arg_0]
0x18003703e  mov     eax, edi
0x180037040  add     rsp, 90h
0x180037047  pop     r15
0x180037049  pop     r14
0x18003704b  pop     rdi
0x18003704c  pop     rsi
0x18003704d  pop     rbp
0x18003704e  retn
```
