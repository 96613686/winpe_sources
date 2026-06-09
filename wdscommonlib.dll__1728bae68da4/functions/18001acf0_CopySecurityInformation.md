# CopySecurityInformation

- ea: `0x18001acf0`
- end: `0x18001aed2`
- name: `CopySecurityInformation`
- size: `482`
- prototype: `__int64 __fastcall(LPCWSTR pObjectName, LPWSTR)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x18001a1c8`

## callees

- `0x18001acf0`
- `0x18001b0cc`
- `0x18001dbe0`
- `0x18001dc30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001adcd`
- `KERNEL32!GetLastError` at `0x18001adcd`
- `KERNEL32!LocalFree` at `0x18001ae97`
- `KERNEL32!LocalFree` at `0x18001ae97`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x18001ad8d`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x18001ad8d`
- `ADVAPI32!GetSecurityDescriptorControl` at `0x18001adbd`
- `ADVAPI32!GetSecurityDescriptorControl` at `0x18001adbd`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x18001ae5e`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x18001ae5e`

## pseudocode

```c
__int64 __fastcall CopySecurityInformation(LPCWSTR pObjectName, LPWSTR a2, int a3)
{
  signed int v6; // ebx
  int NamedSecurityInfoW; // eax
  int v8; // ebx
  DWORD LastError; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  int v12; // eax
  SECURITY_INFORMATION v13; // r8d
  __int64 v14; // rdx
  __int64 v15; // r8
  DWORD dwRevision; // [rsp+40h] [rbp-30h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+48h] [rbp-28h] BYREF
  PACL pSacl; // [rsp+50h] [rbp-20h] BYREF
  PACL pDacl; // [rsp+58h] [rbp-18h] BYREF
  PSID psidGroup; // [rsp+60h] [rbp-10h] BYREF
  PSID ppsidOwner; // [rsp+68h] [rbp-8h] BYREF
  WORD pControl; // [rsp+A8h] [rbp+38h] BYREF

  dwRevision = 0;
  psidGroup = 0;
  ppsidOwner = 0;
  pDacl = 0;
  pSacl = 0;
  pSecurityDescriptor = 0;
  pControl = 0;
  v6 = WdsModifySecurityPrivilege(1);
  if ( v6 >= 0 )
  {
    v6 = WdsModifyRestorePrivilege(1);
    if ( v6 >= 0 )
    {
      NamedSecurityInfoW = GetNamedSecurityInfoW(
                             pObjectName,
                             SE_FILE_OBJECT,
                             0xFu,
                             &ppsidOwner,
                             &psidGroup,
                             &pDacl,
                             &pSacl,
                             &pSecurityDescriptor);
      dwRevision = NamedSecurityInfoW;
      if ( NamedSecurityInfoW )
      {
        if ( NamedSecurityInfoW <= 0 )
        {
          v6 = NamedSecurityInfoW;
          goto LABEL_20;
        }
        v8 = (unsigned __int16)NamedSecurityInfoW;
        goto LABEL_19;
      }
      if ( GetSecurityDescriptorControl(pSecurityDescriptor, &pControl, &dwRevision) )
      {
        if ( a3 )
        {
          v13 = ((pControl & 0xF000) << 19) | 0xF;
          if ( (pControl & 0x2000) != 0 )
            v13 = ((pControl & 0xF000) << 19) | 0x4000000F;
        }
        else
        {
          v13 = -1073741809;
        }
        dwRevision = SetNamedSecurityInfoW(a2, SE_FILE_OBJECT, v13, ppsidOwner, psidGroup, pDacl, pSacl);
        if ( (unsigned int)ElValidateWin32_8(dwRevision, v14, v15, 2299) )
        {
          v6 = dwRevision;
          if ( (int)dwRevision > 0 )
          {
            v8 = (unsigned __int16)dwRevision;
LABEL_19:
            v6 = v8 | 0x80070000;
          }
        }
      }
      else
      {
        LastError = GetLastError();
        v12 = ElValidateWin32_8(LastError, v10, v11, 2263);
        v6 = v12;
        if ( v12 > 0 )
          v6 = (unsigned __int16)v12 | 0x80070000;
        if ( v6 >= 0 )
          v6 = -2147467259;
      }
    }
  }
LABEL_20:
  if ( pSecurityDescriptor )
  {
    LocalFree(pSecurityDescriptor);
    pSecurityDescriptor = 0;
  }
  WdsModifyRestorePrivilege(0);
  WdsModifySecurityPrivilege(0);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001acf0  mov     [rsp-18h+arg_0], rbx
0x18001acf5  mov     [rsp-18h+arg_8], rsi
0x18001acfa  mov     [rsp-18h+arg_10], rdi
0x18001acff  push    rbp
0x18001ad00  push    r14
0x18001ad02  push    r15
0x18001ad04  mov     rbp, rsp
0x18001ad07  sub     rsp, 70h
0x18001ad0b  xor     r15d, r15d
0x18001ad0e  mov     rsi, rcx
0x18001ad11  mov     edi, r8d
0x18001ad14  mov     [rbp+dwRevision], r15d
0x18001ad18  mov     r14, rdx
0x18001ad1b  mov     [rbp+psidGroup], r15
0x18001ad1f  mov     [rbp+ppsidOwner], r15
0x18001ad23  lea     ecx, [r15+1]
0x18001ad27  mov     [rbp+pDacl], r15
0x18001ad2b  mov     [rbp+pSacl], r15
0x18001ad2f  mov     [rbp+pSecurityDescriptor], r15
0x18001ad33  mov     [rbp+pControl], r15w
0x18001ad38  call    WdsModifySecurityPrivilege
0x18001ad3d  mov     ebx, eax
0x18001ad3f  test    eax, eax
0x18001ad41  js      loc_18001AE8E
0x18001ad47  lea     ecx, [r15+1]
0x18001ad4b  call    WdsModifyRestorePrivilege
0x18001ad50  mov     ebx, eax
0x18001ad52  test    eax, eax
0x18001ad54  js      loc_18001AE8E
0x18001ad5a  lea     rax, [rbp+pSecurityDescriptor]
0x18001ad5e  mov     rcx, rsi; pObjectName
0x18001ad61  mov     [rsp+70h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x18001ad66  lea     r9, [rbp+ppsidOwner]; ppsidOwner
0x18001ad6a  lea     rax, [rbp+pSacl]
0x18001ad6e  mov     [rsp+70h+ppSacl], rax; ppSacl
0x18001ad73  lea     edx, [r15+1]; ObjectType
0x18001ad77  lea     rax, [rbp+pDacl]
0x18001ad7b  mov     [rsp+70h+ppDacl], rax; ppDacl
0x18001ad80  lea     r8d, [r15+0Fh]; SecurityInfo
0x18001ad84  lea     rax, [rbp+psidGroup]
0x18001ad88  mov     [rsp+70h+ppsidGroup], rax; ppsidGroup
0x18001ad8d  call    cs:__imp_GetNamedSecurityInfoW
0x18001ad94  nop     dword ptr [rax+rax+00h]
0x18001ad99  mov     [rbp+dwRevision], eax
0x18001ad9c  test    eax, eax
0x18001ad9e  jz      short loc_18001ADB1
0x18001ada0  jg      short loc_18001ADA9
0x18001ada2  mov     ebx, eax
0x18001ada4  jmp     loc_18001AE8E
0x18001ada9  movzx   ebx, ax
0x18001adac  jmp     loc_18001AE88
0x18001adb1  mov     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x18001adb5  lea     r8, [rbp+dwRevision]; lpdwRevision
0x18001adb9  lea     rdx, [rbp+pControl]; pControl
0x18001adbd  call    cs:__imp_GetSecurityDescriptorControl
0x18001adc4  nop     dword ptr [rax+rax+00h]
0x18001adc9  test    eax, eax
0x18001adcb  jnz     short loc_18001AE07
0x18001adcd  call    cs:__imp_GetLastError
0x18001add4  nop     dword ptr [rax+rax+00h]
0x18001add9  mov     ecx, eax
0x18001addb  mov     r9d, 8D7h
0x18001ade1  call    ElValidateWin32_8
0x18001ade6  mov     ebx, eax
0x18001ade8  test    eax, eax
0x18001adea  jle     short loc_18001ADF5
0x18001adec  movzx   ebx, ax
0x18001adef  or      ebx, 80070000h
0x18001adf5  test    ebx, ebx
0x18001adf7  js      loc_18001AE8E
0x18001adfd  mov     ebx, 80004005h
0x18001ae02  jmp     loc_18001AE8E
0x18001ae07  test    edi, edi
0x18001ae09  jnz     short loc_18001AE13
0x18001ae0b  mov     r8d, 0C000000Fh
0x18001ae11  jmp     short loc_18001AE37
0x18001ae13  movzx   r8d, [rbp+pControl]
0x18001ae18  mov     eax, 2000h
0x18001ae1d  and     r8d, 0FFFFF000h
0x18001ae24  shl     r8d, 13h
0x18001ae28  or      r8d, 0Fh
0x18001ae2c  test    [rbp+pControl], ax
0x18001ae30  jz      short loc_18001AE37
0x18001ae32  bts     r8d, 1Eh; SecurityInfo
0x18001ae37  mov     rax, [rbp+pSacl]
0x18001ae3b  mov     edx, 1; ObjectType
0x18001ae40  mov     r9, [rbp+ppsidOwner]; psidOwner
0x18001ae44  mov     rcx, r14; pObjectName
0x18001ae47  mov     [rsp+70h+ppSacl], rax; pSacl
0x18001ae4c  mov     rax, [rbp+pDacl]
0x18001ae50  mov     [rsp+70h+ppDacl], rax; pDacl
0x18001ae55  mov     rax, [rbp+psidGroup]
0x18001ae59  mov     [rsp+70h+ppsidGroup], rax; psidGroup
0x18001ae5e  call    cs:__imp_SetNamedSecurityInfoW
0x18001ae65  nop     dword ptr [rax+rax+00h]
0x18001ae6a  mov     ecx, eax
0x18001ae6c  mov     [rbp+dwRevision], eax
0x18001ae6f  mov     r9d, 8FBh
0x18001ae75  call    ElValidateWin32_8
0x18001ae7a  test    eax, eax
0x18001ae7c  jz      short loc_18001AE8E
0x18001ae7e  mov     ebx, [rbp+dwRevision]
0x18001ae81  test    ebx, ebx
0x18001ae83  jle     short loc_18001AE8E
0x18001ae85  movzx   ebx, bx
0x18001ae88  or      ebx, 80070000h
0x18001ae8e  mov     rcx, [rbp+pSecurityDescriptor]; hMem
0x18001ae92  test    rcx, rcx
0x18001ae95  jz      short loc_18001AEA7
0x18001ae97  call    cs:__imp_LocalFree
0x18001ae9e  nop     dword ptr [rax+rax+00h]
0x18001aea3  mov     [rbp+pSecurityDescriptor], r15
0x18001aea7  xor     ecx, ecx
0x18001aea9  call    WdsModifyRestorePrivilege
0x18001aeae  xor     ecx, ecx
0x18001aeb0  call    WdsModifySecurityPrivilege
0x18001aeb5  lea     r11, [rsp+70h+var_s0]
0x18001aeba  mov     eax, ebx
0x18001aebc  mov     rbx, [r11+20h]
0x18001aec0  mov     rsi, [r11+28h]
0x18001aec4  mov     rdi, [r11+30h]
0x18001aec8  mov     rsp, r11
0x18001aecb  pop     r15
0x18001aecd  pop     r14
0x18001aecf  pop     rbp
0x18001aed0  retn
```
