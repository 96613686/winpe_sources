# BuildSecurityDescriptorForSharingAccessInternal

- ea: `0x180023374`
- end: `0x18002368f`
- name: `BuildSecurityDescriptorForSharingAccessInternal`
- size: `795`
- prototype: `__int64 __fastcall(PSID Sid, PSID, PSID Owner, PSID, ACCESS_MASK AccessMask, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180017ce0`

## callees

- `0x180012290`
- `0x1800125c8`
- `0x180023374`
- `0x18004fa50`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x180023535`
- `ntdll!RtlEqualSid` at `0x180023564`
- `ntdll!RtlEqualSid` at `0x180023574`
- `ntdll!RtlEqualSid` at `0x180023535`
- `ntdll!RtlEqualSid` at `0x180023564`
- `ntdll!RtlEqualSid` at `0x180023574`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x1800235eb`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x1800235eb`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x180023601`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x180023601`
- `ntdll!RtlInitializeSid` at `0x180023409`
- `ntdll!RtlInitializeSid` at `0x180023409`
- `ntdll!RtlSubAuthoritySid` at `0x180023414`
- `ntdll!RtlSubAuthoritySid` at `0x180023414`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x1800235ca`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x1800235ca`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x18002363b`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x18002363b`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180023429`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180023429`
- `ntdll!RtlLengthSecurityDescriptor` at `0x180023611`
- `ntdll!RtlLengthSecurityDescriptor` at `0x180023611`
- `ntdll!RtlLengthRequiredSid` at `0x1800233dd`
- `ntdll!RtlLengthRequiredSid` at `0x1800233dd`
- `ntdll!RtlAddAccessAllowedAce` at `0x1800234ed`
- `ntdll!RtlAddAccessAllowedAce` at `0x180023517`
- `ntdll!RtlAddAccessAllowedAce` at `0x18002354e`
- `ntdll!RtlAddAccessAllowedAce` at `0x18002358b`
- `ntdll!RtlAddAccessAllowedAce` at `0x1800235ae`
- `ntdll!RtlAddAccessAllowedAce` at `0x1800234ed`
- `ntdll!RtlAddAccessAllowedAce` at `0x180023517`
- `ntdll!RtlAddAccessAllowedAce` at `0x18002354e`
- `ntdll!RtlAddAccessAllowedAce` at `0x18002358b`
- `ntdll!RtlAddAccessAllowedAce` at `0x1800235ae`
- `ntdll!RtlLengthSid` at `0x180023446`
- `ntdll!RtlLengthSid` at `0x18002345a`
- `ntdll!RtlLengthSid` at `0x180023471`
- `ntdll!RtlLengthSid` at `0x180023488`
- `ntdll!RtlLengthSid` at `0x18002349a`
- `ntdll!RtlLengthSid` at `0x180023446`
- `ntdll!RtlLengthSid` at `0x18002345a`
- `ntdll!RtlLengthSid` at `0x180023471`
- `ntdll!RtlLengthSid` at `0x180023488`
- `ntdll!RtlLengthSid` at `0x18002349a`
- `ntdll!RtlCreateAcl` at `0x1800234cc`
- `ntdll!RtlCreateAcl` at `0x1800234cc`

## pseudocode

```c
__int64 __fastcall BuildSecurityDescriptorForSharingAccessInternal(
        PSID Sid,
        PSID a2,
        PSID Owner,
        PSID a4,
        ACCESS_MASK AccessMask,
        struct _ACL *a6,
        _QWORD *a7)
{
  ULONG v11; // eax
  void *v12; // rax
  void *v13; // r15
  NTSTATUS Acl; // ebx
  void *v15; // rdi
  __int64 v16; // rbx
  __int64 v17; // rbx
  struct _ACL *v18; // rax
  struct _ACL *v19; // rsi
  void *v20; // rax
  ULONG BufferLength; // [rsp+20h] [rbp-61h] BYREF
  PSID Sida; // [rsp+28h] [rbp-59h]
  PACL Sacl; // [rsp+30h] [rbp-51h]
  _QWORD *v25; // [rsp+38h] [rbp-49h]
  _OWORD SecurityDescriptor[2]; // [rsp+40h] [rbp-41h] BYREF
  __int64 v27; // [rsp+60h] [rbp-21h]
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+68h] [rbp-19h] BYREF

  Sacl = a6;
  v25 = a7;
  Sida = a2;
  v27 = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  BufferLength = 0;
  v11 = RtlLengthRequiredSid(1u);
  v12 = (void *)AccessHlprAlloc(v11);
  v13 = v12;
  if ( v12 )
  {
    v15 = 0;
    RtlInitializeSid(v12, &IdentifierAuthority, 1u);
    *RtlSubAuthoritySid(v13, 0) = 18;
    Acl = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
    if ( Acl >= 0 )
    {
      v16 = 8;
      if ( Owner )
        v16 = RtlLengthSid(Owner) + 16LL;
      if ( a4 )
        v16 += RtlLengthSid(a4) + 8LL;
      if ( Sid )
        v16 += RtlLengthSid(Sid) + 8LL;
      if ( a2 )
        v16 += RtlLengthSid(a2) + 8LL;
      v17 = RtlLengthSid(v13) + v16;
      v18 = (struct _ACL *)AccessHlprAlloc(v17 + 8);
      v19 = v18;
      if ( v18 )
      {
        Acl = RtlCreateAcl(v18, v17 + 8, 2u);
        if ( Acl >= 0 )
        {
          Acl = RtlAddAccessAllowedAce(v19, 2u, 0x10000000u, Owner);
          if ( Acl >= 0 )
          {
            if ( !a4 || (Acl = RtlAddAccessAllowedAce(v19, 2u, 0x10000000u, a4), Acl >= 0) )
            {
              if ( RtlEqualSid(Owner, v13) || (Acl = RtlAddAccessAllowedAce(v19, 2u, 0x10000000u, v13), Acl >= 0) )
              {
                if ( RtlEqualSid(Sid, v13)
                  || RtlEqualSid(Sid, Owner)
                  || (Acl = RtlAddAccessAllowedAce(v19, 2u, AccessMask, Sid), Acl >= 0) )
                {
                  if ( !Sida || (Acl = RtlAddAccessAllowedAce(v19, 2u, AccessMask, Sida), Acl >= 0) )
                  {
                    Acl = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v19, 0);
                    if ( Acl >= 0 )
                    {
                      if ( !Sacl || (Acl = RtlSetSaclSecurityDescriptor(SecurityDescriptor, 1u, Sacl, 0), Acl >= 0) )
                      {
                        Acl = RtlSetOwnerSecurityDescriptor(SecurityDescriptor, Owner, 0);
                        if ( Acl >= 0 )
                        {
                          BufferLength = RtlLengthSecurityDescriptor(SecurityDescriptor);
                          v20 = (void *)AccessHlprAlloc(BufferLength);
                          v15 = v20;
                          if ( v20 )
                          {
                            Acl = RtlAbsoluteToSelfRelativeSD(SecurityDescriptor, v20, &BufferLength);
                            if ( Acl >= 0 )
                            {
                              *v25 = v15;
                              v15 = 0;
                            }
                          }
                          else
                          {
                            Acl = -1073741801;
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
        FreeTransientObjectSecurityDescriptor(v19);
      }
      else
      {
        Acl = -1073741801;
      }
    }
    FreeTransientObjectSecurityDescriptor(v13);
    if ( v15 )
      FreeTransientObjectSecurityDescriptor(v15);
  }
  else
  {
    return (unsigned int)-1073741801;
  }
  return (unsigned int)Acl;
}

```

## disassembly

```asm
0x180023374  push    rbp
0x180023376  push    rbx
0x180023377  push    rsi
0x180023378  push    rdi
0x180023379  push    r12
0x18002337b  push    r13
0x18002337d  push    r14
0x18002337f  push    r15
0x180023381  lea     rbp, [rsp-7]
0x180023386  sub     rsp, 88h
0x18002338d  mov     rax, cs:__security_cookie
0x180023394  xor     rax, rsp
0x180023397  mov     [rbp+3Fh+var_50], rax
0x18002339b  mov     rax, [rbp+3Fh+arg_28]
0x18002339f  xor     ebx, ebx
0x1800233a1  mov     [rbp+3Fh+Sacl], rax
0x1800233a5  xorps   xmm0, xmm0
0x1800233a8  mov     rax, [rbp+3Fh+arg_30]
0x1800233ac  mov     r12, rcx
0x1800233af  mov     [rbp+3Fh+var_88], rax
0x1800233b3  mov     r13, r9
0x1800233b6  xor     eax, eax
0x1800233b8  mov     [rbp+3Fh+Sid], rdx
0x1800233bc  lea     ecx, [rbx+1]; SubAuthorityCount
0x1800233bf  mov     [rbp+3Fh+var_60], rax
0x1800233c3  mov     r14, r8
0x1800233c6  mov     dword ptr [rbp+3Fh+IdentifierAuthority.Value], ebx
0x1800233c9  mov     rsi, rdx
0x1800233cc  mov     word ptr [rbp+3Fh+IdentifierAuthority.Value+4], 500h
0x1800233d2  movups  [rbp+3Fh+SecurityDescriptor], xmm0
0x1800233d6  mov     [rbp+3Fh+BufferLength], ebx
0x1800233d9  movups  [rbp+3Fh+var_70], xmm0
0x1800233dd  call    cs:__imp_RtlLengthRequiredSid
0x1800233e3  mov     ecx, eax
0x1800233e5  call    AccessHlprAlloc
0x1800233ea  mov     r15, rax
0x1800233ed  test    rax, rax
0x1800233f0  jnz     short loc_1800233FC
0x1800233f2  mov     ebx, 0C0000017h
0x1800233f7  jmp     loc_18002366D
0x1800233fc  mov     r8b, 1; SubAuthorityCount
0x1800233ff  lea     rdx, [rbp+3Fh+IdentifierAuthority]; IdentifierAuthority
0x180023403  mov     rcx, r15; Sid
0x180023406  mov     rdi, rbx
0x180023409  call    cs:__imp_RtlInitializeSid
0x18002340f  xor     edx, edx; SubAuthority
0x180023411  mov     rcx, r15; Sid
0x180023414  call    cs:__imp_RtlSubAuthoritySid
0x18002341a  mov     edx, 1; Revision
0x18002341f  lea     rcx, [rbp+3Fh+SecurityDescriptor]; SecurityDescriptor
0x180023423  mov     dword ptr [rax], 12h
0x180023429  call    cs:__imp_RtlCreateSecurityDescriptor
0x18002342f  mov     ebx, eax
0x180023431  test    eax, eax
0x180023433  js      loc_180023658
0x180023439  mov     ebx, 8
0x18002343e  test    r14, r14
0x180023441  jz      short loc_180023452
0x180023443  mov     rcx, r14; Sid
0x180023446  call    cs:__imp_RtlLengthSid
0x18002344c  mov     ebx, eax
0x18002344e  add     rbx, 10h
0x180023452  test    r13, r13
0x180023455  jz      short loc_180023469
0x180023457  mov     rcx, r13; Sid
0x18002345a  call    cs:__imp_RtlLengthSid
0x180023460  mov     eax, eax
0x180023462  add     rax, 8
0x180023466  add     rbx, rax
0x180023469  test    r12, r12
0x18002346c  jz      short loc_180023480
0x18002346e  mov     rcx, r12; Sid
0x180023471  call    cs:__imp_RtlLengthSid
0x180023477  mov     eax, eax
0x180023479  add     rax, 8
0x18002347d  add     rbx, rax
0x180023480  test    rsi, rsi
0x180023483  jz      short loc_180023497
0x180023485  mov     rcx, rsi; Sid
0x180023488  call    cs:__imp_RtlLengthSid
0x18002348e  mov     eax, eax
0x180023490  add     rax, 8
0x180023494  add     rbx, rax
0x180023497  mov     rcx, r15; Sid
0x18002349a  call    cs:__imp_RtlLengthSid
0x1800234a0  mov     eax, eax
0x1800234a2  add     rbx, rax
0x1800234a5  lea     rcx, [rbx+8]
0x1800234a9  call    AccessHlprAlloc
0x1800234ae  mov     rsi, rax
0x1800234b1  test    rax, rax
0x1800234b4  jnz     short loc_1800234C0
0x1800234b6  mov     ebx, 0C0000017h
0x1800234bb  jmp     loc_180023658
0x1800234c0  lea     edx, [rbx+8]; AclSize
0x1800234c3  mov     r8d, 2; AclRevision
0x1800234c9  mov     rcx, rsi; Acl
0x1800234cc  call    cs:__imp_RtlCreateAcl
0x1800234d2  mov     ebx, eax
0x1800234d4  test    eax, eax
0x1800234d6  js      loc_180023650
0x1800234dc  mov     r9, r14; Sid
0x1800234df  mov     edx, 2; Revision
0x1800234e4  mov     r8d, 10000000h; AccessMask
0x1800234ea  mov     rcx, rsi; Acl
0x1800234ed  call    cs:__imp_RtlAddAccessAllowedAce
0x1800234f3  mov     ebx, eax
0x1800234f5  test    eax, eax
0x1800234f7  js      loc_180023650
0x1800234fd  test    r13, r13
0x180023500  jz      short loc_180023529
0x180023502  mov     r9, r13; Sid
0x180023505  mov     r8d, 10000000h; AccessMask
0x18002350b  mov     r13d, 2
0x180023511  mov     rcx, rsi; Acl
0x180023514  mov     edx, r13d; Revision
0x180023517  call    cs:__imp_RtlAddAccessAllowedAce
0x18002351d  mov     ebx, eax
0x18002351f  test    eax, eax
0x180023521  js      loc_180023650
0x180023527  jmp     short loc_18002352F
0x180023529  mov     r13d, 2
0x18002352f  mov     rdx, r15; Sid2
0x180023532  mov     rcx, r14; Sid1
0x180023535  call    cs:__imp_RtlEqualSid
0x18002353b  test    al, al
0x18002353d  jnz     short loc_18002355E
0x18002353f  mov     r9, r15; Sid
0x180023542  mov     r8d, 10000000h; AccessMask
0x180023548  mov     edx, r13d; Revision
0x18002354b  mov     rcx, rsi; Acl
0x18002354e  call    cs:__imp_RtlAddAccessAllowedAce
0x180023554  mov     ebx, eax
0x180023556  test    eax, eax
0x180023558  js      loc_180023650
0x18002355e  mov     rdx, r15; Sid2
0x180023561  mov     rcx, r12; Sid1
0x180023564  call    cs:__imp_RtlEqualSid
0x18002356a  test    al, al
0x18002356c  jnz     short loc_18002359B
0x18002356e  mov     rdx, r14; Sid2
0x180023571  mov     rcx, r12; Sid1
0x180023574  call    cs:__imp_RtlEqualSid
0x18002357a  test    al, al
0x18002357c  jnz     short loc_18002359B
0x18002357e  mov     r8d, [rbp+3Fh+AccessMask]; AccessMask
0x180023582  mov     r9, r12; Sid
0x180023585  mov     edx, r13d; Revision
0x180023588  mov     rcx, rsi; Acl
0x18002358b  call    cs:__imp_RtlAddAccessAllowedAce
0x180023591  mov     ebx, eax
0x180023593  test    eax, eax
0x180023595  js      loc_180023650
0x18002359b  mov     r9, [rbp+3Fh+Sid]; Sid
0x18002359f  test    r9, r9
0x1800235a2  jz      short loc_1800235BE
0x1800235a4  mov     r8d, [rbp+3Fh+AccessMask]; AccessMask
0x1800235a8  mov     edx, r13d; Revision
0x1800235ab  mov     rcx, rsi; Acl
0x1800235ae  call    cs:__imp_RtlAddAccessAllowedAce
0x1800235b4  mov     ebx, eax
0x1800235b6  test    eax, eax
0x1800235b8  js      loc_180023650
0x1800235be  xor     r9d, r9d; DaclDefaulted
0x1800235c1  lea     rcx, [rbp+3Fh+SecurityDescriptor]; SecurityDescriptor
0x1800235c5  mov     r8, rsi; Dacl
0x1800235c8  mov     dl, 1; DaclPresent
0x1800235ca  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1800235d0  mov     ebx, eax
0x1800235d2  test    eax, eax
0x1800235d4  js      short loc_180023650
0x1800235d6  mov     rax, [rbp+3Fh+Sacl]
0x1800235da  test    rax, rax
0x1800235dd  jz      short loc_1800235F7
0x1800235df  xor     r9d, r9d; SaclDefaulted
0x1800235e2  lea     rcx, [rbp+3Fh+SecurityDescriptor]; SecurityDescriptor
0x1800235e6  mov     r8, rax; Sacl
0x1800235e9  mov     dl, 1; SaclPresent
0x1800235eb  call    cs:__imp_RtlSetSaclSecurityDescriptor
0x1800235f1  mov     ebx, eax
0x1800235f3  test    eax, eax
0x1800235f5  js      short loc_180023650
0x1800235f7  xor     r8d, r8d; OwnerDefaulted
0x1800235fa  lea     rcx, [rbp+3Fh+SecurityDescriptor]; SecurityDescriptor
0x1800235fe  mov     rdx, r14; Owner
0x180023601  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x180023607  mov     ebx, eax
0x180023609  test    eax, eax
0x18002360b  js      short loc_180023650
0x18002360d  lea     rcx, [rbp+3Fh+SecurityDescriptor]; SecurityDescriptor
0x180023611  call    cs:__imp_RtlLengthSecurityDescriptor
0x180023617  mov     ecx, eax
0x180023619  mov     [rbp+3Fh+BufferLength], ecx
0x18002361c  call    AccessHlprAlloc
0x180023621  mov     rdi, rax
0x180023624  test    rax, rax
0x180023627  jnz     short loc_180023630
0x180023629  mov     ebx, 0C0000017h
0x18002362e  jmp     short loc_180023650
0x180023630  lea     r8, [rbp+3Fh+BufferLength]; BufferLength
0x180023634  mov     rdx, rdi; SelfRelativeSecurityDescriptor
0x180023637  lea     rcx, [rbp+3Fh+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x18002363b  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x180023641  mov     ebx, eax
0x180023643  test    eax, eax
0x180023645  js      short loc_180023650
0x180023647  mov     rax, [rbp+3Fh+var_88]
0x18002364b  mov     [rax], rdi
0x18002364e  xor     edi, edi
0x180023650  mov     rcx, rsi
0x180023653  call    FreeTransientObjectSecurityDescriptor
0x180023658  mov     rcx, r15
0x18002365b  call    FreeTransientObjectSecurityDescriptor
0x180023660  test    rdi, rdi
0x180023663  jz      short loc_18002366D
0x180023665  mov     rcx, rdi
0x180023668  call    FreeTransientObjectSecurityDescriptor
0x18002366d  mov     eax, ebx
0x18002366f  mov     rcx, [rbp+3Fh+var_50]
0x180023673  xor     rcx, rsp; StackCookie
0x180023676  call    __security_check_cookie
0x18002367b  add     rsp, 88h
0x180023682  pop     r15
0x180023684  pop     r14
0x180023686  pop     r13
0x180023688  pop     r12
0x18002368a  pop     rdi
0x18002368b  pop     rsi
0x18002368c  pop     rbx
0x18002368d  pop     rbp
0x18002368e  retn
```
