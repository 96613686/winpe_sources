# SetUserIntegrityLabel(void *,_MANDATORY_LEVEL)

- ea: `0x140038b60`
- end: `0x140038cf3`
- name: `?SetUserIntegrityLabel@@YAKPEAXW4_MANDATORY_LEVEL@@@Z`
- size: `403`
- prototype: `unsigned int __fastcall(HANDLE hObj, enum _MANDATORY_LEVEL)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400957a4`

## callees

- `0x1400057f4`
- `0x140038b60`
- `0x140053720`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140038c7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140038c7a`
- `ntdll!RtlFreeSid` at `0x140038ceb`
- `ntdll!RtlFreeSid` at `0x140038ceb`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x140038c5c`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x140038c5c`
- `ntdll!RtlAddMandatoryAce` at `0x140038c44`
- `ntdll!RtlAddMandatoryAce` at `0x140038c44`
- `ntdll!RtlCreateAcl` at `0x140038c1c`
- `ntdll!RtlCreateAcl` at `0x140038c1c`
- `ntdll!RtlCreateSecurityDescriptor` at `0x140038c03`
- `ntdll!RtlCreateSecurityDescriptor` at `0x140038c03`
- `ntdll!RtlAllocateAndInitializeSid` at `0x140038bf3`
- `ntdll!RtlAllocateAndInitializeSid` at `0x140038bf3`
- `ext-ms-win-rtcore-ntuser-usersecurity-l1-1-0!SetUserObjectSecurity` at `0x140038c70`
- `ext-ms-win-rtcore-ntuser-usersecurity-l1-1-0!SetUserObjectSecurity` at `0x140038c70`

## pseudocode

```c
__int64 __fastcall SetUserIntegrityLabel(HANDLE hObj, enum _MANDATORY_LEVEL a2)
{
  DWORD LastError; // edi
  PSID SubAuthority3; // [rsp+28h] [rbp-100h]
  DWORD pSIRequested; // [rsp+60h] [rbp-C8h] BYREF
  PSID Sid; // [rsp+68h] [rbp-C0h] BYREF
  DWORD v8; // [rsp+70h] [rbp-B8h]
  _OWORD SecurityDescriptor[2]; // [rsp+78h] [rbp-B0h] BYREF
  __int64 v10; // [rsp+98h] [rbp-90h]
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+A0h] [rbp-88h] BYREF
  struct _ACL Acl; // [rsp+B0h] [rbp-78h] BYREF

  pSIRequested = 16;
  LastError = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  v10 = 0;
  Sid = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 4096;
  RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0x1000u, 0, 0, 0, 0, 0, 0, 0, &Sid);
  RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
  RtlCreateAcl(&Acl, 0x58u, 2u);
  LODWORD(SubAuthority3) = 1;
  RtlAddMandatoryAce(&Acl, 2u, 0, (ULONG)Sid, 0x11u, SubAuthority3);
  RtlSetSaclSecurityDescriptor(SecurityDescriptor, 1u, &Acl, 0);
  if ( !SetUserObjectSecurity(hObj, &pSIRequested, SecurityDescriptor) )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_ee043302f2783e8bc46ba484c6240be2_Traceguids, LastError);
    }
  }
  if ( Sid )
    RtlFreeSid(Sid);
  return LastError;
}

