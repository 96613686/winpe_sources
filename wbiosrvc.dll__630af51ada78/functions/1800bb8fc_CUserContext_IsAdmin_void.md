# CUserContext::IsAdmin(void)

- ea: `0x1800bb8fc`
- end: `0x1800bbb15`
- name: `?IsAdmin@CUserContext@@QEBAHXZ`
- size: `537`
- prototype: `__int64 __fastcall(CUserContext *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800bc7e0`
- `0x1800bc920`
- `0x1800bca60`

## callees

- `0x180068f60`
- `0x1800bb8fc`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800bb9c1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800bb9fd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800bb9c1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800bb9fd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bb998`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bb9a0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bb9e1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bbade`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bbae7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bb998`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bb9a0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bb9e1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bbade`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bbae7`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800bba16`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800bba16`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800bb9d5`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800bb9d5`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800bba32`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800bba32`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x1800bbacb`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x1800bbacb`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x1800bba62`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x1800bba62`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x1800bba72`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x1800bba72`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x1800bba7b`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x1800bba7b`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800bba4e`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800bba4e`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800bb98c`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800bb98c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800bb9f0`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800bb9f0`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800bb9aa`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800bbaf1`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800bb9aa`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800bbaf1`

## pseudocode

```c
__int64 __fastcall CUserContext::IsAdmin(void **this)
{
  void *v2; // rcx
  HLOCAL v4; // rax
  void *v5; // rbx
  struct _ACL *v6; // rcx
  DWORD v7; // esi
  struct _ACL *v8; // rax
  struct _ACL *v9; // rdi
  BOOL v10; // eax
  void *v11; // rdx
  unsigned int v12; // esi
  PSID pGroup; // [rsp+60h] [rbp-29h] BYREF
  WINBOOL AccessStatus; // [rsp+68h] [rbp-21h] BYREF
  DWORD GrantedAccess; // [rsp+6Ch] [rbp-1Dh] BYREF
  DWORD PrivilegeSetLength; // [rsp+70h] [rbp-19h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+74h] [rbp-15h] BYREF
  struct _GENERIC_MAPPING GenericMapping; // [rsp+80h] [rbp-9h] BYREF
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+90h] [rbp+7h] BYREF

  PrivilegeSetLength = 20;
  pGroup = 0;
  GrantedAccess = 0;
  GenericMapping = 0;
  AccessStatus = 0;
  memset(&PrivilegeSet, 0, sizeof(PrivilegeSet));
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &pGroup)
    || (v4 = LocalAlloc(0x40u, 0x28u), (v5 = v4) == 0) )
  {
    LocalFree(0);
    v2 = 0;
LABEL_3:
    LocalFree(v2);
    FreeSid(pGroup);
    return 0;
  }
  if ( !InitializeSecurityDescriptor(v4, 1u)
    || (v7 = GetLengthSid(pGroup) + 16, v8 = (struct _ACL *)LocalAlloc(0x40u, v7), (v9 = v8) == 0) )
  {
    v6 = 0;
LABEL_7:
    LocalFree(v6);
    v2 = v5;
    goto LABEL_3;
  }
  v10 = InitializeAcl(v8, v7, 2u);
  v6 = v9;
  if ( !v10 )
    goto LABEL_7;
  if ( !AddAccessAllowedAce(v9, 2u, 3u, pGroup)
    || !SetSecurityDescriptorDacl(v5, 1, v9, 0)
    || (SetSecurityDescriptorGroup(v5, pGroup, 0),
        SetSecurityDescriptorOwner(v5, pGroup, 0),
        !IsValidSecurityDescriptor(v5)) )
  {
    v6 = v9;
    goto LABEL_7;
  }
  v11 = *this;
  GenericMapping.GenericRead = 1;
  *(_QWORD *)&GenericMapping.GenericWrite = 2;
  GenericMapping.GenericAll = 3;
  v12 = 0;
  if ( AccessCheck(v5, v11, 1u, &GenericMapping, &PrivilegeSet, &PrivilegeSetLength, &GrantedAccess, &AccessStatus) )
    v12 = AccessStatus;
  LocalFree(v9);
  LocalFree(v5);
  FreeSid(pGroup);
  return v12;
}

```

## disassembly

