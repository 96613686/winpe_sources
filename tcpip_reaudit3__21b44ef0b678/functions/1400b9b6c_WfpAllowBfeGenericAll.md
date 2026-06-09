# WfpAllowBfeGenericAll

- ea: `0x1400b9b6c`
- end: `0x1400b9df9`
- name: `WfpAllowBfeGenericAll`
- size: `653`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140179cc0`
- `0x140282180`
- `0x1402822e8`
- `0x1402825b4`

## callees

- `0x1400541c0`
- `0x1400b9b6c`
- `0x1400b9f3c`
- `0x1400be690`
- `0x1401bf4d0`

## import_xrefs

- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1400b9d52`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1400b9d52`
- `ntoskrnl!RtlCreateAcl` at `0x1400b9cdc`
- `ntoskrnl!RtlCreateAcl` at `0x1400b9cdc`
- `ntoskrnl!RtlLengthSid` at `0x1400b9c9e`
- `ntoskrnl!RtlLengthSid` at `0x1400b9c9e`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1400b9d2c`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1400b9d2c`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400b9d0a`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400b9d0a`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400b9c11`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400b9c29`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400b9c41`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400b9c59`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400b9c71`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400b9c89`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400b9c11`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400b9c29`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400b9c41`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400b9c59`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400b9c71`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400b9c89`
- `ntoskrnl!RtlInitializeSid` at `0x1400b9c00`
- `ntoskrnl!RtlInitializeSid` at `0x1400b9c00`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1400b9bc4`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1400b9bc4`
- `ntoskrnl!ObSetSecurityObjectByPointer` at `0x1400b9d6e`
- `ntoskrnl!ObSetSecurityObjectByPointer` at `0x1400b9d6e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b9d9d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b9db3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b9d9d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b9db3`

## string_xrefs

- `0x1400b9d1a`: `RtlAddAccessAllowedAce`
- `0x1400b9d3c`: `RtlCreateSecurityDescriptor`
- `0x1400b9d7e`: `RtlSetDaclSecurityDescriptor`
- `0x1400b9cec`: `RtlCreateAcl`

## pseudocode

```c
__int64 __fastcall WfpAllowBfeGenericAll(__int64 a1)
{
  ULONG v2; // eax
  __int64 v3; // rax
  PSID v4; // rsi
  __int64 v5; // rbx
  __int64 v6; // r15
  NTSTATUS v7; // eax
  __int64 v8; // rcx
  const char *v9; // rdx
  PACL Acl; // [rsp+20h] [rbp-50h] BYREF
  PSID Sid; // [rsp+28h] [rbp-48h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+30h] [rbp-40h] BYREF
  __int64 v14; // [rsp+50h] [rbp-20h]
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+58h] [rbp-18h] BYREF

  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  Sid = 0;
  Acl = 0;
  v14 = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  v2 = RtlLengthRequiredSid(6u);
  v3 = WfpPoolAllocQualified(v2, 256, 1146320710, &Sid);
  v4 = Sid;
  v5 = v3;
  if ( v3 )
    goto LABEL_15;
  RtlInitializeSid(Sid, &IdentifierAuthority, 6u);
  *RtlSubAuthoritySid(v4, 0) = 80;
  *RtlSubAuthoritySid(v4, 1u) = 1383147646;
  *RtlSubAuthoritySid(v4, 2u) = 27650227;
  *RtlSubAuthoritySid(v4, 3u) = -1584301238;
  *RtlSubAuthoritySid(v4, 4u) = 1662982300;
  *RtlSubAuthoritySid(v4, 5u) = 1023958487;
  v6 = RtlLengthSid(v4) + 16;
  v5 = WfpPoolAllocQualified(v6, 256, 1146320710, &Acl);
  if ( !v5 )
  {
    v7 = RtlCreateAcl(Acl, v6, 2u);
    if ( v7 < 0 )
    {
      v9 = "RtlCreateAcl";
LABEL_12:
      v5 = WfpReportSysErrorAsNtStatus(v8, v9, (unsigned int)v7);
      goto LABEL_13;
    }
    v7 = RtlAddAccessAllowedAce(Acl, 2u, 0x10000000u, v4);
    if ( v7 < 0 )
    {
      v9 = "RtlAddAccessAllowedAce";
      goto LABEL_12;
    }
    v7 = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
    if ( v7 < 0 )
    {
      v9 = "RtlCreateSecurityDescriptor";
      goto LABEL_12;
    }
    v7 = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, Acl, 0);
    if ( v7 < 0 || (v7 = ObSetSecurityObjectByPointer(a1, 4, SecurityDescriptor), v7 < 0) )
    {
      v9 = "RtlSetDaclSecurityDescriptor";
      goto LABEL_12;
    }
  }
LABEL_13:
  if ( Acl )
    ExFreePoolWithTag(Acl, 0);
LABEL_15:
  if ( v4 )
    ExFreePoolWithTag(v4, 0);
  if ( v5 )
    WfpReportError(v5, "WfpAllowBfeGenericAll");
  return v5;
}