```

## disassembly

```asm
0x140038b60  mov     [rsp+arg_8], rbx
0x140038b65  push    rdi
0x140038b66  sub     rsp, 120h
0x140038b6d  mov     rax, cs:__security_cookie
0x140038b74  xor     rax, rsp
0x140038b77  mov     [rsp+128h+var_18], rax
0x140038b7f  mov     rbx, rcx
0x140038b82  mov     [rsp+128h+pSIRequested], 10h
0x140038b8a  xor     ecx, ecx
0x140038b8c  mov     edi, ecx
0x140038b8e  xorps   xmm0, xmm0
0x140038b91  xor     eax, eax
0x140038b93  movups  [rsp+128h+SecurityDescriptor], xmm0
0x140038b98  movups  [rsp+128h+var_A0], xmm0
0x140038ba0  mov     [rsp+128h+var_90], rax
0x140038ba8  mov     [rsp+128h+var_C0], rcx
0x140038bad  mov     dword ptr [rsp+128h+IdentifierAuthority.Value], eax
0x140038bb4  mov     word ptr [rsp+128h+IdentifierAuthority.Value+4], 1000h
0x140038bbe  lea     rax, [rsp+128h+var_C0]
0x140038bc3  mov     [rsp+128h+Sid], rax; Sid
0x140038bc8  mov     [rsp+128h+SubAuthority7], ecx; SubAuthority7
0x140038bcc  mov     [rsp+128h+SubAuthority6], ecx; SubAuthority6
0x140038bd0  mov     [rsp+128h+SubAuthority5], ecx; SubAuthority5
0x140038bd4  mov     [rsp+128h+SubAuthority4], ecx; SubAuthority4
0x140038bd8  mov     dword ptr [rsp+128h+SubAuthority3], ecx; SubAuthority3
0x140038bdc  mov     [rsp+128h+SubAuthority2], ecx; SubAuthority2
0x140038be0  xor     r9d, r9d; SubAuthority1
0x140038be3  mov     r8d, 1000h; SubAuthority0
0x140038be9  mov     dl, 1; SubAuthorityCount
0x140038beb  lea     rcx, [rsp+128h+IdentifierAuthority]; IdentifierAuthority
0x140038bf3  call    cs:__imp_RtlAllocateAndInitializeSid
0x140038bf9  mov     edx, 1; Revision
0x140038bfe  lea     rcx, [rsp+128h+SecurityDescriptor]; SecurityDescriptor
0x140038c03  call    cs:__imp_RtlCreateSecurityDescriptor
0x140038c09  mov     edx, 58h ; 'X'; AclSize
0x140038c0e  mov     r8d, 2; AclRevision
0x140038c14  lea     rcx, [rsp+128h+Acl]; Acl
0x140038c1c  call    cs:__imp_RtlCreateAcl
0x140038c22  mov     dword ptr [rsp+128h+SubAuthority3], 1; LabelSid
0x140038c2a  mov     byte ptr [rsp+128h+SubAuthority2], 11h; AceType
0x140038c2f  mov     r9, [rsp+128h+var_C0]; MandatoryFlags
0x140038c34  xor     r8d, r8d; Flags
0x140038c37  mov     edx, 2; Revision
0x140038c3c  lea     rcx, [rsp+128h+Acl]; Acl
0x140038c44  call    cs:__imp_RtlAddMandatoryAce
0x140038c4a  xor     r9d, r9d; SaclDefaulted
0x140038c4d  lea     r8, [rsp+128h+Acl]; Sacl
0x140038c55  mov     dl, 1; SaclPresent
0x140038c57  lea     rcx, [rsp+128h+SecurityDescriptor]; SecurityDescriptor
0x140038c5c  call    cs:__imp_RtlSetSaclSecurityDescriptor
0x140038c62  nop
0x140038c63  lea     r8, [rsp+128h+SecurityDescriptor]; pSID
0x140038c68  lea     rdx, [rsp+128h+pSIRequested]; pSIRequested
0x140038c6d  mov     rcx, rbx; hObj
0x140038c70  call    cs:__imp_SetUserObjectSecurity
0x140038c76  test    eax, eax
0x140038c78  jnz     short loc_140038CBE
0x140038c7a  call    cs:__imp_GetLastError
0x140038c80  mov     edi, eax
0x140038c82  mov     [rsp+128h+var_B8], eax
0x140038c86  lea     rax, WPP_GLOBAL_Control
0x140038c8d  mov     rcx, cs:WPP_GLOBAL_Control
0x140038c94  cmp     rcx, rax
0x140038c97  jz      short loc_140038CBE
0x140038c99  test    byte ptr [rcx+1Ch], 4
0x140038c9d  jz      short loc_140038CBE
0x140038c9f  cmp     byte ptr [rcx+19h], 2
0x140038ca3  jb      short loc_140038CBE
0x140038ca5  mov     edx, 1Bh
0x140038caa  mov     r9d, edi
0x140038cad  lea     r8, WPP_ee043302f2783e8bc46ba484c6240be2_Traceguids
0x140038cb4  mov     rcx, [rcx+10h]
0x140038cb8  call    WPP_SF_d
0x140038cbd  nop
0x140038cbe  mov     rcx, [rsp+128h+var_C0]; Sid
0x140038cc3  test    rcx, rcx
0x140038cc6  jnz     short loc_140038CEB
0x140038cc8  mov     eax, edi
0x140038cca  mov     rcx, [rsp+128h+var_18]
0x140038cd2  xor     rcx, rsp; StackCookie
0x140038cd5  call    __security_check_cookie
0x140038cda  mov     rbx, [rsp+128h+arg_8]
0x140038ce2  add     rsp, 120h
0x140038ce9  pop     rdi
0x140038cea  retn
0x140038ceb  call    cs:__imp_RtlFreeSid
0x140038cf1  jmp     short loc_140038CC8
0x14009e590  push    rbp
0x14009e592  sub     rsp, 60h
0x14009e596  mov     rbp, rdx
0x14009e599  add     rsp, 60h
0x14009e59d  pop     rbp
0x14009e59e  retn
```
