# WfpAllowBfeGenericAll

- ea: `0x1400b9f4c`
- end: `0x1400ba1d9`
- name: `WfpAllowBfeGenericAll`
- size: `653`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140179b80`
- `0x140282180`
- `0x1402822e8`
- `0x1402825b4`

## callees

- `0x140053f20`
- `0x1400b9f4c`
- `0x1400ba31c`
- `0x1400be890`
- `0x1401bf390`

## import_xrefs

- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1400ba132`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1400ba132`
- `ntoskrnl!RtlCreateAcl` at `0x1400ba0bc`
- `ntoskrnl!RtlCreateAcl` at `0x1400ba0bc`
- `ntoskrnl!RtlLengthSid` at `0x1400ba07e`
- `ntoskrnl!RtlLengthSid` at `0x1400ba07e`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1400ba10c`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1400ba10c`
- `ntoskrnl!ObSetSecurityObjectByPointer` at `0x1400ba14e`
- `ntoskrnl!ObSetSecurityObjectByPointer` at `0x1400ba14e`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400ba0ea`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400ba0ea`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400b9ff1`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400ba009`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400ba021`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400ba039`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400ba051`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400ba069`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400b9ff1`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400ba009`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400ba021`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400ba039`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400ba051`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400ba069`
- `ntoskrnl!RtlInitializeSid` at `0x1400b9fe0`
- `ntoskrnl!RtlInitializeSid` at `0x1400b9fe0`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1400b9fa4`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1400b9fa4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ba17d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ba193`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ba17d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ba193`

## string_xrefs

