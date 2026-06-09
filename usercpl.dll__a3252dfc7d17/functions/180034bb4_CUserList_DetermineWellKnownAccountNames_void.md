# CUserList::DetermineWellKnownAccountNames(void)

- ea: `0x180034bb4`
- end: `0x180034f48`
- name: `?DetermineWellKnownAccountNames@CUserList@@CAXXZ`
- size: `916`
- prototype: `static void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180034f50`

## callees

- `0x180034bb4`
- `0x18007728a`
- `0x1800772c0`

## import_xrefs

- `samcli!NetUserModalsGet` at `0x180034c07`
- `samcli!NetUserModalsGet` at `0x180034c07`
- `netutils!NetApiBufferFree` at `0x180034d05`
- `netutils!NetApiBufferFree` at `0x180034d05`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180034c1d`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180034c7b`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180034ce6`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180034c1d`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180034c7b`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180034ce6`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x180034c2c`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x180034c48`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x180034c9d`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x180034cb3`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x180034c2c`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x180034c48`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x180034c9d`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x180034cb3`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180034c6c`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180034cd7`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180034c6c`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180034cd7`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180034c5d`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180034cc8`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180034c5d`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180034cc8`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180034d90`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180034e11`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180034e92`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180034f13`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180034d90`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180034e11`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180034e92`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180034f13`
- `ntdll!RtlFreeSid` at `0x180034d9a`
- `ntdll!RtlFreeSid` at `0x180034e1b`
- `ntdll!RtlFreeSid` at `0x180034e9c`
- `ntdll!RtlFreeSid` at `0x180034f1d`
- `ntdll!RtlFreeSid` at `0x180034d9a`
- `ntdll!RtlFreeSid` at `0x180034e1b`
- `ntdll!RtlFreeSid` at `0x180034e9c`
- `ntdll!RtlFreeSid` at `0x180034f1d`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180034d4c`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180034dd5`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180034e56`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180034ed7`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180034d4c`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180034dd5`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180034e56`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180034ed7`

## pseudocode

```c
void CUserList::DetermineWellKnownAccountNames(void)
{
  DWORD v0; // edi
  void *v1; // rbx
  DWORD SidLengthRequired; // eax
  void *v3; // rbx
  DWORD v4; // eax
  DWORD cchReferencedDomainName; // [rsp+60h] [rbp-29h] BYREF
  DWORD cchName; // [rsp+64h] [rbp-25h] BYREF
  PSID Sid; // [rsp+68h] [rbp-21h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+70h] [rbp-19h] BYREF
  LPBYTE bufptr; // [rsp+78h] [rbp-11h] BYREF
  WCHAR ReferencedDomainName[16]; // [rsp+80h] [rbp-9h] BYREF

  if ( !byte_1800A26AC )
  {
    bufptr = 0;
    Sid = 0;
    cchName = 0;
    cchReferencedDomainName = 0;
    peUse = 0;
    if ( !NetUserModalsGet(0, 2u, &bufptr) )
    {
      v0 = *GetSidSubAuthorityCount(*((PSID *)bufptr + 1));
      if ( GetSidLengthRequired(v0 + 1) > 0x100 )
      {
        memset_0(&CUserList::s_SIDAdministrator, 0, 0x100u);
      }
      else
      {
        v1 = (void *)*((_QWORD *)bufptr + 1);
        SidLengthRequired = GetSidLengthRequired(v0 + 1);
        if ( CopySid(SidLengthRequired, &CUserList::s_SIDAdministrator, v1) )
        {
          *GetSidSubAuthority(&CUserList::s_SIDAdministrator, v0) = 500;
          *GetSidSubAuthorityCount(&CUserList::s_SIDAdministrator) = v0 + 1;
        }
      }
      if ( GetSidLengthRequired(v0 + 1) > 0x100 )
      {
        memset_0(&CUserList::s_SIDAdministrator, 0, 0x100u);
      }
      else
      {
        v3 = (void *)*((_QWORD *)bufptr + 1);
        v4 = GetSidLengthRequired(v0 + 1);
        if ( CopySid(v4, &CUserList::s_SIDGuest, v3) )
        {
          *GetSidSubAuthority(&CUserList::s_SIDGuest, v0) = 501;
          *GetSidSubAuthorityCount(&CUserList::s_SIDGuest) = v0 + 1;
        }
      }
      NetApiBufferFree(bufptr);
    }
    if ( RtlAllocateAndInitializeSid(&IdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &Sid) >= 0 )
    {
      cchName = 257;
      cchReferencedDomainName = 16;
      LookupAccountSidW(
        0,
        Sid,
        &CUserList::s_szAdministratorsGroupName,
        &cchName,
        ReferencedDomainName,
        &cchReferencedDomainName,
        &peUse);
      RtlFreeSid(Sid);
    }
    if ( RtlAllocateAndInitializeSid(&IdentifierAuthority, 2u, 0x20u, 0x223u, 0, 0, 0, 0, 0, 0, &Sid) >= 0 )
    {
      cchName = 257;
      cchReferencedDomainName = 16;
      LookupAccountSidW(
        0,
        Sid,
        &CUserList::s_szPowerUsersGroupName,
        &cchName,
        ReferencedDomainName,
        &cchReferencedDomainName,
        &peUse);
      RtlFreeSid(Sid);
    }
    if ( RtlAllocateAndInitializeSid(&IdentifierAuthority, 2u, 0x20u, 0x221u, 0, 0, 0, 0, 0, 0, &Sid) >= 0 )
    {
      cchName = 257;
      cchReferencedDomainName = 16;
      LookupAccountSidW(
        0,
        Sid,
        &CUserList::s_szUsersGroupName,
        &cchName,
        ReferencedDomainName,
        &cchReferencedDomainName,
        &peUse);
      RtlFreeSid(Sid);
    }
    if ( RtlAllocateAndInitializeSid(&IdentifierAuthority, 2u, 0x20u, 0x222u, 0, 0, 0, 0, 0, 0, &Sid) >= 0 )
    {
      cchName = 257;
      cchReferencedDomainName = 16;
      LookupAccountSidW(
        0,
        Sid,
        &CUserList::s_szGuestsGroupName,
        &cchName,
        ReferencedDomainName,
        &cchReferencedDomainName,
        &peUse);
      RtlFreeSid(Sid);
    }
    byte_1800A26AC = 1;
  }
}

```