```

## disassembly

```asm
0x1400b9b6c  mov     [rsp-18h+arg_8], rbx
0x1400b9b71  mov     [rsp-18h+arg_10], rsi
0x1400b9b76  push    rbp
0x1400b9b77  push    r14
0x1400b9b79  push    r15
0x1400b9b7b  mov     rbp, rsp
0x1400b9b7e  sub     rsp, 70h
0x1400b9b82  mov     rax, cs:__security_cookie
0x1400b9b89  xor     rax, rsp
0x1400b9b8c  mov     [rbp+var_10], rax
0x1400b9b90  xor     eax, eax
0x1400b9b92  mov     dword ptr [rbp+IdentifierAuthority.Value], 0
0x1400b9b99  xorps   xmm0, xmm0
0x1400b9b9c  mov     word ptr [rbp+IdentifierAuthority.Value+4], 500h
0x1400b9ba2  mov     r14, rcx
0x1400b9ba5  mov     [rbp+Sid], 0
0x1400b9bad  mov     [rbp+Acl], 0
0x1400b9bb5  lea     ecx, [rax+6]; SubAuthorityCount
0x1400b9bb8  mov     [rbp+var_20], rax
0x1400b9bbc  movups  [rbp+SecurityDescriptor], xmm0
0x1400b9bc0  movups  [rbp+var_30], xmm0
0x1400b9bc4  call    cs:__imp_RtlLengthRequiredSid
0x1400b9bcb  nop     dword ptr [rax+rax+00h]
0x1400b9bd0  mov     ecx, eax
0x1400b9bd2  lea     r9, [rbp+Sid]
0x1400b9bd6  mov     edx, 100h
0x1400b9bdb  mov     r8d, 44537746h
0x1400b9be1  call    WfpPoolAllocQualified
0x1400b9be6  mov     rsi, [rbp+Sid]
0x1400b9bea  mov     rbx, rax
0x1400b9bed  test    rax, rax
0x1400b9bf0  jnz     loc_1400B9DA9
0x1400b9bf6  mov     r8b, 6; SubAuthorityCount
0x1400b9bf9  lea     rdx, [rbp+IdentifierAuthority]; IdentifierAuthority
0x1400b9bfd  mov     rcx, rsi; Sid
0x1400b9c00  call    cs:__imp_RtlInitializeSid
0x1400b9c07  nop     dword ptr [rax+rax+00h]
0x1400b9c0c  xor     edx, edx; SubAuthority
0x1400b9c0e  mov     rcx, rsi; Sid
0x1400b9c11  call    cs:__imp_RtlSubAuthoritySid
0x1400b9c18  nop     dword ptr [rax+rax+00h]
0x1400b9c1d  lea     edx, [rbx+1]; SubAuthority
0x1400b9c20  mov     rcx, rsi; Sid
0x1400b9c23  mov     dword ptr [rax], 50h ; 'P'
0x1400b9c29  call    cs:__imp_RtlSubAuthoritySid
0x1400b9c30  nop     dword ptr [rax+rax+00h]
0x1400b9c35  lea     edx, [rbx+2]; SubAuthority
0x1400b9c38  mov     rcx, rsi; Sid
0x1400b9c3b  mov     dword ptr [rax], 5271287Eh
0x1400b9c41  call    cs:__imp_RtlSubAuthoritySid
0x1400b9c48  nop     dword ptr [rax+rax+00h]
0x1400b9c4d  lea     edx, [rbx+3]; SubAuthority
0x1400b9c50  mov     rcx, rsi; Sid
0x1400b9c53  mov     dword ptr [rax], 1A5E8B3h
0x1400b9c59  call    cs:__imp_RtlSubAuthoritySid
0x1400b9c60  nop     dword ptr [rax+rax+00h]
0x1400b9c65  lea     edx, [rbx+4]; SubAuthority
0x1400b9c68  mov     rcx, rsi; Sid
0x1400b9c6b  mov     dword ptr [rax], 0A1917B4Ah
0x1400b9c71  call    cs:__imp_RtlSubAuthoritySid
0x1400b9c78  nop     dword ptr [rax+rax+00h]
0x1400b9c7d  lea     edx, [rbx+5]; SubAuthority
0x1400b9c80  mov     rcx, rsi; Sid
0x1400b9c83  mov     dword ptr [rax], 631F189Ch
0x1400b9c89  call    cs:__imp_RtlSubAuthoritySid
0x1400b9c90  nop     dword ptr [rax+rax+00h]
0x1400b9c95  mov     rcx, rsi; Sid
0x1400b9c98  mov     dword ptr [rax], 3D085DD7h
0x1400b9c9e  call    cs:__imp_RtlLengthSid
0x1400b9ca5  nop     dword ptr [rax+rax+00h]
0x1400b9caa  lea     r9, [rbp+Acl]
0x1400b9cae  mov     edx, 100h
0x1400b9cb3  mov     r8d, 44537746h
0x1400b9cb9  lea     r15d, [rax+10h]
0x1400b9cbd  mov     ecx, r15d
0x1400b9cc0  call    WfpPoolAllocQualified
0x1400b9cc5  mov     rbx, rax
0x1400b9cc8  test    rax, rax
0x1400b9ccb  jnz     loc_1400B9D90
0x1400b9cd1  mov     rcx, [rbp+Acl]; Acl
0x1400b9cd5  lea     r8d, [rax+2]; AclRevision
0x1400b9cd9  mov     edx, r15d; AclLength
0x1400b9cdc  call    cs:__imp_RtlCreateAcl
0x1400b9ce3  nop     dword ptr [rax+rax+00h]
0x1400b9ce8  test    eax, eax
0x1400b9cea  jns     short loc_1400B9CF8
0x1400b9cec  lea     rdx, aRtlcreateacl; "RtlCreateAcl"
0x1400b9cf3  jmp     loc_1400B9D85
0x1400b9cf8  mov     rcx, [rbp+Acl]; Acl
0x1400b9cfc  mov     r9, rsi; Sid
0x1400b9cff  mov     edx, 2; AceRevision
0x1400b9d04  mov     r8d, 10000000h; AccessMask
0x1400b9d0a  call    cs:__imp_RtlAddAccessAllowedAce
0x1400b9d11  nop     dword ptr [rax+rax+00h]
0x1400b9d16  test    eax, eax
0x1400b9d18  jns     short loc_1400B9D23
0x1400b9d1a  lea     rdx, aRtladdaccessal; "RtlAddAccessAllowedAce"
0x1400b9d21  jmp     short loc_1400B9D85
0x1400b9d23  mov     edx, 1; Revision
0x1400b9d28  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1400b9d2c  call    cs:__imp_RtlCreateSecurityDescriptor
0x1400b9d33  nop     dword ptr [rax+rax+00h]
0x1400b9d38  test    eax, eax
0x1400b9d3a  jns     short loc_1400B9D45
0x1400b9d3c  lea     rdx, aRtlcreatesecur; "RtlCreateSecurityDescriptor"
0x1400b9d43  jmp     short loc_1400B9D85
0x1400b9d45  mov     r8, [rbp+Acl]; Dacl
0x1400b9d49  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1400b9d4d  xor     r9d, r9d; DaclDefaulted
0x1400b9d50  mov     dl, 1; DaclPresent
0x1400b9d52  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1400b9d59  nop     dword ptr [rax+rax+00h]
0x1400b9d5e  test    eax, eax
0x1400b9d60  js      short loc_1400B9D7E
0x1400b9d62  lea     r8, [rbp+SecurityDescriptor]
0x1400b9d66  mov     edx, 4
0x1400b9d6b  mov     rcx, r14
0x1400b9d6e  call    cs:__imp_ObSetSecurityObjectByPointer
0x1400b9d75  nop     dword ptr [rax+rax+00h]
0x1400b9d7a  test    eax, eax
0x1400b9d7c  jns     short loc_1400B9D90
0x1400b9d7e  lea     rdx, aRtlsetdaclsecu; "RtlSetDaclSecurityDescriptor"
0x1400b9d85  mov     r8d, eax
0x1400b9d88  call    WfpReportSysErrorAsNtStatus
0x1400b9d8d  mov     rbx, rax
0x1400b9d90  cmp     [rbp+Acl], 0
0x1400b9d95  jz      short loc_1400B9DA9
0x1400b9d97  mov     rcx, [rbp+Acl]; P
0x1400b9d9b  xor     edx, edx; Tag
0x1400b9d9d  call    cs:__imp_ExFreePoolWithTag
0x1400b9da4  nop     dword ptr [rax+rax+00h]
0x1400b9da9  test    rsi, rsi
0x1400b9dac  jz      short loc_1400B9DBF
0x1400b9dae  xor     edx, edx; Tag
0x1400b9db0  mov     rcx, rsi; P
0x1400b9db3  call    cs:__imp_ExFreePoolWithTag
0x1400b9dba  nop     dword ptr [rax+rax+00h]
0x1400b9dbf  test    rbx, rbx
0x1400b9dc2  jz      short loc_1400B9DD3
0x1400b9dc4  lea     rdx, aWfpallowbfegen; "WfpAllowBfeGenericAll"
0x1400b9dcb  mov     rcx, rbx
0x1400b9dce  call    WfpReportError
0x1400b9dd3  mov     rax, rbx
0x1400b9dd6  mov     rcx, [rbp+var_10]
0x1400b9dda  xor     rcx, rsp; StackCookie
0x1400b9ddd  call    __security_check_cookie
0x1400b9de2  lea     r11, [rsp+70h+var_s0]
0x1400b9de7  mov     rbx, [r11+28h]
0x1400b9deb  mov     rsi, [r11+30h]
0x1400b9def  mov     rsp, r11
0x1400b9df2  pop     r15
0x1400b9df4  pop     r14
0x1400b9df6  pop     rbp
0x1400b9df7  retn
```
