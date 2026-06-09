# AllocAbsoluteSDFromString

- ea: `0x18002fe70`
- end: `0x1800300e4`
- name: `AllocAbsoluteSDFromString`
- size: `628`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800199a4`

## callees

- `0x180003950`
- `0x180003974`
- `0x180005f64`
- `0x18000a6d0`
- `0x18002fe70`
- `0x180042630`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ff4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ff4a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002fedd`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002fedd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800300b7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800300b7`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x18002ff31`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x180030079`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x18002ff31`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x180030079`

## string_xrefs

- `0x180030000`: `C:\__w\1\s\src\Client\lib\util\SecurityUtil.cpp`
- `0x18003008c`: `C:\__w\1\s\src\Client\lib\util\SecurityUtil.cpp`

## pseudocode

```c
__int64 __fastcall AllocAbsoluteSDFromString(__int64 a1, _QWORD *a2)
{
  char *v2; // rbx
  unsigned int LastError; // edi
  __int64 v5; // rdx
  const char *v6; // r9
  __int64 v7; // rdx
  DWORD v8; // r9d
  DWORD v9; // r10d
  DWORD v10; // r11d
  DWORD v11; // ecx
  DWORD v12; // edx
  int lpdwDaclSize; // [rsp+28h] [rbp-19h]
  DWORD dwPrimaryGroupSize; // [rsp+68h] [rbp+27h] BYREF
  DWORD dwOwnerSize; // [rsp+6Ch] [rbp+2Bh] BYREF
  DWORD dwDaclSize; // [rsp+70h] [rbp+2Fh] BYREF
  DWORD dwAbsoluteSecurityDescriptorSize; // [rsp+74h] [rbp+33h] BYREF
  DWORD dwSaclSize; // [rsp+78h] [rbp+37h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+80h] [rbp+3Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A0h] [rbp+5Fh]

  v2 = 0;
  SecurityDescriptor = 0;
  dwAbsoluteSecurityDescriptorSize = 0;
  dwOwnerSize = 0;
  dwPrimaryGroupSize = 0;
  dwDaclSize = 0;
  dwSaclSize = 0;
  if ( !a2 )
  {
    LastError = -2147467261;
    v5 = 541;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SecurityUtil.cpp",
      (const char *)LastError,
      lpdwDaclSize);
    goto LABEL_17;
  }
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
         L"O:BAG:BAD:(A;;0x1013ffff;;;SY)(A;;0x1013ffff;;;BA)",
         1u,
         &SecurityDescriptor,
         0) )
  {
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
      LastError = -2145120257;
      v5 = 551;
      goto LABEL_12;
    }
    if ( GetLastError() == 122 )
    {
      v8 = 8 - (dwAbsoluteSecurityDescriptorSize & 7) + dwAbsoluteSecurityDescriptorSize;
      dwAbsoluteSecurityDescriptorSize = v8;
      v9 = 8 - (dwDaclSize & 7) + dwDaclSize;
      dwDaclSize = v9;
      dwSaclSize += 8 - (dwSaclSize & 7);
      v10 = 8 - (dwOwnerSize & 7) + dwOwnerSize;
      dwOwnerSize = v10;
      v11 = 8 - (dwPrimaryGroupSize & 7) + dwPrimaryGroupSize;
      dwPrimaryGroupSize = v11;
      v12 = v8 + v9 + v11 + v10 + dwSaclSize;
      if ( v12 )
      {
        v2 = (char *)SafeSusAllocArray(v12, 1u);
        LastError = v2 == 0 ? 0x8007000E : 0;
        if ( !v2 )
        {
          v5 = 563;
          goto LABEL_12;
        }
        v8 = dwAbsoluteSecurityDescriptorSize;
        v10 = dwOwnerSize;
        v11 = dwPrimaryGroupSize;
        v9 = dwDaclSize;
      }
      if ( MakeAbsoluteSD(
             SecurityDescriptor,
             v2,
             &dwAbsoluteSecurityDescriptorSize,
             (PACL)&v2[v8 + v11 + v10],
             &dwDaclSize,
             (PACL)&v2[v8 + v11 + v10 + v9],
             &dwSaclSize,
             &v2[v8 + v11],
             &dwOwnerSize,
             &v2[v8],
             &dwPrimaryGroupSize) )
      {
        *a2 = v2;
        LastError = 0;
        goto LABEL_20;
      }
      v7 = 580;
    }
    else
    {
      v7 = 553;
    }
  }
  else
  {
    v7 = 547;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)v7,
                (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SecurityUtil.cpp",
                v6);
LABEL_17:
  if ( v2 )
    CSusBaseAllocTag<942762101>::operator delete(v2);
LABEL_20:
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  return LastError;
}

