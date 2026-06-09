# SrvLibGenerateSrvServiceSD

- ea: `0x14004e5a0`
- end: `0x14004e772`
- name: `SrvLibGenerateSrvServiceSD`
- size: `466`
- prototype: `__int64 __fastcall(ACCESS_MASK AccessMask)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x140007c60`
- `0x140007ec0`
- `0x14002a3e0`
- `0x14004e5a0`

## import_xrefs

- `ntoskrnl!RtlLengthRequiredSid` at `0x14004e5d2`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14004e5d2`
- `ntoskrnl!RtlInitializeSid` at `0x14004e60d`
- `ntoskrnl!RtlInitializeSid` at `0x14004e60d`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14004e61e`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14004e636`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14004e64e`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14004e666`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14004e67e`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14004e696`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14004e61e`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14004e636`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14004e64e`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14004e666`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14004e67e`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14004e696`
- `ntoskrnl!RtlCreateAcl` at `0x14004e6d3`
- `ntoskrnl!RtlCreateAcl` at `0x14004e6d3`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14004e6ea`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14004e6ea`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14004e717`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14004e717`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14004e72e`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14004e72e`

## pseudocode

```c
void *__fastcall SrvLibGenerateSrvServiceSD(ACCESS_MASK AccessMask)
{
  void *v2; // rbx
  ULONG v3; // edi
  void *PoolWithTag; // rax
  void *v5; // rsi
  ULONG v6; // r14d
  struct _ACL *v7; // rax
  struct _ACL *v8; // rdi
  void *v9; // rax
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+20h] [rbp-48h] BYREF

  *(_DWORD *)IdentifierAuthority.Value = 0;
  v2 = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  v3 = RtlLengthRequiredSid(6u);
  PoolWithTag = (void *)SrvNetAllocatePoolWithTag(258, v3, 1280529228);
  v5 = PoolWithTag;
  if ( PoolWithTag )
  {
    RtlInitializeSid(PoolWithTag, &IdentifierAuthority, 6u);
    *RtlSubAuthoritySid(v5, 0) = 80;
    *RtlSubAuthoritySid(v5, 1u) = 879696042;
    *RtlSubAuthoritySid(v5, 2u) = -1943298450;
    *RtlSubAuthoritySid(v5, 3u) = 370232824;
    *RtlSubAuthoritySid(v5, 4u) = -1770678392;
    v6 = v3 + 16;
    *RtlSubAuthoritySid(v5, 5u) = -271430585;
    v7 = (struct _ACL *)SrvNetAllocatePoolWithTag(258, v3 + 16, 1280529228);
    v8 = v7;
    if ( v7 )
    {
      RtlCreateAcl(v7, v6, 2u);
      RtlAddAccessAllowedAce(v8, 2u, AccessMask, v5);
      v9 = (void *)SrvNetAllocatePoolWithTag(258, 40, 1280529228);
      v2 = v9;
      if ( v9 )
      {
        RtlCreateSecurityDescriptor(v9, 1u);
        RtlSetDaclSecurityDescriptor(v2, 1u, v8, 0);
      }
    }
    SrvNetWskNotifyCleanupProviderContext(v5);
    if ( !v2 && v8 )
      SrvNetWskNotifyCleanupProviderContext(v8);
  }
  return v2;
}

