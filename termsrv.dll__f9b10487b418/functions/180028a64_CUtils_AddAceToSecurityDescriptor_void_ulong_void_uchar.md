# CUtils::AddAceToSecurityDescriptor(void * *,ulong,void *,uchar)

- ea: `0x180028a64`
- end: `0x180028ea2`
- name: `?AddAceToSecurityDescriptor@CUtils@@SAJPEAPEAXKPEAXE@Z`
- size: `1086`
- prototype: `static int(void **, unsigned int, void *, unsigned __int8)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800b8f58`

## callees

- `0x18000a210`
- `0x180015dcc`
- `0x180028a64`
- `0x1800321f0`
- `0x180033058`
- `0x18009c564`
- `0x18009e160`
- `0x1800c4da0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028b13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028b66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028c80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028ce4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028d02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028d55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028da1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028dd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028b13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028b66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028c80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028ce4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028d02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028d55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028da1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028dd9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180028c5d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180028c5d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028e03`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028e71`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028e03`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028e71`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180028c76`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180028c76`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x180028cd6`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x180028d3a`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x180028cd6`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x180028d3a`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180028c4b`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180028c4b`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180028cb4`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180028cb4`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180028b5c`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180028b5c`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180028b09`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180028d97`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180028b09`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180028d97`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180028b87`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180028b87`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180028dcf`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180028dcf`

## string_xrefs

- `0x180028b28`: `GetSecurityDescriptorDacl failed: 0x%x`
- `0x180028db6`: `GetSecurityDescriptorDacl failed: 0x%x`
- `0x180028dee`: `SetSecurityDescriptorDacl failed: 0x%x`
- `0x180028b7b`: `GetAclInformation 0x%x`
- `0x180028c95`: `InitializeAcl failed: 0x%x`
- `0x180028e49`: `SD has NULL DACL, Present %d, Defaulted %d`

## pseudocode

```c
__int64 __fastcall CUtils::AddAceToSecurityDescriptor(void **a1, int a2, void *a3)
{
  struct _ACL *v5; // r12
  PSECURITY_DESCRIPTOR v6; // r15
  __int16 *v7; // rbx
  unsigned int v8; // ebx
  signed int LastError; // eax
  const char *v10; // rdx
  signed int v11; // eax
  DWORD LengthSid; // eax
  unsigned __int64 v13; // rcx
  unsigned __int64 v14; // rcx
  void *v15; // rsp
  void *v16; // rsp
  DWORD v17; // ebx
  struct _ACL *v18; // rax
  signed int v19; // eax
  DWORD i; // ebx
  signed int v21; // eax
  signed int v22; // eax
  unsigned int *v23; // r8
  signed int v24; // eax
  signed int v25; // eax
  unsigned int *v26; // r8
  signed int v27; // eax
  __int16 pAceList; // [rsp+30h] [rbp+0h] BYREF
  unsigned __int16 v30; // [rsp+32h] [rbp+2h]
  int v31; // [rsp+34h] [rbp+4h]
  WINBOOL bDaclDefaulted; // [rsp+38h] [rbp+8h] BYREF
  WINBOOL bDaclPresent; // [rsp+3Ch] [rbp+Ch] BYREF
  PACL pDacl; // [rsp+40h] [rbp+10h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+48h] [rbp+18h] BYREF
  DWORD v36; // [rsp+50h] [rbp+20h]
  LPVOID pAce; // [rsp+58h] [rbp+28h] BYREF
  PSECURITY_DESCRIPTOR pSelfRelativeSecurityDescriptor; // [rsp+60h] [rbp+30h]
  void *v39; // [rsp+68h] [rbp+38h] BYREF
  PSID pSourceSid; // [rsp+70h] [rbp+40h]
  __int16 *p_pAceList; // [rsp+78h] [rbp+48h]
  void **v42; // [rsp+88h] [rbp+58h]
  void *v43; // [rsp+90h] [rbp+60h]
  __int16 *v44; // [rsp+98h] [rbp+68h]
  __int64 pAclInformation; // [rsp+A0h] [rbp+70h] BYREF
  int v46; // [rsp+A8h] [rbp+78h]

  pSourceSid = a3;
  v42 = a1;
  v43 = a3;
  bDaclPresent = 0;
  bDaclDefaulted = 0;
  pAce = 0;
  pAclInformation = 0;
  v46 = 0;
  pDacl = 0;
  v5 = 0;
  v39 = 0;
  v6 = 0;
  pSecurityDescriptor = 0;
  v7 = (__int16 *)*a1;
  pSelfRelativeSecurityDescriptor = v7;
  v44 = v7;
  if ( v7[1] < 0 )
  {
    if ( !GetSecurityDescriptorDacl(v7, &bDaclPresent, &pDacl, &bDaclDefaulted) )
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      v10 = "GetSecurityDescriptorDacl failed: 0x%x";
LABEL_8:
      _DbgPrintMessage(8, v10, v8);
      goto LABEL_54;
    }
    if ( pDacl )
    {
      if ( !GetAclInformation(pDacl, &pAclInformation, 0xCu, AclSizeInformation) )
      {
        v11 = GetLastError();
        v8 = v11;
        if ( v11 > 0 )
          v8 = (unsigned __int16)v11 | 0x80070000;
        v10 = "GetAclInformation 0x%x";
        goto LABEL_8;
      }
      LengthSid = GetLengthSid(a3);
      v36 = LengthSid;
      LOWORD(v31) = LengthSid + 8;
      pAceList = LengthSid + 8;
      v13 = (unsigned __int16)(LengthSid + 8) + 15LL;
      if ( v13 <= (unsigned __int16)(LengthSid + 8) )
        v13 = 0xFFFFFFFFFFFFFF0LL;
      v14 = v13 & 0xFFFFFFFFFFFFFFF0uLL;
      v15 = alloca(v14);
      v16 = alloca(v14);
      p_pAceList = &pAceList;
      if ( !&pAceList
        || (pAceList = 0,
            v30 = LengthSid + 8,
            v31 = a2,
            CopySid((unsigned __int16)LengthSid, &bDaclDefaulted, pSourceSid),
            v17 = HIDWORD(pAclInformation) + v30,
            v18 = (struct _ACL *)LocalAlloc(0, v17),
            (v5 = v18) == 0) )
      {
        v8 = -2147024882;
        goto LABEL_54;
      }
      if ( !InitializeAcl(v18, v17, 2u) )
      {
        v19 = GetLastError();
        v8 = v19;
        if ( v19 > 0 )
          v8 = (unsigned __int16)v19 | 0x80070000;
        v10 = "InitializeAcl failed: 0x%x";
        goto LABEL_8;
      }
      for ( i = 0; i < (unsigned int)pAclInformation; ++i )
      {
        if ( !GetAce(pDacl, i, &pAce) )
        {
          v22 = GetLastError();
          v8 = v22;
          if ( v22 > 0 )
            v8 = (unsigned __int16)v22 | 0x80070000;
          v10 = "GetAce failed: 0x%x";
          goto LABEL_8;
        }
        if ( !AddAce(v5, 2u, i, pAce, *((unsigned __int16 *)pAce + 1)) )
          goto LABEL_28;
      }
      if ( !AddAce(v5, 2u, i, &pAceList, v30) )
      {
LABEL_28:
        v21 = GetLastError();
        v8 = v21;
        if ( v21 > 0 )
          v8 = (unsigned __int16)v21 | 0x80070000;
        v10 = "AddAce failed: 0x%x";
        goto LABEL_8;
      }
      if ( !(unsigned int)CUtils::SelfRelativeToAbsoluteSD(pSelfRelativeSecurityDescriptor, &pSecurityDescriptor, v23) )
      {
        v24 = GetLastError();
        v8 = v24;
        if ( v24 > 0 )
          v8 = (unsigned __int16)v24 | 0x80070000;
        _DbgPrintMessage(8, "SelfRelativeToAbsoluteSD failed: 0x%x", v8);
        v6 = pSecurityDescriptor;
        goto LABEL_54;
      }
      v6 = pSecurityDescriptor;
      if ( !GetSecurityDescriptorDacl(pSecurityDescriptor, &bDaclPresent, &pDacl, &bDaclDefaulted) )
      {
        v25 = GetLastError();
        v8 = v25;
        if ( v25 > 0 )
          v8 = (unsigned __int16)v25 | 0x80070000;
        v10 = "GetSecurityDescriptorDacl failed: 0x%x";
        goto LABEL_8;
      }
      if ( !SetSecurityDescriptorDacl(v6, 1, v5, 0) )
      {
        v27 = GetLastError();
        v8 = v27;
        if ( v27 > 0 )
          v8 = (unsigned __int16)v27 | 0x80070000;
        v10 = "SetSecurityDescriptorDacl failed: 0x%x";
        goto LABEL_8;
      }
      if ( pDacl )
        pDacl = (PACL)LocalFree(pDacl);
      v5 = 0;
      if ( !(unsigned int)CUtils::AbsoluteToSelfRelativeSD(v6, &v39, v26) )
      {
        _DbgPrintMessage(8, "AbsoluteToSelfRelativeSD failed");
        goto LABEL_3;
      }
      CUtils::CleanupSD(*a1);
      *a1 = v39;
    }
    else
    {
      _DbgPrintMessage(8, "SD has NULL DACL, Present %d, Defaulted %d", bDaclPresent, bDaclDefaulted);
    }
    v8 = 0;
    goto LABEL_54;
  }
  _DbgPrintMessage(8, "SD is not Self-Relative");
