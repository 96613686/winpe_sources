# SmpInitializePendingRename

- ea: `0x14000e080`
- end: `0x14000e2df`
- name: `SmpInitializePendingRename`
- size: `607`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1400146ac`

## callees

- `0x14000e080`
- `0x14001cc40`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x14000e243`
- `ntdll!RtlInitUnicodeString` at `0x14000e243`
- `ntdll!NtClose` at `0x14000e28f`
- `ntdll!NtClose` at `0x14000e28f`
- `ntdll!RtlAllocateHeap` at `0x14000e19b`
- `ntdll!RtlAllocateHeap` at `0x14000e19b`
- `ntdll!RtlFreeHeap` at `0x14000e2a9`
- `ntdll!RtlFreeHeap` at `0x14000e2a9`
- `ntdll!RtlAllocateAndInitializeSid` at `0x14000e112`
- `ntdll!RtlAllocateAndInitializeSid` at `0x14000e15a`
- `ntdll!RtlAllocateAndInitializeSid` at `0x14000e112`
- `ntdll!RtlAllocateAndInitializeSid` at `0x14000e15a`
- `ntdll!RtlCreateSecurityDescriptor` at `0x14000e1b6`
- `ntdll!RtlCreateSecurityDescriptor` at `0x14000e1b6`
- `ntdll!RtlCreateAcl` at `0x14000e1d1`
- `ntdll!RtlCreateAcl` at `0x14000e1d1`
- `ntdll!RtlAddAccessAllowedAce` at `0x14000e1f5`
- `ntdll!RtlAddAccessAllowedAce` at `0x14000e214`
- `ntdll!RtlAddAccessAllowedAce` at `0x14000e1f5`
- `ntdll!RtlAddAccessAllowedAce` at `0x14000e214`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x14000e22c`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x14000e22c`
- `ntdll!RtlFreeSid` at `0x14000e2b3`
- `ntdll!RtlFreeSid` at `0x14000e2bd`
- `ntdll!RtlFreeSid` at `0x14000e2b3`
- `ntdll!RtlFreeSid` at `0x14000e2bd`
- `ntdll!RtlLengthSid` at `0x14000e16e`
- `ntdll!RtlLengthSid` at `0x14000e17a`
- `ntdll!RtlLengthSid` at `0x14000e16e`
- `ntdll!RtlLengthSid` at `0x14000e17a`
- `ntdll!NtCreateMutant` at `0x14000e27f`
- `ntdll!NtCreateMutant` at `0x14000e27f`

## string_xrefs

- `0x14000e238`: `\PendingRenameMutex`

## pseudocode

```c
__int64 SmpInitializePendingRename()
{
  NTSTATUS Acl; // edi
  ULONG v2; // ebx
  ULONG v3; // esi
  struct _ACL *Heap; // rbx
  PSID v5; // [rsp+60h] [rbp-59h] BYREF
  PSID Sid; // [rsp+68h] [rbp-51h] BYREF
  void *MutantHandle; // [rsp+70h] [rbp-49h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-41h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+A8h] [rbp-11h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+B8h] [rbp-1h] BYREF
  __int64 v11; // [rsp+D8h] [rbp+1Fh]
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+E0h] [rbp+27h] BYREF

  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  MutantHandle = 0;
  v5 = 0;
  v11 = 0;
  Sid = 0;
  memset(&ObjectAttributes, 0, 44);
  *(_DWORD *)IdentifierAuthority.Value = 0;
  DestinationString = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  if ( RtlAllocateAndInitializeSid(&IdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &Sid) < 0 )
    return 3221225626LL;
  Acl = RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &v5);
  if ( Acl >= 0 )
  {
    v2 = RtlLengthSid(Sid);
    v3 = v2 + RtlLengthSid(v5) + 32;
    Heap = (struct _ACL *)RtlAllocateHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), SmBaseTag, v3);
    if ( Heap )
    {
      Acl = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
      if ( Acl >= 0 )
      {
        Acl = RtlCreateAcl(Heap, v3, 2u);
        if ( Acl >= 0 )
        {
          Acl = RtlAddAccessAllowedAce(Heap, 2u, 0x120001u, Sid);
          if ( Acl >= 0 )
          {
            Acl = RtlAddAccessAllowedAce(Heap, 2u, 0x120001u, v5);
            if ( Acl >= 0 )
            {
              Acl = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, Heap, 0);
              if ( Acl >= 0 )
              {
                RtlInitUnicodeString(&DestinationString, L"\\PendingRenameMutex");
                ObjectAttributes.Length = 48;
                ObjectAttributes.ObjectName = &DestinationString;
                ObjectAttributes.RootDirectory = 0;
                ObjectAttributes.SecurityDescriptor = SecurityDescriptor;
                ObjectAttributes.Attributes = 80;
                ObjectAttributes.SecurityQualityOfService = 0;
                Acl = NtCreateMutant(&MutantHandle, 0x1F0001u, &ObjectAttributes, 0);
                if ( Acl >= 0 )
                  Acl = NtClose(MutantHandle);
              }
            }
          }
        }
      }
      RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, Heap);
    }
    RtlFreeSid(v5);
  }
  RtlFreeSid(Sid);
  return (unsigned int)Acl;
}

```

