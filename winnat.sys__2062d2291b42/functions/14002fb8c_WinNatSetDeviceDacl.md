# WinNatSetDeviceDacl

- ea: `0x14002fb8c`
- end: `0x14002fe6c`
- name: `WinNatSetDeviceDacl`
- size: `736`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140036078`

## callees

- `0x14001f320`
- `0x14002fb8c`

## import_xrefs

- `ntoskrnl!ObSetSecurityObjectByPointer` at `0x14002fe07`
- `ntoskrnl!ObSetSecurityObjectByPointer` at `0x14002fe07`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14002fdea`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14002fdea`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14002fdcc`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14002fdcc`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14002fd66`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14002fd91`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14002fdb2`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14002fd66`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14002fd91`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14002fdb2`
- `ntoskrnl!RtlCreateAcl` at `0x14002fd3f`
- `ntoskrnl!RtlCreateAcl` at `0x14002fd3f`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14002fc49`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14002fc61`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14002fc79`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14002fc91`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14002fca9`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14002fcc1`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14002fc49`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14002fc61`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14002fc79`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14002fc91`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14002fca9`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14002fcc1`
- `ntoskrnl!RtlInitializeSid` at `0x14002fc2e`
- `ntoskrnl!RtlInitializeSid` at `0x14002fc2e`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14002fbeb`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14002fbeb`
- `ntoskrnl!SeExports` at `0x14002fbb3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002fe21`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002fe38`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002fe21`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002fe38`
- `ntoskrnl!ExAllocatePool2` at `0x14002fc04`
- `ntoskrnl!ExAllocatePool2` at `0x14002fd16`
- `ntoskrnl!ExAllocatePool2` at `0x14002fc04`
- `ntoskrnl!ExAllocatePool2` at `0x14002fd16`
- `ntoskrnl!RtlLengthSid` at `0x14002fcd6`
- `ntoskrnl!RtlLengthSid` at `0x14002fce7`
- `ntoskrnl!RtlLengthSid` at `0x14002fcf8`
- `ntoskrnl!RtlLengthSid` at `0x14002fcd6`
- `ntoskrnl!RtlLengthSid` at `0x14002fce7`
- `ntoskrnl!RtlLengthSid` at `0x14002fcf8`

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
0x14002fb8c  mov     [rsp-28h+arg_8], rbx
0x14002fb91  mov     [rsp-28h+arg_10], rsi
0x14002fb96  push    rbp
0x14002fb97  push    rdi
0x14002fb98  push    r12
0x14002fb9a  push    r14
0x14002fb9c  push    r15
0x14002fb9e  mov     rbp, rsp
0x14002fba1  sub     rsp, 60h
0x14002fba5  mov     rax, cs:__security_cookie
0x14002fbac  xor     rax, rsp
0x14002fbaf  mov     [rbp+var_10], rax
0x14002fbb3  mov     rax, cs:__imp_SeExports
0x14002fbba  mov     r12, rcx
0x14002fbbd  xorps   xmm0, xmm0
0x14002fbc0  mov     rcx, [rax]
0x14002fbc3  xor     eax, eax
0x14002fbc5  mov     r15, [rcx+110h]
0x14002fbcc  mov     r14, [rcx+108h]
0x14002fbd3  lea     ecx, [rax+6]; SubAuthorityCount
0x14002fbd6  movups  [rbp+SecurityDescriptor], xmm0
0x14002fbda  mov     [rbp+var_20], rax
0x14002fbde  movups  [rbp+var_30], xmm0
0x14002fbe2  mov     dword ptr [rbp+IdentifierAuthority.Value], eax
0x14002fbe5  mov     word ptr [rbp+IdentifierAuthority.Value+4], 500h
0x14002fbeb  call    cs:__imp_RtlLengthRequiredSid
0x14002fbf2  nop     dword ptr [rax+rax+00h]
0x14002fbf7  mov     edx, eax
0x14002fbf9  mov     ecx, 100h
0x14002fbfe  mov     r8d, 6E694E57h
0x14002fc04  call    cs:__imp_ExAllocatePool2
0x14002fc0b  nop     dword ptr [rax+rax+00h]
0x14002fc10  mov     rsi, rax
0x14002fc13  test    rax, rax
0x14002fc16  jnz     short loc_14002FC22
0x14002fc18  mov     ebx, 0C000009Ah
0x14002fc1d  jmp     loc_14002FE44
0x14002fc22  mov     r8b, 6; SubAuthorityCount
0x14002fc25  lea     rdx, [rbp+IdentifierAuthority]; IdentifierAuthority
0x14002fc29  mov     rcx, rsi; Sid
0x14002fc2c  xor     edi, edi
0x14002fc2e  call    cs:__imp_RtlInitializeSid
0x14002fc35  nop     dword ptr [rax+rax+00h]
0x14002fc3a  mov     ebx, eax
0x14002fc3c  test    eax, eax
0x14002fc3e  js      loc_14002FE15
0x14002fc44  xor     edx, edx; SubAuthority
0x14002fc46  mov     rcx, rsi; Sid
0x14002fc49  call    cs:__imp_RtlSubAuthoritySid
0x14002fc50  nop     dword ptr [rax+rax+00h]
0x14002fc55  lea     edx, [rdi+1]; SubAuthority
0x14002fc58  mov     rcx, rsi; Sid
0x14002fc5b  mov     dword ptr [rax], 50h ; 'P'
0x14002fc61  call    cs:__imp_RtlSubAuthoritySid
0x14002fc68  nop     dword ptr [rax+rax+00h]
0x14002fc6d  lea     edx, [rdi+2]; SubAuthority
0x14002fc70  mov     rcx, rsi; Sid
0x14002fc73  mov     dword ptr [rax], 2CE9D2F4h
0x14002fc79  call    cs:__imp_RtlSubAuthoritySid
0x14002fc80  nop     dword ptr [rax+rax+00h]
0x14002fc85  lea     edx, [rdi+3]; SubAuthority
0x14002fc88  mov     rcx, rsi; Sid
0x14002fc8b  mov     dword ptr [rax], 2FDFE22Eh
0x14002fc91  call    cs:__imp_RtlSubAuthoritySid
0x14002fc98  nop     dword ptr [rax+rax+00h]
0x14002fc9d  lea     edx, [rdi+4]; SubAuthority
0x14002fca0  mov     rcx, rsi; Sid
0x14002fca3  mov     dword ptr [rax], 13ABF2D7h
0x14002fca9  call    cs:__imp_RtlSubAuthoritySid
0x14002fcb0  nop     dword ptr [rax+rax+00h]
0x14002fcb5  lea     edx, [rdi+5]; SubAuthority
0x14002fcb8  mov     rcx, rsi; Sid
0x14002fcbb  mov     dword ptr [rax], 33A4DA7Fh
0x14002fcc1  call    cs:__imp_RtlSubAuthoritySid
0x14002fcc8  nop     dword ptr [rax+rax+00h]
0x14002fccd  mov     rcx, rsi; Sid
0x14002fcd0  mov     dword ptr [rax], 9E6E116Dh
0x14002fcd6  call    cs:__imp_RtlLengthSid
0x14002fcdd  nop     dword ptr [rax+rax+00h]
0x14002fce2  mov     rcx, r15; Sid
0x14002fce5  mov     ebx, eax
0x14002fce7  call    cs:__imp_RtlLengthSid
0x14002fcee  nop     dword ptr [rax+rax+00h]
0x14002fcf3  mov     rcx, r14; Sid
0x14002fcf6  add     ebx, eax
0x14002fcf8  call    cs:__imp_RtlLengthSid
0x14002fcff  nop     dword ptr [rax+rax+00h]
0x14002fd04  mov     ecx, 100h
0x14002fd09  mov     r8d, 6E694E57h
0x14002fd0f  add     eax, 20h ; ' '
0x14002fd12  add     ebx, eax
0x14002fd14  mov     edx, ebx
0x14002fd16  call    cs:__imp_ExAllocatePool2
0x14002fd1d  nop     dword ptr [rax+rax+00h]
0x14002fd22  mov     rdi, rax
0x14002fd25  test    rax, rax
0x14002fd28  jnz     short loc_14002FD34
0x14002fd2a  mov     ebx, 0C000009Ah
0x14002fd2f  jmp     loc_14002FE15
0x14002fd34  mov     r8d, 2; AclRevision
0x14002fd3a  mov     edx, ebx; AclLength
0x14002fd3c  mov     rcx, rdi; Acl
0x14002fd3f  call    cs:__imp_RtlCreateAcl
0x14002fd46  nop     dword ptr [rax+rax+00h]
0x14002fd4b  mov     ebx, eax
0x14002fd4d  test    eax, eax
0x14002fd4f  js      loc_14002FE15
0x14002fd55  mov     r9, rsi; Sid
0x14002fd58  mov     edx, 2; AceRevision
0x14002fd5d  mov     r8d, 10000000h; AccessMask
0x14002fd63  mov     rcx, rdi; Acl
0x14002fd66  call    cs:__imp_RtlAddAccessAllowedAce
0x14002fd6d  nop     dword ptr [rax+rax+00h]
0x14002fd72  mov     ebx, eax
0x14002fd74  test    eax, eax
0x14002fd76  js      loc_14002FE15
0x14002fd7c  mov     r9, r14; Sid
0x14002fd7f  mov     r8d, 10000000h; AccessMask
0x14002fd85  mov     r14d, 2
0x14002fd8b  mov     rcx, rdi; Acl
0x14002fd8e  mov     edx, r14d; AceRevision
0x14002fd91  call    cs:__imp_RtlAddAccessAllowedAce
0x14002fd98  nop     dword ptr [rax+rax+00h]
0x14002fd9d  mov     ebx, eax
0x14002fd9f  test    eax, eax
0x14002fda1  js      short loc_14002FE15
0x14002fda3  mov     r9, r15; Sid
0x14002fda6  mov     r8d, 10000000h; AccessMask
0x14002fdac  mov     edx, r14d; AceRevision
0x14002fdaf  mov     rcx, rdi; Acl
0x14002fdb2  call    cs:__imp_RtlAddAccessAllowedAce
0x14002fdb9  nop     dword ptr [rax+rax+00h]
0x14002fdbe  mov     ebx, eax
0x14002fdc0  test    eax, eax
0x14002fdc2  js      short loc_14002FE15
0x14002fdc4  lea     edx, [r14-1]; Revision
0x14002fdc8  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x14002fdcc  call    cs:__imp_RtlCreateSecurityDescriptor
0x14002fdd3  nop     dword ptr [rax+rax+00h]
0x14002fdd8  mov     ebx, eax
0x14002fdda  test    eax, eax
0x14002fddc  js      short loc_14002FE15
0x14002fdde  xor     r9d, r9d; DaclDefaulted
0x14002fde1  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x14002fde5  mov     r8, rdi; Dacl
0x14002fde8  mov     dl, 1; DaclPresent
0x14002fdea  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x14002fdf1  nop     dword ptr [rax+rax+00h]
0x14002fdf6  mov     ebx, eax
0x14002fdf8  test    eax, eax
0x14002fdfa  js      short loc_14002FE15
0x14002fdfc  lea     r8, [rbp+SecurityDescriptor]
0x14002fe00  mov     rcx, r12
0x14002fe03  lea     edx, [r14+2]
0x14002fe07  call    cs:__imp_ObSetSecurityObjectByPointer
0x14002fe0e  nop     dword ptr [rax+rax+00h]
0x14002fe13  mov     ebx, eax
0x14002fe15  mov     r14d, 6E694E57h
0x14002fe1b  mov     rcx, rsi; P
0x14002fe1e  mov     edx, r14d; Tag
0x14002fe21  call    cs:__imp_ExFreePoolWithTag
0x14002fe28  nop     dword ptr [rax+rax+00h]
0x14002fe2d  test    rdi, rdi
0x14002fe30  jz      short loc_14002FE44
0x14002fe32  mov     edx, r14d; Tag
0x14002fe35  mov     rcx, rdi; P
0x14002fe38  call    cs:__imp_ExFreePoolWithTag
0x14002fe3f  nop     dword ptr [rax+rax+00h]
0x14002fe44  mov     eax, ebx
0x14002fe46  mov     rcx, [rbp+var_10]
0x14002fe4a  xor     rcx, rsp; StackCookie
0x14002fe4d  call    __security_check_cookie
0x14002fe52  lea     r11, [rsp+60h+var_s0]
0x14002fe57  mov     rbx, [r11+38h]
0x14002fe5b  mov     rsi, [r11+40h]
0x14002fe5f  mov     rsp, r11
0x14002fe62  pop     r15
0x14002fe64  pop     r14
0x14002fe66  pop     r12
0x14002fe68  pop     rdi
0x14002fe69  pop     rbp
0x14002fe6a  retn
```
