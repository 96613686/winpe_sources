# SmpSetDumpSecurityAndAttributes

- ea: `0x140012930`
- end: `0x140012bb1`
- name: `SmpSetDumpSecurityAndAttributes`
- size: `641`
- prototype: `__int64 __fastcall(HANDLE FileHandle)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140011758`
- `0x1400127a8`

## callees

- `0x140012930`
- `0x14001cc40`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x140012b4c`
- `ntdll!RtlFreeHeap` at `0x140012b6d`
- `ntdll!RtlFreeHeap` at `0x140012b8e`
- `ntdll!RtlFreeHeap` at `0x140012b4c`
- `ntdll!RtlFreeHeap` at `0x140012b6d`
- `ntdll!RtlFreeHeap` at `0x140012b8e`
- `ntdll!NtSetInformationFile` at `0x140012b29`
- `ntdll!NtSetInformationFile` at `0x140012b29`
- `ntdll!NtQueryInformationFile` at `0x140012b01`
- `ntdll!NtQueryInformationFile` at `0x140012b01`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1400129ce`
- `ntdll!RtlAllocateAndInitializeSid` at `0x140012a0d`
- `ntdll!RtlAllocateAndInitializeSid` at `0x140012a4f`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1400129ce`
- `ntdll!RtlAllocateAndInitializeSid` at `0x140012a0d`
- `ntdll!RtlAllocateAndInitializeSid` at `0x140012a4f`
- `ntdll!RtlCreateSecurityDescriptor` at `0x140012a66`
- `ntdll!RtlCreateSecurityDescriptor` at `0x140012a66`
- `ntdll!RtlCreateAcl` at `0x140012a79`
- `ntdll!RtlCreateAcl` at `0x140012a79`
- `ntdll!RtlAddAccessAllowedAce` at `0x140012a93`
- `ntdll!RtlAddAccessAllowedAce` at `0x140012aa8`
- `ntdll!RtlAddAccessAllowedAce` at `0x140012a93`
- `ntdll!RtlAddAccessAllowedAce` at `0x140012aa8`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x140012abb`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x140012abb`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x140012acd`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x140012acd`
- `ntdll!NtSetSecurityObject` at `0x140012add`
- `ntdll!NtSetSecurityObject` at `0x140012add`

## pseudocode

```c
__int64 __fastcall SmpSetDumpSecurityAndAttributes(HANDLE FileHandle)
{
  NTSTATUS v2; // ebx
  PSID Owner; // [rsp+60h] [rbp-A0h] BYREF
  PSID Sid; // [rsp+68h] [rbp-98h] BYREF
  PSID BaseAddress; // [rsp+70h] [rbp-90h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+78h] [rbp-88h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v9; // [rsp+A8h] [rbp-58h]
  struct _SID_IDENTIFIER_AUTHORITY v10; // [rsp+B0h] [rbp-50h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+B8h] [rbp-48h] BYREF
  _OWORD FileInformation[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v13; // [rsp+E0h] [rbp-20h]
  struct _ACL Acl; // [rsp+F0h] [rbp-10h] BYREF

  *(_WORD *)&v10.Value[4] = 1280;
  *(_DWORD *)v10.Value = 0;
  v9 = 0;
  v13 = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 256;
  BaseAddress = 0;
  Sid = 0;
  Owner = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  IoStatusBlock = 0;
  memset(FileInformation, 0, sizeof(FileInformation));
  v2 = RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0, 0, 0, 0, 0, 0, 0, 0, &BaseAddress);
  if ( v2 >= 0 )
  {
    v2 = RtlAllocateAndInitializeSid(&v10, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &Sid);
    if ( v2 >= 0 )
    {
      v2 = RtlAllocateAndInitializeSid(&v10, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &Owner);
      if ( v2 >= 0 )
      {
        RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
        RtlCreateAcl(&Acl, 0x400u, 2u);
        RtlAddAccessAllowedAce(&Acl, 2u, 0x100D0000u, Owner);
        RtlAddAccessAllowedAce(&Acl, 2u, 0x100D0000u, Sid);
        RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, &Acl, 0);
        RtlSetOwnerSecurityDescriptor(SecurityDescriptor, Owner, 0);
        v2 = NtSetSecurityObject(FileHandle, 4u, SecurityDescriptor);
        if ( v2 >= 0 )
        {
          v2 = NtQueryInformationFile(FileHandle, &IoStatusBlock, FileInformation, 0x28u, FileBasicInformation);
          if ( v2 >= 0 )
          {
            LODWORD(v13) = v13 & 0xFFFFFFF9;
            v2 = NtSetInformationFile(FileHandle, &IoStatusBlock, FileInformation, 0x28u, FileBasicInformation);
          }
        }
      }
    }
  }
  if ( BaseAddress )
    RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, BaseAddress);
  if ( Sid )
    RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, Sid);
  if ( Owner )
    RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, Owner);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140012930  push    rbp
