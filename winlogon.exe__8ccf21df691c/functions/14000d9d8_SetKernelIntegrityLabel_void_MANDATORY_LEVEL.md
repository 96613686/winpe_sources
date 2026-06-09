# SetKernelIntegrityLabel(void *,_MANDATORY_LEVEL)

- ea: `0x14000d9d8`
- end: `0x14000db19`
- name: `?SetKernelIntegrityLabel@@YAJPEAXW4_MANDATORY_LEVEL@@@Z`
- size: `321`
- prototype: `__int64 __fastcall(HANDLE Handle, enum _MANDATORY_LEVEL)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14000cb50`

## callees

- `0x14000d9d8`
- `0x140053720`

## import_xrefs

- `ntdll!RtlFreeSid` at `0x14000daef`
- `ntdll!RtlFreeSid` at `0x14000daef`
- `ntdll!NtSetSecurityObject` at `0x14000dadd`
- `ntdll!NtSetSecurityObject` at `0x14000dadd`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x14000daca`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x14000daca`
- `ntdll!RtlAddMandatoryAce` at `0x14000dab2`
- `ntdll!RtlAddMandatoryAce` at `0x14000dab2`
- `ntdll!RtlCreateAcl` at `0x14000da8b`
- `ntdll!RtlCreateAcl` at `0x14000da8b`
- `ntdll!RtlCreateSecurityDescriptor` at `0x14000da75`
- `ntdll!RtlCreateSecurityDescriptor` at `0x14000da75`
- `ntdll!RtlAllocateAndInitializeSid` at `0x14000da66`
- `ntdll!RtlAllocateAndInitializeSid` at `0x14000da66`

## pseudocode

```c
__int64 __fastcall SetKernelIntegrityLabel(HANDLE Handle, enum _MANDATORY_LEVEL a2)
{
  unsigned int v3; // ebx
  PSID SubAuthority3; // [rsp+28h] [rbp-F0h]
  PSID Sid; // [rsp+60h] [rbp-B8h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+68h] [rbp-B0h] BYREF
  __int64 v8; // [rsp+88h] [rbp-90h]
  struct _SID_IDENTIFIER_AUTHORITY v9; // [rsp+90h] [rbp-88h] BYREF
  struct _ACL Acl; // [rsp+A0h] [rbp-78h] BYREF

  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  v8 = 0;
  Sid = 0;
  *(_DWORD *)v9.Value = 0;
  *(_WORD *)&v9.Value[4] = 4096;
  RtlAllocateAndInitializeSid(&v9, 1u, 0x1000u, 0, 0, 0, 0, 0, 0, 0, &Sid);
  RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
  RtlCreateAcl(&Acl, 0x58u, 2u);
  LODWORD(SubAuthority3) = 1;
  RtlAddMandatoryAce(&Acl, 2u, 0, (ULONG)Sid, 0x11u, SubAuthority3);
  RtlSetSaclSecurityDescriptor(SecurityDescriptor, 1u, &Acl, 0);
  v3 = NtSetSecurityObject(Handle, 0x10u, SecurityDescriptor);
  if ( Sid )
    RtlFreeSid(Sid);
  return v3;
}

```

## disassembly