## disassembly

```asm
0x180034bb4  push    rbp
0x180034bb6  push    rbx
0x180034bb7  push    rsi
0x180034bb8  push    rdi
0x180034bb9  push    r12
0x180034bbb  push    r14
0x180034bbd  push    r15
0x180034bbf  lea     rbp, [rsp-27h]
0x180034bc4  sub     rsp, 0B0h
0x180034bcb  mov     rax, cs:__security_cookie
0x180034bd2  xor     rax, rsp
0x180034bd5  mov     [rbp+57h+var_40], rax
0x180034bd9  xor     r15d, r15d
0x180034bdc  cmp     cs:byte_1800A26AC, r15b
0x180034be3  jnz     loc_180034F2A
0x180034be9  lea     r8, [rbp+57h+bufptr]; bufptr
0x180034bed  mov     [rbp+57h+bufptr], r15
0x180034bf1  lea     edx, [r15+2]; level
0x180034bf5  mov     [rbp+57h+var_78], r15
0x180034bf9  xor     ecx, ecx; servername
0x180034bfb  mov     [rbp+57h+cchName], r15d
0x180034bff  mov     [rbp+57h+cchReferencedDomainName], r15d
0x180034c03  mov     [rbp+57h+peUse], r15d
0x180034c07  call    cs:__imp_NetUserModalsGet
0x180034c0d  test    eax, eax
0x180034c0f  jnz     loc_180034D0B
0x180034c15  mov     rcx, [rbp+57h+bufptr]
0x180034c19  mov     rcx, [rcx+8]; pSid
0x180034c1d  call    cs:__imp_GetSidSubAuthorityCount
0x180034c23  movzx   edi, byte ptr [rax]
0x180034c26  lea     esi, [rdi+1]
0x180034c29  mov     cl, sil; nSubAuthorityCount
0x180034c2c  call    cs:__imp_GetSidLengthRequired
0x180034c32  mov     r12d, 100h
0x180034c38  cmp     eax, r12d
0x180034c3b  ja      short loc_180034C86
0x180034c3d  mov     rax, [rbp+57h+bufptr]
0x180034c41  mov     cl, sil; nSubAuthorityCount
0x180034c44  mov     rbx, [rax+8]
0x180034c48  call    cs:__imp_GetSidLengthRequired
0x180034c4e  mov     r8, rbx; pSourceSid
0x180034c51  lea     rbx, ?s_SIDAdministrator@CUserList@@0PAEA; uchar near * CUserList::s_SIDAdministrator
0x180034c58  mov     rdx, rbx; pDestinationSid
0x180034c5b  mov     ecx, eax; nDestinationSidLength
0x180034c5d  call    cs:__imp_CopySid
0x180034c63  test    eax, eax
0x180034c65  jz      short loc_180034C9A
0x180034c67  mov     edx, edi; nSubAuthority
0x180034c69  mov     rcx, rbx; pSid
0x180034c6c  call    cs:__imp_GetSidSubAuthority
0x180034c72  mov     rcx, rbx; pSid
0x180034c75  mov     dword ptr [rax], 1F4h
0x180034c7b  call    cs:__imp_GetSidSubAuthorityCount
0x180034c81  mov     [rax], sil
0x180034c84  jmp     short loc_180034C9A
0x180034c86  lea     rbx, ?s_SIDAdministrator@CUserList@@0PAEA; uchar near * CUserList::s_SIDAdministrator
0x180034c8d  mov     r8, r12; Size
0x180034c90  mov     rcx, rbx; void *
0x180034c93  xor     edx, edx; Val
0x180034c95  call    memset_0
0x180034c9a  mov     cl, sil; nSubAuthorityCount
0x180034c9d  call    cs:__imp_GetSidLengthRequired
0x180034ca3  cmp     eax, r12d
0x180034ca6  ja      short loc_180034CF4
0x180034ca8  mov     rax, [rbp+57h+bufptr]
0x180034cac  mov     cl, sil; nSubAuthorityCount
0x180034caf  mov     rbx, [rax+8]
0x180034cb3  call    cs:__imp_GetSidLengthRequired
0x180034cb9  mov     r8, rbx; pSourceSid
0x180034cbc  lea     rbx, ?s_SIDGuest@CUserList@@0PAEA; uchar near * CUserList::s_SIDGuest
0x180034cc3  mov     rdx, rbx; pDestinationSid
0x180034cc6  mov     ecx, eax; nDestinationSidLength
0x180034cc8  call    cs:__imp_CopySid
0x180034cce  test    eax, eax
0x180034cd0  jz      short loc_180034D01
0x180034cd2  mov     edx, edi; nSubAuthority
0x180034cd4  mov     rcx, rbx; pSid
0x180034cd7  call    cs:__imp_GetSidSubAuthority
0x180034cdd  mov     rcx, rbx; pSid
0x180034ce0  mov     dword ptr [rax], 1F5h
0x180034ce6  call    cs:__imp_GetSidSubAuthorityCount
0x180034cec  inc     dil
0x180034cef  mov     [rax], dil
0x180034cf2  jmp     short loc_180034D01
0x180034cf4  mov     r8, r12; Size
0x180034cf7  xor     edx, edx; Val
0x180034cf9  mov     rcx, rbx; void *
0x180034cfc  call    memset_0
0x180034d01  mov     rcx, [rbp+57h+bufptr]; Buffer
0x180034d05  call    cs:__imp_NetApiBufferFree
0x180034d0b  lea     rax, [rbp+57h+var_78]
0x180034d0f  mov     esi, 20h ; ' '
0x180034d14  mov     [rsp+0E0h+Sid], rax; Sid
0x180034d19  lea     r14, IdentifierAuthority
0x180034d20  mov     [rsp+0E0h+SubAuthority7], r15d; SubAuthority7
0x180034d25  mov     r9d, 220h; SubAuthority1
0x180034d2b  mov     [rsp+0E0h+SubAuthority6], r15d; SubAuthority6
0x180034d30  mov     r8d, esi; SubAuthority0
0x180034d33  mov     [rsp+0E0h+SubAuthority5], r15d; SubAuthority5
0x180034d38  mov     dl, 2; SubAuthorityCount
0x180034d3a  mov     [rsp+0E0h+SubAuthority4], r15d; SubAuthority4
0x180034d3f  mov     rcx, r14; IdentifierAuthority
0x180034d42  mov     [rsp+0E0h+SubAuthority3], r15d; SubAuthority3
0x180034d47  mov     [rsp+0E0h+SubAuthority2], r15d; SubAuthority2
0x180034d4c  call    cs:__imp_RtlAllocateAndInitializeSid
0x180034d52  mov     ebx, 101h
0x180034d57  lea     edi, [rsi-10h]
0x180034d5a  test    eax, eax
0x180034d5c  js      short loc_180034DA0
0x180034d5e  mov     rdx, [rbp+57h+var_78]; Sid
0x180034d62  lea     rax, [rbp+57h+peUse]
0x180034d66  mov     qword ptr [rsp+0E0h+SubAuthority4], rax; peUse
0x180034d6b  lea     r9, [rbp+57h+cchName]; cchName
0x180034d6f  lea     rax, [rbp+57h+cchReferencedDomainName]
0x180034d73  mov     [rbp+57h+cchName], ebx
0x180034d76  mov     qword ptr [rsp+0E0h+SubAuthority3], rax; cchReferencedDomainName
0x180034d7b  lea     r8, ?s_szAdministratorsGroupName@CUserList@@0PAGA; Name
0x180034d82  lea     rax, [rbp+57h+ReferencedDomainName]
0x180034d86  mov     [rbp+57h+cchReferencedDomainName], edi
0x180034d89  xor     ecx, ecx; lpSystemName
0x180034d8b  mov     qword ptr [rsp+0E0h+SubAuthority2], rax; ReferencedDomainName
0x180034d90  call    cs:__imp_LookupAccountSidW
0x180034d96  mov     rcx, [rbp+57h+var_78]; Sid
0x180034d9a  call    cs:__imp_RtlFreeSid
0x180034da0  lea     rax, [rbp+57h+var_78]
0x180034da4  mov     r9d, 223h; SubAuthority1
0x180034daa  mov     [rsp+0E0h+Sid], rax; Sid
0x180034daf  mov     r8d, esi; SubAuthority0
0x180034db2  mov     [rsp+0E0h+SubAuthority7], r15d; SubAuthority7
0x180034db7  mov     dl, 2; SubAuthorityCount
0x180034db9  mov     [rsp+0E0h+SubAuthority6], r15d; SubAuthority6
0x180034dbe  mov     rcx, r14; IdentifierAuthority
0x180034dc1  mov     [rsp+0E0h+SubAuthority5], r15d; SubAuthority5
0x180034dc6  mov     [rsp+0E0h+SubAuthority4], r15d; SubAuthority4
0x180034dcb  mov     [rsp+0E0h+SubAuthority3], r15d; SubAuthority3
0x180034dd0  mov     [rsp+0E0h+SubAuthority2], r15d; SubAuthority2
0x180034dd5  call    cs:__imp_RtlAllocateAndInitializeSid
0x180034ddb  test    eax, eax
0x180034ddd  js      short loc_180034E21
0x180034ddf  mov     rdx, [rbp+57h+var_78]; Sid
0x180034de3  lea     rax, [rbp+57h+peUse]
0x180034de7  mov     qword ptr [rsp+0E0h+SubAuthority4], rax; peUse
0x180034dec  lea     r9, [rbp+57h+cchName]; cchName
0x180034df0  lea     rax, [rbp+57h+cchReferencedDomainName]
0x180034df4  mov     [rbp+57h+cchName], ebx
0x180034df7  mov     qword ptr [rsp+0E0h+SubAuthority3], rax; cchReferencedDomainName
0x180034dfc  lea     r8, ?s_szPowerUsersGroupName@CUserList@@0PAGA; Name
0x180034e03  lea     rax, [rbp+57h+ReferencedDomainName]
0x180034e07  mov     [rbp+57h+cchReferencedDomainName], edi
0x180034e0a  xor     ecx, ecx; lpSystemName
0x180034e0c  mov     qword ptr [rsp+0E0h+SubAuthority2], rax; ReferencedDomainName
0x180034e11  call    cs:__imp_LookupAccountSidW
0x180034e17  mov     rcx, [rbp+57h+var_78]; Sid
0x180034e1b  call    cs:__imp_RtlFreeSid
0x180034e21  lea     rax, [rbp+57h+var_78]
0x180034e25  mov     r9d, 221h; SubAuthority1
0x180034e2b  mov     [rsp+0E0h+Sid], rax; Sid
0x180034e30  mov     r8d, esi; SubAuthority0
0x180034e33  mov     [rsp+0E0h+SubAuthority7], r15d; SubAuthority7
0x180034e38  mov     dl, 2; SubAuthorityCount
0x180034e3a  mov     [rsp+0E0h+SubAuthority6], r15d; SubAuthority6
0x180034e3f  mov     rcx, r14; IdentifierAuthority
0x180034e42  mov     [rsp+0E0h+SubAuthority5], r15d; SubAuthority5
0x180034e47  mov     [rsp+0E0h+SubAuthority4], r15d; SubAuthority4
0x180034e4c  mov     [rsp+0E0h+SubAuthority3], r15d; SubAuthority3
0x180034e51  mov     [rsp+0E0h+SubAuthority2], r15d; SubAuthority2
0x180034e56  call    cs:__imp_RtlAllocateAndInitializeSid
0x180034e5c  test    eax, eax
0x180034e5e  js      short loc_180034EA2
0x180034e60  mov     rdx, [rbp+57h+var_78]; Sid
0x180034e64  lea     rax, [rbp+57h+peUse]
0x180034e68  mov     qword ptr [rsp+0E0h+SubAuthority4], rax; peUse
0x180034e6d  lea     r9, [rbp+57h+cchName]; cchName
0x180034e71  lea     rax, [rbp+57h+cchReferencedDomainName]
0x180034e75  mov     [rbp+57h+cchName], ebx
0x180034e78  mov     qword ptr [rsp+0E0h+SubAuthority3], rax; cchReferencedDomainName
0x180034e7d  lea     r8, ?s_szUsersGroupName@CUserList@@0PAGA; Name
0x180034e84  lea     rax, [rbp+57h+ReferencedDomainName]
0x180034e88  mov     [rbp+57h+cchReferencedDomainName], edi
0x180034e8b  xor     ecx, ecx; lpSystemName
0x180034e8d  mov     qword ptr [rsp+0E0h+SubAuthority2], rax; ReferencedDomainName
0x180034e92  call    cs:__imp_LookupAccountSidW
0x180034e98  mov     rcx, [rbp+57h+var_78]; Sid
0x180034e9c  call    cs:__imp_RtlFreeSid
0x180034ea2  lea     rax, [rbp+57h+var_78]
0x180034ea6  mov     r9d, 222h; SubAuthority1
0x180034eac  mov     [rsp+0E0h+Sid], rax; Sid
0x180034eb1  mov     r8d, esi; SubAuthority0
0x180034eb4  mov     [rsp+0E0h+SubAuthority7], r15d; SubAuthority7
0x180034eb9  mov     dl, 2; SubAuthorityCount
0x180034ebb  mov     [rsp+0E0h+SubAuthority6], r15d; SubAuthority6
0x180034ec0  mov     rcx, r14; IdentifierAuthority
0x180034ec3  mov     [rsp+0E0h+SubAuthority5], r15d; SubAuthority5
0x180034ec8  mov     [rsp+0E0h+SubAuthority4], r15d; SubAuthority4
0x180034ecd  mov     [rsp+0E0h+SubAuthority3], r15d; SubAuthority3
0x180034ed2  mov     [rsp+0E0h+SubAuthority2], r15d; SubAuthority2
0x180034ed7  call    cs:__imp_RtlAllocateAndInitializeSid
0x180034edd  test    eax, eax
0x180034edf  js      short loc_180034F23
0x180034ee1  mov     rdx, [rbp+57h+var_78]; Sid
0x180034ee5  lea     rax, [rbp+57h+peUse]
0x180034ee9  mov     qword ptr [rsp+0E0h+SubAuthority4], rax; peUse
0x180034eee  lea     r9, [rbp+57h+cchName]; cchName
0x180034ef2  lea     rax, [rbp+57h+cchReferencedDomainName]
0x180034ef6  mov     [rbp+57h+cchName], ebx
0x180034ef9  mov     qword ptr [rsp+0E0h+SubAuthority3], rax; cchReferencedDomainName
0x180034efe  lea     r8, ?s_szGuestsGroupName@CUserList@@0PAGA; Name
0x180034f05  lea     rax, [rbp+57h+ReferencedDomainName]
0x180034f09  mov     [rbp+57h+cchReferencedDomainName], edi
0x180034f0c  xor     ecx, ecx; lpSystemName
0x180034f0e  mov     qword ptr [rsp+0E0h+SubAuthority2], rax; ReferencedDomainName
0x180034f13  call    cs:__imp_LookupAccountSidW
0x180034f19  mov     rcx, [rbp+57h+var_78]; Sid
0x180034f1d  call    cs:__imp_RtlFreeSid
0x180034f23  mov     cs:byte_1800A26AC, 1
0x180034f2a  mov     rcx, [rbp+57h+var_40]
0x180034f2e  xor     rcx, rsp; StackCookie
0x180034f31  call    __security_check_cookie
0x180034f36  add     rsp, 0B0h
0x180034f3d  pop     r15
0x180034f3f  pop     r14
0x180034f41  pop     r12
0x180034f43  pop     rdi
0x180034f44  pop     rsi
0x180034f45  pop     rbx
0x180034f46  pop     rbp
0x180034f47  retn
```
