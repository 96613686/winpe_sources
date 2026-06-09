# WdcSecurityObject::SetSecurity(ulong,void *)

- ea: `0x1800307e0`
- end: `0x180030d5e`
- name: `?SetSecurity@WdcSecurityObject@@UEAAJKPEAX@Z`
- size: `1406`
- prototype: `int(WdcSecurityObject *__hidden this, unsigned int, void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000b854`
- `0x1800307e0`
- `0x180068f70`
- `0x180086010`

## import_xrefs

- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18003084a`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18003084a`
- `ADVAPI32!MakeAbsoluteSD` at `0x1800308b9`
- `ADVAPI32!MakeAbsoluteSD` at `0x1800309da`
- `ADVAPI32!MakeAbsoluteSD` at `0x1800308b9`
- `ADVAPI32!MakeAbsoluteSD` at `0x1800309da`
- `ADVAPI32!GetSecurityDescriptorGroup` at `0x180030a18`
- `ADVAPI32!GetSecurityDescriptorGroup` at `0x180030a18`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x180030a50`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x180030a50`
- `ADVAPI32!GetSecurityDescriptorOwner` at `0x180030a8e`
- `ADVAPI32!GetSecurityDescriptorOwner` at `0x180030a8e`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x180030ac6`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x180030ac6`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x180030b08`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x180030b08`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180030b43`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180030b43`
- `ADVAPI32!GetSecurityDescriptorSacl` at `0x180030b85`
- `ADVAPI32!GetSecurityDescriptorSacl` at `0x180030b85`
- `ADVAPI32!SetSecurityDescriptorSacl` at `0x180030bc0`
- `ADVAPI32!SetSecurityDescriptorSacl` at `0x180030bc0`
- `ADVAPI32!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180030c0a`
- `ADVAPI32!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180030c0a`
- `KERNEL32!GetLastError` at `0x180030854`
- `KERNEL32!GetLastError` at `0x1800308c7`
- `KERNEL32!GetLastError` at `0x1800309e4`
- `KERNEL32!GetLastError` at `0x180030a22`
- `KERNEL32!GetLastError` at `0x180030a5a`
- `KERNEL32!GetLastError` at `0x180030a98`
- `KERNEL32!GetLastError` at `0x180030ad0`
- `KERNEL32!GetLastError` at `0x180030b12`
- `KERNEL32!GetLastError` at `0x180030b4d`
- `KERNEL32!GetLastError` at `0x180030b8f`
- `KERNEL32!GetLastError` at `0x180030bca`
- `KERNEL32!GetLastError` at `0x180030c14`
- `KERNEL32!GetLastError` at `0x180030854`
- `KERNEL32!GetLastError` at `0x1800308c7`
- `KERNEL32!GetLastError` at `0x1800309e4`
- `KERNEL32!GetLastError` at `0x180030a22`
- `KERNEL32!GetLastError` at `0x180030a5a`
- `KERNEL32!GetLastError` at `0x180030a98`
- `KERNEL32!GetLastError` at `0x180030ad0`
- `KERNEL32!GetLastError` at `0x180030b12`
- `KERNEL32!GetLastError` at `0x180030b4d`
- `KERNEL32!GetLastError` at `0x180030b8f`
- `KERNEL32!GetLastError` at `0x180030bca`
- `KERNEL32!GetLastError` at `0x180030c14`
- `KERNEL32!LocalFree` at `0x180030cce`
- `KERNEL32!LocalFree` at `0x180030ce5`
- `KERNEL32!LocalFree` at `0x180030cfb`
- `KERNEL32!LocalFree` at `0x180030d0d`
- `KERNEL32!LocalFree` at `0x180030d1f`
- `KERNEL32!LocalFree` at `0x180030d2d`
- `KERNEL32!LocalFree` at `0x180030d3b`
- `KERNEL32!LocalFree` at `0x180030cce`
- `KERNEL32!LocalFree` at `0x180030ce5`
- `KERNEL32!LocalFree` at `0x180030cfb`
- `KERNEL32!LocalFree` at `0x180030d0d`
- `KERNEL32!LocalFree` at `0x180030d1f`
- `KERNEL32!LocalFree` at `0x180030d2d`
- `KERNEL32!LocalFree` at `0x180030d3b`
- `KERNEL32!LocalAlloc` at `0x1800308eb`
- `KERNEL32!LocalAlloc` at `0x18003093b`
- `KERNEL32!LocalAlloc` at `0x180030952`
- `KERNEL32!LocalAlloc` at `0x18003096c`
- `KERNEL32!LocalAlloc` at `0x180030986`
- `KERNEL32!LocalAlloc` at `0x1800308eb`
- `KERNEL32!LocalAlloc` at `0x18003093b`
- `KERNEL32!LocalAlloc` at `0x180030952`
- `KERNEL32!LocalAlloc` at `0x18003096c`
- `KERNEL32!LocalAlloc` at `0x180030986`
- `OLEAUT32!__imp_SysAllocString` at `0x180030c55`
- `OLEAUT32!__imp_SysAllocString` at `0x180030c55`
- `OLEAUT32!__imp_SysFreeString` at `0x180030c44`
- `OLEAUT32!__imp_SysFreeString` at `0x180030c44`