## disassembly

```asm
0x14000e080  push    rbp
0x14000e082  push    rbx
0x14000e083  push    rsi
0x14000e084  push    rdi
0x14000e085  push    r14
0x14000e087  lea     rbp, [rsp-37h]
0x14000e08c  sub     rsp, 0F0h
0x14000e093  mov     rax, cs:__security_cookie
0x14000e09a  xor     rax, rsp
0x14000e09d  mov     [rbp+57h+var_28], rax
0x14000e0a1  xor     r14d, r14d
0x14000e0a4  mov     word ptr [rbp+57h+IdentifierAuthority.Value+4], 500h
0x14000e0aa  xorps   xmm0, xmm0
0x14000e0ad  mov     [rbp+57h+MutantHandle], r14
0x14000e0b1  xor     eax, eax
0x14000e0b3  mov     [rbp+57h+var_B0], r14
0x14000e0b7  mov     [rbp+57h+var_38], rax
0x14000e0bb  lea     rcx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x14000e0bf  lea     rax, [rbp+57h+var_A8]
0x14000e0c3  mov     [rbp+57h+var_A8], r14
0x14000e0c7  mov     [rsp+110h+Sid], rax; Sid
0x14000e0cc  lea     r8d, [r14+20h]; SubAuthority0
0x14000e0d0  mov     [rsp+110h+SubAuthority7], r14d; SubAuthority7
0x14000e0d5  mov     r9d, 220h; SubAuthority1
0x14000e0db  mov     [rsp+110h+SubAuthority6], r14d; SubAuthority6
0x14000e0e0  mov     dl, 2; SubAuthorityCount
0x14000e0e2  mov     [rsp+110h+SubAuthority5], r14d; SubAuthority5
0x14000e0e7  mov     [rsp+110h+SubAuthority4], r14d; SubAuthority4
0x14000e0ec  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x14000e0f0  mov     [rsp+110h+SubAuthority3], r14d; SubAuthority3
0x14000e0f5  mov     [rsp+110h+SubAuthority2], r14d; SubAuthority2
0x14000e0fa  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x14000e0fe  mov     dword ptr [rbp+57h+IdentifierAuthority.Value], r14d
0x14000e102  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x14000e106  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14000e10a  movups  [rbp+57h+SecurityDescriptor], xmm0
0x14000e10e  movups  [rbp+57h+var_48], xmm0
0x14000e112  call    cs:__imp_RtlAllocateAndInitializeSid
0x14000e118  test    eax, eax
0x14000e11a  jns     short loc_14000E126
0x14000e11c  mov     eax, 0C000009Ah
0x14000e121  jmp     loc_14000E2C5
0x14000e126  lea     rax, [rbp+57h+var_B0]
0x14000e12a  xor     r9d, r9d; SubAuthority1
0x14000e12d  mov     [rsp+110h+Sid], rax; Sid
0x14000e132  lea     rcx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x14000e136  mov     [rsp+110h+SubAuthority7], r14d; SubAuthority7
0x14000e13b  mov     dl, 1; SubAuthorityCount
0x14000e13d  mov     [rsp+110h+SubAuthority6], r14d; SubAuthority6
0x14000e142  mov     [rsp+110h+SubAuthority5], r14d; SubAuthority5
0x14000e147  lea     r8d, [r9+12h]; SubAuthority0
0x14000e14b  mov     [rsp+110h+SubAuthority4], r14d; SubAuthority4
0x14000e150  mov     [rsp+110h+SubAuthority3], r14d; SubAuthority3
0x14000e155  mov     [rsp+110h+SubAuthority2], r14d; SubAuthority2
0x14000e15a  call    cs:__imp_RtlAllocateAndInitializeSid
0x14000e160  mov     edi, eax
0x14000e162  test    eax, eax
0x14000e164  js      loc_14000E2B9
0x14000e16a  mov     rcx, [rbp+57h+var_A8]; Sid
0x14000e16e  call    cs:__imp_RtlLengthSid
0x14000e174  mov     rcx, [rbp+57h+var_B0]; Sid
0x14000e178  mov     ebx, eax
0x14000e17a  call    cs:__imp_RtlLengthSid
0x14000e180  mov     rcx, gs:60h
0x14000e189  mov     edx, cs:SmBaseTag; Flags
0x14000e18f  lea     esi, [rax+20h]
0x14000e192  mov     rcx, [rcx+30h]; HeapHandle
0x14000e196  add     esi, ebx
0x14000e198  mov     r8d, esi; Size
0x14000e19b  call    cs:__imp_RtlAllocateHeap
0x14000e1a1  mov     rbx, rax
0x14000e1a4  test    rax, rax
0x14000e1a7  jz      loc_14000E2AF
0x14000e1ad  mov     edx, 1; Revision
0x14000e1b2  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x14000e1b6  call    cs:__imp_RtlCreateSecurityDescriptor
0x14000e1bc  mov     edi, eax
0x14000e1be  test    eax, eax
0x14000e1c0  js      loc_14000E297
0x14000e1c6  mov     r8d, 2; AclRevision
0x14000e1cc  mov     edx, esi; AclLength
0x14000e1ce  mov     rcx, rbx; Acl
0x14000e1d1  call    cs:__imp_RtlCreateAcl
0x14000e1d7  mov     edi, eax
0x14000e1d9  test    eax, eax
0x14000e1db  js      loc_14000E297
0x14000e1e1  mov     r9, [rbp+57h+var_A8]; Sid
0x14000e1e5  mov     esi, 120001h
0x14000e1ea  mov     r8d, esi; AccessMask
0x14000e1ed  mov     edx, 2; AceRevision
0x14000e1f2  mov     rcx, rbx; Acl
0x14000e1f5  call    cs:__imp_RtlAddAccessAllowedAce
0x14000e1fb  mov     edi, eax
0x14000e1fd  test    eax, eax
0x14000e1ff  js      loc_14000E297
0x14000e205  mov     r9, [rbp+57h+var_B0]; Sid
0x14000e209  mov     r8d, esi; AccessMask
0x14000e20c  mov     edx, 2; AceRevision
0x14000e211  mov     rcx, rbx; Acl
0x14000e214  call    cs:__imp_RtlAddAccessAllowedAce
0x14000e21a  mov     edi, eax
0x14000e21c  test    eax, eax
0x14000e21e  js      short loc_14000E297
0x14000e220  xor     r9d, r9d; DaclDefaulted
0x14000e223  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x14000e227  mov     r8, rbx; Dacl
0x14000e22a  mov     dl, 1; DaclPresent
0x14000e22c  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x14000e232  mov     edi, eax
0x14000e234  test    eax, eax
0x14000e236  js      short loc_14000E297
0x14000e238  lea     rdx, aPendingrenamem; "\\PendingRenameMutex"
0x14000e23f  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14000e243  call    cs:__imp_RtlInitUnicodeString
0x14000e249  lea     rax, [rbp+57h+DestinationString]
0x14000e24d  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14000e254  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14000e258  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14000e25c  lea     rax, [rbp+57h+SecurityDescriptor]
0x14000e260  mov     [rbp+57h+ObjectAttributes.RootDirectory], r14
0x14000e264  xor     r9d, r9d; InitialOwner
0x14000e267  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], rax
0x14000e26b  mov     edx, 1F0001h; DesiredAccess
0x14000e270  mov     [rbp+57h+ObjectAttributes.Attributes], 50h ; 'P'
0x14000e277  lea     rcx, [rbp+57h+MutantHandle]; MutantHandle
0x14000e27b  mov     [rbp+57h+ObjectAttributes.SecurityQualityOfService], r14
0x14000e27f  call    cs:__imp_NtCreateMutant
0x14000e285  mov     edi, eax
0x14000e287  test    eax, eax
0x14000e289  js      short loc_14000E297
0x14000e28b  mov     rcx, [rbp+57h+MutantHandle]; Handle
0x14000e28f  call    cs:__imp_NtClose
0x14000e295  mov     edi, eax
0x14000e297  mov     rcx, gs:60h
0x14000e2a0  mov     r8, rbx; BaseAddress
0x14000e2a3  xor     edx, edx; Flags
0x14000e2a5  mov     rcx, [rcx+30h]; HeapHandle
0x14000e2a9  call    cs:__imp_RtlFreeHeap
0x14000e2af  mov     rcx, [rbp+57h+var_B0]; Sid
0x14000e2b3  call    cs:__imp_RtlFreeSid
0x14000e2b9  mov     rcx, [rbp+57h+var_A8]; Sid
0x14000e2bd  call    cs:__imp_RtlFreeSid
0x14000e2c3  mov     eax, edi
0x14000e2c5  mov     rcx, [rbp+57h+var_28]
0x14000e2c9  xor     rcx, rsp; StackCookie
0x14000e2cc  call    __security_check_cookie
0x14000e2d1  add     rsp, 0F0h
0x14000e2d8  pop     r14
0x14000e2da  pop     rdi
0x14000e2db  pop     rsi
0x14000e2dc  pop     rbx
0x14000e2dd  pop     rbp
0x14000e2de  retn
```
