# CSecurityInformation::WriteObjectSecurity(ushort const *,ulong,void *)

- ea: `0x18000c8b0`
- end: `0x18000ca30`
- name: `?WriteObjectSecurity@CSecurityInformation@@MEAAJPEBGKPEAX@Z`
- size: `384`
- prototype: `int __fastcall(SE_OBJECT_TYPE *this, WCHAR *, SECURITY_INFORMATION, void *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180008110`

## callees

- `0x18000c8b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c930`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c930`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18000c984`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18000c984`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18000c8ee`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18000c8ee`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18000c926`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18000c926`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x18000c96b`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x18000c96b`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x18000c956`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x18000c956`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x18000c99d`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x18000c99d`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x18000ca04`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x18000ca04`

## pseudocode

```c
int __fastcall CSecurityInformation::WriteObjectSecurity(
        SE_OBJECT_TYPE *this,
        WCHAR *a2,
        SECURITY_INFORMATION a3,
        void *a4)
{
  SECURITY_INFORMATION v5; // ebx
  int result; // eax
  WINBOOL bOwnerDefaulted; // [rsp+40h] [rbp-30h] BYREF
  WINBOOL bDaclPresent; // [rsp+44h] [rbp-2Ch] BYREF
  DWORD dwRevision; // [rsp+48h] [rbp-28h] BYREF
  PACL pSacl; // [rsp+50h] [rbp-20h] BYREF
  PACL pDacl; // [rsp+58h] [rbp-18h] BYREF
  PSID pGroup; // [rsp+60h] [rbp-10h] BYREF
  PSID pOwner; // [rsp+68h] [rbp-8h] BYREF
  WORD pControl; // [rsp+A8h] [rbp+38h] BYREF

  v5 = a3;
  if ( !a4 || !a2 )
    return -2147467261;
  if ( !a3 || !IsValidSecurityDescriptor(a4) )
    return -2147024809;
  pControl = 0;
  dwRevision = 0;
  pOwner = 0;
  pGroup = 0;
  pDacl = 0;
  pSacl = 0;
  bOwnerDefaulted = 0;
  bDaclPresent = 0;
  if ( GetSecurityDescriptorControl(a4, &pControl, &dwRevision)
    && GetSecurityDescriptorOwner(a4, &pOwner, &bOwnerDefaulted)
    && GetSecurityDescriptorGroup(a4, &pGroup, &bOwnerDefaulted)
    && GetSecurityDescriptorDacl(a4, &bDaclPresent, &pDacl, &bOwnerDefaulted)
    && GetSecurityDescriptorSacl(a4, &bDaclPresent, &pSacl, &bOwnerDefaulted) )
  {
    if ( (v5 & 4) != 0 )
    {
      if ( (pControl & 0x1000) != 0 )
        v5 |= 0x80000000;
      else
        v5 |= 0x20000000u;
    }
    if ( (v5 & 8) != 0 )
    {
      if ( (pControl & 0x2000) != 0 )
        v5 |= 0x40000000u;
      else
        v5 |= 0x10000000u;
    }
    result = SetNamedSecurityInfoW(a2, this[13], v5, pOwner, pGroup, pDacl, pSacl);
  }
  else
  {
    result = GetLastError();
  }
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18000c8b0  mov     [rsp-18h+arg_0], rbx
0x18000c8b5  mov     [rsp-18h+arg_8], rsi
0x18000c8ba  push    rbp
0x18000c8bb  push    rdi
0x18000c8bc  push    r14
0x18000c8be  mov     rbp, rsp
0x18000c8c1  sub     rsp, 70h
0x18000c8c5  mov     rdi, r9
0x18000c8c8  mov     ebx, r8d
0x18000c8cb  mov     rsi, rdx
0x18000c8ce  mov     r14, rcx
0x18000c8d1  test    r9, r9
0x18000c8d4  jz      loc_18000CA16
0x18000c8da  test    rdx, rdx
0x18000c8dd  jz      loc_18000CA16
0x18000c8e3  test    ebx, ebx
0x18000c8e5  jz      loc_18000CA0F
0x18000c8eb  mov     rcx, r9; pSecurityDescriptor
0x18000c8ee  call    cs:__imp_IsValidSecurityDescriptor
0x18000c8f4  test    eax, eax
0x18000c8f6  jz      loc_18000CA0F
0x18000c8fc  xor     eax, eax
0x18000c8fe  lea     r8, [rbp+dwRevision]; lpdwRevision
0x18000c902  lea     rdx, [rbp+pControl]; pControl
0x18000c906  mov     [rbp+pControl], ax
0x18000c90a  mov     rcx, rdi; pSecurityDescriptor
0x18000c90d  mov     [rbp+dwRevision], eax
0x18000c910  mov     [rbp+pOwner], rax
0x18000c914  mov     [rbp+pGroup], rax
0x18000c918  mov     [rbp+pDacl], rax
0x18000c91c  mov     [rbp+pSacl], rax
0x18000c920  mov     [rbp+bOwnerDefaulted], eax
0x18000c923  mov     [rbp+bDaclPresent], eax
0x18000c926  call    cs:__imp_GetSecurityDescriptorControl
0x18000c92c  test    eax, eax
0x18000c92e  jnz     short loc_18000C94B
0x18000c930  call    cs:__imp_GetLastError
0x18000c936  test    eax, eax
0x18000c938  jle     loc_18000CA1B
0x18000c93e  movzx   eax, ax
0x18000c941  or      eax, 80070000h
0x18000c946  jmp     loc_18000CA1B
0x18000c94b  lea     r8, [rbp+bOwnerDefaulted]; lpbOwnerDefaulted
0x18000c94f  mov     rcx, rdi; pSecurityDescriptor
0x18000c952  lea     rdx, [rbp+pOwner]; pOwner
0x18000c956  call    cs:__imp_GetSecurityDescriptorOwner
0x18000c95c  test    eax, eax
0x18000c95e  jz      short loc_18000C930
0x18000c960  lea     r8, [rbp+bOwnerDefaulted]; lpbGroupDefaulted
0x18000c964  mov     rcx, rdi; pSecurityDescriptor
0x18000c967  lea     rdx, [rbp+pGroup]; pGroup
0x18000c96b  call    cs:__imp_GetSecurityDescriptorGroup
0x18000c971  test    eax, eax
0x18000c973  jz      short loc_18000C930
0x18000c975  lea     r9, [rbp+bOwnerDefaulted]; lpbDaclDefaulted
0x18000c979  mov     rcx, rdi; pSecurityDescriptor
0x18000c97c  lea     r8, [rbp+pDacl]; pDacl
0x18000c980  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x18000c984  call    cs:__imp_GetSecurityDescriptorDacl
0x18000c98a  test    eax, eax
0x18000c98c  jz      short loc_18000C930
0x18000c98e  lea     r9, [rbp+bOwnerDefaulted]; lpbSaclDefaulted
0x18000c992  mov     rcx, rdi; pSecurityDescriptor
0x18000c995  lea     r8, [rbp+pSacl]; pSacl
0x18000c999  lea     rdx, [rbp+bDaclPresent]; lpbSaclPresent
0x18000c99d  call    cs:__imp_GetSecurityDescriptorSacl
0x18000c9a3  test    eax, eax
0x18000c9a5  jz      short loc_18000C930
0x18000c9a7  test    bl, 4
0x18000c9aa  jz      short loc_18000C9C1
0x18000c9ac  mov     eax, 1000h
0x18000c9b1  test    [rbp+pControl], ax
0x18000c9b5  jz      short loc_18000C9BD
0x18000c9b7  bts     ebx, 1Fh
0x18000c9bb  jmp     short loc_18000C9C1
0x18000c9bd  bts     ebx, 1Dh
0x18000c9c1  test    bl, 8
0x18000c9c4  jz      short loc_18000C9DB
0x18000c9c6  mov     eax, 2000h
0x18000c9cb  test    [rbp+pControl], ax
0x18000c9cf  jz      short loc_18000C9D7
0x18000c9d1  bts     ebx, 1Eh
0x18000c9d5  jmp     short loc_18000C9DB
0x18000c9d7  bts     ebx, 1Ch
0x18000c9db  mov     rax, [rbp+pSacl]
0x18000c9df  mov     r8d, ebx; SecurityInfo
0x18000c9e2  mov     r9, [rbp+pOwner]; psidOwner
0x18000c9e6  mov     rcx, rsi; pObjectName
0x18000c9e9  mov     edx, [r14+34h]; ObjectType
0x18000c9ed  mov     [rsp+70h+var_40], rax; pSacl
0x18000c9f2  mov     rax, [rbp+pDacl]
0x18000c9f6  mov     [rsp+70h+var_48], rax; pDacl
0x18000c9fb  mov     rax, [rbp+pGroup]
0x18000c9ff  mov     [rsp+70h+psidGroup], rax; psidGroup
0x18000ca04  call    cs:__imp_SetNamedSecurityInfoW
0x18000ca0a  jmp     loc_18000C936
0x18000ca0f  mov     eax, 80070057h
0x18000ca14  jmp     short loc_18000CA1B
0x18000ca16  mov     eax, 80004003h
0x18000ca1b  lea     r11, [rsp+70h+var_s0]
0x18000ca20  mov     rbx, [r11+20h]
0x18000ca24  mov     rsi, [r11+28h]
0x18000ca28  mov     rsp, r11
0x18000ca2b  pop     r14
0x18000ca2d  pop     rdi
0x18000ca2e  pop     rbp
0x18000ca2f  retn
```
