# SqospCreateQoSControlSecurityDescriptor

- ea: `0x140012c78`
- end: `0x1400131c6`
- name: `SqospCreateQoSControlSecurityDescriptor`
- size: `1358`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400161ec`

## callees

- `0x140008250`
- `0x1400089b8`
- `0x140008a54`
- `0x140008d20`
- `0x140009240`
- `0x140012c78`

## import_xrefs

- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1400130c4`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1400130c4`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x140013018`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x140013018`
- `ntoskrnl!RtlInitializeSid` at `0x140012ce9`
- `ntoskrnl!RtlInitializeSid` at `0x140012ce9`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140012d43`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140012d5d`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140012d43`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140012d5d`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140012fb8`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140012fb8`
- `ntoskrnl!RtlLengthSid` at `0x140012d80`
- `ntoskrnl!RtlLengthSid` at `0x140012d9f`
- `ntoskrnl!RtlLengthSid` at `0x140012db0`
- `ntoskrnl!RtlLengthSid` at `0x140012d80`
- `ntoskrnl!RtlLengthSid` at `0x140012d9f`
- `ntoskrnl!RtlLengthSid` at `0x140012db0`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140012cba`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140012cba`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140012e56`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140012eba`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140012f13`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140012e56`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140012eba`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140012f13`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140013148`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140013148`
- `ntoskrnl!RtlCreateAcl` at `0x140012de5`
- `ntoskrnl!RtlCreateAcl` at `0x140012de5`
- `ntoskrnl!RtlSetGroupSecurityDescriptor` at `0x140013078`
- `ntoskrnl!RtlSetGroupSecurityDescriptor` at `0x140013078`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140012f64`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140012f64`
- `ntoskrnl!SeExports` at `0x140012d6f`
- `ntoskrnl!SeExports` at `0x140012d8c`
- `ntoskrnl!SeExports` at `0x140012e37`
- `ntoskrnl!SeExports` at `0x140012e9b`
- `ntoskrnl!SeExports` at `0x140013000`
- `ntoskrnl!SeExports` at `0x140013060`

## pseudocode

```c
__int64 __fastcall SqospCreateQoSControlSecurityDescriptor(_QWORD *a1)
{
  ULONG v2; // eax
  void *v3; // rax
  void *v4; // r15
  NTSTATUS Acl; // ebx
  __int64 v6; // r8
  ULONG v7; // ebx
  ULONG v8; // ebx
  ULONG v9; // ebx
  struct _ACL *v10; // rax
  struct _ACL *v11; // r14
  void *v12; // rsi
  __int64 v13; // r8
  PDEVICE_OBJECT v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // r9
  ULONG v17; // eax
  void *v18; // rax
  size_t Size; // [rsp+20h] [rbp-48h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+28h] [rbp-40h] BYREF
  __int64 v22; // [rsp+48h] [rbp-20h]
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+50h] [rbp-18h] BYREF

  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  v22 = 0;
  LODWORD(Size) = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  *(_DWORD *)IdentifierAuthority.Value = 0;
  v2 = RtlLengthRequiredSid(2u);
  v3 = (void *)SqospAllocate(v2);
  v4 = v3;
  if ( v3 )
  {
    Acl = RtlInitializeSid(v3, &IdentifierAuthority, 2u);
    if ( Acl < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 47, v6, (unsigned int)Acl);
      }
      goto LABEL_67;
    }
    *RtlSubAuthoritySid(v4, 0) = 83;
    *RtlSubAuthoritySid(v4, 1u) = 0;
    v7 = RtlLengthSid(SeExports->SeLocalSystemSid);
    v8 = RtlLengthSid(SeExports->SeAliasAdminsSid) + v7;
    v9 = RtlLengthSid(v4) + 32 + v8;
    v10 = (struct _ACL *)SqospAllocate(v9);
    v11 = v10;
    if ( !v10 )
    {
      Acl = -1073741670;
LABEL_67:
      SqospFree(v4);
      return (unsigned int)Acl;
    }
    v12 = 0;
    Acl = RtlCreateAcl(v10, v9, 2u);
    if ( Acl >= 0 )
    {
      Acl = RtlAddAccessAllowedAce(v11, 2u, 0x1F01FFu, SeExports->SeLocalSystemSid);
      if ( Acl >= 0 )
      {
        Acl = RtlAddAccessAllowedAce(v11, 2u, 0x1F01FFu, SeExports->SeAliasAdminsSid);
        if ( Acl >= 0 )
        {
          Acl = RtlAddAccessAllowedAce(v11, 2u, 0x1F01FFu, v4);
          if ( Acl >= 0 )
          {
            Acl = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
            if ( Acl >= 0 )
            {
              Acl = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v11, 0);
              if ( Acl >= 0 )
              {
                Acl = RtlSetOwnerSecurityDescriptor(SecurityDescriptor, SeExports->SeLocalSystemSid, 0);
                if ( Acl >= 0 )
                {
                  Acl = RtlSetGroupSecurityDescriptor(SecurityDescriptor, SeExports->SeLocalSystemSid, 0);
                  if ( Acl >= 0 )
                  {
                    v17 = RtlLengthSecurityDescriptor(SecurityDescriptor);
                    LODWORD(Size) = v17;
                    if ( v17 >= 0x28 )
                    {
                      v18 = (void *)SqospAllocate(v17);
                      v12 = v18;
                      if ( v18 )
                      {
                        memset(v18, 0, (unsigned int)Size);
                        Acl = RtlAbsoluteToSelfRelativeSD(SecurityDescriptor, v12, (PULONG)&Size);
                        if ( Acl >= 0 )
                        {
                          *a1 = v12;
                          v12 = 0;
                          Acl = 0;
                        }
                        else
                        {
                          v14 = WPP_GLOBAL_Control;
                          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                          {
                            v15 = 57;
                            goto LABEL_15;
                          }
                        }
                      }
                      else
                      {
                        Acl = -1073741670;
                      }
                    }
                    else
                    {
                      Acl = -1073741595;
                      v14 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                      {
                        v15 = 56;
                        v16 = 3221225701LL;
                        goto LABEL_16;
                      }
                    }
                  }
                  else
                  {
                    v14 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                    {
                      v15 = 55;
                      goto LABEL_15;
                    }
                  }
                }
                else
                {
                  v14 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                  {
                    v15 = 54;
                    goto LABEL_15;
                  }
                }
              }
              else
              {
                v14 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                {
                  v15 = 53;
                  goto LABEL_15;
                }
              }
            }
            else
            {
              v14 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              {
                v15 = 52;
                goto LABEL_15;
              }
            }
          }
          else
          {
            v14 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              v15 = 51;
              goto LABEL_15;
            }
          }
        }
        else
        {
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            v15 = 50;
            goto LABEL_15;
          }
        }
      }
      else
      {
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          v15 = 49;
          goto LABEL_15;
        }
      }
    }
    else
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v15 = 48;
LABEL_15:
        v16 = (unsigned int)Acl;
