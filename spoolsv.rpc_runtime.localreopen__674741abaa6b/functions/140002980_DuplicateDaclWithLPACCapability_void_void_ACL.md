# DuplicateDaclWithLPACCapability(void *,void *,_ACL * *)

- ea: `0x140002980`
- end: `0x140002c71`
- name: `?DuplicateDaclWithLPACCapability@@YAKPEAX0PEAPEAU_ACL@@@Z`
- size: `753`
- prototype: `unsigned int(void *, void *, struct _ACL **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400709e0`

## callees

- `0x140002980`
- `0x140004790`
- `0x14002d0a0`
- `0x140070d98`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140002c40`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140002c40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400029d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002c26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400029d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002c26`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1400029c8`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1400029c8`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x140002a20`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x140002a20`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x140002a55`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x140002b4e`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x140002a55`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x140002b4e`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x140002b7b`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x140002b7b`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x140002b1d`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x140002b1d`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x140002bd4`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x140002bd4`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140002ae8`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140002ae8`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x140002bf2`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x140002bf2`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x140002c0e`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x140002c0e`
- `ADVAPI32!EqualSid` at `0x140002a80`
- `ADVAPI32!EqualSid` at `0x140002aa5`
- `ADVAPI32!EqualSid` at `0x140002ba3`
- `ADVAPI32!EqualSid` at `0x140002a80`
- `ADVAPI32!EqualSid` at `0x140002aa5`
- `ADVAPI32!EqualSid` at `0x140002ba3`

## pseudocode

```c
__int64 __fastcall DuplicateDaclWithLPACCapability(void *a1, void *a2, struct _ACL **a3)
{
  DWORD LastError; // ebx
  int v6; // esi
  int v7; // ebx
  DWORD i; // edi
  char *v9; // r14
  DWORD LengthSid; // eax
  DWORD v11; // ebx
  struct _ACL *v12; // rax
  struct _ACL *v13; // rdi
  DWORD j; // ebx
  _DWORD *v15; // rsi
  WINBOOL bDaclPresent; // [rsp+30h] [rbp-40h] BYREF
  PACL pDacl; // [rsp+38h] [rbp-38h] BYREF
  LPVOID pAceList; // [rsp+40h] [rbp-30h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+48h] [rbp-28h] BYREF
  LPVOID pAce; // [rsp+50h] [rbp-20h] BYREF
  __int64 pAclInformation; // [rsp+58h] [rbp-18h] BYREF
  int v23; // [rsp+60h] [rbp-10h]

  pDacl = 0;
  bDaclPresent = 0;
  bDaclDefaulted = 0;
  if ( !GetSecurityDescriptorDacl(a1, &bDaclPresent, &pDacl, &bDaclDefaulted) )
    return GetLastError();
  if ( !bDaclPresent )
    return 87;
  if ( !pDacl )
  {
    PrvSpoolssTelemetry::NullDacl();
    return 87;
  }
  pAclInformation = 0;
  v23 = 0;
  if ( !GetAclInformation(pDacl, &pAclInformation, 0xCu, AclSizeInformation) )
    return GetLastError();
  v6 = 0;
  v7 = 0;
  for ( i = 0; i < (unsigned int)pAclInformation; ++i )
  {
    pAce = 0;
    if ( !GetAce(pDacl, i, &pAce) )
      return GetLastError();
    if ( !*(_BYTE *)pAce )
    {
      v9 = (char *)pAce + 8;
      if ( EqualSid((char *)pAce + 8, g_pAppContainerSid) )
      {
        v6 = 1;
      }
      else
      {
        if ( EqualSid(v9, g_pLPACCapabilitySid) )
          v7 = 1;
        if ( !v6 )
          continue;
      }
      if ( v7 )
        return 183;
    }
  }
  if ( !v6 || v7 )
    return 183;
  LengthSid = GetLengthSid(g_pLPACCapabilitySid);
  v11 = LengthSid + HIDWORD(pAclInformation);
  v12 = (struct _ACL *)DllAllocSplMem(LengthSid + HIDWORD(pAclInformation) + 12);
  v13 = v12;
  if ( v12 )
  {
    if ( !InitializeAcl(v12, v11 + 12, 2u) )
      goto LABEL_35;
    for ( j = 0; j < (unsigned int)pAclInformation; ++j )
    {
      pAceList = 0;
      if ( !GetAce(pDacl, j, &pAceList) )
        goto LABEL_35;
      if ( !AddAce(v13, 2u, 0xFFFFFFFF, pAceList, *((unsigned __int16 *)pAceList + 1)) )
        goto LABEL_35;
      v15 = pAceList;
      if ( !*(_BYTE *)pAceList
        && EqualSid((char *)pAceList + 8, g_pAppContainerSid)
        && !AddAccessAllowedAceEx(v13, 2u, *((unsigned __int8 *)pAceList + 1), v15[1], g_pLPACCapabilitySid) )
      {
        goto LABEL_35;
      }
    }
    if ( InitializeSecurityDescriptor(a2, 1u) && SetSecurityDescriptorDacl(a2, 1, v13, 0) )
    {
      *a3 = v13;
      return 0;
    }
    else
    {
LABEL_35:
      LastError = GetLastError();
      HeapFree(g_hSpoolssHeap, 0, v13);
    }
  }
  else
  {
    return 8;
  }
  return LastError;
}

```

