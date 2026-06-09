# WinNatSetDeviceDacl

- ea: `0x14002eb8c`
- end: `0x14002ee6c`
- name: `WinNatSetDeviceDacl`
- size: `736`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140035078`

## callees

- `0x14001ede0`
- `0x14002eb8c`

## import_xrefs

- `ntoskrnl!ObSetSecurityObjectByPointer` at `0x14002ee07`
- `ntoskrnl!ObSetSecurityObjectByPointer` at `0x14002ee07`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14002edea`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14002edea`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14002edcc`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14002edcc`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14002ed66`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14002ed91`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14002edb2`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14002ed66`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14002ed91`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14002edb2`
- `ntoskrnl!RtlCreateAcl` at `0x14002ed3f`
- `ntoskrnl!RtlCreateAcl` at `0x14002ed3f`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14002ec49`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14002ec61`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14002ec79`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14002ec91`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14002eca9`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14002ecc1`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14002ec49`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14002ec61`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14002ec79`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14002ec91`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14002eca9`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14002ecc1`
- `ntoskrnl!RtlInitializeSid` at `0x14002ec2e`
- `ntoskrnl!RtlInitializeSid` at `0x14002ec2e`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14002ebeb`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14002ebeb`
- `ntoskrnl!SeExports` at `0x14002ebb3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002ee21`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002ee38`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002ee21`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002ee38`
- `ntoskrnl!ExAllocatePool2` at `0x14002ec04`
- `ntoskrnl!ExAllocatePool2` at `0x14002ed16`
- `ntoskrnl!ExAllocatePool2` at `0x14002ec04`
- `ntoskrnl!ExAllocatePool2` at `0x14002ed16`
- `ntoskrnl!RtlLengthSid` at `0x14002ecd6`
- `ntoskrnl!RtlLengthSid` at `0x14002ece7`
- `ntoskrnl!RtlLengthSid` at `0x14002ecf8`
- `ntoskrnl!RtlLengthSid` at `0x14002ecd6`
- `ntoskrnl!RtlLengthSid` at `0x14002ece7`
- `ntoskrnl!RtlLengthSid` at `0x14002ecf8`

## pseudocode

```c
__int64 __fastcall WinNatSetDeviceDacl(__int64 a1)
{
  PSID SeAliasAdminsSid; // r15
  PSID SeLocalSystemSid; // r14
  ULONG v4; // eax
  void *Pool2; // rax
  void *v6; // rsi
  NTSTATUS Acl; // ebx
  struct _ACL *v8; // rdi
  ULONG v9; // ebx
  ULONG v10; // ebx
  ULONG v11; // ebx
  struct _ACL *v12; // rax
  _OWORD SecurityDescriptor[2]; // [rsp+20h] [rbp-40h] BYREF
  __int64 v15; // [rsp+40h] [rbp-20h]
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+48h] [rbp-18h] BYREF

  SeAliasAdminsSid = SeExports->SeAliasAdminsSid;
  SeLocalSystemSid = SeExports->SeLocalSystemSid;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  v15 = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  v4 = RtlLengthRequiredSid(6u);
  Pool2 = (void *)ExAllocatePool2(256, v4, 1852395095);
  v6 = Pool2;
  if ( Pool2 )
  {
    v8 = 0;
    Acl = RtlInitializeSid(Pool2, &IdentifierAuthority, 6u);
    if ( Acl >= 0 )
    {
      *RtlSubAuthoritySid(v6, 0) = 80;
      *RtlSubAuthoritySid(v6, 1u) = 753521396;
      *RtlSubAuthoritySid(v6, 2u) = 803201582;
      *RtlSubAuthoritySid(v6, 3u) = 330035927;
      *RtlSubAuthoritySid(v6, 4u) = 866441855;
      *RtlSubAuthoritySid(v6, 5u) = -1636953747;
      v9 = RtlLengthSid(v6);
      v10 = RtlLengthSid(SeAliasAdminsSid) + v9;
      v11 = RtlLengthSid(SeLocalSystemSid) + 32 + v10;
      v12 = (struct _ACL *)ExAllocatePool2(256, v11, 1852395095);
      v8 = v12;
      if ( v12 )
      {
        Acl = RtlCreateAcl(v12, v11, 2u);
        if ( Acl >= 0 )
        {
          Acl = RtlAddAccessAllowedAce(v8, 2u, 0x10000000u, v6);
          if ( Acl >= 0 )
          {
            Acl = RtlAddAccessAllowedAce(v8, 2u, 0x10000000u, SeLocalSystemSid);
            if ( Acl >= 0 )
            {
              Acl = RtlAddAccessAllowedAce(v8, 2u, 0x10000000u, SeAliasAdminsSid);
              if ( Acl >= 0 )
              {
                Acl = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
                if ( Acl >= 0 )
                {
                  Acl = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v8, 0);
                  if ( Acl >= 0 )
                    Acl = ObSetSecurityObjectByPointer(a1, 4, SecurityDescriptor);
                }
              }
            }
          }
        }
      }
      else
      {
        Acl = -1073741670;
      }
    }
    ExFreePoolWithTag(v6, 0x6E694E57u);
    if ( v8 )
      ExFreePoolWithTag(v8, 0x6E694E57u);
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return (unsigned int)Acl;
}

```

