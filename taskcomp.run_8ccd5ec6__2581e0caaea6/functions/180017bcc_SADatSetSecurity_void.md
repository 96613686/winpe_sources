# SADatSetSecurity(void *)

- ea: `0x180017bcc`
- end: `0x180017d7b`
- name: `?SADatSetSecurity@@YAKPEAX@Z`
- size: `431`
- prototype: `unsigned int __fastcall(HANDLE handle)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800177d4`

## callees

- `0x180017bcc`
- `0x180030700`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180017c46`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180017c46`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180017d54`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180017d54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017c56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017c56`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017d2a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017d3f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017d2a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017d3f`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180017ce1`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180017ce1`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x180017d13`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x180017d13`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x180017c91`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x180017c91`

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
0x180017bcc  push    rbp
0x180017bce  push    rbx
0x180017bcf  push    rsi
0x180017bd0  push    rdi
0x180017bd1  lea     rbp, [rsp-3Fh]
0x180017bd6  sub     rsp, 0C8h
0x180017bdd  mov     rax, cs:__security_cookie
0x180017be4  xor     rax, rsp
0x180017be7  mov     [rbp+57h+var_28], rax
0x180017beb  xor     esi, esi
0x180017bed  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x180017bf3  xorps   xmm0, xmm0
0x180017bf6  mov     [rbp+57h+var_78], rsi
0x180017bfa  lea     rax, [rbp+57h+var_78]
0x180017bfe  mov     [rbp+57h+ppDacl], rsi
0x180017c02  mov     [rsp+0E0h+pSid], rax; pSid
0x180017c07  mov     rdi, rcx
0x180017c0a  mov     [rsp+0E0h+nSubAuthority7], esi; nSubAuthority7
0x180017c0e  lea     r8d, [rsi+0Bh]; nSubAuthority0
0x180017c12  mov     [rsp+0E0h+nSubAuthority6], esi; nSubAuthority6
0x180017c16  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x180017c1a  mov     [rsp+0E0h+nSubAuthority5], esi; nSubAuthority5
0x180017c1e  xor     r9d, r9d; nSubAuthority1
0x180017c21  mov     [rsp+0E0h+nSubAuthority4], esi; nSubAuthority4
0x180017c25  mov     dl, 1; nSubAuthorityCount
0x180017c27  mov     [rsp+0E0h+nSubAuthority3], esi; nSubAuthority3
0x180017c2b  mov     [rsp+0E0h+nSubAuthority2], esi; nSubAuthority2
0x180017c2f  mov     [rbp+57h+NewAcl], rsi
0x180017c33  mov     [rbp+57h+ppSecurityDescriptor], rsi
0x180017c37  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], xmm0
0x180017c3b  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], esi
0x180017c3e  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.Trustee.pMultipleTrustee], xmm0
0x180017c42  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeType], xmm0
0x180017c46  call    cs:__imp_AllocateAndInitializeSid
0x180017c4d  nop     dword ptr [rax+rax+00h]
0x180017c52  test    eax, eax
0x180017c54  jnz     short loc_180017C67
0x180017c56  call    cs:__imp_GetLastError
0x180017c5d  nop     dword ptr [rax+rax+00h]
0x180017c62  jmp     loc_180017D1F
0x180017c67  xor     r9d, r9d; ppsidOwner
0x180017c6a  lea     rax, [rbp+57h+ppSecurityDescriptor]
0x180017c6e  mov     qword ptr [rsp+0E0h+nSubAuthority5], rax; ppSecurityDescriptor
0x180017c73  mov     rcx, rdi; handle
0x180017c76  lea     rax, [rbp+57h+ppDacl]
0x180017c7a  mov     qword ptr [rsp+0E0h+nSubAuthority4], rsi; ppSacl
0x180017c7f  mov     qword ptr [rsp+0E0h+nSubAuthority3], rax; ppDacl
0x180017c84  lea     edx, [r9+1]; ObjectType
0x180017c88  mov     qword ptr [rsp+0E0h+nSubAuthority2], rsi; ppsidGroup
0x180017c8d  lea     r8d, [r9+4]; SecurityInfo
0x180017c91  call    cs:__imp_GetSecurityInfo
0x180017c98  nop     dword ptr [rax+rax+00h]
0x180017c9d  mov     ebx, eax
0x180017c9f  test    eax, eax
0x180017ca1  jnz     short loc_180017D21
0x180017ca3  lea     ecx, [rax+30h]
0x180017ca6  lea     rax, [rbp+57h+pListOfExplicitEntries]
0x180017caa  mov     [rax], sil
0x180017cad  inc     rax
0x180017cb0  sub     rcx, 1
0x180017cb4  jnz     short loc_180017CAA
0x180017cb6  mov     rax, [rbp+57h+var_78]
0x180017cba  lea     r9, [rbp+57h+NewAcl]; NewAcl
0x180017cbe  mov     r8, [rbp+57h+ppDacl]; OldAcl
0x180017cc2  lea     rdx, [rbp+57h+pListOfExplicitEntries]; pListOfExplicitEntries
0x180017cc6  mov     ecx, 1; cCountOfExplicitEntries
0x180017ccb  mov     [rbp+57h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x180017ccf  mov     [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], 80000000h
0x180017cd6  mov     qword ptr [rbp+57h+pListOfExplicitEntries.grfAccessMode], 1
0x180017cde  mov     [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeForm], esi
0x180017ce1  call    cs:__imp_SetEntriesInAclW
0x180017ce8  nop     dword ptr [rax+rax+00h]
0x180017ced  mov     ebx, eax
0x180017cef  test    eax, eax
0x180017cf1  jnz     short loc_180017D21
0x180017cf3  mov     rax, [rbp+57h+NewAcl]
0x180017cf7  lea     edx, [rbx+1]; ObjectType
0x180017cfa  mov     qword ptr [rsp+0E0h+nSubAuthority4], rsi; pSacl
0x180017cff  lea     r8d, [rbx+4]; SecurityInfo
0x180017d03  mov     qword ptr [rsp+0E0h+nSubAuthority3], rax; pDacl
0x180017d08  xor     r9d, r9d; psidOwner
0x180017d0b  mov     rcx, rdi; handle
0x180017d0e  mov     qword ptr [rsp+0E0h+nSubAuthority2], rsi; psidGroup
0x180017d13  call    cs:__imp_SetSecurityInfo
0x180017d1a  nop     dword ptr [rax+rax+00h]
0x180017d1f  mov     ebx, eax
0x180017d21  mov     rcx, [rbp+57h+ppSecurityDescriptor]; hMem
0x180017d25  test    rcx, rcx
0x180017d28  jz      short loc_180017D36
0x180017d2a  call    cs:__imp_LocalFree
0x180017d31  nop     dword ptr [rax+rax+00h]
0x180017d36  mov     rcx, [rbp+57h+NewAcl]; hMem
0x180017d3a  test    rcx, rcx
0x180017d3d  jz      short loc_180017D4B
0x180017d3f  call    cs:__imp_LocalFree
0x180017d46  nop     dword ptr [rax+rax+00h]
0x180017d4b  mov     rcx, [rbp+57h+var_78]; pSid
0x180017d4f  test    rcx, rcx
0x180017d52  jz      short loc_180017D60
0x180017d54  call    cs:__imp_FreeSid
0x180017d5b  nop     dword ptr [rax+rax+00h]
0x180017d60  mov     eax, ebx
0x180017d62  mov     rcx, [rbp+57h+var_28]
0x180017d66  xor     rcx, rsp; StackCookie
0x180017d69  call    __security_check_cookie
0x180017d6e  add     rsp, 0C8h
0x180017d75  pop     rdi
0x180017d76  pop     rsi
0x180017d77  pop     rbx
0x180017d78  pop     rbp
0x180017d79  retn
```