```asm
0x14000d9d8  mov     r11, rsp
0x14000d9db  mov     [r11+10h], rbx
0x14000d9df  push    r14
0x14000d9e1  sub     rsp, 110h
0x14000d9e8  mov     rax, cs:__security_cookie
0x14000d9ef  xor     rax, rsp
0x14000d9f2  mov     [rsp+118h+var_18], rax
0x14000d9fa  mov     rbx, rcx
0x14000d9fd  xorps   xmm0, xmm0
0x14000da00  xor     eax, eax
0x14000da02  movups  [rsp+118h+SecurityDescriptor], xmm0
0x14000da07  movups  [rsp+118h+var_A0], xmm0
0x14000da0c  mov     [r11-90h], rax
0x14000da13  xor     r14d, r14d
0x14000da16  mov     [rsp+118h+var_B8], r14
0x14000da1b  mov     [r11-88h], r14d
0x14000da22  mov     [rsp+118h+var_84], 1000h
0x14000da2c  lea     rax, [rsp+118h+var_B8]
0x14000da31  mov     [rsp+118h+Sid], rax; Sid
0x14000da36  mov     [rsp+118h+SubAuthority7], r14d; SubAuthority7
0x14000da3b  mov     [rsp+118h+SubAuthority6], r14d; SubAuthority6
0x14000da40  mov     [rsp+118h+SubAuthority5], r14d; SubAuthority5
0x14000da45  mov     [rsp+118h+SubAuthority4], r14d; SubAuthority4
0x14000da4a  mov     dword ptr [rsp+118h+SubAuthority3], r14d; SubAuthority3
0x14000da4f  mov     [rsp+118h+SubAuthority2], r14d; SubAuthority2
0x14000da54  xor     r9d, r9d; SubAuthority1
0x14000da57  mov     r8d, 1000h; SubAuthority0
0x14000da5d  mov     dl, 1; SubAuthorityCount
0x14000da5f  lea     rcx, [r11-88h]; IdentifierAuthority
0x14000da66  call    cs:__imp_RtlAllocateAndInitializeSid
0x14000da6c  lea     edx, [r14+1]; Revision
0x14000da70  lea     rcx, [rsp+118h+SecurityDescriptor]; SecurityDescriptor
0x14000da75  call    cs:__imp_RtlCreateSecurityDescriptor
0x14000da7b  lea     edx, [r14+58h]; AclSize
0x14000da7f  lea     r8d, [r14+2]; AclRevision
0x14000da83  lea     rcx, [rsp+118h+Acl]; Acl
0x14000da8b  call    cs:__imp_RtlCreateAcl
0x14000da91  mov     dword ptr [rsp+118h+SubAuthority3], 1; LabelSid
0x14000da99  mov     byte ptr [rsp+118h+SubAuthority2], 11h; AceType
0x14000da9e  mov     r9, [rsp+118h+var_B8]; MandatoryFlags
0x14000daa3  xor     r8d, r8d; Flags
0x14000daa6  lea     edx, [r14+2]; Revision
0x14000daaa  lea     rcx, [rsp+118h+Acl]; Acl
0x14000dab2  call    cs:__imp_RtlAddMandatoryAce
0x14000dab8  xor     r9d, r9d; SaclDefaulted
0x14000dabb  lea     r8, [rsp+118h+Acl]; Sacl
0x14000dac3  mov     dl, 1; SaclPresent
0x14000dac5  lea     rcx, [rsp+118h+SecurityDescriptor]; SecurityDescriptor
0x14000daca  call    cs:__imp_RtlSetSaclSecurityDescriptor
0x14000dad0  nop
0x14000dad1  lea     r8, [rsp+118h+SecurityDescriptor]; SecurityDescriptor
0x14000dad6  lea     edx, [r14+10h]; SecurityInformation
0x14000dada  mov     rcx, rbx; Handle
0x14000dadd  call    cs:__imp_NtSetSecurityObject
0x14000dae3  mov     ebx, eax
0x14000dae5  mov     rcx, [rsp+118h+var_B8]; Sid
0x14000daea  test    rcx, rcx
0x14000daed  jz      short loc_14000DAF5
0x14000daef  call    cs:__imp_RtlFreeSid
0x14000daf5  mov     eax, ebx
0x14000daf7  mov     rcx, [rsp+118h+var_18]
0x14000daff  xor     rcx, rsp; StackCookie
0x14000db02  call    __security_check_cookie
0x14000db07  mov     rbx, [rsp+118h+arg_8]
0x14000db0f  add     rsp, 110h
0x14000db16  pop     r14
0x14000db18  retn
0x14009d294  push    rbp
0x14009d296  sub     rsp, 60h
0x14009d29a  mov     rbp, rdx
0x14009d29d  add     rsp, 60h
0x14009d2a1  pop     rbp
0x14009d2a2  retn
```