```

## disassembly

```asm
0x18002fe70  mov     rax, rsp
0x18002fe73  mov     [rax+8], rbx
0x18002fe77  mov     [rax+18h], rsi
0x18002fe7b  mov     [rax+20h], rdi
0x18002fe7f  push    rbp
0x18002fe80  lea     rbp, [rax-5Fh]
0x18002fe84  sub     rsp, 90h
0x18002fe8b  mov     rax, cs:__security_cookie
0x18002fe92  xor     rax, rsp
0x18002fe95  mov     [rbp+57h+var_10], rax
0x18002fe99  xor     ebx, ebx
0x18002fe9b  mov     [rbp+57h+SecurityDescriptor], 0
0x18002fea3  mov     [rbp+57h+dwAbsoluteSecurityDescriptorSize], ebx
0x18002fea6  mov     rsi, rdx
0x18002fea9  mov     [rbp+57h+dwOwnerSize], ebx
0x18002feac  mov     [rbp+57h+dwPrimaryGroupSize], ebx
0x18002feaf  mov     [rbp+57h+dwDaclSize], ebx
0x18002feb2  mov     [rbp+57h+dwSaclSize], ebx
0x18002feb5  test    rdx, rdx
0x18002feb8  jnz     short loc_18002FEC9
0x18002feba  mov     edi, 80004003h
0x18002febf  mov     edx, 21Dh
0x18002fec4  jmp     loc_18002FFFC
0x18002fec9  xor     r9d, r9d; SecurityDescriptorSize
0x18002fecc  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x18002fed0  lea     rcx, StringSecurityDescriptor; "O:BAG:BAD:(A;;0x1013ffff;;;SY)(A;;0x101"...
0x18002fed7  lea     edi, [r9+1]
0x18002fedb  mov     edx, edi; StringSDRevision
0x18002fedd  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18002fee3  test    eax, eax
0x18002fee5  jnz     short loc_18002FEF1
0x18002fee7  mov     edx, 223h
0x18002feec  jmp     loc_180030088
0x18002fef1  mov     rcx, [rbp+57h+SecurityDescriptor]; pSelfRelativeSecurityDescriptor
0x18002fef5  lea     rax, [rbp+57h+dwPrimaryGroupSize]
0x18002fef9  mov     [rsp+90h+lpdwPrimaryGroupSize], rax; lpdwPrimaryGroupSize
0x18002fefe  lea     r8, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x18002ff02  mov     [rsp+90h+pPrimaryGroup], rbx; pPrimaryGroup
0x18002ff07  lea     rax, [rbp+57h+dwOwnerSize]
0x18002ff0b  mov     [rsp+90h+lpdwOwnerSize], rax; lpdwOwnerSize
0x18002ff10  xor     r9d, r9d; pDacl
0x18002ff13  mov     [rsp+90h+pOwner], rbx; pOwner
0x18002ff18  lea     rax, [rbp+57h+dwSaclSize]
0x18002ff1c  mov     [rsp+90h+lpdwSaclSize], rax; lpdwSaclSize
0x18002ff21  xor     edx, edx; pAbsoluteSecurityDescriptor
0x18002ff23  lea     rax, [rbp+57h+dwDaclSize]
0x18002ff27  mov     [rsp+90h+pSacl], rbx; pSacl
0x18002ff2c  mov     [rsp+90h+lpdwDaclSize], rax; int
0x18002ff31  call    cs:__imp_MakeAbsoluteSD
0x18002ff37  test    eax, eax
0x18002ff39  jz      short loc_18002FF4A
0x18002ff3b  mov     edi, 80240FFFh
0x18002ff40  mov     edx, 227h
0x18002ff45  jmp     loc_18002FFFC
0x18002ff4a  call    cs:__imp_GetLastError
0x18002ff50  cmp     eax, 7Ah ; 'z'
0x18002ff53  jz      short loc_18002FF5F
0x18002ff55  mov     edx, 229h
0x18002ff5a  jmp     loc_180030088
0x18002ff5f  mov     r9d, [rbp+57h+dwAbsoluteSecurityDescriptorSize]
0x18002ff63  mov     r8d, 8
0x18002ff69  mov     r10d, [rbp+57h+dwDaclSize]
0x18002ff6d  mov     ecx, r9d
0x18002ff70  mov     edx, [rbp+57h+dwSaclSize]
0x18002ff73  and     ecx, 7
0x18002ff76  mov     r11d, [rbp+57h+dwOwnerSize]
0x18002ff7a  mov     eax, r8d
0x18002ff7d  sub     eax, ecx
0x18002ff7f  mov     ecx, r10d
0x18002ff82  add     r9d, eax
0x18002ff85  and     ecx, 7
0x18002ff88  mov     eax, r8d
0x18002ff8b  mov     [rbp+57h+dwAbsoluteSecurityDescriptorSize], r9d
0x18002ff8f  sub     eax, ecx
0x18002ff91  mov     ecx, edx
0x18002ff93  add     r10d, eax
0x18002ff96  and     ecx, 7
0x18002ff99  mov     eax, r8d
0x18002ff9c  mov     [rbp+57h+dwDaclSize], r10d
0x18002ffa0  sub     eax, ecx
0x18002ffa2  mov     ecx, r11d
0x18002ffa5  add     edx, eax
0x18002ffa7  and     ecx, 7
0x18002ffaa  mov     [rbp+57h+dwSaclSize], edx
0x18002ffad  mov     eax, r8d
0x18002ffb0  sub     eax, ecx
0x18002ffb2  mov     ecx, [rbp+57h+dwPrimaryGroupSize]
0x18002ffb5  add     r11d, eax
0x18002ffb8  mov     eax, ecx
0x18002ffba  and     eax, 7
0x18002ffbd  mov     [rbp+57h+dwOwnerSize], r11d
0x18002ffc1  sub     r8d, eax
0x18002ffc4  add     ecx, r8d
0x18002ffc7  mov     [rbp+57h+dwPrimaryGroupSize], ecx
0x18002ffca  lea     eax, [rcx+r11]
0x18002ffce  add     edx, eax
0x18002ffd0  add     edx, r10d
0x18002ffd3  add     edx, r9d
0x18002ffd6  jz      short loc_180030023
0x18002ffd8  mov     ecx, edx; unsigned __int64
0x18002ffda  mov     rdx, rdi; unsigned __int64
0x18002ffdd  call    ?SafeSusAllocArray@@YAPEAX_K0@Z; SafeSusAllocArray(unsigned __int64,unsigned __int64)
0x18002ffe2  mov     rbx, rax
0x18002ffe5  neg     rax
0x18002ffe8  sbb     edi, edi
0x18002ffea  not     edi
0x18002ffec  and     edi, 8007000Eh
0x18002fff2  test    rbx, rbx
0x18002fff5  jnz     short loc_180030014
0x18002fff7  mov     edx, 233h; void *
0x18002fffc  mov     rcx, [rbp+5Fh]; this
0x180030000  lea     r8, aCW1SSrcClientL_16; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180030007  mov     r9d, edi; char *
0x18003000a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003000f  jmp     loc_18003009A
0x180030014  mov     r9d, [rbp+57h+dwAbsoluteSecurityDescriptorSize]
0x180030018  mov     r11d, [rbp+57h+dwOwnerSize]
0x18003001c  mov     ecx, [rbp+57h+dwPrimaryGroupSize]
0x18003001f  mov     r10d, [rbp+57h+dwDaclSize]
0x180030023  mov     r8d, ecx
0x180030026  lea     rcx, [rbp+57h+dwPrimaryGroupSize]
0x18003002a  mov     [rsp+90h+lpdwPrimaryGroupSize], rcx; lpdwPrimaryGroupSize
0x18003002f  lea     rcx, [rbp+57h+dwOwnerSize]
0x180030033  mov     edx, r9d
0x180030036  add     rdx, rbx
0x180030039  mov     r9d, r11d
0x18003003c  mov     [rsp+90h+pPrimaryGroup], rdx; pPrimaryGroup
0x180030041  add     r8, rdx
0x180030044  mov     [rsp+90h+lpdwOwnerSize], rcx; lpdwOwnerSize
0x180030049  add     r9, r8; pDacl
0x18003004c  mov     [rsp+90h+pOwner], r8; pOwner
0x180030051  lea     rcx, [rbp+57h+dwSaclSize]
0x180030055  mov     [rsp+90h+lpdwSaclSize], rcx; lpdwSaclSize
0x18003005a  lea     r8, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x18003005e  mov     rcx, [rbp+57h+SecurityDescriptor]; pSelfRelativeSecurityDescriptor
0x180030062  mov     rdx, rbx; pAbsoluteSecurityDescriptor
0x180030065  mov     eax, r10d
0x180030068  add     rax, r9
0x18003006b  mov     [rsp+90h+pSacl], rax; pSacl
0x180030070  lea     rax, [rbp+57h+dwDaclSize]
0x180030074  mov     [rsp+90h+lpdwDaclSize], rax; lpdwDaclSize
0x180030079  call    cs:__imp_MakeAbsoluteSD
0x18003007f  test    eax, eax
0x180030081  jnz     short loc_1800300A9
0x180030083  mov     edx, 244h; void *
0x180030088  mov     rcx, [rbp+5Fh]; this
0x18003008c  lea     r8, aCW1SSrcClientL_16; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180030093  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180030098  mov     edi, eax
0x18003009a  test    rbx, rbx
0x18003009d  jz      short loc_1800300AE
0x18003009f  mov     rcx, rbx; lpMem
0x1800300a2  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x1800300a7  jmp     short loc_1800300AE
0x1800300a9  mov     [rsi], rbx
0x1800300ac  xor     edi, edi
0x1800300ae  mov     rcx, [rbp+57h+SecurityDescriptor]; hMem
0x1800300b2  test    rcx, rcx
0x1800300b5  jz      short loc_1800300BD
0x1800300b7  call    cs:__imp_LocalFree
0x1800300bd  mov     eax, edi
0x1800300bf  mov     rcx, [rbp+57h+var_10]
0x1800300c3  xor     rcx, rsp; StackCookie
0x1800300c6  call    __security_check_cookie
0x1800300cb  lea     r11, [rsp+90h+var_s0]
0x1800300d3  mov     rbx, [r11+10h]
0x1800300d7  mov     rsi, [r11+20h]
0x1800300db  mov     rdi, [r11+28h]
0x1800300df  mov     rsp, r11
0x1800300e2  pop     rbp
0x1800300e3  retn
```