LABEL_16:
        WPP_SF_D(v14->AttachedDevice, v15, v13, v16);
      }
    }
    SqospFree(v11);
    if ( v12 )
      SqospFree(v12);
    goto LABEL_67;
  }
  return (unsigned int)-1073741670;
}

```

## disassembly

```asm
0x140012c78  push    rbp
0x140012c7a  push    rbx
0x140012c7b  push    rsi
0x140012c7c  push    r12
0x140012c7e  push    r14
0x140012c80  push    r15
0x140012c82  mov     rbp, rsp
0x140012c85  sub     rsp, 68h
0x140012c89  mov     rax, cs:__security_cookie
0x140012c90  xor     rax, rsp
0x140012c93  mov     [rbp+var_10], rax
0x140012c97  xor     eax, eax
0x140012c99  mov     word ptr [rbp+IdentifierAuthority.Value+4], 500h
0x140012c9f  xorps   xmm0, xmm0
0x140012ca2  mov     [rbp+var_20], rax
0x140012ca6  mov     r12, rcx
0x140012ca9  mov     dword ptr [rbp+Size], eax
0x140012cac  movups  [rbp+SecurityDescriptor], xmm0
0x140012cb0  lea     ecx, [rax+2]; SubAuthorityCount
0x140012cb3  mov     dword ptr [rbp+IdentifierAuthority.Value], eax
0x140012cb6  movups  [rbp+var_30], xmm0
0x140012cba  call    cs:__imp_RtlLengthRequiredSid
0x140012cc1  nop     dword ptr [rax+rax+00h]
0x140012cc6  mov     ecx, eax
0x140012cc8  call    SqospAllocate
0x140012ccd  mov     r15, rax
0x140012cd0  test    rax, rax
0x140012cd3  jnz     short loc_140012CDF
0x140012cd5  mov     ebx, 0C000009Ah
0x140012cda  jmp     loc_1400131A9
0x140012cdf  mov     r8b, 2; SubAuthorityCount
0x140012ce2  lea     rdx, [rbp+IdentifierAuthority]; IdentifierAuthority
0x140012ce6  mov     rcx, r15; Sid
0x140012ce9  call    cs:__imp_RtlInitializeSid
0x140012cf0  nop     dword ptr [rax+rax+00h]
0x140012cf5  mov     ebx, eax
0x140012cf7  test    eax, eax
0x140012cf9  jns     short loc_140012D3E
0x140012cfb  mov     rcx, cs:WPP_GLOBAL_Control
0x140012d02  lea     rax, WPP_GLOBAL_Control
0x140012d09  cmp     rcx, rax
0x140012d0c  jz      loc_1400131A1
0x140012d12  mov     edx, [rcx+2Ch]
0x140012d15  test    dl, 1
0x140012d18  jz      loc_1400131A1
0x140012d1e  cmp     byte ptr [rcx+29h], 2
0x140012d22  jb      loc_1400131A1
0x140012d28  mov     rcx, [rcx+18h]
0x140012d2c  mov     edx, 2Fh ; '/'
0x140012d31  mov     r9d, ebx
0x140012d34  call    WPP_SF_D
0x140012d39  jmp     loc_1400131A1
0x140012d3e  xor     edx, edx; SubAuthority
0x140012d40  mov     rcx, r15; Sid
0x140012d43  call    cs:__imp_RtlSubAuthoritySid
0x140012d4a  nop     dword ptr [rax+rax+00h]
0x140012d4f  mov     edx, 1; SubAuthority
0x140012d54  mov     rcx, r15; Sid
0x140012d57  mov     dword ptr [rax], 53h ; 'S'
0x140012d5d  call    cs:__imp_RtlSubAuthoritySid
0x140012d64  nop     dword ptr [rax+rax+00h]
0x140012d69  mov     dword ptr [rax], 0
0x140012d6f  mov     rax, cs:__imp_SeExports
0x140012d76  mov     rcx, [rax]
0x140012d79  mov     rcx, [rcx+108h]; Sid
0x140012d80  call    cs:__imp_RtlLengthSid
0x140012d87  nop     dword ptr [rax+rax+00h]
0x140012d8c  mov     rcx, cs:__imp_SeExports
0x140012d93  mov     ebx, eax
0x140012d95  mov     rcx, [rcx]
0x140012d98  mov     rcx, [rcx+110h]; Sid
0x140012d9f  call    cs:__imp_RtlLengthSid
0x140012da6  nop     dword ptr [rax+rax+00h]
0x140012dab  mov     rcx, r15; Sid
0x140012dae  add     ebx, eax
0x140012db0  call    cs:__imp_RtlLengthSid
0x140012db7  nop     dword ptr [rax+rax+00h]
0x140012dbc  add     eax, 20h ; ' '
0x140012dbf  add     ebx, eax
0x140012dc1  mov     ecx, ebx
0x140012dc3  call    SqospAllocate
0x140012dc8  mov     r14, rax
0x140012dcb  test    rax, rax
0x140012dce  jnz     short loc_140012DDA
0x140012dd0  mov     ebx, 0C000009Ah
0x140012dd5  jmp     loc_1400131A1
0x140012dda  xor     esi, esi
0x140012ddc  mov     edx, ebx; AclLength
0x140012dde  mov     rcx, r14; Acl
0x140012de1  lea     r8d, [rsi+2]; AclRevision
0x140012de5  call    cs:__imp_RtlCreateAcl
0x140012dec  nop     dword ptr [rax+rax+00h]
0x140012df1  mov     ebx, eax
0x140012df3  test    eax, eax
0x140012df5  jns     short loc_140012E37
0x140012df7  mov     rcx, cs:WPP_GLOBAL_Control
0x140012dfe  lea     rax, WPP_GLOBAL_Control
0x140012e05  cmp     rcx, rax
0x140012e08  jz      loc_14001318C
0x140012e0e  mov     eax, [rcx+2Ch]
0x140012e11  test    al, 1
0x140012e13  jz      loc_14001318C
0x140012e19  cmp     byte ptr [rcx+29h], 2
0x140012e1d  jb      loc_14001318C
0x140012e23  lea     edx, [rsi+30h]
0x140012e26  mov     r9d, ebx
0x140012e29  mov     rcx, [rcx+18h]
0x140012e2d  call    WPP_SF_D
0x140012e32  jmp     loc_14001318C
0x140012e37  mov     rax, cs:__imp_SeExports
0x140012e3e  mov     edx, 2; AceRevision
0x140012e43  mov     r8d, 1F01FFh; AccessMask
0x140012e49  mov     rcx, r14; Acl
0x140012e4c  mov     r9, [rax]
0x140012e4f  mov     r9, [r9+108h]; Sid
0x140012e56  call    cs:__imp_RtlAddAccessAllowedAce
0x140012e5d  nop     dword ptr [rax+rax+00h]
0x140012e62  mov     ebx, eax
0x140012e64  test    eax, eax
0x140012e66  jns     short loc_140012E9B
0x140012e68  mov     rcx, cs:WPP_GLOBAL_Control
0x140012e6f  lea     rax, WPP_GLOBAL_Control
0x140012e76  cmp     rcx, rax
0x140012e79  jz      loc_14001318C
0x140012e7f  mov     eax, [rcx+2Ch]
0x140012e82  test    al, 1
0x140012e84  jz      loc_14001318C
0x140012e8a  cmp     byte ptr [rcx+29h], 2
0x140012e8e  jb      loc_14001318C
0x140012e94  mov     edx, 31h ; '1'
0x140012e99  jmp     short loc_140012E26
0x140012e9b  mov     rax, cs:__imp_SeExports
0x140012ea2  mov     edx, 2; AceRevision
0x140012ea7  mov     r8d, 1F01FFh; AccessMask
0x140012ead  mov     rcx, r14; Acl
0x140012eb0  mov     r9, [rax]
0x140012eb3  mov     r9, [r9+110h]; Sid
0x140012eba  call    cs:__imp_RtlAddAccessAllowedAce
0x140012ec1  nop     dword ptr [rax+rax+00h]
0x140012ec6  mov     ebx, eax
0x140012ec8  test    eax, eax
0x140012eca  jns     short loc_140012F02
0x140012ecc  mov     rcx, cs:WPP_GLOBAL_Control
0x140012ed3  lea     rax, WPP_GLOBAL_Control
0x140012eda  cmp     rcx, rax
0x140012edd  jz      loc_14001318C
0x140012ee3  mov     eax, [rcx+2Ch]
0x140012ee6  test    al, 1
0x140012ee8  jz      loc_14001318C
0x140012eee  cmp     byte ptr [rcx+29h], 2
0x140012ef2  jb      loc_14001318C
0x140012ef8  mov     edx, 32h ; '2'
0x140012efd  jmp     loc_140012E26
0x140012f02  mov     r9, r15; Sid
0x140012f05  mov     edx, 2; AceRevision
0x140012f0a  mov     r8d, 1F01FFh; AccessMask
0x140012f10  mov     rcx, r14; Acl
0x140012f13  call    cs:__imp_RtlAddAccessAllowedAce
0x140012f1a  nop     dword ptr [rax+rax+00h]
0x140012f1f  mov     ebx, eax
0x140012f21  test    eax, eax
0x140012f23  jns     short loc_140012F5B
0x140012f25  mov     rcx, cs:WPP_GLOBAL_Control
0x140012f2c  lea     rax, WPP_GLOBAL_Control
0x140012f33  cmp     rcx, rax
0x140012f36  jz      loc_14001318C
0x140012f3c  mov     eax, [rcx+2Ch]
0x140012f3f  test    al, 1
0x140012f41  jz      loc_14001318C
0x140012f47  cmp     byte ptr [rcx+29h], 2
0x140012f4b  jb      loc_14001318C
0x140012f51  mov     edx, 33h ; '3'
0x140012f56  jmp     loc_140012E26
0x140012f5b  mov     edx, 1; Revision
0x140012f60  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140012f64  call    cs:__imp_RtlCreateSecurityDescriptor
0x140012f6b  nop     dword ptr [rax+rax+00h]
0x140012f70  mov     ebx, eax
0x140012f72  test    eax, eax
0x140012f74  jns     short loc_140012FAC
0x140012f76  mov     rcx, cs:WPP_GLOBAL_Control
0x140012f7d  lea     rax, WPP_GLOBAL_Control
0x140012f84  cmp     rcx, rax
0x140012f87  jz      loc_14001318C
0x140012f8d  mov     eax, [rcx+2Ch]
0x140012f90  test    al, 1
0x140012f92  jz      loc_14001318C
0x140012f98  cmp     byte ptr [rcx+29h], 2
0x140012f9c  jb      loc_14001318C
0x140012fa2  mov     edx, 34h ; '4'
0x140012fa7  jmp     loc_140012E26
0x140012fac  xor     r9d, r9d; DaclDefaulted
0x140012faf  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140012fb3  mov     r8, r14; Dacl
0x140012fb6  mov     dl, 1; DaclPresent
0x140012fb8  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x140012fbf  nop     dword ptr [rax+rax+00h]
0x140012fc4  mov     ebx, eax
0x140012fc6  test    eax, eax
0x140012fc8  jns     short loc_140013000
0x140012fca  mov     rcx, cs:WPP_GLOBAL_Control
0x140012fd1  lea     rax, WPP_GLOBAL_Control
0x140012fd8  cmp     rcx, rax
0x140012fdb  jz      loc_14001318C
0x140012fe1  mov     eax, [rcx+2Ch]
0x140012fe4  test    al, 1
0x140012fe6  jz      loc_14001318C
0x140012fec  cmp     byte ptr [rcx+29h], 2
0x140012ff0  jb      loc_14001318C
0x140012ff6  mov     edx, 35h ; '5'
0x140012ffb  jmp     loc_140012E26
0x140013000  mov     rax, cs:__imp_SeExports
0x140013007  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x14001300b  xor     r8d, r8d; OwnerDefaulted
0x14001300e  mov     rdx, [rax]
0x140013011  mov     rdx, [rdx+108h]; Owner
0x140013018  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x14001301f  nop     dword ptr [rax+rax+00h]
0x140013024  mov     ebx, eax
0x140013026  test    eax, eax
0x140013028  jns     short loc_140013060
0x14001302a  mov     rcx, cs:WPP_GLOBAL_Control
0x140013031  lea     rax, WPP_GLOBAL_Control
0x140013038  cmp     rcx, rax
0x14001303b  jz      loc_14001318C
0x140013041  mov     eax, [rcx+2Ch]
0x140013044  test    al, 1
0x140013046  jz      loc_14001318C
0x14001304c  cmp     byte ptr [rcx+29h], 2
0x140013050  jb      loc_14001318C
0x140013056  mov     edx, 36h ; '6'
0x14001305b  jmp     loc_140012E26
0x140013060  mov     rax, cs:__imp_SeExports
0x140013067  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x14001306b  xor     r8d, r8d; GroupDefaulted
0x14001306e  mov     rdx, [rax]
0x140013071  mov     rdx, [rdx+108h]; Group
0x140013078  call    cs:__imp_RtlSetGroupSecurityDescriptor
0x14001307f  nop     dword ptr [rax+rax+00h]
0x140013084  mov     ebx, eax
0x140013086  test    eax, eax
0x140013088  jns     short loc_1400130C0
0x14001308a  mov     rcx, cs:WPP_GLOBAL_Control
0x140013091  lea     rax, WPP_GLOBAL_Control
0x140013098  cmp     rcx, rax
0x14001309b  jz      loc_14001318C
0x1400130a1  mov     eax, [rcx+2Ch]
0x1400130a4  test    al, 1
0x1400130a6  jz      loc_14001318C
0x1400130ac  cmp     byte ptr [rcx+29h], 2
0x1400130b0  jb      loc_14001318C
0x1400130b6  mov     edx, 37h ; '7'
0x1400130bb  jmp     loc_140012E26
0x1400130c0  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1400130c4  call    cs:__imp_RtlLengthSecurityDescriptor
0x1400130cb  nop     dword ptr [rax+rax+00h]
0x1400130d0  mov     dword ptr [rbp+Size], eax
0x1400130d3  cmp     eax, 28h ; '('
0x1400130d6  jnb     short loc_140013119
0x1400130d8  mov     ebx, 0C00000E5h
0x1400130dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400130e4  lea     rax, WPP_GLOBAL_Control
0x1400130eb  cmp     rcx, rax
0x1400130ee  jz      loc_14001318C
0x1400130f4  mov     eax, [rcx+2Ch]
0x1400130f7  test    al, 1
0x1400130f9  jz      loc_14001318C
0x1400130ff  cmp     byte ptr [rcx+29h], 2
0x140013103  jb      loc_14001318C
0x140013109  mov     edx, 38h ; '8'
0x14001310e  mov     r9d, 0C00000E5h
0x140013114  jmp     loc_140012E29
0x140013119  mov     ecx, eax
0x14001311b  call    SqospAllocate
0x140013120  mov     rsi, rax
0x140013123  test    rax, rax
0x140013126  jnz     short loc_14001312F
0x140013128  mov     ebx, 0C000009Ah
0x14001312d  jmp     short loc_14001318C
0x14001312f  mov     r8d, dword ptr [rbp+Size]; Size
0x140013133  xor     edx, edx; Val
0x140013135  mov     rcx, rsi; void *
0x140013138  call    memset
0x14001313d  lea     r8, [rbp+Size]; BufferLength
0x140013141  mov     rdx, rsi; SelfRelativeSecurityDescriptor
0x140013144  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x140013148  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x14001314f  nop     dword ptr [rax+rax+00h]
0x140013154  mov     ebx, eax
0x140013156  test    eax, eax
0x140013158  jns     short loc_140013184
0x14001315a  mov     rcx, cs:WPP_GLOBAL_Control
0x140013161  lea     rax, WPP_GLOBAL_Control
0x140013168  cmp     rcx, rax
0x14001316b  jz      short loc_14001318C
0x14001316d  mov     eax, [rcx+2Ch]
0x140013170  test    al, 1
0x140013172  jz      short loc_14001318C
0x140013174  cmp     byte ptr [rcx+29h], 2
0x140013178  jb      short loc_14001318C
  ... truncated ...
```