LABEL_3:
  v8 = -2147023558;
LABEL_54:
  if ( v6 )
    CUtils::CleanupSD(v6);
  if ( v5 )
    LocalFree(v5);
  return v8;
}

```

## disassembly

```asm
0x180028a64  mov     [rsp-8+arg_8], edx
0x180028a68  push    rbp
0x180028a69  push    rsi
0x180028a6a  push    rdi
0x180028a6b  push    r12
0x180028a6d  push    r13
0x180028a6f  push    r14
0x180028a71  push    r15
0x180028a73  sub     rsp, 0C0h
0x180028a7a  lea     rbp, [rsp+30h]
0x180028a7f  mov     [rbp+0C0h+arg_18], rbx
0x180028a86  mov     rax, cs:__security_cookie
0x180028a8d  xor     rax, rbp
0x180028a90  mov     [rbp+0C0h+var_40], rax
0x180028a97  mov     rsi, r8
0x180028a9a  mov     [rbp+0C0h+pSourceSid], r8
0x180028a9e  mov     r13, rcx
0x180028aa1  mov     [rbp+0C0h+var_68], rcx
0x180028aa5  mov     [rbp+0C0h+var_60], r8
0x180028aa9  xor     edi, edi
0x180028aab  mov     [rbp+0C0h+bDaclPresent], edi
0x180028aae  mov     [rbp+0C0h+bDaclDefaulted], edi
0x180028ab1  mov     [rbp+0C0h+pAce], rdi
0x180028ab5  xor     eax, eax
0x180028ab7  mov     [rbp+0C0h+pAclInformation], rax
0x180028abb  mov     [rbp+0C0h+var_48], eax
0x180028abe  mov     [rbp+0C0h+pDacl], rdi
0x180028ac2  mov     r12d, edi
0x180028ac5  mov     [rbp+0C0h+var_88], rdi
0x180028ac9  mov     r15d, edi
0x180028acc  mov     [rbp+0C0h+pSecurityDescriptor], rdi
0x180028ad0  mov     rbx, [rcx]
0x180028ad3  mov     [rbp+0C0h+pSelfRelativeSecurityDescriptor], rbx
0x180028ad7  mov     [rbp+0C0h+var_58], rbx
0x180028adb  cmp     [rbx+2], di
0x180028adf  jl      short loc_180028AFA
0x180028ae1  lea     rdx, aSdIsNotSelfRel; "SD is not Self-Relative"
0x180028ae8  lea     ecx, [rdi+8]; int
0x180028aeb  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180028af0  mov     ebx, 8007053Ah
0x180028af5  jmp     loc_180028E5C
0x180028afa  lea     r9, [rbp+0C0h+bDaclDefaulted]; lpbDaclDefaulted
0x180028afe  lea     r8, [rbp+0C0h+pDacl]; pDacl
0x180028b02  lea     rdx, [rbp+0C0h+bDaclPresent]; lpbDaclPresent
0x180028b06  mov     rcx, rbx; pSecurityDescriptor
0x180028b09  call    cs:__imp_GetSecurityDescriptorDacl
0x180028b0f  test    eax, eax
0x180028b11  jnz     short loc_180028B41
0x180028b13  call    cs:__imp_GetLastError
0x180028b19  mov     ebx, eax
0x180028b1b  test    eax, eax
0x180028b1d  jle     short loc_180028B28
0x180028b1f  movzx   ebx, ax
0x180028b22  or      ebx, 80070000h
0x180028b28  lea     rdx, aGetsecuritydes_1; "GetSecurityDescriptorDacl failed: 0x%x"
0x180028b2f  mov     ecx, 8; int
0x180028b34  mov     r8d, ebx
0x180028b37  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180028b3c  jmp     loc_180028E5C
0x180028b41  mov     rcx, [rbp+0C0h+pDacl]; pAcl
0x180028b45  test    rcx, rcx
0x180028b48  jz      loc_180028E41
0x180028b4e  mov     r9d, 2; dwAclInformationClass
0x180028b54  lea     r8d, [r9+0Ah]; nAclInformationLength
0x180028b58  lea     rdx, [rbp+0C0h+pAclInformation]; pAclInformation
0x180028b5c  call    cs:__imp_GetAclInformation
0x180028b62  test    eax, eax
0x180028b64  jnz     short loc_180028B84
0x180028b66  call    cs:__imp_GetLastError
0x180028b6c  mov     ebx, eax
0x180028b6e  test    eax, eax
0x180028b70  jle     short loc_180028B7B
0x180028b72  movzx   ebx, ax
0x180028b75  or      ebx, 80070000h
0x180028b7b  lea     rdx, aGetaclinformat; "GetAclInformation 0x%x"
0x180028b82  jmp     short loc_180028B2F
0x180028b84  mov     rcx, rsi; pSid
0x180028b87  call    cs:__imp_GetLengthSid
0x180028b8d  mov     r8d, eax
0x180028b90  mov     [rbp+0C0h+var_A0], eax
0x180028b93  mov     esi, 8
0x180028b98  lea     edx, [rsi+rax]
0x180028b9b  mov     word ptr [rbp+0C0h+var_BC], dx
0x180028b9f  mov     [rbp+0C0h+pAceList], dx
0x180028ba3  movzx   eax, dx
0x180028ba6  lea     rcx, [rax+0Fh]
0x180028baa  cmp     rcx, rax
0x180028bad  ja      short loc_180028BB9
0x180028baf  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180028bb9  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180028bbd  mov     rax, rcx
0x180028bc0  call    _alloca_probe
0x180028bc5  sub     rsp, rcx
0x180028bc8  lea     r14, [rsp+0F0h+pAceList]
0x180028bcd  mov     [rbp+0C0h+var_78], r14
0x180028bd1  mov     r9, [rbp+0C0h+pSourceSid]
0x180028bd5  jmp     short loc_180028C1C
0x180028bd7  call    _o__resetstkoflw_0
0x180028bdc  xor     r14d, r14d
0x180028bdf  mov     [rbp+0C0h+var_78], r14
0x180028be3  movzx   r8d, [rbp+0C0h+pAceList]
0x180028be8  lea     rdx, aAllocaFailedFo; "alloca failed for %d bytes"
0x180028bef  lea     ecx, [r14+8]; int
0x180028bf3  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180028bf8  xor     edi, edi
0x180028bfa  lea     esi, [rdi+8]
0x180028bfd  mov     r12d, edi
0x180028c00  mov     r15, [rbp+0C0h+pSecurityDescriptor]
0x180028c04  mov     r13, [rbp+0C0h+var_68]
0x180028c08  mov     r9, [rbp+0C0h+var_60]
0x180028c0c  mov     rax, [rbp+0C0h+var_58]
0x180028c10  mov     [rbp+0C0h+pSelfRelativeSecurityDescriptor], rax
0x180028c14  movzx   edx, word ptr [rbp+0C0h+var_BC]
0x180028c18  mov     r8d, [rbp+0C0h+var_A0]
0x180028c1c  test    r14, r14
0x180028c1f  jnz     short loc_180028C2B
0x180028c21  mov     ebx, 8007000Eh
0x180028c26  jmp     loc_180028E5C
0x180028c2b  mov     word ptr [r14], 0
0x180028c31  mov     [r14+2], dx
0x180028c36  mov     eax, [rbp+0C0h+arg_8]
0x180028c3c  mov     [r14+4], eax
0x180028c40  lea     rdx, [r14+8]; pDestinationSid
0x180028c44  movzx   ecx, r8w; nDestinationSidLength
0x180028c48  mov     r8, r9; pSourceSid
0x180028c4b  call    cs:__imp_CopySid
0x180028c51  movzx   ebx, word ptr [r14+2]
0x180028c56  add     ebx, dword ptr [rbp+0C0h+pAclInformation+4]
0x180028c59  mov     edx, ebx; uBytes
0x180028c5b  xor     ecx, ecx; uFlags
0x180028c5d  call    cs:__imp_LocalAlloc
0x180028c63  mov     r12, rax
0x180028c66  test    rax, rax
0x180028c69  jz      short loc_180028C21
0x180028c6b  mov     r8d, 2; dwAclRevision
0x180028c71  mov     edx, ebx; nAclLength
0x180028c73  mov     rcx, rax; pAcl
0x180028c76  call    cs:__imp_InitializeAcl
0x180028c7c  test    eax, eax
0x180028c7e  jnz     short loc_180028CA3
0x180028c80  call    cs:__imp_GetLastError
0x180028c86  mov     ebx, eax
0x180028c88  test    eax, eax
0x180028c8a  jle     short loc_180028C95
0x180028c8c  movzx   ebx, ax
0x180028c8f  or      ebx, 80070000h
0x180028c95  lea     rdx, aInitializeaclF; "InitializeAcl failed: 0x%x"
0x180028c9c  mov     ecx, esi
0x180028c9e  jmp     loc_180028B34
0x180028ca3  mov     ebx, edi
0x180028ca5  cmp     ebx, dword ptr [rbp+0C0h+pAclInformation]
0x180028ca8  jnb     short loc_180028D23
0x180028caa  lea     r8, [rbp+0C0h+pAce]; pAce
0x180028cae  mov     edx, ebx; dwAceIndex
0x180028cb0  mov     rcx, [rbp+0C0h+pDacl]; pAcl
0x180028cb4  call    cs:__imp_GetAce
0x180028cba  test    eax, eax
0x180028cbc  jz      short loc_180028D02
0x180028cbe  mov     r9, [rbp+0C0h+pAce]; pAceList
0x180028cc2  movzx   eax, word ptr [r9+2]
0x180028cc7  mov     [rsp+0F0h+nAceListLength], eax; nAceListLength
0x180028ccb  mov     r8d, ebx; dwStartingAceIndex
0x180028cce  mov     edx, 2; dwAceRevision
0x180028cd3  mov     rcx, r12; pAcl
0x180028cd6  call    cs:__imp_AddAce
0x180028cdc  test    eax, eax
0x180028cde  jz      short loc_180028CE4
0x180028ce0  inc     ebx
0x180028ce2  jmp     short loc_180028CA5
0x180028ce4  call    cs:__imp_GetLastError
0x180028cea  mov     ebx, eax
0x180028cec  test    eax, eax
0x180028cee  jle     short loc_180028CF9
0x180028cf0  movzx   ebx, ax
0x180028cf3  or      ebx, 80070000h
0x180028cf9  lea     rdx, aAddaceFailed0x; "AddAce failed: 0x%x"
0x180028d00  jmp     short loc_180028C9C
0x180028d02  call    cs:__imp_GetLastError
0x180028d08  mov     ebx, eax
0x180028d0a  test    eax, eax
0x180028d0c  jle     short loc_180028D17
0x180028d0e  movzx   ebx, ax
0x180028d11  or      ebx, 80070000h
0x180028d17  lea     rdx, aGetaceFailed0x_0; "GetAce failed: 0x%x"
0x180028d1e  jmp     loc_180028C9C
0x180028d23  movzx   eax, word ptr [r14+2]
0x180028d28  mov     [rsp+0F0h+nAceListLength], eax; nAceListLength
0x180028d2c  mov     r9, r14; pAceList
0x180028d2f  mov     r8d, ebx; dwStartingAceIndex
0x180028d32  mov     edx, 2; dwAceRevision
0x180028d37  mov     rcx, r12; pAcl
0x180028d3a  call    cs:__imp_AddAce
0x180028d40  test    eax, eax
0x180028d42  jz      short loc_180028CE4
0x180028d44  lea     rdx, [rbp+0C0h+pSecurityDescriptor]; void **
0x180028d48  mov     rcx, [rbp+0C0h+pSelfRelativeSecurityDescriptor]; pSelfRelativeSecurityDescriptor
0x180028d4c  call    ?SelfRelativeToAbsoluteSD@CUtils@@SAHPEAXPEAPEAXPEAK@Z; CUtils::SelfRelativeToAbsoluteSD(void *,void * *,ulong *)
0x180028d51  test    eax, eax
0x180028d53  jnz     short loc_180028D84
0x180028d55  call    cs:__imp_GetLastError
0x180028d5b  mov     ebx, eax
0x180028d5d  test    eax, eax
0x180028d5f  jle     short loc_180028D6A
0x180028d61  movzx   ebx, ax
0x180028d64  or      ebx, 80070000h
0x180028d6a  mov     r8d, ebx
0x180028d6d  lea     rdx, aSelfrelativeto; "SelfRelativeToAbsoluteSD failed: 0x%x"
0x180028d74  mov     ecx, esi; int
0x180028d76  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180028d7b  mov     r15, [rbp+0C0h+pSecurityDescriptor]
0x180028d7f  jmp     loc_180028E5C
0x180028d84  lea     r9, [rbp+0C0h+bDaclDefaulted]; lpbDaclDefaulted
0x180028d88  lea     r8, [rbp+0C0h+pDacl]; pDacl
0x180028d8c  lea     rdx, [rbp+0C0h+bDaclPresent]; lpbDaclPresent
0x180028d90  mov     r15, [rbp+0C0h+pSecurityDescriptor]
0x180028d94  mov     rcx, r15; pSecurityDescriptor
0x180028d97  call    cs:__imp_GetSecurityDescriptorDacl
0x180028d9d  test    eax, eax
0x180028d9f  jnz     short loc_180028DC2
0x180028da1  call    cs:__imp_GetLastError
0x180028da7  mov     ebx, eax
0x180028da9  test    eax, eax
0x180028dab  jle     short loc_180028DB6
0x180028dad  movzx   ebx, ax
0x180028db0  or      ebx, 80070000h
0x180028db6  lea     rdx, aGetsecuritydes_1; "GetSecurityDescriptorDacl failed: 0x%x"
0x180028dbd  jmp     loc_180028C9C
0x180028dc2  xor     r9d, r9d; bDaclDefaulted
0x180028dc5  mov     r8, r12; pDacl
0x180028dc8  lea     edx, [r9+1]; bDaclPresent
0x180028dcc  mov     rcx, r15; pSecurityDescriptor
0x180028dcf  call    cs:__imp_SetSecurityDescriptorDacl
0x180028dd5  test    eax, eax
0x180028dd7  jnz     short loc_180028DFA
0x180028dd9  call    cs:__imp_GetLastError
0x180028ddf  mov     ebx, eax
0x180028de1  test    eax, eax
0x180028de3  jle     short loc_180028DEE
0x180028de5  movzx   ebx, ax
0x180028de8  or      ebx, 80070000h
0x180028dee  lea     rdx, aSetsecuritydes; "SetSecurityDescriptorDacl failed: 0x%x"
0x180028df5  jmp     loc_180028C9C
0x180028dfa  mov     rcx, [rbp+0C0h+pDacl]; hMem
0x180028dfe  test    rcx, rcx
0x180028e01  jz      short loc_180028E0D
0x180028e03  call    cs:__imp_LocalFree
0x180028e09  mov     [rbp+0C0h+pDacl], rax
0x180028e0d  mov     r12, rdi
0x180028e10  lea     rdx, [rbp+0C0h+var_88]; void **
0x180028e14  mov     rcx, r15; pAbsoluteSecurityDescriptor
0x180028e17  call    ?AbsoluteToSelfRelativeSD@CUtils@@SAHPEAXPEAPEAXPEAK@Z; CUtils::AbsoluteToSelfRelativeSD(void *,void * *,ulong *)
0x180028e1c  test    eax, eax
0x180028e1e  jnz     short loc_180028E2E
0x180028e20  lea     rdx, aAbsolutetoself_0; "AbsoluteToSelfRelativeSD failed"
0x180028e27  mov     ecx, esi
0x180028e29  jmp     loc_180028AEB
0x180028e2e  mov     rcx, [r13+0]; hMem
0x180028e32  call    ?CleanupSD@CUtils@@SAXPEAX@Z; CUtils::CleanupSD(void *)
0x180028e37  mov     rax, [rbp+0C0h+var_88]
0x180028e3b  mov     [r13+0], rax
0x180028e3f  jmp     short loc_180028E5A
0x180028e41  mov     r9d, [rbp+0C0h+bDaclDefaulted]
0x180028e45  mov     r8d, [rbp+0C0h+bDaclPresent]
0x180028e49  lea     rdx, aSdHasNullDaclP; "SD has NULL DACL, Present %d, Defaulted"...
0x180028e50  mov     ecx, 8; int
0x180028e55  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180028e5a  mov     ebx, edi
0x180028e5c  test    r15, r15
0x180028e5f  jz      short loc_180028E69
0x180028e61  mov     rcx, r15; hMem
0x180028e64  call    ?CleanupSD@CUtils@@SAXPEAX@Z; CUtils::CleanupSD(void *)
0x180028e69  test    r12, r12
0x180028e6c  jz      short loc_180028E77
0x180028e6e  mov     rcx, r12; hMem
0x180028e71  call    cs:__imp_LocalFree
0x180028e77  mov     eax, ebx
0x180028e79  mov     rcx, [rbp+0C0h+var_40]
0x180028e80  xor     rcx, rbp; StackCookie
0x180028e83  call    __security_check_cookie
0x180028e88  mov     rbx, [rbp+0C0h+arg_18]
0x180028e8f  lea     rsp, [rbp+90h]
0x180028e96  pop     r15
0x180028e98  pop     r14
0x180028e9a  pop     r13
0x180028e9c  pop     r12
0x180028e9e  pop     rdi
0x180028e9f  pop     rsi
0x180028ea0  pop     rbp
0x180028ea1  retn
0x1800c5432  push    rbp
0x1800c5434  sub     rsp, 30h
0x1800c5438  lea     rbp, [rdx+30h]
0x1800c543c  mov     rax, [rcx]
0x1800c543f  xor     ecx, ecx
0x1800c5441  cmp     dword ptr [rax], 0C00000FDh
0x1800c5447  setz    cl
0x1800c544a  mov     eax, ecx
0x1800c544c  add     rsp, 30h
0x1800c5450  pop     rbp
0x1800c5451  retn
  ... truncated ...
```
