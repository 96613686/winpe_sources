# SADatSetSecurity(void *)

- ea: `0x180016c54`
- end: `0x180016dd2`
- name: `?SADatSetSecurity@@YAKPEAX@Z`
- size: `382`
- prototype: `__int64 __fastcall(HANDLE handle)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800168b8`

## callees

- `0x180016c54`
- `0x18002e5b0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180016cce`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180016cce`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180016db2`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180016db2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016cd8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016cd8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016d94`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016da3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016d94`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016da3`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180016d57`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180016d57`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x180016d83`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x180016d83`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x180016d0d`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x180016d0d`

## pseudocode

```c
__int64 __fastcall SADatSetSecurity(HANDLE handle)
{
  DWORD LastError; // eax
  DWORD SecurityInfo; // ebx
  __int64 v4; // rcx
  _EXPLICIT_ACCESS_W *p_pListOfExplicitEntries; // rax
  PACL NewAcl; // [rsp+60h] [rbp-29h] BYREF
  PSID pSid; // [rsp+68h] [rbp-21h] BYREF
  PACL ppDacl; // [rsp+70h] [rbp-19h] BYREF
  PSECURITY_DESCRIPTOR ppSecurityDescriptor; // [rsp+78h] [rbp-11h] BYREF
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+80h] [rbp-9h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+B0h] [rbp+27h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  pSid = 0;
  ppDacl = 0;
  NewAcl = 0;
  ppSecurityDescriptor = 0;
  memset(&pListOfExplicitEntries, 0, sizeof(pListOfExplicitEntries));
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0xBu, 0, 0, 0, 0, 0, 0, 0, &pSid) )
  {
    LastError = GetLastError();
LABEL_8:
    SecurityInfo = LastError;
    goto LABEL_9;
  }
  SecurityInfo = GetSecurityInfo(handle, SE_FILE_OBJECT, 4u, 0, 0, &ppDacl, 0, &ppSecurityDescriptor);
  if ( !SecurityInfo )
  {
    v4 = 48;
    p_pListOfExplicitEntries = &pListOfExplicitEntries;
    do
    {
      LOBYTE(p_pListOfExplicitEntries->grfAccessPermissions) = 0;
      p_pListOfExplicitEntries = (_EXPLICIT_ACCESS_W *)((char *)p_pListOfExplicitEntries + 1);
      --v4;
    }
    while ( v4 );
    pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)pSid;
    pListOfExplicitEntries.grfAccessPermissions = 0x80000000;
    *(_QWORD *)&pListOfExplicitEntries.grfAccessMode = 1;
    pListOfExplicitEntries.Trustee.TrusteeForm = TRUSTEE_IS_SID;
    SecurityInfo = SetEntriesInAclW(1u, &pListOfExplicitEntries, ppDacl, &NewAcl);
    if ( !SecurityInfo )
    {
      LastError = SetSecurityInfo(handle, SE_FILE_OBJECT, 4u, 0, 0, NewAcl, 0);
      goto LABEL_8;
    }
  }
LABEL_9:
  if ( ppSecurityDescriptor )
    LocalFree(ppSecurityDescriptor);
  if ( NewAcl )
    LocalFree(NewAcl);
  if ( pSid )
    FreeSid(pSid);
  return SecurityInfo;
}