- `0x1400ba0cc`: `RtlCreateAcl`
- `0x1400ba0fa`: `RtlAddAccessAllowedAce`
- `0x1400ba11c`: `RtlCreateSecurityDescriptor`
- `0x1400ba15e`: `RtlSetDaclSecurityDescriptor`

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
0x1400b9f4c  mov     [rsp-18h+arg_8], rbx
0x1400b9f51  mov     [rsp-18h+arg_10], rsi
0x1400b9f56  push    rbp
0x1400b9f57  push    r14
0x1400b9f59  push    r15
0x1400b9f5b  mov     rbp, rsp
0x1400b9f5e  sub     rsp, 70h
0x1400b9f62  mov     rax, cs:__security_cookie
0x1400b9f69  xor     rax, rsp
0x1400b9f6c  mov     [rbp+var_10], rax
0x1400b9f70  xor     eax, eax
0x1400b9f72  mov     dword ptr [rbp+IdentifierAuthority.Value], 0
0x1400b9f79  xorps   xmm0, xmm0
0x1400b9f7c  mov     word ptr [rbp+IdentifierAuthority.Value+4], 500h
0x1400b9f82  mov     r14, rcx
0x1400b9f85  mov     [rbp+Sid], 0
0x1400b9f8d  mov     [rbp+Acl], 0
0x1400b9f95  lea     ecx, [rax+6]; SubAuthorityCount
0x1400b9f98  mov     [rbp+var_20], rax
0x1400b9f9c  movups  [rbp+SecurityDescriptor], xmm0
0x1400b9fa0  movups  [rbp+var_30], xmm0
0x1400b9fa4  call    cs:__imp_RtlLengthRequiredSid
0x1400b9fab  nop     dword ptr [rax+rax+00h]
0x1400b9fb0  mov     ecx, eax
0x1400b9fb2  lea     r9, [rbp+Sid]
0x1400b9fb6  mov     edx, 100h
0x1400b9fbb  mov     r8d, 44537746h
0x1400b9fc1  call    WfpPoolAllocQualified
0x1400b9fc6  mov     rsi, [rbp+Sid]
0x1400b9fca  mov     rbx, rax
0x1400b9fcd  test    rax, rax
0x1400b9fd0  jnz     loc_1400BA189
0x1400b9fd6  mov     r8b, 6; SubAuthorityCount
0x1400b9fd9  lea     rdx, [rbp+IdentifierAuthority]; IdentifierAuthority
0x1400b9fdd  mov     rcx, rsi; Sid
0x1400b9fe0  call    cs:__imp_RtlInitializeSid
0x1400b9fe7  nop     dword ptr [rax+rax+00h]
0x1400b9fec  xor     edx, edx; SubAuthority
0x1400b9fee  mov     rcx, rsi; Sid
0x1400b9ff1  call    cs:__imp_RtlSubAuthoritySid
0x1400b9ff8  nop     dword ptr [rax+rax+00h]
0x1400b9ffd  lea     edx, [rbx+1]; SubAuthority
0x1400ba000  mov     rcx, rsi; Sid
0x1400ba003  mov     dword ptr [rax], 50h ; 'P'
0x1400ba009  call    cs:__imp_RtlSubAuthoritySid
0x1400ba010  nop     dword ptr [rax+rax+00h]
0x1400ba015  lea     edx, [rbx+2]; SubAuthority
0x1400ba018  mov     rcx, rsi; Sid
0x1400ba01b  mov     dword ptr [rax], 5271287Eh
0x1400ba021  call    cs:__imp_RtlSubAuthoritySid
0x1400ba028  nop     dword ptr [rax+rax+00h]
0x1400ba02d  lea     edx, [rbx+3]; SubAuthority
0x1400ba030  mov     rcx, rsi; Sid
0x1400ba033  mov     dword ptr [rax], 1A5E8B3h
0x1400ba039  call    cs:__imp_RtlSubAuthoritySid
0x1400ba040  nop     dword ptr [rax+rax+00h]
0x1400ba045  lea     edx, [rbx+4]; SubAuthority
0x1400ba048  mov     rcx, rsi; Sid
0x1400ba04b  mov     dword ptr [rax], 0A1917B4Ah
0x1400ba051  call    cs:__imp_RtlSubAuthoritySid
0x1400ba058  nop     dword ptr [rax+rax+00h]
0x1400ba05d  lea     edx, [rbx+5]; SubAuthority
0x1400ba060  mov     rcx, rsi; Sid
0x1400ba063  mov     dword ptr [rax], 631F189Ch
0x1400ba069  call    cs:__imp_RtlSubAuthoritySid
0x1400ba070  nop     dword ptr [rax+rax+00h]
0x1400ba075  mov     rcx, rsi; Sid
0x1400ba078  mov     dword ptr [rax], 3D085DD7h
0x1400ba07e  call    cs:__imp_RtlLengthSid
0x1400ba085  nop     dword ptr [rax+rax+00h]
0x1400ba08a  lea     r9, [rbp+Acl]
0x1400ba08e  mov     edx, 100h
0x1400ba093  mov     r8d, 44537746h
0x1400ba099  lea     r15d, [rax+10h]
0x1400ba09d  mov     ecx, r15d
0x1400ba0a0  call    WfpPoolAllocQualified
0x1400ba0a5  mov     rbx, rax
0x1400ba0a8  test    rax, rax
0x1400ba0ab  jnz     loc_1400BA170
0x1400ba0b1  mov     rcx, [rbp+Acl]; Acl
0x1400ba0b5  lea     r8d, [rax+2]; AclRevision
0x1400ba0b9  mov     edx, r15d; AclLength
0x1400ba0bc  call    cs:__imp_RtlCreateAcl
0x1400ba0c3  nop     dword ptr [rax+rax+00h]
0x1400ba0c8  test    eax, eax
0x1400ba0ca  jns     short loc_1400BA0D8
0x1400ba0cc  lea     rdx, aRtlcreateacl; "RtlCreateAcl"
0x1400ba0d3  jmp     loc_1400BA165
0x1400ba0d8  mov     rcx, [rbp+Acl]; Acl
0x1400ba0dc  mov     r9, rsi; Sid
0x1400ba0df  mov     edx, 2; AceRevision
0x1400ba0e4  mov     r8d, 10000000h; AccessMask
0x1400ba0ea  call    cs:__imp_RtlAddAccessAllowedAce
0x1400ba0f1  nop     dword ptr [rax+rax+00h]
0x1400ba0f6  test    eax, eax
0x1400ba0f8  jns     short loc_1400BA103
0x1400ba0fa  lea     rdx, aRtladdaccessal; "RtlAddAccessAllowedAce"
0x1400ba101  jmp     short loc_1400BA165
0x1400ba103  mov     edx, 1; Revision
0x1400ba108  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1400ba10c  call    cs:__imp_RtlCreateSecurityDescriptor
0x1400ba113  nop     dword ptr [rax+rax+00h]
0x1400ba118  test    eax, eax
0x1400ba11a  jns     short loc_1400BA125
0x1400ba11c  lea     rdx, aRtlcreatesecur; "RtlCreateSecurityDescriptor"
0x1400ba123  jmp     short loc_1400BA165
0x1400ba125  mov     r8, [rbp+Acl]; Dacl
0x1400ba129  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1400ba12d  xor     r9d, r9d; DaclDefaulted
0x1400ba130  mov     dl, 1; DaclPresent
0x1400ba132  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1400ba139  nop     dword ptr [rax+rax+00h]
0x1400ba13e  test    eax, eax
0x1400ba140  js      short loc_1400BA15E
0x1400ba142  lea     r8, [rbp+SecurityDescriptor]
0x1400ba146  mov     edx, 4
0x1400ba14b  mov     rcx, r14
0x1400ba14e  call    cs:__imp_ObSetSecurityObjectByPointer
0x1400ba155  nop     dword ptr [rax+rax+00h]
0x1400ba15a  test    eax, eax
0x1400ba15c  jns     short loc_1400BA170
0x1400ba15e  lea     rdx, aRtlsetdaclsecu; "RtlSetDaclSecurityDescriptor"
0x1400ba165  mov     r8d, eax
0x1400ba168  call    WfpReportSysErrorAsNtStatus
0x1400ba16d  mov     rbx, rax
0x1400ba170  cmp     [rbp+Acl], 0
0x1400ba175  jz      short loc_1400BA189
0x1400ba177  mov     rcx, [rbp+Acl]; P
0x1400ba17b  xor     edx, edx; Tag
0x1400ba17d  call    cs:__imp_ExFreePoolWithTag
0x1400ba184  nop     dword ptr [rax+rax+00h]
0x1400ba189  test    rsi, rsi
0x1400ba18c  jz      short loc_1400BA19F
0x1400ba18e  xor     edx, edx; Tag
0x1400ba190  mov     rcx, rsi; P
0x1400ba193  call    cs:__imp_ExFreePoolWithTag
0x1400ba19a  nop     dword ptr [rax+rax+00h]
0x1400ba19f  test    rbx, rbx
0x1400ba1a2  jz      short loc_1400BA1B3
0x1400ba1a4  lea     rdx, aWfpallowbfegen; "WfpAllowBfeGenericAll"
0x1400ba1ab  mov     rcx, rbx
0x1400ba1ae  call    WfpReportError
0x1400ba1b3  mov     rax, rbx
0x1400ba1b6  mov     rcx, [rbp+var_10]
0x1400ba1ba  xor     rcx, rsp; StackCookie
0x1400ba1bd  call    __security_check_cookie
0x1400ba1c2  lea     r11, [rsp+70h+var_s0]
0x1400ba1c7  mov     rbx, [r11+28h]
0x1400ba1cb  mov     rsi, [r11+30h]
0x1400ba1cf  mov     rsp, r11
0x1400ba1d2  pop     r15
0x1400ba1d4  pop     r14
0x1400ba1d6  pop     rbp
0x1400ba1d7  retn
```
