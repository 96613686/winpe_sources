# CFSShareSecurityInformation::SetSecurity(ulong,void *)

- ea: `0x18000ac00`
- end: `0x18000ae79`
- name: `?SetSecurity@CFSShareSecurityInformation@@UEAAJKPEAX@Z`
- size: `633`
- prototype: `__int64 __fastcall(CFSShareSecurityInformation *this, int, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000ac00`
- `0x180015e64`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000acc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000adb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000acc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000adb5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ae16`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ae2a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ae33`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ae3c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ae45`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ae4f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ae16`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ae2a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ae33`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ae3c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ae45`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ae4f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000acf6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ad16`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ad2c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ad42`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ad58`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000acf6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ad16`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ad2c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ad42`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ad58`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18000addb`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18000addb`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18000ac3e`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18000ac3e`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x18000acbd`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x18000adab`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x18000acbd`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x18000adab`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18000adf3`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18000adf3`

## pseudocode

```c
__int64 __fastcall CFSShareSecurityInformation::SetSecurity(CFSShareSecurityInformation *this, int a2, void *a3)
{
  char v4; // bl
  void *v7; // rcx
  struct _ACL *v8; // r15
  struct _ACL *pSacl; // r12
  HLOCAL pOwner; // r13
  signed int LastError; // eax
  signed int SelfRelativeSecurityDescriptor; // ebx
  HLOCAL v13; // rdi
  HLOCAL pPrimaryGroup; // rax
  DWORD dwSaclSize; // [rsp+60h] [rbp-9h] BYREF
  DWORD dwDaclSize; // [rsp+64h] [rbp-5h] BYREF
  DWORD dwAbsoluteSecurityDescriptorSize; // [rsp+68h] [rbp-1h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+6Ch] [rbp+3h] BYREF
  WINBOOL bDaclPresent; // [rsp+70h] [rbp+7h] BYREF
  PACL pDacl; // [rsp+78h] [rbp+Fh] BYREF
  void *v21; // [rsp+80h] [rbp+17h] BYREF
  HLOCAL hMem; // [rsp+88h] [rbp+1Fh]
  DWORD dwPrimaryGroupSize; // [rsp+E0h] [rbp+77h] BYREF
  DWORD dwOwnerSize; // [rsp+E8h] [rbp+7Fh] BYREF

  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  if ( a2 && IsValidSecurityDescriptor(a3) )
  {
    if ( (v4 & 4) == 0 )
      return 0;
    v7 = (void *)*((_QWORD *)this + 32);
    v21 = 0;
    v8 = 0;
    dwAbsoluteSecurityDescriptorSize = 0;
    pSacl = 0;
    dwDaclSize = 0;
    pOwner = 0;
    dwSaclSize = 0;
    dwOwnerSize = 0;
    dwPrimaryGroupSize = 0;
    hMem = 0;
    if ( MakeAbsoluteSD(
           v7,
           0,
           &dwAbsoluteSecurityDescriptorSize,
           0,
           &dwDaclSize,
           0,
           &dwSaclSize,
           0,
           &dwOwnerSize,
           0,
           &dwPrimaryGroupSize)
      || (LastError = GetLastError(), SelfRelativeSecurityDescriptor = LastError, LastError == 122) )
    {
      v13 = LocalAlloc(0x40u, dwAbsoluteSecurityDescriptorSize);
      if ( !v13
        || (v8 = (struct _ACL *)LocalAlloc(0x40u, dwDaclSize)) == 0
        || (pSacl = (struct _ACL *)LocalAlloc(0x40u, dwSaclSize)) == 0
        || (pOwner = LocalAlloc(0x40u, dwOwnerSize)) == 0
        || (pPrimaryGroup = LocalAlloc(0x40u, dwPrimaryGroupSize), (hMem = pPrimaryGroup) == 0) )
      {
        SelfRelativeSecurityDescriptor = -2147024882;
LABEL_24:
        LocalFree(v13);
        LocalFree(v8);
        LocalFree(pSacl);
        LocalFree(pOwner);
        LocalFree(hMem);
        return (unsigned int)SelfRelativeSecurityDescriptor;
      }
      if ( MakeAbsoluteSD(
             *((PSECURITY_DESCRIPTOR *)this + 32),
             v13,
             &dwAbsoluteSecurityDescriptorSize,
             v8,
             &dwDaclSize,
             pSacl,
             &dwSaclSize,
             pOwner,
             &dwOwnerSize,
             pPrimaryGroup,
             &dwPrimaryGroupSize) )
      {
        bDaclPresent = 0;
        bDaclDefaulted = 0;
        pDacl = 0;
        if ( GetSecurityDescriptorDacl(a3, &bDaclPresent, &pDacl, &bDaclDefaulted) )
        {
          if ( SetSecurityDescriptorDacl(v13, bDaclPresent, pDacl, bDaclDefaulted) )
          {
            SelfRelativeSecurityDescriptor = MakeSelfRelativeSecurityDescriptor(v13, &v21);
            if ( SelfRelativeSecurityDescriptor >= 0 )
            {
              LocalFree(*((HLOCAL *)this + 32));
              *((_QWORD *)this + 32) = v21;
            }
            goto LABEL_24;
          }
        }
      }
      LastError = GetLastError();
      SelfRelativeSecurityDescriptor = LastError;
    }
    else
    {
      v13 = 0;
    }
    if ( LastError > 0 )
      SelfRelativeSecurityDescriptor = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_24;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x18000ac00  mov     [rsp-8+arg_0], rbx
0x18000ac05  push    rbp
0x18000ac06  push    rsi
0x18000ac07  push    rdi
0x18000ac08  push    r12
0x18000ac0a  push    r13
0x18000ac0c  push    r14
0x18000ac0e  push    r15
0x18000ac10  lea     rbp, [rsp-27h]
0x18000ac15  sub     rsp, 90h
0x18000ac1c  mov     rsi, r8
0x18000ac1f  mov     ebx, edx
0x18000ac21  mov     r14, rcx
0x18000ac24  test    r8, r8
0x18000ac27  jnz     short loc_18000AC33
0x18000ac29  mov     eax, 80004003h
0x18000ac2e  jmp     loc_18000AE5E
0x18000ac33  test    ebx, ebx
0x18000ac35  jz      loc_18000AE59
0x18000ac3b  mov     rcx, rsi; pSecurityDescriptor
0x18000ac3e  call    cs:__imp_IsValidSecurityDescriptor
0x18000ac44  test    eax, eax
0x18000ac46  jz      loc_18000AE59
0x18000ac4c  test    bl, 4
0x18000ac4f  jnz     short loc_18000AC58
0x18000ac51  xor     eax, eax
0x18000ac53  jmp     loc_18000AE5E
0x18000ac58  mov     rcx, [r14+100h]; pSelfRelativeSecurityDescriptor
0x18000ac5f  lea     rax, [rbp+57h+dwPrimaryGroupSize]
0x18000ac63  xor     ebx, ebx
0x18000ac65  mov     [rsp+0C0h+lpdwPrimaryGroupSize], rax; lpdwPrimaryGroupSize
0x18000ac6a  mov     [rsp+0C0h+pPrimaryGroup], rbx; pPrimaryGroup
0x18000ac6f  lea     rax, [rbp+57h+dwOwnerSize]
0x18000ac73  mov     [rsp+0C0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x18000ac78  lea     r8, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x18000ac7c  mov     [rsp+0C0h+pOwner], rbx; pOwner
0x18000ac81  lea     rax, [rbp+57h+dwSaclSize]
0x18000ac85  mov     [rsp+0C0h+lpdwSaclSize], rax; lpdwSaclSize
0x18000ac8a  xor     r9d, r9d; pDacl
0x18000ac8d  lea     rax, [rbp+57h+dwDaclSize]
0x18000ac91  mov     [rsp+0C0h+pSacl], rbx; pSacl
0x18000ac96  xor     edx, edx; pAbsoluteSecurityDescriptor
0x18000ac98  mov     [rsp+0C0h+lpdwDaclSize], rax; lpdwDaclSize
0x18000ac9d  mov     [rbp+57h+var_40], rbx
0x18000aca1  mov     r15d, ebx
0x18000aca4  mov     [rbp+57h+dwAbsoluteSecurityDescriptorSize], ebx
0x18000aca7  mov     r12d, ebx
0x18000acaa  mov     [rbp+57h+dwDaclSize], ebx
0x18000acad  mov     r13d, ebx
0x18000acb0  mov     [rbp+57h+dwSaclSize], ebx
0x18000acb3  mov     [rbp+57h+dwOwnerSize], ebx
0x18000acb6  mov     [rbp+57h+dwPrimaryGroupSize], ebx
0x18000acb9  mov     [rbp+57h+hMem], rbx
0x18000acbd  call    cs:__imp_MakeAbsoluteSD
0x18000acc3  test    eax, eax
0x18000acc5  jnz     short loc_18000ACEE
0x18000acc7  call    cs:__imp_GetLastError
0x18000accd  mov     ebx, eax
0x18000accf  cmp     eax, 7Ah ; 'z'
0x18000acd2  jz      short loc_18000ACEC
0x18000acd4  xor     edi, edi
0x18000acd6  test    eax, eax
0x18000acd8  jle     loc_18000AE27
0x18000acde  movzx   ebx, ax
0x18000ace1  or      ebx, 80070000h
0x18000ace7  jmp     loc_18000AE27
0x18000acec  xor     ebx, ebx
0x18000acee  mov     edx, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; uBytes
0x18000acf1  mov     ecx, 40h ; '@'; uFlags
0x18000acf6  call    cs:__imp_LocalAlloc
0x18000acfc  mov     rdi, rax
0x18000acff  test    rax, rax
0x18000ad02  jnz     short loc_18000AD0E
0x18000ad04  mov     ebx, 8007000Eh
0x18000ad09  jmp     loc_18000AE27
0x18000ad0e  mov     edx, [rbp+57h+dwDaclSize]; uBytes
0x18000ad11  mov     ecx, 40h ; '@'; uFlags
0x18000ad16  call    cs:__imp_LocalAlloc
0x18000ad1c  mov     r15, rax
0x18000ad1f  test    rax, rax
0x18000ad22  jz      short loc_18000AD04
0x18000ad24  mov     edx, [rbp+57h+dwSaclSize]; uBytes
0x18000ad27  mov     ecx, 40h ; '@'; uFlags
0x18000ad2c  call    cs:__imp_LocalAlloc
0x18000ad32  mov     r12, rax
0x18000ad35  test    rax, rax
0x18000ad38  jz      short loc_18000AD04
0x18000ad3a  mov     edx, [rbp+57h+dwOwnerSize]; uBytes
0x18000ad3d  mov     ecx, 40h ; '@'; uFlags
0x18000ad42  call    cs:__imp_LocalAlloc
0x18000ad48  mov     r13, rax
0x18000ad4b  test    rax, rax
0x18000ad4e  jz      short loc_18000AD04
0x18000ad50  mov     edx, [rbp+57h+dwPrimaryGroupSize]; uBytes
0x18000ad53  mov     ecx, 40h ; '@'; uFlags
0x18000ad58  call    cs:__imp_LocalAlloc
0x18000ad5e  mov     [rbp+57h+hMem], rax
0x18000ad62  test    rax, rax
0x18000ad65  jz      short loc_18000AD04
0x18000ad67  lea     rcx, [rbp+57h+dwPrimaryGroupSize]
0x18000ad6b  mov     r9, r15; pDacl
0x18000ad6e  mov     [rsp+0C0h+lpdwPrimaryGroupSize], rcx; lpdwPrimaryGroupSize
0x18000ad73  lea     r8, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x18000ad77  mov     rcx, [r14+100h]; pSelfRelativeSecurityDescriptor
0x18000ad7e  mov     rdx, rdi; pAbsoluteSecurityDescriptor
0x18000ad81  mov     [rsp+0C0h+pPrimaryGroup], rax; pPrimaryGroup
0x18000ad86  lea     rax, [rbp+57h+dwOwnerSize]
0x18000ad8a  mov     [rsp+0C0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x18000ad8f  lea     rax, [rbp+57h+dwSaclSize]
0x18000ad93  mov     [rsp+0C0h+pOwner], r13; pOwner
0x18000ad98  mov     [rsp+0C0h+lpdwSaclSize], rax; lpdwSaclSize
0x18000ad9d  lea     rax, [rbp+57h+dwDaclSize]
0x18000ada1  mov     [rsp+0C0h+pSacl], r12; pSacl
0x18000ada6  mov     [rsp+0C0h+lpdwDaclSize], rax; lpdwDaclSize
0x18000adab  call    cs:__imp_MakeAbsoluteSD
0x18000adb1  test    eax, eax
0x18000adb3  jnz     short loc_18000ADC2
0x18000adb5  call    cs:__imp_GetLastError
0x18000adbb  mov     ebx, eax
0x18000adbd  jmp     loc_18000ACD6
0x18000adc2  lea     r9, [rbp+57h+bDaclDefaulted]; lpbDaclDefaulted
0x18000adc6  mov     [rbp+57h+bDaclPresent], ebx
0x18000adc9  lea     r8, [rbp+57h+pDacl]; pDacl
0x18000adcd  mov     [rbp+57h+bDaclDefaulted], ebx
0x18000add0  lea     rdx, [rbp+57h+bDaclPresent]; lpbDaclPresent
0x18000add4  mov     [rbp+57h+pDacl], rbx
0x18000add8  mov     rcx, rsi; pSecurityDescriptor
0x18000addb  call    cs:__imp_GetSecurityDescriptorDacl
0x18000ade1  test    eax, eax
0x18000ade3  jz      short loc_18000ADB5
0x18000ade5  mov     r9d, [rbp+57h+bDaclDefaulted]; bDaclDefaulted
0x18000ade9  mov     rcx, rdi; pSecurityDescriptor
0x18000adec  mov     r8, [rbp+57h+pDacl]; pDacl
0x18000adf0  mov     edx, [rbp+57h+bDaclPresent]; bDaclPresent
0x18000adf3  call    cs:__imp_SetSecurityDescriptorDacl
0x18000adf9  test    eax, eax
0x18000adfb  jz      short loc_18000ADB5
0x18000adfd  lea     rdx, [rbp+57h+var_40]; void **
0x18000ae01  mov     rcx, rdi; Src
0x18000ae04  call    ?MakeSelfRelativeSecurityDescriptor@@YAJPEAXPEAPEAX@Z; MakeSelfRelativeSecurityDescriptor(void *,void * *)
0x18000ae09  mov     ebx, eax
0x18000ae0b  test    eax, eax
0x18000ae0d  js      short loc_18000AE27
0x18000ae0f  mov     rcx, [r14+100h]; hMem
0x18000ae16  call    cs:__imp_LocalFree
0x18000ae1c  mov     rcx, [rbp+57h+var_40]
0x18000ae20  mov     [r14+100h], rcx
0x18000ae27  mov     rcx, rdi; hMem
0x18000ae2a  call    cs:__imp_LocalFree
0x18000ae30  mov     rcx, r15; hMem
0x18000ae33  call    cs:__imp_LocalFree
0x18000ae39  mov     rcx, r12; hMem
0x18000ae3c  call    cs:__imp_LocalFree
0x18000ae42  mov     rcx, r13; hMem
0x18000ae45  call    cs:__imp_LocalFree
0x18000ae4b  mov     rcx, [rbp+57h+hMem]; hMem
0x18000ae4f  call    cs:__imp_LocalFree
0x18000ae55  mov     eax, ebx
0x18000ae57  jmp     short loc_18000AE5E
0x18000ae59  mov     eax, 80070057h
0x18000ae5e  mov     rbx, [rsp+0C0h+arg_0]
0x18000ae66  add     rsp, 90h
0x18000ae6d  pop     r15
0x18000ae6f  pop     r14
0x18000ae71  pop     r13
0x18000ae73  pop     r12
0x18000ae75  pop     rdi
0x18000ae76  pop     rsi
0x18000ae77  pop     rbp
0x18000ae78  retn
```