## disassembly

```asm
0x14002eb8c  mov     [rsp-28h+arg_8], rbx
0x14002eb91  mov     [rsp-28h+arg_10], rsi
0x14002eb96  push    rbp
0x14002eb97  push    rdi
0x14002eb98  push    r12
0x14002eb9a  push    r14
0x14002eb9c  push    r15
0x14002eb9e  mov     rbp, rsp
0x14002eba1  sub     rsp, 60h
0x14002eba5  mov     rax, cs:__security_cookie
0x14002ebac  xor     rax, rsp
0x14002ebaf  mov     [rbp+var_10], rax
0x14002ebb3  mov     rax, cs:__imp_SeExports
0x14002ebba  mov     r12, rcx
0x14002ebbd  xorps   xmm0, xmm0
0x14002ebc0  mov     rcx, [rax]
0x14002ebc3  xor     eax, eax
0x14002ebc5  mov     r15, [rcx+110h]
0x14002ebcc  mov     r14, [rcx+108h]
0x14002ebd3  lea     ecx, [rax+6]; SubAuthorityCount
0x14002ebd6  movups  [rbp+SecurityDescriptor], xmm0
0x14002ebda  mov     [rbp+var_20], rax
0x14002ebde  movups  [rbp+var_30], xmm0
0x14002ebe2  mov     dword ptr [rbp+IdentifierAuthority.Value], eax
0x14002ebe5  mov     word ptr [rbp+IdentifierAuthority.Value+4], 500h
0x14002ebeb  call    cs:__imp_RtlLengthRequiredSid
0x14002ebf2  nop     dword ptr [rax+rax+00h]
0x14002ebf7  mov     edx, eax
0x14002ebf9  mov     ecx, 100h
0x14002ebfe  mov     r8d, 6E694E57h
0x14002ec04  call    cs:__imp_ExAllocatePool2
0x14002ec0b  nop     dword ptr [rax+rax+00h]
0x14002ec10  mov     rsi, rax
0x14002ec13  test    rax, rax
0x14002ec16  jnz     short loc_14002EC22
0x14002ec18  mov     ebx, 0C000009Ah
0x14002ec1d  jmp     loc_14002EE44
0x14002ec22  mov     r8b, 6; SubAuthorityCount
0x14002ec25  lea     rdx, [rbp+IdentifierAuthority]; IdentifierAuthority
0x14002ec29  mov     rcx, rsi; Sid
0x14002ec2c  xor     edi, edi
0x14002ec2e  call    cs:__imp_RtlInitializeSid
0x14002ec35  nop     dword ptr [rax+rax+00h]
0x14002ec3a  mov     ebx, eax
0x14002ec3c  test    eax, eax
0x14002ec3e  js      loc_14002EE15
0x14002ec44  xor     edx, edx; SubAuthority
0x14002ec46  mov     rcx, rsi; Sid
0x14002ec49  call    cs:__imp_RtlSubAuthoritySid
0x14002ec50  nop     dword ptr [rax+rax+00h]
0x14002ec55  lea     edx, [rdi+1]; SubAuthority
0x14002ec58  mov     rcx, rsi; Sid
0x14002ec5b  mov     dword ptr [rax], 50h ; 'P'
0x14002ec61  call    cs:__imp_RtlSubAuthoritySid
0x14002ec68  nop     dword ptr [rax+rax+00h]
0x14002ec6d  lea     edx, [rdi+2]; SubAuthority
0x14002ec70  mov     rcx, rsi; Sid
0x14002ec73  mov     dword ptr [rax], 2CE9D2F4h
0x14002ec79  call    cs:__imp_RtlSubAuthoritySid
0x14002ec80  nop     dword ptr [rax+rax+00h]
0x14002ec85  lea     edx, [rdi+3]; SubAuthority
0x14002ec88  mov     rcx, rsi; Sid
0x14002ec8b  mov     dword ptr [rax], 2FDFE22Eh
0x14002ec91  call    cs:__imp_RtlSubAuthoritySid
0x14002ec98  nop     dword ptr [rax+rax+00h]
0x14002ec9d  lea     edx, [rdi+4]; SubAuthority
0x14002eca0  mov     rcx, rsi; Sid
0x14002eca3  mov     dword ptr [rax], 13ABF2D7h
0x14002eca9  call    cs:__imp_RtlSubAuthoritySid
0x14002ecb0  nop     dword ptr [rax+rax+00h]
0x14002ecb5  lea     edx, [rdi+5]; SubAuthority
0x14002ecb8  mov     rcx, rsi; Sid
0x14002ecbb  mov     dword ptr [rax], 33A4DA7Fh
0x14002ecc1  call    cs:__imp_RtlSubAuthoritySid
0x14002ecc8  nop     dword ptr [rax+rax+00h]
0x14002eccd  mov     rcx, rsi; Sid
0x14002ecd0  mov     dword ptr [rax], 9E6E116Dh
0x14002ecd6  call    cs:__imp_RtlLengthSid
0x14002ecdd  nop     dword ptr [rax+rax+00h]
0x14002ece2  mov     rcx, r15; Sid
0x14002ece5  mov     ebx, eax
0x14002ece7  call    cs:__imp_RtlLengthSid
0x14002ecee  nop     dword ptr [rax+rax+00h]
0x14002ecf3  mov     rcx, r14; Sid
0x14002ecf6  add     ebx, eax
0x14002ecf8  call    cs:__imp_RtlLengthSid
0x14002ecff  nop     dword ptr [rax+rax+00h]
0x14002ed04  mov     ecx, 100h
0x14002ed09  mov     r8d, 6E694E57h
0x14002ed0f  add     eax, 20h ; ' '
0x14002ed12  add     ebx, eax
0x14002ed14  mov     edx, ebx
0x14002ed16  call    cs:__imp_ExAllocatePool2
0x14002ed1d  nop     dword ptr [rax+rax+00h]
0x14002ed22  mov     rdi, rax
0x14002ed25  test    rax, rax
0x14002ed28  jnz     short loc_14002ED34
0x14002ed2a  mov     ebx, 0C000009Ah
0x14002ed2f  jmp     loc_14002EE15
0x14002ed34  mov     r8d, 2; AclRevision
0x14002ed3a  mov     edx, ebx; AclLength
0x14002ed3c  mov     rcx, rdi; Acl
0x14002ed3f  call    cs:__imp_RtlCreateAcl
0x14002ed46  nop     dword ptr [rax+rax+00h]
0x14002ed4b  mov     ebx, eax
0x14002ed4d  test    eax, eax
0x14002ed4f  js      loc_14002EE15
0x14002ed55  mov     r9, rsi; Sid
0x14002ed58  mov     edx, 2; AceRevision
0x14002ed5d  mov     r8d, 10000000h; AccessMask
0x14002ed63  mov     rcx, rdi; Acl
0x14002ed66  call    cs:__imp_RtlAddAccessAllowedAce
0x14002ed6d  nop     dword ptr [rax+rax+00h]
0x14002ed72  mov     ebx, eax
0x14002ed74  test    eax, eax
0x14002ed76  js      loc_14002EE15
0x14002ed7c  mov     r9, r14; Sid
0x14002ed7f  mov     r8d, 10000000h; AccessMask
0x14002ed85  mov     r14d, 2
0x14002ed8b  mov     rcx, rdi; Acl
0x14002ed8e  mov     edx, r14d; AceRevision
0x14002ed91  call    cs:__imp_RtlAddAccessAllowedAce
0x14002ed98  nop     dword ptr [rax+rax+00h]
0x14002ed9d  mov     ebx, eax
0x14002ed9f  test    eax, eax
0x14002eda1  js      short loc_14002EE15
0x14002eda3  mov     r9, r15; Sid
0x14002eda6  mov     r8d, 10000000h; AccessMask
0x14002edac  mov     edx, r14d; AceRevision
0x14002edaf  mov     rcx, rdi; Acl
0x14002edb2  call    cs:__imp_RtlAddAccessAllowedAce
0x14002edb9  nop     dword ptr [rax+rax+00h]
0x14002edbe  mov     ebx, eax
0x14002edc0  test    eax, eax
0x14002edc2  js      short loc_14002EE15
0x14002edc4  lea     edx, [r14-1]; Revision
0x14002edc8  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x14002edcc  call    cs:__imp_RtlCreateSecurityDescriptor
0x14002edd3  nop     dword ptr [rax+rax+00h]
0x14002edd8  mov     ebx, eax
0x14002edda  test    eax, eax
0x14002eddc  js      short loc_14002EE15
0x14002edde  xor     r9d, r9d; DaclDefaulted
0x14002ede1  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x14002ede5  mov     r8, rdi; Dacl
0x14002ede8  mov     dl, 1; DaclPresent
0x14002edea  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x14002edf1  nop     dword ptr [rax+rax+00h]
0x14002edf6  mov     ebx, eax
0x14002edf8  test    eax, eax
0x14002edfa  js      short loc_14002EE15
0x14002edfc  lea     r8, [rbp+SecurityDescriptor]
0x14002ee00  mov     rcx, r12
0x14002ee03  lea     edx, [r14+2]
0x14002ee07  call    cs:__imp_ObSetSecurityObjectByPointer
0x14002ee0e  nop     dword ptr [rax+rax+00h]
0x14002ee13  mov     ebx, eax
0x14002ee15  mov     r14d, 6E694E57h
0x14002ee1b  mov     rcx, rsi; P
0x14002ee1e  mov     edx, r14d; Tag
0x14002ee21  call    cs:__imp_ExFreePoolWithTag
0x14002ee28  nop     dword ptr [rax+rax+00h]
0x14002ee2d  test    rdi, rdi
0x14002ee30  jz      short loc_14002EE44
0x14002ee32  mov     edx, r14d; Tag
0x14002ee35  mov     rcx, rdi; P
0x14002ee38  call    cs:__imp_ExFreePoolWithTag
0x14002ee3f  nop     dword ptr [rax+rax+00h]
0x14002ee44  mov     eax, ebx
0x14002ee46  mov     rcx, [rbp+var_10]
0x14002ee4a  xor     rcx, rsp; StackCookie
0x14002ee4d  call    __security_check_cookie
0x14002ee52  lea     r11, [rsp+60h+var_s0]
0x14002ee57  mov     rbx, [r11+38h]
0x14002ee5b  mov     rsi, [r11+40h]
0x14002ee5f  mov     rsp, r11
0x14002ee62  pop     r15
0x14002ee64  pop     r14
0x14002ee66  pop     r12
0x14002ee68  pop     rdi
0x14002ee69  pop     rbp
0x14002ee6a  retn
```