```

## disassembly

```asm
0x180016c54  push    rbp
0x180016c56  push    rbx
0x180016c57  push    rsi
0x180016c58  push    rdi
0x180016c59  lea     rbp, [rsp-3Fh]
0x180016c5e  sub     rsp, 0C8h
0x180016c65  mov     rax, cs:__security_cookie
0x180016c6c  xor     rax, rsp
0x180016c6f  mov     [rbp+57h+var_28], rax
0x180016c73  xor     esi, esi
0x180016c75  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x180016c7b  xorps   xmm0, xmm0
0x180016c7e  mov     [rbp+57h+var_78], rsi
0x180016c82  lea     rax, [rbp+57h+var_78]
0x180016c86  mov     [rbp+57h+ppDacl], rsi
0x180016c8a  mov     [rsp+0E0h+pSid], rax; pSid
0x180016c8f  mov     rdi, rcx
0x180016c92  mov     [rsp+0E0h+nSubAuthority7], esi; nSubAuthority7
0x180016c96  lea     r8d, [rsi+0Bh]; nSubAuthority0
0x180016c9a  mov     [rsp+0E0h+nSubAuthority6], esi; nSubAuthority6
0x180016c9e  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x180016ca2  mov     [rsp+0E0h+nSubAuthority5], esi; nSubAuthority5
0x180016ca6  xor     r9d, r9d; nSubAuthority1
0x180016ca9  mov     [rsp+0E0h+nSubAuthority4], esi; nSubAuthority4
0x180016cad  mov     dl, 1; nSubAuthorityCount
0x180016caf  mov     [rsp+0E0h+nSubAuthority3], esi; nSubAuthority3
0x180016cb3  mov     [rsp+0E0h+nSubAuthority2], esi; nSubAuthority2
0x180016cb7  mov     [rbp+57h+NewAcl], rsi
0x180016cbb  mov     [rbp+57h+ppSecurityDescriptor], rsi
0x180016cbf  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], xmm0
0x180016cc3  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], esi
0x180016cc6  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.Trustee.pMultipleTrustee], xmm0
0x180016cca  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeType], xmm0
0x180016cce  call    cs:__imp_AllocateAndInitializeSid
0x180016cd4  test    eax, eax
0x180016cd6  jnz     short loc_180016CE3
0x180016cd8  call    cs:__imp_GetLastError
0x180016cde  jmp     loc_180016D89
0x180016ce3  xor     r9d, r9d; ppsidOwner
0x180016ce6  lea     rax, [rbp+57h+ppSecurityDescriptor]
0x180016cea  mov     qword ptr [rsp+0E0h+nSubAuthority5], rax; ppSecurityDescriptor
0x180016cef  mov     rcx, rdi; handle
0x180016cf2  lea     rax, [rbp+57h+ppDacl]
0x180016cf6  mov     qword ptr [rsp+0E0h+nSubAuthority4], rsi; ppSacl
0x180016cfb  mov     qword ptr [rsp+0E0h+nSubAuthority3], rax; ppDacl
0x180016d00  lea     edx, [r9+1]; ObjectType
0x180016d04  mov     qword ptr [rsp+0E0h+nSubAuthority2], rsi; ppsidGroup
0x180016d09  lea     r8d, [r9+4]; SecurityInfo
0x180016d0d  call    cs:__imp_GetSecurityInfo
0x180016d13  mov     ebx, eax
0x180016d15  test    eax, eax
0x180016d17  jnz     short loc_180016D8B
0x180016d19  lea     ecx, [rax+30h]
0x180016d1c  lea     rax, [rbp+57h+pListOfExplicitEntries]
0x180016d20  mov     [rax], sil
0x180016d23  inc     rax
0x180016d26  sub     rcx, 1
0x180016d2a  jnz     short loc_180016D20
0x180016d2c  mov     rax, [rbp+57h+var_78]
0x180016d30  lea     r9, [rbp+57h+NewAcl]; NewAcl
0x180016d34  mov     r8, [rbp+57h+ppDacl]; OldAcl
0x180016d38  lea     rdx, [rbp+57h+pListOfExplicitEntries]; pListOfExplicitEntries
0x180016d3c  mov     ecx, 1; cCountOfExplicitEntries
0x180016d41  mov     [rbp+57h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x180016d45  mov     [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], 80000000h
0x180016d4c  mov     qword ptr [rbp+57h+pListOfExplicitEntries.grfAccessMode], 1
0x180016d54  mov     [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeForm], esi
0x180016d57  call    cs:__imp_SetEntriesInAclW
0x180016d5d  mov     ebx, eax
0x180016d5f  test    eax, eax
0x180016d61  jnz     short loc_180016D8B
0x180016d63  mov     rax, [rbp+57h+NewAcl]
0x180016d67  lea     edx, [rbx+1]; ObjectType
0x180016d6a  mov     qword ptr [rsp+0E0h+nSubAuthority4], rsi; pSacl
0x180016d6f  lea     r8d, [rbx+4]; SecurityInfo
0x180016d73  mov     qword ptr [rsp+0E0h+nSubAuthority3], rax; pDacl
0x180016d78  xor     r9d, r9d; psidOwner
0x180016d7b  mov     rcx, rdi; handle
0x180016d7e  mov     qword ptr [rsp+0E0h+nSubAuthority2], rsi; psidGroup
0x180016d83  call    cs:__imp_SetSecurityInfo
0x180016d89  mov     ebx, eax
0x180016d8b  mov     rcx, [rbp+57h+ppSecurityDescriptor]; hMem
0x180016d8f  test    rcx, rcx
0x180016d92  jz      short loc_180016D9A
0x180016d94  call    cs:__imp_LocalFree
0x180016d9a  mov     rcx, [rbp+57h+NewAcl]; hMem
0x180016d9e  test    rcx, rcx
0x180016da1  jz      short loc_180016DA9
0x180016da3  call    cs:__imp_LocalFree
0x180016da9  mov     rcx, [rbp+57h+var_78]; pSid
0x180016dad  test    rcx, rcx
0x180016db0  jz      short loc_180016DB8
0x180016db2  call    cs:__imp_FreeSid
0x180016db8  mov     eax, ebx
0x180016dba  mov     rcx, [rbp+57h+var_28]
0x180016dbe  xor     rcx, rsp; StackCookie
0x180016dc1  call    __security_check_cookie
0x180016dc6  add     rsp, 0C8h
0x180016dcd  pop     rdi
0x180016dce  pop     rsi
0x180016dcf  pop     rbx
0x180016dd0  pop     rbp
0x180016dd1  retn
```