```asm
0x1800bb8fc  push    rbp
0x1800bb8fe  push    rbx
0x1800bb8ff  push    rsi
0x1800bb900  push    rdi
0x1800bb901  push    r14
0x1800bb903  push    r15
0x1800bb905  lea     rbp, [rsp-2Fh]
0x1800bb90a  sub     rsp, 0B8h
0x1800bb911  mov     rax, cs:__security_cookie
0x1800bb918  xor     rax, rsp
0x1800bb91b  mov     [rbp+57h+var_38], rax
0x1800bb91f  xor     r15d, r15d
0x1800bb922  mov     [rbp+57h+PrivilegeSetLength], 14h
0x1800bb929  xor     eax, eax
0x1800bb92b  mov     [rbp+57h+pGroup], r15
0x1800bb92f  mov     [rbp+57h+PrivilegeSet.Privilege.Attributes], eax
0x1800bb932  mov     r14, rcx
0x1800bb935  lea     rax, [rbp+57h+pGroup]
0x1800bb939  mov     [rbp+57h+GrantedAccess], r15d
0x1800bb93d  mov     [rsp+0E0h+pSid], rax; pSid
0x1800bb942  lea     r8d, [r15+20h]; nSubAuthority0
0x1800bb946  mov     [rsp+0E0h+nSubAuthority7], r15d; nSubAuthority7
0x1800bb94b  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x1800bb94f  mov     [rsp+0E0h+nSubAuthority6], r15d; nSubAuthority6
0x1800bb954  xorps   xmm0, xmm0
0x1800bb957  mov     [rsp+0E0h+nSubAuthority5], r15d; nSubAuthority5
0x1800bb95c  xorps   xmm1, xmm1
0x1800bb95f  mov     [rsp+0E0h+nSubAuthority4], r15d; nSubAuthority4
0x1800bb964  mov     r9d, 220h; nSubAuthority1
0x1800bb96a  mov     [rsp+0E0h+nSubAuthority3], r15d; nSubAuthority3
0x1800bb96f  mov     dl, 2; nSubAuthorityCount
0x1800bb971  mov     [rsp+0E0h+nSubAuthority2], r15d; nSubAuthority2
0x1800bb976  movups  xmmword ptr [rbp+57h+GenericMapping.GenericRead], xmm0
0x1800bb97a  mov     [rbp+57h+AccessStatus], r15d
0x1800bb97e  movups  xmmword ptr [rbp+57h+PrivilegeSet.PrivilegeCount], xmm1
0x1800bb982  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r15d
0x1800bb986  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x1800bb98c  call    cs:__imp_AllocateAndInitializeSid
0x1800bb992  test    eax, eax
0x1800bb994  jnz     short loc_1800BB9B7
0x1800bb996  xor     ecx, ecx; hMem
0x1800bb998  call    cs:__imp_LocalFree
0x1800bb99e  xor     ecx, ecx; hMem
0x1800bb9a0  call    cs:__imp_LocalFree
0x1800bb9a6  mov     rcx, [rbp+57h+pGroup]; pSid
0x1800bb9aa  call    cs:__imp_FreeSid
0x1800bb9b0  xor     eax, eax
0x1800bb9b2  jmp     loc_1800BBAF9
0x1800bb9b7  mov     edx, 28h ; '('; uBytes
0x1800bb9bc  lea     edi, [rdx+18h]
0x1800bb9bf  mov     ecx, edi; uFlags
0x1800bb9c1  call    cs:__imp_LocalAlloc
0x1800bb9c7  mov     rbx, rax
0x1800bb9ca  test    rax, rax
0x1800bb9cd  jz      short loc_1800BB996
0x1800bb9cf  lea     edx, [rdi-3Fh]; dwRevision
0x1800bb9d2  mov     rcx, rax; pSecurityDescriptor
0x1800bb9d5  call    cs:__imp_InitializeSecurityDescriptor
0x1800bb9db  test    eax, eax
0x1800bb9dd  jnz     short loc_1800BB9EC
0x1800bb9df  xor     ecx, ecx; hMem
0x1800bb9e1  call    cs:__imp_LocalFree
0x1800bb9e7  mov     rcx, rbx
0x1800bb9ea  jmp     short loc_1800BB9A0
0x1800bb9ec  mov     rcx, [rbp+57h+pGroup]; pSid
0x1800bb9f0  call    cs:__imp_GetLengthSid
0x1800bb9f6  mov     ecx, edi; uFlags
0x1800bb9f8  lea     esi, [rax+10h]
0x1800bb9fb  mov     edx, esi; uBytes
0x1800bb9fd  call    cs:__imp_LocalAlloc
0x1800bba03  mov     rdi, rax
0x1800bba06  test    rax, rax
0x1800bba09  jz      short loc_1800BB9DF
0x1800bba0b  mov     r8d, 2; dwAclRevision
0x1800bba11  mov     edx, esi; nAclLength
0x1800bba13  mov     rcx, rax; pAcl
0x1800bba16  call    cs:__imp_InitializeAcl
0x1800bba1c  mov     rcx, rdi; pAcl
0x1800bba1f  test    eax, eax
0x1800bba21  jz      short loc_1800BB9E1
0x1800bba23  mov     r9, [rbp+57h+pGroup]; pSid
0x1800bba27  mov     esi, 3
0x1800bba2c  mov     r8d, esi; AccessMask
0x1800bba2f  lea     edx, [rsi-1]; dwAceRevision
0x1800bba32  call    cs:__imp_AddAccessAllowedAce
0x1800bba38  test    eax, eax
0x1800bba3a  jnz     short loc_1800BBA41
0x1800bba3c  mov     rcx, rdi
0x1800bba3f  jmp     short loc_1800BB9E1
0x1800bba41  xor     r9d, r9d; bDaclDefaulted
0x1800bba44  mov     r8, rdi; pDacl
0x1800bba47  mov     rcx, rbx; pSecurityDescriptor
0x1800bba4a  lea     edx, [r9+1]; bDaclPresent
0x1800bba4e  call    cs:__imp_SetSecurityDescriptorDacl
0x1800bba54  test    eax, eax
0x1800bba56  jz      short loc_1800BBA3C
0x1800bba58  mov     rdx, [rbp+57h+pGroup]; pGroup
0x1800bba5c  xor     r8d, r8d; bGroupDefaulted
0x1800bba5f  mov     rcx, rbx; pSecurityDescriptor
0x1800bba62  call    cs:__imp_SetSecurityDescriptorGroup
0x1800bba68  mov     rdx, [rbp+57h+pGroup]; pOwner
0x1800bba6c  xor     r8d, r8d; bOwnerDefaulted
0x1800bba6f  mov     rcx, rbx; pSecurityDescriptor
0x1800bba72  call    cs:__imp_SetSecurityDescriptorOwner
0x1800bba78  mov     rcx, rbx; pSecurityDescriptor
0x1800bba7b  call    cs:__imp_IsValidSecurityDescriptor
0x1800bba81  test    eax, eax
0x1800bba83  jz      short loc_1800BBA3C
0x1800bba85  mov     rdx, [r14]; ClientToken
0x1800bba88  lea     rax, [rbp+57h+AccessStatus]
0x1800bba8c  mov     qword ptr [rsp+0E0h+nSubAuthority5], rax; AccessStatus
0x1800bba91  lea     r9, [rbp+57h+GenericMapping]; GenericMapping
0x1800bba95  lea     rax, [rbp+57h+GrantedAccess]
0x1800bba99  mov     [rbp+57h+GenericMapping.GenericRead], 1
0x1800bbaa0  mov     qword ptr [rsp+0E0h+nSubAuthority4], rax; GrantedAccess
0x1800bbaa5  mov     r8d, 1; DesiredAccess
0x1800bbaab  lea     rax, [rbp+57h+PrivilegeSetLength]
0x1800bbaaf  mov     qword ptr [rbp+57h+GenericMapping.GenericWrite], 2
0x1800bbab7  mov     qword ptr [rsp+0E0h+nSubAuthority3], rax; PrivilegeSetLength
0x1800bbabc  mov     rcx, rbx; pSecurityDescriptor
0x1800bbabf  lea     rax, [rbp+57h+PrivilegeSet]
0x1800bbac3  mov     [rbp+57h+GenericMapping.GenericAll], esi
0x1800bbac6  mov     qword ptr [rsp+0E0h+nSubAuthority2], rax; PrivilegeSet
0x1800bbacb  call    cs:__imp_AccessCheck
0x1800bbad1  mov     esi, r15d
0x1800bbad4  test    eax, eax
0x1800bbad6  jz      short loc_1800BBADB
0x1800bbad8  mov     esi, [rbp+57h+AccessStatus]
0x1800bbadb  mov     rcx, rdi; hMem
0x1800bbade  call    cs:__imp_LocalFree
0x1800bbae4  mov     rcx, rbx; hMem
0x1800bbae7  call    cs:__imp_LocalFree
0x1800bbaed  mov     rcx, [rbp+57h+pGroup]; pSid
0x1800bbaf1  call    cs:__imp_FreeSid
0x1800bbaf7  mov     eax, esi
0x1800bbaf9  mov     rcx, [rbp+57h+var_38]
0x1800bbafd  xor     rcx, rsp; StackCookie
0x1800bbb00  call    __security_check_cookie
0x1800bbb05  add     rsp, 0B8h
0x1800bbb0c  pop     r15
0x1800bbb0e  pop     r14
0x1800bbb10  pop     rdi
0x1800bbb11  pop     rsi
0x1800bbb12  pop     rbx
0x1800bbb13  pop     rbp
0x1800bbb14  retn
```