## disassembly

```asm
0x140002980  push    rbp
0x140002982  push    rbx
0x140002983  push    rsi
0x140002984  push    rdi
0x140002985  push    r12
0x140002987  push    r14
0x140002989  push    r15
0x14000298b  mov     rbp, rsp
0x14000298e  sub     rsp, 70h
0x140002992  mov     rax, cs:__security_cookie
0x140002999  xor     rax, rsp
0x14000299c  mov     [rbp+var_8], rax
0x1400029a0  mov     r12, r8
0x1400029a3  mov     [rbp+pDacl], 0
0x1400029ab  mov     r15, rdx
0x1400029ae  mov     [rbp+bDaclPresent], 0
0x1400029b5  lea     r8, [rbp+pDacl]; pDacl
0x1400029b9  mov     [rbp+bDaclDefaulted], 0
0x1400029c0  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x1400029c4  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x1400029c8  call    cs:__imp_GetSecurityDescriptorDacl
0x1400029cf  nop     dword ptr [rax+rax+00h]
0x1400029d4  test    eax, eax
0x1400029d6  jnz     short loc_1400029EB
0x1400029d8  call    cs:__imp_GetLastError
0x1400029df  nop     dword ptr [rax+rax+00h]
0x1400029e4  mov     ebx, eax
0x1400029e6  jmp     loc_140002C53
0x1400029eb  cmp     [rbp+bDaclPresent], 0
0x1400029ef  jnz     short loc_1400029FB
0x1400029f1  mov     ebx, 57h ; 'W'
0x1400029f6  jmp     loc_140002C53
0x1400029fb  mov     rcx, [rbp+pDacl]; pAcl
0x1400029ff  test    rcx, rcx
0x140002a02  jnz     short loc_140002A0B
0x140002a04  call    ?NullDacl@PrvSpoolssTelemetry@@SAXXZ; PrvSpoolssTelemetry::NullDacl(void)
0x140002a09  jmp     short loc_1400029F1
0x140002a0b  xor     eax, eax
0x140002a0d  lea     rdx, [rbp+pAclInformation]; pAclInformation
0x140002a11  mov     [rbp+pAclInformation], rax
0x140002a15  mov     [rbp+var_10], eax
0x140002a18  lea     r9d, [rax+2]; dwAclInformationClass
0x140002a1c  lea     r8d, [rax+0Ch]; nAclInformationLength
0x140002a20  call    cs:__imp_GetAclInformation
0x140002a27  nop     dword ptr [rax+rax+00h]
0x140002a2c  test    eax, eax
0x140002a2e  jz      short loc_1400029D8
0x140002a30  xor     esi, esi
0x140002a32  xor     ebx, ebx
0x140002a34  xor     edi, edi
0x140002a36  lea     r14d, [rsi+1]
0x140002a3a  cmp     edi, dword ptr [rbp+pAclInformation]
0x140002a3d  jnb     loc_140002AD1
0x140002a43  mov     rcx, [rbp+pDacl]; pAcl
0x140002a47  lea     r8, [rbp+pAce]; pAce
0x140002a4b  mov     edx, edi; dwAceIndex
0x140002a4d  mov     [rbp+pAce], 0
0x140002a55  call    cs:__imp_GetAce
0x140002a5c  nop     dword ptr [rax+rax+00h]
0x140002a61  test    eax, eax
0x140002a63  jz      loc_1400029D8
0x140002a69  mov     rax, [rbp+pAce]
0x140002a6d  cmp     byte ptr [rax], 0
0x140002a70  jnz     short loc_140002AC9
0x140002a72  mov     rdx, cs:?g_pAppContainerSid@@3PEAXEA; pSid2
0x140002a79  lea     r14, [rax+8]
0x140002a7d  mov     rcx, r14; pSid1
0x140002a80  call    cs:__imp_EqualSid
0x140002a87  nop     dword ptr [rax+rax+00h]
0x140002a8c  test    eax, eax
0x140002a8e  jz      short loc_140002A9B
0x140002a90  mov     r14d, 1
0x140002a96  mov     esi, r14d
0x140002a99  jmp     short loc_140002AC1
0x140002a9b  mov     rdx, cs:?g_pLPACCapabilitySid@@3PEAXEA; pSid2
0x140002aa2  mov     rcx, r14; pSid1
0x140002aa5  call    cs:__imp_EqualSid
0x140002aac  nop     dword ptr [rax+rax+00h]
0x140002ab1  test    eax, eax
0x140002ab3  mov     r14d, 1
0x140002ab9  cmovnz  ebx, r14d
0x140002abd  test    esi, esi
0x140002abf  jz      short loc_140002AC9
0x140002ac1  test    ebx, ebx
0x140002ac3  jnz     loc_140002C4E
0x140002ac9  add     edi, r14d
0x140002acc  jmp     loc_140002A3A
0x140002ad1  test    esi, esi
0x140002ad3  jz      loc_140002C4E
0x140002ad9  test    ebx, ebx
0x140002adb  jnz     loc_140002C4E
0x140002ae1  mov     rcx, cs:?g_pLPACCapabilitySid@@3PEAXEA; pSid
0x140002ae8  call    cs:__imp_GetLengthSid
0x140002aef  nop     dword ptr [rax+rax+00h]
0x140002af4  mov     ebx, dword ptr [rbp+pAclInformation+4]
0x140002af7  add     ebx, eax
0x140002af9  lea     ecx, [rbx+0Ch]; dwBytes
0x140002afc  call    DllAllocSplMem
0x140002b01  mov     rdi, rax
0x140002b04  test    rax, rax
0x140002b07  jnz     short loc_140002B11
0x140002b09  lea     ebx, [rax+8]
0x140002b0c  jmp     loc_140002C53
0x140002b11  mov     r8d, 2; dwAclRevision
0x140002b17  lea     edx, [rbx+0Ch]; nAclLength
0x140002b1a  mov     rcx, rdi; pAcl
0x140002b1d  call    cs:__imp_InitializeAcl
0x140002b24  nop     dword ptr [rax+rax+00h]
0x140002b29  test    eax, eax
0x140002b2b  jz      loc_140002C26
0x140002b31  xor     ebx, ebx
0x140002b33  cmp     ebx, dword ptr [rbp+pAclInformation]
0x140002b36  jnb     loc_140002BEC
0x140002b3c  mov     rcx, [rbp+pDacl]; pAcl
0x140002b40  lea     r8, [rbp+pAceList]; pAce
0x140002b44  mov     edx, ebx; dwAceIndex
0x140002b46  mov     [rbp+pAceList], 0
0x140002b4e  call    cs:__imp_GetAce
0x140002b55  nop     dword ptr [rax+rax+00h]
0x140002b5a  test    eax, eax
0x140002b5c  jz      loc_140002C26
0x140002b62  mov     r9, [rbp+pAceList]; pAceList
0x140002b66  or      r8d, 0FFFFFFFFh; dwStartingAceIndex
0x140002b6a  mov     edx, 2; dwAceRevision
0x140002b6f  mov     rcx, rdi; pAcl
0x140002b72  movzx   eax, word ptr [r9+2]
0x140002b77  mov     [rsp+70h+nAceListLength], eax; nAceListLength
0x140002b7b  call    cs:__imp_AddAce
0x140002b82  nop     dword ptr [rax+rax+00h]
0x140002b87  test    eax, eax
0x140002b89  jz      loc_140002C26
0x140002b8f  mov     rsi, [rbp+pAceList]
0x140002b93  cmp     byte ptr [rsi], 0
0x140002b96  jnz     short loc_140002BE4
0x140002b98  mov     rdx, cs:?g_pAppContainerSid@@3PEAXEA; pSid2
0x140002b9f  lea     rcx, [rsi+8]; pSid1
0x140002ba3  call    cs:__imp_EqualSid
0x140002baa  nop     dword ptr [rax+rax+00h]
0x140002baf  test    eax, eax
0x140002bb1  jz      short loc_140002BE4
0x140002bb3  mov     rax, [rbp+pAceList]
0x140002bb7  mov     edx, 2; dwAceRevision
0x140002bbc  mov     r9d, [rsi+4]; AccessMask
0x140002bc0  mov     rcx, rdi; pAcl
0x140002bc3  movzx   r8d, byte ptr [rax+1]; AceFlags
0x140002bc8  mov     rax, cs:?g_pLPACCapabilitySid@@3PEAXEA; void * g_pLPACCapabilitySid
0x140002bcf  mov     qword ptr [rsp+70h+nAceListLength], rax; pSid
0x140002bd4  call    cs:__imp_AddAccessAllowedAceEx
0x140002bdb  nop     dword ptr [rax+rax+00h]
0x140002be0  test    eax, eax
0x140002be2  jz      short loc_140002C26
0x140002be4  add     ebx, r14d
0x140002be7  jmp     loc_140002B33
0x140002bec  mov     edx, r14d; dwRevision
0x140002bef  mov     rcx, r15; pSecurityDescriptor
0x140002bf2  call    cs:__imp_InitializeSecurityDescriptor
0x140002bf9  nop     dword ptr [rax+rax+00h]
0x140002bfe  test    eax, eax
0x140002c00  jz      short loc_140002C26
0x140002c02  xor     r9d, r9d; bDaclDefaulted
0x140002c05  mov     r8, rdi; pDacl
0x140002c08  mov     edx, r14d; bDaclPresent
0x140002c0b  mov     rcx, r15; pSecurityDescriptor
0x140002c0e  call    cs:__imp_SetSecurityDescriptorDacl
0x140002c15  nop     dword ptr [rax+rax+00h]
0x140002c1a  test    eax, eax
0x140002c1c  jz      short loc_140002C26
0x140002c1e  mov     [r12], rdi
0x140002c22  xor     ebx, ebx
0x140002c24  jmp     short loc_140002C53
0x140002c26  call    cs:__imp_GetLastError
0x140002c2d  nop     dword ptr [rax+rax+00h]
0x140002c32  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x140002c39  mov     r8, rdi; lpMem
0x140002c3c  xor     edx, edx; dwFlags
0x140002c3e  mov     ebx, eax
0x140002c40  call    cs:__imp_HeapFree
0x140002c47  nop     dword ptr [rax+rax+00h]
0x140002c4c  jmp     short loc_140002C53
0x140002c4e  mov     ebx, 0B7h
0x140002c53  mov     eax, ebx
0x140002c55  mov     rcx, [rbp+var_8]
0x140002c59  xor     rcx, rsp; StackCookie
0x140002c5c  call    __security_check_cookie
0x140002c61  add     rsp, 70h
0x140002c65  pop     r15
0x140002c67  pop     r14
0x140002c69  pop     r12
0x140002c6b  pop     rdi
0x140002c6c  pop     rsi
0x140002c6d  pop     rbx
0x140002c6e  pop     rbp
0x140002c6f  retn
```