## string_xrefs

- `0x18003091b`: `WdcSecurityObject::SetSecurity`

## pseudocode

```c
__int64 __fastcall WdcSecurityObject::SetSecurity(WdcSecurityObject *this, int a2, void *a3)
{
  const WCHAR *v6; // rcx
  HLOCAL v7; // r14
  HLOCAL pOwner; // r13
  void *v9; // r12
  signed int LastError; // eax
  signed int v11; // ebx
  signed int v12; // eax
  bool v13; // sf
  int v14; // eax
  struct _ACL *pSacl; // rbx
  HLOCAL pPrimaryGroup; // rax
  signed int v17; // eax
  signed int v18; // eax
  signed int v19; // eax
  signed int v20; // eax
  signed int v21; // eax
  signed int v22; // eax
  signed int v23; // eax
  signed int v24; // eax
  signed int v25; // eax
  signed int v26; // eax
  OLECHAR *v27; // rcx
  const OLECHAR *v28; // rbx
  BSTR v29; // rax
  LPDWORD lpdwDaclSize; // [rsp+20h] [rbp-69h]
  DWORD dwPrimaryGroupSize; // [rsp+60h] [rbp-29h] BYREF
  DWORD dwOwnerSize; // [rsp+64h] [rbp-25h] BYREF
  DWORD dwSaclSize; // [rsp+68h] [rbp-21h] BYREF
  DWORD dwDaclSize; // [rsp+6Ch] [rbp-1Dh] BYREF
  DWORD dwAbsoluteSecurityDescriptorSize; // [rsp+70h] [rbp-19h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+78h] [rbp-11h] BYREF
  PSID pGroup; // [rsp+80h] [rbp-9h] BYREF
  PACL v39; // [rsp+88h] [rbp-1h] BYREF
  LPWSTR StringSecurityDescriptor; // [rsp+90h] [rbp+7h] BYREF
  PACL pDacl; // [rsp+98h] [rbp+Fh]
  HLOCAL hMem; // [rsp+A0h] [rbp+17h]
  WINBOOL bGroupDefaulted; // [rsp+F0h] [rbp+67h] BYREF
  WINBOOL bDaclPresent; // [rsp+108h] [rbp+7Fh] BYREF

  StringSecurityDescriptor = 0;
  pGroup = 0;
  v6 = (const WCHAR *)*((_QWORD *)this + 6);
  v39 = 0;
  SecurityDescriptor = 0;
  v7 = 0;
  bGroupDefaulted = 0;
  bDaclPresent = 0;
  pOwner = 0;
  dwAbsoluteSecurityDescriptorSize = 0;
  v9 = 0;
  dwDaclSize = 0;
  dwSaclSize = 0;
  dwOwnerSize = 0;
  dwPrimaryGroupSize = 0;
  pDacl = 0;
  hMem = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(v6, 1u, &SecurityDescriptor, 0) )
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( !LastError )
      goto LABEL_13;
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
    if ( v11 < 0 )
      goto LABEL_14;
  }
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
    goto LABEL_82;
  }
  v12 = GetLastError();
  v13 = v12 < 0;
  if ( v12 )
  {
    if ( v12 > 0 )
      v13 = 1;
    if ( !v13 )
    {
LABEL_82:
      v11 = -2147467259;
      goto LABEL_83;
    }
  }
  v7 = LocalAlloc(0x40u, dwAbsoluteSecurityDescriptorSize);
  if ( !v7 )
    goto LABEL_12;
  pDacl = (PACL)LocalAlloc(0x40u, dwDaclSize);
  if ( !pDacl )
    goto LABEL_12;
  hMem = LocalAlloc(0x40u, dwSaclSize);
  pSacl = (struct _ACL *)hMem;
  if ( !hMem )
    goto LABEL_12;
  pOwner = LocalAlloc(0x40u, dwOwnerSize);
  if ( !pOwner )
    goto LABEL_12;
  pPrimaryGroup = LocalAlloc(0x40u, dwPrimaryGroupSize);
  v9 = pPrimaryGroup;
  if ( !pPrimaryGroup )
    goto LABEL_12;
  if ( !MakeAbsoluteSD(
          SecurityDescriptor,
          v7,
          &dwAbsoluteSecurityDescriptorSize,
          pDacl,
          &dwDaclSize,
          pSacl,
          &dwSaclSize,
          pOwner,
          &dwOwnerSize,
          pPrimaryGroup,
          &dwPrimaryGroupSize) )
  {
    v17 = GetLastError();
    v11 = v17;
    if ( !v17 )
      goto LABEL_13;
    if ( v17 > 0 )
      v11 = (unsigned __int16)v17 | 0x80070000;
    if ( v11 < 0 )
      goto LABEL_14;
  }
  if ( (a2 & 2) != 0 )
  {
    if ( !GetSecurityDescriptorGroup(a3, &pGroup, &bGroupDefaulted) )
    {
      v18 = GetLastError();
      v11 = v18;
      if ( !v18 )
        goto LABEL_13;
      if ( v18 > 0 )
        v11 = (unsigned __int16)v18 | 0x80070000;
      if ( v11 < 0 )
        goto LABEL_14;
    }
    if ( !SetSecurityDescriptorGroup(v7, pGroup, bGroupDefaulted) )
    {
      v19 = GetLastError();
      v11 = v19;
      if ( !v19 )
        goto LABEL_13;
      if ( v19 > 0 )
        v11 = (unsigned __int16)v19 | 0x80070000;
      if ( v11 < 0 )
        goto LABEL_14;
    }
  }
  if ( (a2 & 1) != 0 )
  {
    if ( !GetSecurityDescriptorOwner(a3, &pGroup, &bGroupDefaulted) )
    {
      v20 = GetLastError();
      v11 = v20;
      if ( !v20 )
        goto LABEL_13;
      if ( v20 > 0 )
        v11 = (unsigned __int16)v20 | 0x80070000;
      if ( v11 < 0 )
        goto LABEL_14;
    }
    if ( !SetSecurityDescriptorOwner(v7, pGroup, bGroupDefaulted) )
    {
      v21 = GetLastError();
      v11 = v21;
      if ( !v21 )
        goto LABEL_13;
      if ( v21 > 0 )
        v11 = (unsigned __int16)v21 | 0x80070000;
      if ( v11 < 0 )
        goto LABEL_14;
    }
  }
  if ( (a2 & 4) != 0 )
  {
    if ( !GetSecurityDescriptorDacl(a3, &bDaclPresent, &v39, &bGroupDefaulted) )
    {
      v22 = GetLastError();
      v11 = v22;
      if ( !v22 )
        goto LABEL_13;
      if ( v22 > 0 )
        v11 = (unsigned __int16)v22 | 0x80070000;
      if ( v11 < 0 )
        goto LABEL_14;
    }
    if ( !SetSecurityDescriptorDacl(v7, bDaclPresent, v39, bGroupDefaulted) )
    {
      v23 = GetLastError();
      v11 = v23;
      if ( !v23 )
        goto LABEL_13;
      if ( v23 > 0 )
        v11 = (unsigned __int16)v23 | 0x80070000;
      if ( v11 < 0 )
        goto LABEL_14;
    }
  }
  if ( (a2 & 8) == 0 )
    goto LABEL_70;
  if ( !GetSecurityDescriptorSacl(a3, &bDaclPresent, &v39, &bGroupDefaulted) )
  {
    v24 = GetLastError();
    v11 = v24;
    if ( !v24 )
      goto LABEL_13;
    if ( v24 > 0 )
      v11 = (unsigned __int16)v24 | 0x80070000;
    if ( v11 < 0 )
      goto LABEL_14;
  }
  if ( SetSecurityDescriptorSacl(v7, bDaclPresent, v39, bGroupDefaulted) )
    goto LABEL_70;
  v25 = GetLastError();
  v11 = v25;
  if ( !v25 )
  {
LABEL_13:
    v11 = -2147467259;
LABEL_14:
    v14 = v11;
LABEL_15:
    LODWORD(lpdwDaclSize) = v14;
    goto LABEL_16;
  }
  if ( v25 > 0 )
    v11 = (unsigned __int16)v25 | 0x80070000;
  if ( v11 < 0 )
    goto LABEL_14;
LABEL_70:
  *((_DWORD *)this + 14) |= a2;
  if ( ConvertSecurityDescriptorToStringSecurityDescriptorW(
         v7,
         1u,
         *((_DWORD *)this + 14),
         &StringSecurityDescriptor,
         0) )
  {
    goto LABEL_75;
  }
  v26 = GetLastError();
  v11 = v26;
  if ( !v26 )
    goto LABEL_13;
  if ( v26 > 0 )
    v11 = (unsigned __int16)v26 | 0x80070000;
  if ( v11 < 0 )
    goto LABEL_14;
LABEL_75:
  v27 = (OLECHAR *)*((_QWORD *)this + 6);
  v28 = StringSecurityDescriptor;
  if ( v27 )
  {
    SysFreeString(v27);
    *((_QWORD *)this + 6) = 0;
  }
  v29 = SysAllocString(v28);
  if ( !v28 || v29 )
  {
    *((_QWORD *)this + 6) = v29;
    v14 = (*((__int64 (__fastcall **)(_QWORD, BSTR))this + 4))(*((_QWORD *)this + 3), v29);
    v11 = v14;
    if ( v14 >= 0 )
      goto LABEL_84;
    goto LABEL_15;
  }
  LODWORD(lpdwDaclSize) = -2147024882;
  WdcDebugMessage(
    "base\\diagnosis\\pdui\\perfmon\\mmc\\inline.cpp",
    "WdcAssignString",
    0,
    L"FAILURE: 0x%08x",
    lpdwDaclSize);
LABEL_12:
  v11 = -2147024882;
  LODWORD(lpdwDaclSize) = -2147024882;
LABEL_16:
  WdcDebugMessage(
    "base\\diagnosis\\pdui\\perfmon\\mmc\\secure.cpp",
    "WdcSecurityObject::SetSecurity",
    0,
    L"FAILURE: 0x%08x",
    lpdwDaclSize);
LABEL_83:
  WdcShowErrorMessage(*((HWND *)this + 9), 0x32Du, v11);
LABEL_84:
  if ( SecurityDescriptor )
  {
    LocalFree(SecurityDescriptor);
    SecurityDescriptor = 0;
  }
  if ( StringSecurityDescriptor )
  {
    LocalFree(StringSecurityDescriptor);
    StringSecurityDescriptor = 0;
  }
  if ( v7 )
    LocalFree(v7);
  if ( pDacl )
    LocalFree(pDacl);
  if ( hMem )
    LocalFree(hMem);
  if ( pOwner )
    LocalFree(pOwner);
  if ( v9 )
    LocalFree(v9);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800307e0  mov     [rsp-8+arg_8], rbx
0x1800307e5  push    rbp
0x1800307e6  push    rsi
0x1800307e7  push    rdi
0x1800307e8  push    r12
0x1800307ea  push    r13
0x1800307ec  push    r14
0x1800307ee  push    r15
0x1800307f0  lea     rbp, [rsp-27h]
0x1800307f5  sub     rsp, 0B0h
0x1800307fc  xor     ebx, ebx
0x1800307fe  mov     rsi, r8
0x180030801  mov     edi, edx
0x180030803  mov     [rbp+57h+StringSecurityDescriptor], rbx
0x180030807  mov     r15, rcx
0x18003080a  mov     [rbp+57h+pGroup], rbx
0x18003080e  mov     rcx, [rcx+30h]; StringSecurityDescriptor
0x180030812  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x180030816  lea     edx, [rbx+1]; StringSDRevision
0x180030819  mov     [rbp+57h+var_58], rbx
0x18003081d  xor     r9d, r9d; SecurityDescriptorSize
0x180030820  mov     [rbp+57h+SecurityDescriptor], rbx
0x180030824  mov     r14d, ebx
0x180030827  mov     [rbp+57h+bGroupDefaulted], ebx
0x18003082a  mov     [rbp+57h+bDaclPresent], ebx
0x18003082d  mov     r13d, ebx
0x180030830  mov     [rbp+57h+dwAbsoluteSecurityDescriptorSize], ebx
0x180030833  mov     r12d, ebx
0x180030836  mov     [rbp+57h+dwDaclSize], ebx
0x180030839  mov     [rbp+57h+dwSaclSize], ebx
0x18003083c  mov     [rbp+57h+dwOwnerSize], ebx
0x18003083f  mov     [rbp+57h+dwPrimaryGroupSize], ebx
0x180030842  mov     [rbp+57h+pDacl], rbx
0x180030846  mov     [rbp+57h+hMem], rbx
0x18003084a  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180030850  test    eax, eax
0x180030852  jnz     short loc_180030879
0x180030854  call    cs:__imp_GetLastError
0x18003085a  mov     ebx, eax
0x18003085c  test    eax, eax
0x18003085e  jz      loc_180030906
0x180030864  jle     short loc_18003086F
0x180030866  movzx   ebx, ax
0x180030869  or      ebx, 80070000h
0x18003086f  test    ebx, ebx
0x180030871  js      loc_18003090B
0x180030877  xor     ebx, ebx
0x180030879  mov     rcx, [rbp+57h+SecurityDescriptor]; pSelfRelativeSecurityDescriptor
0x18003087d  lea     rax, [rbp+57h+dwPrimaryGroupSize]
0x180030881  mov     [rsp+0E0h+lpdwPrimaryGroupSize], rax; lpdwPrimaryGroupSize
0x180030886  lea     r8, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x18003088a  mov     [rsp+0E0h+pPrimaryGroup], rbx; pPrimaryGroup
0x18003088f  lea     rax, [rbp+57h+dwOwnerSize]
0x180030893  mov     [rsp+0E0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x180030898  xor     r9d, r9d; pDacl
0x18003089b  mov     [rsp+0E0h+pOwner], rbx; pOwner
0x1800308a0  lea     rax, [rbp+57h+dwSaclSize]
0x1800308a4  mov     [rsp+0E0h+lpdwSaclSize], rax; lpdwSaclSize
0x1800308a9  xor     edx, edx; pAbsoluteSecurityDescriptor
0x1800308ab  lea     rax, [rbp+57h+dwDaclSize]
0x1800308af  mov     [rsp+0E0h+pSacl], rbx; pSacl
0x1800308b4  mov     [rsp+0E0h+lpdwDaclSize], rax; lpdwDaclSize
0x1800308b9  call    cs:__imp_MakeAbsoluteSD
0x1800308bf  test    eax, eax
0x1800308c1  jnz     loc_180030CAF
0x1800308c7  call    cs:__imp_GetLastError
0x1800308cd  test    eax, eax
0x1800308cf  jz      short loc_1800308E3
0x1800308d1  jle     short loc_1800308DD
0x1800308d3  movzx   eax, ax
0x1800308d6  or      eax, 80070000h
0x1800308db  test    eax, eax
0x1800308dd  jns     loc_180030CAF
0x1800308e3  mov     edx, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; uBytes
0x1800308e6  mov     ecx, 40h ; '@'; uFlags
0x1800308eb  call    cs:__imp_LocalAlloc
0x1800308f1  mov     r14, rax
0x1800308f4  test    rax, rax
0x1800308f7  jnz     short loc_180030933
0x1800308f9  mov     edi, 8007000Eh
0x1800308fe  mov     ebx, edi
0x180030900  mov     dword ptr [rsp+0E0h+lpdwDaclSize], edi
0x180030904  jmp     short loc_180030911
0x180030906  mov     ebx, 80004005h
0x18003090b  mov     eax, ebx
0x18003090d  mov     dword ptr [rsp+0E0h+lpdwDaclSize], eax
0x180030911  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180030918  xor     r8d, r8d; int
0x18003091b  lea     rdx, aWdcsecurityobj_1; "WdcSecurityObject::SetSecurity"
0x180030922  lea     rcx, aBaseDiagnosisP_8; "base\\diagnosis\\pdui\\perfmon\\mmc\\se"...
0x180030929  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18003092e  jmp     loc_180030CB4
0x180030933  mov     edx, [rbp+57h+dwDaclSize]; uBytes
0x180030936  mov     ecx, 40h ; '@'; uFlags
0x18003093b  call    cs:__imp_LocalAlloc
0x180030941  mov     [rbp+57h+pDacl], rax
0x180030945  test    rax, rax
0x180030948  jz      short loc_1800308F9
0x18003094a  mov     edx, [rbp+57h+dwSaclSize]; uBytes
0x18003094d  mov     ecx, 40h ; '@'; uFlags
0x180030952  call    cs:__imp_LocalAlloc
0x180030958  mov     [rbp+57h+hMem], rax
0x18003095c  mov     rbx, rax
0x18003095f  test    rax, rax
0x180030962  jz      short loc_1800308F9
0x180030964  mov     edx, [rbp+57h+dwOwnerSize]; uBytes
0x180030967  mov     ecx, 40h ; '@'; uFlags
0x18003096c  call    cs:__imp_LocalAlloc
0x180030972  mov     r13, rax
0x180030975  test    rax, rax
0x180030978  jz      loc_1800308F9
0x18003097e  mov     edx, [rbp+57h+dwPrimaryGroupSize]; uBytes
0x180030981  mov     ecx, 40h ; '@'; uFlags
0x180030986  call    cs:__imp_LocalAlloc
0x18003098c  mov     r12, rax
0x18003098f  test    rax, rax
0x180030992  jz      loc_1800308F9
0x180030998  mov     r9, [rbp+57h+pDacl]; pDacl
0x18003099c  lea     rax, [rbp+57h+dwPrimaryGroupSize]
0x1800309a0  mov     rcx, [rbp+57h+SecurityDescriptor]; pSelfRelativeSecurityDescriptor
0x1800309a4  lea     r8, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x1800309a8  mov     [rsp+0E0h+lpdwPrimaryGroupSize], rax; lpdwPrimaryGroupSize
0x1800309ad  mov     rdx, r14; pAbsoluteSecurityDescriptor
0x1800309b0  mov     [rsp+0E0h+pPrimaryGroup], r12; pPrimaryGroup
0x1800309b5  lea     rax, [rbp+57h+dwOwnerSize]
0x1800309b9  mov     [rsp+0E0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x1800309be  lea     rax, [rbp+57h+dwSaclSize]
0x1800309c2  mov     [rsp+0E0h+pOwner], r13; pOwner
0x1800309c7  mov     [rsp+0E0h+lpdwSaclSize], rax; lpdwSaclSize
0x1800309cc  lea     rax, [rbp+57h+dwDaclSize]
0x1800309d0  mov     [rsp+0E0h+pSacl], rbx; pSacl
0x1800309d5  mov     [rsp+0E0h+lpdwDaclSize], rax; lpdwDaclSize
0x1800309da  call    cs:__imp_MakeAbsoluteSD
0x1800309e0  test    eax, eax
0x1800309e2  jnz     short loc_180030A07
0x1800309e4  call    cs:__imp_GetLastError
0x1800309ea  mov     ebx, eax
0x1800309ec  test    eax, eax
0x1800309ee  jz      loc_180030906
0x1800309f4  jle     short loc_1800309FF
0x1800309f6  movzx   ebx, ax
0x1800309f9  or      ebx, 80070000h
0x1800309ff  test    ebx, ebx
0x180030a01  js      loc_18003090B
0x180030a07  test    dil, 2
0x180030a0b  jz      short loc_180030A7D
0x180030a0d  lea     r8, [rbp+57h+bGroupDefaulted]; lpbGroupDefaulted
0x180030a11  mov     rcx, rsi; pSecurityDescriptor
0x180030a14  lea     rdx, [rbp+57h+pGroup]; pGroup
0x180030a18  call    cs:__imp_GetSecurityDescriptorGroup
0x180030a1e  test    eax, eax
0x180030a20  jnz     short loc_180030A45
0x180030a22  call    cs:__imp_GetLastError
0x180030a28  mov     ebx, eax
0x180030a2a  test    eax, eax
0x180030a2c  jz      loc_180030906
0x180030a32  jle     short loc_180030A3D
0x180030a34  movzx   ebx, ax
0x180030a37  or      ebx, 80070000h
0x180030a3d  test    ebx, ebx
0x180030a3f  js      loc_18003090B
0x180030a45  mov     r8d, [rbp+57h+bGroupDefaulted]; bGroupDefaulted
0x180030a49  mov     rcx, r14; pSecurityDescriptor
0x180030a4c  mov     rdx, [rbp+57h+pGroup]; pGroup
0x180030a50  call    cs:__imp_SetSecurityDescriptorGroup
0x180030a56  test    eax, eax
0x180030a58  jnz     short loc_180030A7D
0x180030a5a  call    cs:__imp_GetLastError
0x180030a60  mov     ebx, eax
0x180030a62  test    eax, eax
0x180030a64  jz      loc_180030906
0x180030a6a  jle     short loc_180030A75
0x180030a6c  movzx   ebx, ax
0x180030a6f  or      ebx, 80070000h
0x180030a75  test    ebx, ebx
0x180030a77  js      loc_18003090B
0x180030a7d  test    dil, 1
0x180030a81  jz      short loc_180030AF3
0x180030a83  lea     r8, [rbp+57h+bGroupDefaulted]; lpbOwnerDefaulted
0x180030a87  mov     rcx, rsi; pSecurityDescriptor
0x180030a8a  lea     rdx, [rbp+57h+pGroup]; pOwner
0x180030a8e  call    cs:__imp_GetSecurityDescriptorOwner
0x180030a94  test    eax, eax
0x180030a96  jnz     short loc_180030ABB
0x180030a98  call    cs:__imp_GetLastError
0x180030a9e  mov     ebx, eax
0x180030aa0  test    eax, eax
0x180030aa2  jz      loc_180030906
0x180030aa8  jle     short loc_180030AB3
0x180030aaa  movzx   ebx, ax
0x180030aad  or      ebx, 80070000h
0x180030ab3  test    ebx, ebx
0x180030ab5  js      loc_18003090B
0x180030abb  mov     r8d, [rbp+57h+bGroupDefaulted]; bOwnerDefaulted
0x180030abf  mov     rcx, r14; pSecurityDescriptor
0x180030ac2  mov     rdx, [rbp+57h+pGroup]; pOwner
0x180030ac6  call    cs:__imp_SetSecurityDescriptorOwner
0x180030acc  test    eax, eax
0x180030ace  jnz     short loc_180030AF3
0x180030ad0  call    cs:__imp_GetLastError
0x180030ad6  mov     ebx, eax
0x180030ad8  test    eax, eax
0x180030ada  jz      loc_180030906
0x180030ae0  jle     short loc_180030AEB
0x180030ae2  movzx   ebx, ax
0x180030ae5  or      ebx, 80070000h
0x180030aeb  test    ebx, ebx
0x180030aed  js      loc_18003090B
0x180030af3  test    dil, 4
0x180030af7  jz      short loc_180030B70
0x180030af9  lea     r9, [rbp+57h+bGroupDefaulted]; lpbDaclDefaulted
0x180030afd  mov     rcx, rsi; pSecurityDescriptor
0x180030b00  lea     r8, [rbp+57h+var_58]; pDacl
0x180030b04  lea     rdx, [rbp+57h+bDaclPresent]; lpbDaclPresent
0x180030b08  call    cs:__imp_GetSecurityDescriptorDacl
0x180030b0e  test    eax, eax
0x180030b10  jnz     short loc_180030B35
0x180030b12  call    cs:__imp_GetLastError
0x180030b18  mov     ebx, eax
0x180030b1a  test    eax, eax
0x180030b1c  jz      loc_180030906
0x180030b22  jle     short loc_180030B2D
0x180030b24  movzx   ebx, ax
0x180030b27  or      ebx, 80070000h
0x180030b2d  test    ebx, ebx
0x180030b2f  js      loc_18003090B
0x180030b35  mov     r9d, [rbp+57h+bGroupDefaulted]; bDaclDefaulted
0x180030b39  mov     rcx, r14; pSecurityDescriptor
0x180030b3c  mov     r8, [rbp+57h+var_58]; pDacl
0x180030b40  mov     edx, [rbp+57h+bDaclPresent]; bDaclPresent
0x180030b43  call    cs:__imp_SetSecurityDescriptorDacl
0x180030b49  test    eax, eax
0x180030b4b  jnz     short loc_180030B70
0x180030b4d  call    cs:__imp_GetLastError
0x180030b53  mov     ebx, eax
0x180030b55  test    eax, eax
0x180030b57  jz      loc_180030906
0x180030b5d  jle     short loc_180030B68
0x180030b5f  movzx   ebx, ax
0x180030b62  or      ebx, 80070000h
0x180030b68  test    ebx, ebx
0x180030b6a  js      loc_18003090B
0x180030b70  test    dil, 8
0x180030b74  jz      short loc_180030BED
0x180030b76  lea     r9, [rbp+57h+bGroupDefaulted]; lpbSaclDefaulted
0x180030b7a  mov     rcx, rsi; pSecurityDescriptor
0x180030b7d  lea     r8, [rbp+57h+var_58]; pSacl
0x180030b81  lea     rdx, [rbp+57h+bDaclPresent]; lpbSaclPresent
0x180030b85  call    cs:__imp_GetSecurityDescriptorSacl
0x180030b8b  test    eax, eax
0x180030b8d  jnz     short loc_180030BB2
0x180030b8f  call    cs:__imp_GetLastError
0x180030b95  mov     ebx, eax
0x180030b97  test    eax, eax
0x180030b99  jz      loc_180030906
0x180030b9f  jle     short loc_180030BAA
0x180030ba1  movzx   ebx, ax
0x180030ba4  or      ebx, 80070000h
0x180030baa  test    ebx, ebx
0x180030bac  js      loc_18003090B
0x180030bb2  mov     r9d, [rbp+57h+bGroupDefaulted]; bSaclDefaulted
0x180030bb6  mov     rcx, r14; pSecurityDescriptor
0x180030bb9  mov     r8, [rbp+57h+var_58]; pSacl
0x180030bbd  mov     edx, [rbp+57h+bDaclPresent]; bSaclPresent
0x180030bc0  call    cs:__imp_SetSecurityDescriptorSacl
0x180030bc6  test    eax, eax
0x180030bc8  jnz     short loc_180030BED
0x180030bca  call    cs:__imp_GetLastError
0x180030bd0  mov     ebx, eax
0x180030bd2  test    eax, eax
0x180030bd4  jz      loc_180030906
0x180030bda  jle     short loc_180030BE5
0x180030bdc  movzx   ebx, ax
0x180030bdf  or      ebx, 80070000h
0x180030be5  test    ebx, ebx
0x180030be7  js      loc_18003090B
0x180030bed  or      [r15+38h], edi
0x180030bf1  lea     r9, [rbp+57h+StringSecurityDescriptor]; StringSecurityDescriptor
0x180030bf5  mov     r8d, [r15+38h]; SecurityInformation
0x180030bf9  mov     edx, 1; RequestedStringSDRevision
0x180030bfe  mov     rcx, r14; SecurityDescriptor
0x180030c01  mov     [rsp+0E0h+lpdwDaclSize], 0; StringSecurityDescriptorLen
0x180030c0a  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x180030c10  test    eax, eax
0x180030c12  jnz     short loc_180030C37
0x180030c14  call    cs:__imp_GetLastError
0x180030c1a  mov     ebx, eax
0x180030c1c  test    eax, eax
0x180030c1e  jz      loc_180030906
0x180030c24  jle     short loc_180030C2F
0x180030c26  movzx   ebx, ax
0x180030c29  or      ebx, 80070000h
0x180030c2f  test    ebx, ebx
0x180030c31  js      loc_18003090B
0x180030c37  mov     rcx, [r15+30h]; bstrString
0x180030c3b  mov     rbx, [rbp+57h+StringSecurityDescriptor]
0x180030c3f  test    rcx, rcx
0x180030c42  jz      short loc_180030C52
0x180030c44  call    cs:__imp_SysFreeString
0x180030c4a  mov     qword ptr [r15+30h], 0
  ... truncated ...
```
