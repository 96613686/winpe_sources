# WfpAllowBfeGenericAll

- ea: `0x1400c369c`
- end: `0x1400c3929`
- name: `WfpAllowBfeGenericAll`
- size: `653`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `4`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14017b880`
- `0x140286150`
- `0x1402862b8`
- `0x140286584`

## callees

- `0x140014a90`
- `0x1400c369c`
- `0x1400c3a6c`
- `0x1400c7fe0`
- `0x1401c0fd0`

## import_xrefs

- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1400c3882`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1400c3882`
- `ntoskrnl!RtlCreateAcl` at `0x1400c380c`
- `ntoskrnl!RtlCreateAcl` at `0x1400c380c`
- `ntoskrnl!RtlLengthSid` at `0x1400c37ce`
- `ntoskrnl!RtlLengthSid` at `0x1400c37ce`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1400c385c`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1400c385c`
- `ntoskrnl!ObSetSecurityObjectByPointer` at `0x1400c389e`
- `ntoskrnl!ObSetSecurityObjectByPointer` at `0x1400c389e`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400c383a`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400c383a`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400c3741`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400c3759`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400c3771`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400c3789`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400c37a1`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400c37b9`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400c3741`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400c3759`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400c3771`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400c3789`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400c37a1`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400c37b9`
- `ntoskrnl!RtlInitializeSid` at `0x1400c3730`
- `ntoskrnl!RtlInitializeSid` at `0x1400c3730`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1400c36f4`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1400c36f4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c38cd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c38e3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c38cd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c38e3`

## string_xrefs

- `0x1400c384a`: `RtlAddAccessAllowedAce`
- `0x1400c381c`: `RtlCreateAcl`
- `0x1400c38ae`: `RtlSetDaclSecurityDescriptor`
- `0x1400c386c`: `RtlCreateSecurityDescriptor`

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
0x1400c369c  mov     [rsp-18h+arg_8], rbx
0x1400c36a1  mov     [rsp-18h+arg_10], rsi
0x1400c36a6  push    rbp
0x1400c36a7  push    r14
0x1400c36a9  push    r15
0x1400c36ab  mov     rbp, rsp
0x1400c36ae  sub     rsp, 70h
0x1400c36b2  mov     rax, cs:__security_cookie
0x1400c36b9  xor     rax, rsp
0x1400c36bc  mov     [rbp+var_10], rax
0x1400c36c0  xor     eax, eax
0x1400c36c2  mov     dword ptr [rbp+IdentifierAuthority.Value], 0
0x1400c36c9  xorps   xmm0, xmm0
0x1400c36cc  mov     word ptr [rbp+IdentifierAuthority.Value+4], 500h
0x1400c36d2  mov     r14, rcx
0x1400c36d5  mov     [rbp+Sid], 0
0x1400c36dd  mov     [rbp+Acl], 0
0x1400c36e5  lea     ecx, [rax+6]; SubAuthorityCount
0x1400c36e8  mov     [rbp+var_20], rax
0x1400c36ec  movups  [rbp+SecurityDescriptor], xmm0
0x1400c36f0  movups  [rbp+var_30], xmm0
0x1400c36f4  call    cs:__imp_RtlLengthRequiredSid
0x1400c36fb  nop     dword ptr [rax+rax+00h]
0x1400c3700  mov     ecx, eax
0x1400c3702  lea     r9, [rbp+Sid]
0x1400c3706  mov     edx, 100h
0x1400c370b  mov     r8d, 44537746h
0x1400c3711  call    WfpPoolAllocQualified
0x1400c3716  mov     rsi, [rbp+Sid]
0x1400c371a  mov     rbx, rax
0x1400c371d  test    rax, rax
0x1400c3720  jnz     loc_1400C38D9
0x1400c3726  mov     r8b, 6; SubAuthorityCount
0x1400c3729  lea     rdx, [rbp+IdentifierAuthority]; IdentifierAuthority
0x1400c372d  mov     rcx, rsi; Sid
0x1400c3730  call    cs:__imp_RtlInitializeSid
0x1400c3737  nop     dword ptr [rax+rax+00h]
0x1400c373c  xor     edx, edx; SubAuthority
0x1400c373e  mov     rcx, rsi; Sid
0x1400c3741  call    cs:__imp_RtlSubAuthoritySid
0x1400c3748  nop     dword ptr [rax+rax+00h]
0x1400c374d  lea     edx, [rbx+1]; SubAuthority
0x1400c3750  mov     rcx, rsi; Sid
0x1400c3753  mov     dword ptr [rax], 50h ; 'P'
0x1400c3759  call    cs:__imp_RtlSubAuthoritySid
0x1400c3760  nop     dword ptr [rax+rax+00h]
0x1400c3765  lea     edx, [rbx+2]; SubAuthority
0x1400c3768  mov     rcx, rsi; Sid
0x1400c376b  mov     dword ptr [rax], 5271287Eh
0x1400c3771  call    cs:__imp_RtlSubAuthoritySid
0x1400c3778  nop     dword ptr [rax+rax+00h]
0x1400c377d  lea     edx, [rbx+3]; SubAuthority
0x1400c3780  mov     rcx, rsi; Sid
0x1400c3783  mov     dword ptr [rax], 1A5E8B3h
0x1400c3789  call    cs:__imp_RtlSubAuthoritySid
0x1400c3790  nop     dword ptr [rax+rax+00h]
0x1400c3795  lea     edx, [rbx+4]; SubAuthority
0x1400c3798  mov     rcx, rsi; Sid
0x1400c379b  mov     dword ptr [rax], 0A1917B4Ah
0x1400c37a1  call    cs:__imp_RtlSubAuthoritySid
0x1400c37a8  nop     dword ptr [rax+rax+00h]
0x1400c37ad  lea     edx, [rbx+5]; SubAuthority
0x1400c37b0  mov     rcx, rsi; Sid
0x1400c37b3  mov     dword ptr [rax], 631F189Ch
0x1400c37b9  call    cs:__imp_RtlSubAuthoritySid
0x1400c37c0  nop     dword ptr [rax+rax+00h]
0x1400c37c5  mov     rcx, rsi; Sid
0x1400c37c8  mov     dword ptr [rax], 3D085DD7h
0x1400c37ce  call    cs:__imp_RtlLengthSid
0x1400c37d5  nop     dword ptr [rax+rax+00h]
0x1400c37da  lea     r9, [rbp+Acl]
0x1400c37de  mov     edx, 100h
0x1400c37e3  mov     r8d, 44537746h
0x1400c37e9  lea     r15d, [rax+10h]
0x1400c37ed  mov     ecx, r15d
0x1400c37f0  call    WfpPoolAllocQualified
0x1400c37f5  mov     rbx, rax
0x1400c37f8  test    rax, rax
0x1400c37fb  jnz     loc_1400C38C0
0x1400c3801  mov     rcx, [rbp+Acl]; Acl
0x1400c3805  lea     r8d, [rax+2]; AclRevision
0x1400c3809  mov     edx, r15d; AclLength
0x1400c380c  call    cs:__imp_RtlCreateAcl
0x1400c3813  nop     dword ptr [rax+rax+00h]
0x1400c3818  test    eax, eax
0x1400c381a  jns     short loc_1400C3828
0x1400c381c  lea     rdx, aRtlcreateacl; "RtlCreateAcl"
0x1400c3823  jmp     loc_1400C38B5
0x1400c3828  mov     rcx, [rbp+Acl]; Acl
0x1400c382c  mov     r9, rsi; Sid
0x1400c382f  mov     edx, 2; AceRevision
0x1400c3834  mov     r8d, 10000000h; AccessMask
0x1400c383a  call    cs:__imp_RtlAddAccessAllowedAce
0x1400c3841  nop     dword ptr [rax+rax+00h]
0x1400c3846  test    eax, eax
0x1400c3848  jns     short loc_1400C3853
0x1400c384a  lea     rdx, aRtladdaccessal; "RtlAddAccessAllowedAce"
0x1400c3851  jmp     short loc_1400C38B5
0x1400c3853  mov     edx, 1; Revision
0x1400c3858  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1400c385c  call    cs:__imp_RtlCreateSecurityDescriptor
0x1400c3863  nop     dword ptr [rax+rax+00h]
0x1400c3868  test    eax, eax
0x1400c386a  jns     short loc_1400C3875
0x1400c386c  lea     rdx, aRtlcreatesecur; "RtlCreateSecurityDescriptor"
0x1400c3873  jmp     short loc_1400C38B5
0x1400c3875  mov     r8, [rbp+Acl]; Dacl
0x1400c3879  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1400c387d  xor     r9d, r9d; DaclDefaulted
0x1400c3880  mov     dl, 1; DaclPresent
0x1400c3882  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1400c3889  nop     dword ptr [rax+rax+00h]
0x1400c388e  test    eax, eax
0x1400c3890  js      short loc_1400C38AE
0x1400c3892  lea     r8, [rbp+SecurityDescriptor]
0x1400c3896  mov     edx, 4
0x1400c389b  mov     rcx, r14
0x1400c389e  call    cs:__imp_ObSetSecurityObjectByPointer
0x1400c38a5  nop     dword ptr [rax+rax+00h]
0x1400c38aa  test    eax, eax
0x1400c38ac  jns     short loc_1400C38C0
0x1400c38ae  lea     rdx, aRtlsetdaclsecu; "RtlSetDaclSecurityDescriptor"
0x1400c38b5  mov     r8d, eax
0x1400c38b8  call    WfpReportSysErrorAsNtStatus
0x1400c38bd  mov     rbx, rax
0x1400c38c0  cmp     [rbp+Acl], 0
0x1400c38c5  jz      short loc_1400C38D9
0x1400c38c7  mov     rcx, [rbp+Acl]; P
0x1400c38cb  xor     edx, edx; Tag
0x1400c38cd  call    cs:__imp_ExFreePoolWithTag
0x1400c38d4  nop     dword ptr [rax+rax+00h]
0x1400c38d9  test    rsi, rsi
0x1400c38dc  jz      short loc_1400C38EF
0x1400c38de  xor     edx, edx; Tag
0x1400c38e0  mov     rcx, rsi; P
0x1400c38e3  call    cs:__imp_ExFreePoolWithTag
0x1400c38ea  nop     dword ptr [rax+rax+00h]
0x1400c38ef  test    rbx, rbx
0x1400c38f2  jz      short loc_1400C3903
0x1400c38f4  lea     rdx, aWfpallowbfegen; "WfpAllowBfeGenericAll"
0x1400c38fb  mov     rcx, rbx
0x1400c38fe  call    WfpReportError
0x1400c3903  mov     rax, rbx
0x1400c3906  mov     rcx, [rbp+var_10]
0x1400c390a  xor     rcx, rsp; StackCookie
0x1400c390d  call    __security_check_cookie
0x1400c3912  lea     r11, [rsp+70h+var_s0]
0x1400c3917  mov     rbx, [r11+28h]
0x1400c391b  mov     rsi, [r11+30h]
0x1400c391f  mov     rsp, r11
0x1400c3922  pop     r15
0x1400c3924  pop     r14
0x1400c3926  pop     rbp
0x1400c3927  retn
```