```

## disassembly

```asm
0x14004e5a0  push    rbx
0x14004e5a2  push    rbp
0x14004e5a3  push    rsi
0x14004e5a4  push    rdi
0x14004e5a5  push    r13
0x14004e5a7  push    r14
0x14004e5a9  sub     rsp, 38h
0x14004e5ad  mov     rax, cs:__security_cookie
0x14004e5b4  xor     rax, rsp
0x14004e5b7  mov     [rsp+68h+var_40], rax
0x14004e5bc  mov     ebp, ecx
0x14004e5be  mov     dword ptr [rsp+68h+IdentifierAuthority.Value], 0
0x14004e5c6  xor     ebx, ebx
0x14004e5c8  mov     word ptr [rsp+68h+IdentifierAuthority.Value+4], 500h
0x14004e5cf  lea     ecx, [rbx+6]; SubAuthorityCount
0x14004e5d2  call    cs:__imp_RtlLengthRequiredSid
0x14004e5d9  nop     dword ptr [rax+rax+00h]
0x14004e5de  mov     r13d, 102h
0x14004e5e4  mov     edx, eax
0x14004e5e6  mov     r8d, 4C53534Ch
0x14004e5ec  mov     edi, eax
0x14004e5ee  mov     ecx, r13d
0x14004e5f1  call    SrvNetAllocatePoolWithTag
0x14004e5f6  mov     rsi, rax
0x14004e5f9  test    rax, rax
0x14004e5fc  jz      loc_14004E754
0x14004e602  mov     r8b, 6; SubAuthorityCount
0x14004e605  lea     rdx, [rsp+68h+IdentifierAuthority]; IdentifierAuthority
0x14004e60a  mov     rcx, rax; Sid
0x14004e60d  call    cs:__imp_RtlInitializeSid
0x14004e614  nop     dword ptr [rax+rax+00h]
0x14004e619  xor     edx, edx; SubAuthority
0x14004e61b  mov     rcx, rsi; Sid
0x14004e61e  call    cs:__imp_RtlSubAuthoritySid
0x14004e625  nop     dword ptr [rax+rax+00h]
0x14004e62a  lea     edx, [rbx+1]; SubAuthority
0x14004e62d  mov     rcx, rsi; Sid
0x14004e630  mov     dword ptr [rax], 50h ; 'P'
0x14004e636  call    cs:__imp_RtlSubAuthoritySid
0x14004e63d  nop     dword ptr [rax+rax+00h]
0x14004e642  lea     edx, [rbx+2]; SubAuthority
0x14004e645  mov     rcx, rsi; Sid
0x14004e648  mov     dword ptr [rax], 346F18AAh
0x14004e64e  call    cs:__imp_RtlSubAuthoritySid
0x14004e655  nop     dword ptr [rax+rax+00h]
0x14004e65a  lea     edx, [rbx+3]; SubAuthority
0x14004e65d  mov     rcx, rsi; Sid
0x14004e660  mov     dword ptr [rax], 8C2B9E6Eh
0x14004e666  call    cs:__imp_RtlSubAuthoritySid
0x14004e66d  nop     dword ptr [rax+rax+00h]
0x14004e672  lea     edx, [rbx+4]; SubAuthority
0x14004e675  mov     rcx, rsi; Sid
0x14004e678  mov     dword ptr [rax], 16114DF8h
0x14004e67e  call    cs:__imp_RtlSubAuthoritySid
0x14004e685  nop     dword ptr [rax+rax+00h]
0x14004e68a  lea     edx, [rbx+5]; SubAuthority
0x14004e68d  mov     rcx, rsi; Sid
0x14004e690  mov     dword ptr [rax], 96759788h
0x14004e696  call    cs:__imp_RtlSubAuthoritySid
0x14004e69d  nop     dword ptr [rax+rax+00h]
0x14004e6a2  lea     r14d, [rdi+10h]
0x14004e6a6  mov     r8d, 4C53534Ch
0x14004e6ac  mov     edx, r14d
0x14004e6af  mov     ecx, r13d
0x14004e6b2  mov     dword ptr [rax], 0EFD24C47h
0x14004e6b8  call    SrvNetAllocatePoolWithTag
0x14004e6bd  mov     rdi, rax
0x14004e6c0  test    rax, rax
0x14004e6c3  jz      short loc_14004E73A
0x14004e6c5  mov     ebx, 2
0x14004e6ca  mov     edx, r14d; AclLength
0x14004e6cd  mov     r8d, ebx; AclRevision
0x14004e6d0  mov     rcx, rax; Acl
0x14004e6d3  call    cs:__imp_RtlCreateAcl
0x14004e6da  nop     dword ptr [rax+rax+00h]
0x14004e6df  mov     r9, rsi; Sid
0x14004e6e2  mov     r8d, ebp; AccessMask
0x14004e6e5  mov     edx, ebx; AceRevision
0x14004e6e7  mov     rcx, rdi; Acl
0x14004e6ea  call    cs:__imp_RtlAddAccessAllowedAce
0x14004e6f1  nop     dword ptr [rax+rax+00h]
0x14004e6f6  lea     edx, [rbx+26h]
0x14004e6f9  mov     r8d, 4C53534Ch
0x14004e6ff  mov     ecx, r13d
0x14004e702  call    SrvNetAllocatePoolWithTag
0x14004e707  mov     rbx, rax
0x14004e70a  test    rax, rax
0x14004e70d  jz      short loc_14004E73A
0x14004e70f  mov     edx, 1; Revision
0x14004e714  mov     rcx, rax; SecurityDescriptor
0x14004e717  call    cs:__imp_RtlCreateSecurityDescriptor
0x14004e71e  nop     dword ptr [rax+rax+00h]
0x14004e723  xor     r9d, r9d; DaclDefaulted
0x14004e726  mov     r8, rdi; Dacl
0x14004e729  mov     dl, 1; DaclPresent
0x14004e72b  mov     rcx, rbx; SecurityDescriptor
0x14004e72e  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x14004e735  nop     dword ptr [rax+rax+00h]
0x14004e73a  mov     rcx, rsi
0x14004e73d  call    SrvNetWskNotifyCleanupProviderContext
0x14004e742  test    rbx, rbx
0x14004e745  jnz     short loc_14004E754
0x14004e747  test    rdi, rdi
0x14004e74a  jz      short loc_14004E754
0x14004e74c  mov     rcx, rdi
0x14004e74f  call    SrvNetWskNotifyCleanupProviderContext
0x14004e754  mov     rax, rbx
0x14004e757  mov     rcx, [rsp+68h+var_40]
0x14004e75c  xor     rcx, rsp; StackCookie
0x14004e75f  call    __security_check_cookie
0x14004e764  add     rsp, 38h
0x14004e768  pop     r14
0x14004e76a  pop     r13
0x14004e76c  pop     rdi
0x14004e76d  pop     rsi
0x14004e76e  pop     rbp
0x14004e76f  pop     rbx
0x14004e770  retn
```
