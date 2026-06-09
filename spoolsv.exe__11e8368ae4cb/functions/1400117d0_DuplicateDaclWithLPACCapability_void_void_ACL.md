# DuplicateDaclWithLPACCapability(void *,void *,_ACL * *)

- ea: `0x1400117d0`
- end: `0x140011a51`
- name: `?DuplicateDaclWithLPACCapability@@YAKPEAX0PEAPEAU_ACL@@@Z`
- size: `641`
- prototype: `unsigned int(void *, void *, struct _ACL **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140069f68`

## callees

- `0x1400041c0`
- `0x1400117d0`
- `0x14002abc0`
- `0x14006a2bc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140011a27`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140011a27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011822`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011a13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011822`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011a13`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x140011818`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x140011818`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x140011864`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x140011864`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x14001188f`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x140011963`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x14001188f`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x140011963`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x14001198a`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x14001198a`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x140011938`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x140011938`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x1400119d3`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x1400119d3`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140011909`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140011909`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x1400119eb`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x1400119eb`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x140011a01`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x140011a01`
- `ADVAPI32!EqualSid` at `0x1400118b0`
- `ADVAPI32!EqualSid` at `0x1400118cf`
- `ADVAPI32!EqualSid` at `0x1400119a8`
- `ADVAPI32!EqualSid` at `0x1400118b0`
- `ADVAPI32!EqualSid` at `0x1400118cf`
- `ADVAPI32!EqualSid` at `0x1400119a8`

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
0x1400117d0  push    rbp
0x1400117d2  push    rbx
0x1400117d3  push    rsi
0x1400117d4  push    rdi
0x1400117d5  push    r12
0x1400117d7  push    r14
0x1400117d9  push    r15
0x1400117db  mov     rbp, rsp
0x1400117de  sub     rsp, 70h
0x1400117e2  mov     rax, cs:__security_cookie
0x1400117e9  xor     rax, rsp
0x1400117ec  mov     [rbp+var_8], rax
0x1400117f0  mov     r12, r8
0x1400117f3  mov     [rbp+pDacl], 0
0x1400117fb  mov     r15, rdx
0x1400117fe  mov     [rbp+bDaclPresent], 0
0x140011805  lea     r8, [rbp+pDacl]; pDacl
0x140011809  mov     [rbp+bDaclDefaulted], 0
0x140011810  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x140011814  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x140011818  call    cs:__imp_GetSecurityDescriptorDacl
0x14001181e  test    eax, eax
0x140011820  jnz     short loc_14001182F
0x140011822  call    cs:__imp_GetLastError
0x140011828  mov     ebx, eax
0x14001182a  jmp     loc_140011A34
0x14001182f  cmp     [rbp+bDaclPresent], 0
0x140011833  jnz     short loc_14001183F
0x140011835  mov     ebx, 57h ; 'W'
0x14001183a  jmp     loc_140011A34
0x14001183f  mov     rcx, [rbp+pDacl]; pAcl
0x140011843  test    rcx, rcx
0x140011846  jnz     short loc_14001184F
0x140011848  call    ?NullDacl@PrvSpoolssTelemetry@@SAXXZ; PrvSpoolssTelemetry::NullDacl(void)
0x14001184d  jmp     short loc_140011835
0x14001184f  xor     eax, eax
0x140011851  lea     rdx, [rbp+pAclInformation]; pAclInformation
0x140011855  mov     [rbp+pAclInformation], rax
0x140011859  mov     [rbp+var_10], eax
0x14001185c  lea     r9d, [rax+2]; dwAclInformationClass
0x140011860  lea     r8d, [rax+0Ch]; nAclInformationLength
0x140011864  call    cs:__imp_GetAclInformation
0x14001186a  test    eax, eax
0x14001186c  jz      short loc_140011822
0x14001186e  xor     esi, esi
0x140011870  xor     ebx, ebx
0x140011872  xor     edi, edi
0x140011874  lea     r14d, [rsi+1]
0x140011878  cmp     edi, dword ptr [rbp+pAclInformation]
0x14001187b  jnb     short loc_1400118F2
0x14001187d  mov     rcx, [rbp+pDacl]; pAcl
0x140011881  lea     r8, [rbp+pAce]; pAce
0x140011885  mov     edx, edi; dwAceIndex
0x140011887  mov     [rbp+pAce], 0
0x14001188f  call    cs:__imp_GetAce
0x140011895  test    eax, eax
0x140011897  jz      short loc_140011822
0x140011899  mov     rax, [rbp+pAce]
0x14001189d  cmp     byte ptr [rax], 0
0x1400118a0  jnz     short loc_1400118ED
0x1400118a2  mov     rdx, cs:?g_pAppContainerSid@@3PEAXEA; pSid2
0x1400118a9  lea     r14, [rax+8]
0x1400118ad  mov     rcx, r14; pSid1
0x1400118b0  call    cs:__imp_EqualSid
0x1400118b6  test    eax, eax
0x1400118b8  jz      short loc_1400118C5
0x1400118ba  mov     r14d, 1
0x1400118c0  mov     esi, r14d
0x1400118c3  jmp     short loc_1400118E5
0x1400118c5  mov     rdx, cs:?g_pLPACCapabilitySid@@3PEAXEA; pSid2
0x1400118cc  mov     rcx, r14; pSid1
0x1400118cf  call    cs:__imp_EqualSid
0x1400118d5  test    eax, eax
0x1400118d7  mov     r14d, 1
0x1400118dd  cmovnz  ebx, r14d
0x1400118e1  test    esi, esi
0x1400118e3  jz      short loc_1400118ED
0x1400118e5  test    ebx, ebx
0x1400118e7  jnz     loc_140011A2F
0x1400118ed  add     edi, r14d
0x1400118f0  jmp     short loc_140011878
0x1400118f2  test    esi, esi
0x1400118f4  jz      loc_140011A2F
0x1400118fa  test    ebx, ebx
0x1400118fc  jnz     loc_140011A2F
0x140011902  mov     rcx, cs:?g_pLPACCapabilitySid@@3PEAXEA; pSid
0x140011909  call    cs:__imp_GetLengthSid
0x14001190f  mov     ebx, dword ptr [rbp+pAclInformation+4]
0x140011912  add     ebx, eax
0x140011914  lea     ecx, [rbx+0Ch]; dwBytes
0x140011917  call    DllAllocSplMem
0x14001191c  mov     rdi, rax
0x14001191f  test    rax, rax
0x140011922  jnz     short loc_14001192C
0x140011924  lea     ebx, [rax+8]
0x140011927  jmp     loc_140011A34
0x14001192c  mov     r8d, 2; dwAclRevision
0x140011932  lea     edx, [rbx+0Ch]; nAclLength
0x140011935  mov     rcx, rdi; pAcl
0x140011938  call    cs:__imp_InitializeAcl
0x14001193e  test    eax, eax
0x140011940  jz      loc_140011A13
0x140011946  xor     ebx, ebx
0x140011948  cmp     ebx, dword ptr [rbp+pAclInformation]
0x14001194b  jnb     loc_1400119E5
0x140011951  mov     rcx, [rbp+pDacl]; pAcl
0x140011955  lea     r8, [rbp+pAceList]; pAce
0x140011959  mov     edx, ebx; dwAceIndex
0x14001195b  mov     [rbp+pAceList], 0
0x140011963  call    cs:__imp_GetAce
0x140011969  test    eax, eax
0x14001196b  jz      loc_140011A13
0x140011971  mov     r9, [rbp+pAceList]; pAceList
0x140011975  or      r8d, 0FFFFFFFFh; dwStartingAceIndex
0x140011979  mov     edx, 2; dwAceRevision
0x14001197e  mov     rcx, rdi; pAcl
0x140011981  movzx   eax, word ptr [r9+2]
0x140011986  mov     [rsp+70h+nAceListLength], eax; nAceListLength
0x14001198a  call    cs:__imp_AddAce
0x140011990  test    eax, eax
0x140011992  jz      short loc_140011A13
0x140011994  mov     rsi, [rbp+pAceList]
0x140011998  cmp     byte ptr [rsi], 0
0x14001199b  jnz     short loc_1400119DD
0x14001199d  mov     rdx, cs:?g_pAppContainerSid@@3PEAXEA; pSid2
0x1400119a4  lea     rcx, [rsi+8]; pSid1
0x1400119a8  call    cs:__imp_EqualSid
0x1400119ae  test    eax, eax
0x1400119b0  jz      short loc_1400119DD
0x1400119b2  mov     rax, [rbp+pAceList]
0x1400119b6  mov     edx, 2; dwAceRevision
0x1400119bb  mov     r9d, [rsi+4]; AccessMask
0x1400119bf  mov     rcx, rdi; pAcl
0x1400119c2  movzx   r8d, byte ptr [rax+1]; AceFlags
0x1400119c7  mov     rax, cs:?g_pLPACCapabilitySid@@3PEAXEA; void * g_pLPACCapabilitySid
0x1400119ce  mov     qword ptr [rsp+70h+nAceListLength], rax; pSid
0x1400119d3  call    cs:__imp_AddAccessAllowedAceEx
0x1400119d9  test    eax, eax
0x1400119db  jz      short loc_140011A13
0x1400119dd  add     ebx, r14d
0x1400119e0  jmp     loc_140011948
0x1400119e5  mov     edx, r14d; dwRevision
0x1400119e8  mov     rcx, r15; pSecurityDescriptor
0x1400119eb  call    cs:__imp_InitializeSecurityDescriptor
0x1400119f1  test    eax, eax
0x1400119f3  jz      short loc_140011A13
0x1400119f5  xor     r9d, r9d; bDaclDefaulted
0x1400119f8  mov     r8, rdi; pDacl
0x1400119fb  mov     edx, r14d; bDaclPresent
0x1400119fe  mov     rcx, r15; pSecurityDescriptor
0x140011a01  call    cs:__imp_SetSecurityDescriptorDacl
0x140011a07  test    eax, eax
0x140011a09  jz      short loc_140011A13
0x140011a0b  mov     [r12], rdi
0x140011a0f  xor     ebx, ebx
0x140011a11  jmp     short loc_140011A34
0x140011a13  call    cs:__imp_GetLastError
0x140011a19  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x140011a20  mov     r8, rdi; lpMem
0x140011a23  xor     edx, edx; dwFlags
0x140011a25  mov     ebx, eax
0x140011a27  call    cs:__imp_HeapFree
0x140011a2d  jmp     short loc_140011A34
0x140011a2f  mov     ebx, 0B7h
0x140011a34  mov     eax, ebx
0x140011a36  mov     rcx, [rbp+var_8]
0x140011a3a  xor     rcx, rsp; StackCookie
0x140011a3d  call    __security_check_cookie
0x140011a42  add     rsp, 70h
0x140011a46  pop     r15
0x140011a48  pop     r14
0x140011a4a  pop     r12
0x140011a4c  pop     rdi
0x140011a4d  pop     rsi
0x140011a4e  pop     rbx
0x140011a4f  pop     rbp
0x140011a50  retn
```