0x140012932  push    rbx
0x140012933  push    rsi
0x140012934  push    rdi
0x140012935  lea     rbp, [rsp-408h]
0x14001293d  sub     rsp, 508h
0x140012944  mov     rax, cs:__security_cookie
0x14001294b  xor     rax, rsp
0x14001294e  mov     [rbp+420h+var_30], rax
0x140012955  xor     esi, esi
0x140012957  mov     word ptr [rbp+420h+var_470.Value+4], 500h
0x14001295d  xor     eax, eax
0x14001295f  mov     dword ptr [rbp+420h+var_470.Value], esi
0x140012962  xorps   xmm0, xmm0
0x140012965  mov     [rbp+420h+var_478], rax
0x140012969  xorps   xmm1, xmm1
0x14001296c  mov     [rbp+420h+var_440], rax
0x140012970  lea     rax, [rsp+520h+BaseAddress]
0x140012975  mov     dword ptr [rbp+420h+IdentifierAuthority.Value], esi
0x140012978  mov     [rsp+520h+Sid], rax; Sid
0x14001297d  mov     rdi, rcx
0x140012980  mov     [rsp+520h+SubAuthority7], esi; SubAuthority7
0x140012984  lea     rcx, [rbp+420h+IdentifierAuthority]; IdentifierAuthority
0x140012988  mov     [rsp+520h+SubAuthority6], esi; SubAuthority6
0x14001298c  xor     r9d, r9d; SubAuthority1
0x14001298f  mov     [rsp+520h+SubAuthority5], esi; SubAuthority5
0x140012993  xor     r8d, r8d; SubAuthority0
0x140012996  mov     [rsp+520h+SubAuthority4], esi; SubAuthority4
0x14001299a  mov     dl, 1; SubAuthorityCount
0x14001299c  mov     [rsp+520h+SubAuthority3], esi; SubAuthority3
0x1400129a0  mov     [rsp+520h+SubAuthority2], esi; SubAuthority2
0x1400129a4  mov     word ptr [rbp+420h+IdentifierAuthority.Value+4], 100h
0x1400129aa  mov     [rsp+520h+BaseAddress], rsi
0x1400129af  mov     [rsp+520h+var_4B8], rsi
0x1400129b4  mov     [rsp+520h+Owner], rsi
0x1400129b9  movups  [rbp+420h+SecurityDescriptor], xmm0
0x1400129bd  movups  [rbp+420h+var_488], xmm0
0x1400129c1  movups  xmmword ptr [rsp+520h+IoStatusBlock], xmm0
0x1400129c6  movups  [rbp+420h+FileInformation], xmm1
0x1400129ca  movups  [rbp+420h+var_450], xmm1
0x1400129ce  call    cs:__imp_RtlAllocateAndInitializeSid
0x1400129d4  mov     ebx, eax
0x1400129d6  test    eax, eax
0x1400129d8  js      loc_140012B31
0x1400129de  lea     rax, [rsp+520h+var_4B8]
0x1400129e3  xor     r9d, r9d; SubAuthority1
0x1400129e6  mov     [rsp+520h+Sid], rax; Sid
0x1400129eb  lea     r8d, [rsi+12h]; SubAuthority0
0x1400129ef  mov     [rsp+520h+SubAuthority7], esi; SubAuthority7
0x1400129f3  lea     rcx, [rbp+420h+var_470]; IdentifierAuthority
0x1400129f7  mov     [rsp+520h+SubAuthority6], esi; SubAuthority6
0x1400129fb  mov     dl, 1; SubAuthorityCount
0x1400129fd  mov     [rsp+520h+SubAuthority5], esi; SubAuthority5
0x140012a01  mov     [rsp+520h+SubAuthority4], esi; SubAuthority4
0x140012a05  mov     [rsp+520h+SubAuthority3], esi; SubAuthority3
0x140012a09  mov     [rsp+520h+SubAuthority2], esi; SubAuthority2
0x140012a0d  call    cs:__imp_RtlAllocateAndInitializeSid
0x140012a13  mov     ebx, eax
0x140012a15  test    eax, eax
0x140012a17  js      loc_140012B31
0x140012a1d  lea     rax, [rsp+520h+Owner]
0x140012a22  mov     r9d, 220h; SubAuthority1
0x140012a28  mov     [rsp+520h+Sid], rax; Sid
0x140012a2d  lea     r8d, [rsi+20h]; SubAuthority0
0x140012a31  mov     [rsp+520h+SubAuthority7], esi; SubAuthority7
0x140012a35  lea     rcx, [rbp+420h+var_470]; IdentifierAuthority
0x140012a39  mov     [rsp+520h+SubAuthority6], esi; SubAuthority6
0x140012a3d  mov     dl, 2; SubAuthorityCount
0x140012a3f  mov     [rsp+520h+SubAuthority5], esi; SubAuthority5
0x140012a43  mov     [rsp+520h+SubAuthority4], esi; SubAuthority4
0x140012a47  mov     [rsp+520h+SubAuthority3], esi; SubAuthority3
0x140012a4b  mov     [rsp+520h+SubAuthority2], esi; SubAuthority2
0x140012a4f  call    cs:__imp_RtlAllocateAndInitializeSid
0x140012a55  mov     ebx, eax
0x140012a57  test    eax, eax
0x140012a59  js      loc_140012B31
0x140012a5f  lea     edx, [rsi+1]; Revision
0x140012a62  lea     rcx, [rbp+420h+SecurityDescriptor]; SecurityDescriptor
0x140012a66  call    cs:__imp_RtlCreateSecurityDescriptor
0x140012a6c  mov     edx, 400h; AclLength
0x140012a71  lea     r8d, [rsi+2]; AclRevision
0x140012a75  lea     rcx, [rbp+420h+Acl]; Acl
0x140012a79  call    cs:__imp_RtlCreateAcl
0x140012a7f  mov     r9, [rsp+520h+Owner]; Sid
0x140012a84  lea     edx, [rsi+2]; AceRevision
0x140012a87  mov     ebx, 100D0000h
0x140012a8c  lea     rcx, [rbp+420h+Acl]; Acl
0x140012a90  mov     r8d, ebx; AccessMask
0x140012a93  call    cs:__imp_RtlAddAccessAllowedAce
0x140012a99  mov     r9, [rsp+520h+var_4B8]; Sid
0x140012a9e  lea     edx, [rsi+2]; AceRevision
0x140012aa1  mov     r8d, ebx; AccessMask
0x140012aa4  lea     rcx, [rbp+420h+Acl]; Acl
0x140012aa8  call    cs:__imp_RtlAddAccessAllowedAce
0x140012aae  xor     r9d, r9d; DaclDefaulted
0x140012ab1  lea     r8, [rbp+420h+Acl]; Dacl
0x140012ab5  mov     dl, 1; DaclPresent
0x140012ab7  lea     rcx, [rbp+420h+SecurityDescriptor]; SecurityDescriptor
0x140012abb  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x140012ac1  mov     rdx, [rsp+520h+Owner]; Owner
0x140012ac6  lea     rcx, [rbp+420h+SecurityDescriptor]; SecurityDescriptor
0x140012aca  xor     r8d, r8d; OwnerDefaulted
0x140012acd  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x140012ad3  lea     r8, [rbp+420h+SecurityDescriptor]; SecurityDescriptor
0x140012ad7  mov     rcx, rdi; Handle
0x140012ada  lea     edx, [rsi+4]; SecurityInformation
0x140012add  call    cs:__imp_NtSetSecurityObject
0x140012ae3  mov     ebx, eax
0x140012ae5  test    eax, eax
0x140012ae7  js      short loc_140012B31
0x140012ae9  lea     r9d, [rsi+28h]; Length
0x140012aed  mov     [rsp+520h+SubAuthority2], 4; FileInformationClass
0x140012af5  lea     r8, [rbp+420h+FileInformation]; FileInformation
0x140012af9  mov     rcx, rdi; FileHandle
0x140012afc  lea     rdx, [rsp+520h+IoStatusBlock]; IoStatusBlock
0x140012b01  call    cs:__imp_NtQueryInformationFile
0x140012b07  mov     ebx, eax
0x140012b09  test    eax, eax
0x140012b0b  js      short loc_140012B31
0x140012b0d  and     dword ptr [rbp+420h+var_440], 0FFFFFFF9h
0x140012b11  lea     r9d, [rsi+28h]; Length
0x140012b15  lea     r8, [rbp+420h+FileInformation]; FileInformation
0x140012b19  mov     [rsp+520h+SubAuthority2], 4; FileInformationClass
0x140012b21  lea     rdx, [rsp+520h+IoStatusBlock]; IoStatusBlock
0x140012b26  mov     rcx, rdi; FileHandle
0x140012b29  call    cs:__imp_NtSetInformationFile
0x140012b2f  mov     ebx, eax
0x140012b31  cmp     [rsp+520h+BaseAddress], rsi
0x140012b36  jz      short loc_140012B52
0x140012b38  mov     rcx, gs:60h
0x140012b41  xor     edx, edx; Flags
0x140012b43  mov     r8, [rsp+520h+BaseAddress]; BaseAddress
0x140012b48  mov     rcx, [rcx+30h]; HeapHandle
0x140012b4c  call    cs:__imp_RtlFreeHeap
0x140012b52  cmp     [rsp+520h+var_4B8], rsi
0x140012b57  jz      short loc_140012B73
0x140012b59  mov     rcx, gs:60h
0x140012b62  xor     edx, edx; Flags
0x140012b64  mov     r8, [rsp+520h+var_4B8]; BaseAddress
0x140012b69  mov     rcx, [rcx+30h]; HeapHandle
0x140012b6d  call    cs:__imp_RtlFreeHeap
0x140012b73  cmp     [rsp+520h+Owner], rsi
0x140012b78  jz      short loc_140012B94
0x140012b7a  mov     rcx, gs:60h
0x140012b83  xor     edx, edx; Flags
0x140012b85  mov     r8, [rsp+520h+Owner]; BaseAddress
0x140012b8a  mov     rcx, [rcx+30h]; HeapHandle
0x140012b8e  call    cs:__imp_RtlFreeHeap
0x140012b94  mov     eax, ebx
0x140012b96  mov     rcx, [rbp+420h+var_30]
0x140012b9d  xor     rcx, rsp; StackCookie
0x140012ba0  call    __security_check_cookie
0x140012ba5  add     rsp, 508h
0x140012bac  pop     rdi
0x140012bad  pop     rsi
0x140012bae  pop     rbx
0x140012baf  pop     rbp
0x140012bb0  retn
```
