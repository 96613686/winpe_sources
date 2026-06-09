# HMInitializeSecurityDescriptor

- ea: `0x14014eb84`
- end: `0x14014f297`
- name: `HMInitializeSecurityDescriptor`
- size: `1811`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14014e960`
- `0x14014eaf0`

## callees

- `0x14004a0d0`
- `0x14004c720`
- `0x14004d770`
- `0x14004dfe0`
- `0x14014eb84`
- `0x140238160`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14014ec75`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014ec87`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014f007`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014f019`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014f07f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014f091`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014f0a2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014f0b4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014f0d6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014f0f2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014f104`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014f11e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014f130`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014f1ad`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014f1bf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014f1d6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014f1e8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014f202`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014f214`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014f25e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014f270`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014ec75`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014ec87`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014f007`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014f019`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014f07f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014f091`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014f0a2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014f0b4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014f0d6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014f0f2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014f104`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014f11e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014f130`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014f1ad`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014f1bf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014f1d6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014f1e8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014f202`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014f214`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014f25e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014f270`
- `ntoskrnl!SeQueryInformationToken` at `0x14014ec14`
- `ntoskrnl!SeQueryInformationToken` at `0x14014ec33`
- `ntoskrnl!SeQueryInformationToken` at `0x14014ece1`
- `ntoskrnl!SeQueryInformationToken` at `0x14014ed02`
- `ntoskrnl!SeQueryInformationToken` at `0x14014ec14`
- `ntoskrnl!SeQueryInformationToken` at `0x14014ec33`
- `ntoskrnl!SeQueryInformationToken` at `0x14014ece1`
- `ntoskrnl!SeQueryInformationToken` at `0x14014ed02`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14014ebfe`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14014ebfe`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14014ec63`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14014ecc1`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14014ed1a`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14014f18c`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14014ec63`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14014ecc1`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14014ed1a`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14014f18c`
- `ntoskrnl!SeExports` at `0x14014ed40`
- `ntoskrnl!SeExports` at `0x14014eda9`
- `ntoskrnl!RtlLengthSid` at `0x14014ed58`
- `ntoskrnl!RtlLengthSid` at `0x14014ef46`
- `ntoskrnl!RtlLengthSid` at `0x14014ed58`
- `ntoskrnl!RtlLengthSid` at `0x14014ef46`
- `ntoskrnl!RtlCreateAcl` at `0x14014ef0c`
- `ntoskrnl!RtlCreateAcl` at `0x14014ef7e`
- `ntoskrnl!RtlCreateAcl` at `0x14014ef0c`
- `ntoskrnl!RtlCreateAcl` at `0x14014ef7e`
- `ntoskrnl!RtlAddAce` at `0x14014ef37`
- `ntoskrnl!RtlAddAce` at `0x14014ef37`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14014efce`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14014efce`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14014ee1c`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14014ee1c`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14014ebe6`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14014ebe6`
- `ntoskrnl!RtlMapGenericMask` at `0x14014ed34`
- `ntoskrnl!RtlMapGenericMask` at `0x14014eec3`
- `ntoskrnl!RtlMapGenericMask` at `0x14014ed34`
- `ntoskrnl!RtlMapGenericMask` at `0x14014eec3`
- `ntoskrnl!RtlInitializeSid` at `0x14014ee57`
- `ntoskrnl!RtlInitializeSid` at `0x14014ee57`
- `ntoskrnl!RtlAddMandatoryAce` at `0x14014efab`
- `ntoskrnl!RtlAddMandatoryAce` at `0x14014efab`
- `ntoskrnl!RtlSetSaclSecurityDescriptor` at `0x14014efed`
- `ntoskrnl!RtlSetSaclSecurityDescriptor` at `0x14014efed`
- `ntoskrnl!RtlCopySid` at `0x14014ed9d`
- `ntoskrnl!RtlCopySid` at `0x14014ed9d`

## pseudocode

```c
__int64 __fastcall HMInitializeSecurityDescriptor(void *a1, struct _GENERIC_MAPPING *a2)
{
  void *v3; // r14
  void *v4; // r15
  unsigned int v5; // ecx
  PVOID v6; // rcx
  DWORD v8; // r12d
  PSID SeAliasAdminsSid; // rsi
  ULONG v10; // r13d
  unsigned __int64 v11; // rcx
  struct _ACL *v12; // rax
  struct _ACL *v13; // rbx
  struct _ACL *v14; // rax
  struct _ACL *v15; // rsi
  struct _ACL *v16; // rdi
  ULONG v17; // eax
  struct _ACL *v18; // rax
  struct _ACL *v19; // rsi
  ULONG v20; // r14d
  struct _ACL *v21; // rax
  ULONG v22; // r12d
  struct _ACL *v23; // rax
  struct _ACL *v24; // r14
  PSECURITY_DESCRIPTOR v25; // r15
  NTSTATUS v26; // eax
  PVOID v27; // rcx
  struct _ACL *v28; // rcx
  struct _ACL *v29; // rcx
  int v30; // r10d
  char *v31; // rdx
  __int64 v32; // rax
  PSID LabelSid; // [rsp+28h] [rbp-51h]
  PVOID TokenInformation; // [rsp+30h] [rbp-49h] BYREF
  DWORD AccessMask; // [rsp+38h] [rbp-41h] BYREF
  PVOID P; // [rsp+40h] [rbp-39h] BYREF
  PVOID v37; // [rsp+48h] [rbp-31h] BYREF
  ULONG v38; // [rsp+50h] [rbp-29h] BYREF
  int v39; // [rsp+54h] [rbp-25h] BYREF
  struct _SECURITY_SUBJECT_CONTEXT v40; // [rsp+58h] [rbp-21h] BYREF
  PGENERIC_MAPPING GenericMapping; // [rsp+78h] [rbp-1h]
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+80h] [rbp+7h]
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+88h] [rbp+Fh] BYREF

  GenericMapping = a2;
  SecurityDescriptor = a1;
  AccessMask = 0;
  memset(&v40, 0, sizeof(v40));
  TokenInformation = 0;
  P = 0;
  v39 = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  v37 = 0;
  if ( RtlCreateSecurityDescriptor(a1, 1u) < 0 )
    return 0;
  SeCaptureSubjectContext(&v40);
  if ( SeQueryInformationToken(v40.PrimaryToken, TokenUser, &TokenInformation) < 0 )
  {
    SeReleaseSubjectContext(&v40);
    return 0;
  }
  if ( SeQueryInformationToken(v40.PrimaryToken, TokenGroups, &P) < 0 )
  {
    SeReleaseSubjectContext(&v40);
    v6 = TokenInformation;
    goto LABEL_6;
  }
  v3 = 0;
  v4 = 0;
  v5 = 0;
  if ( !*(_DWORD *)P )
    goto LABEL_5;
  while ( 1 )
  {
    v30 = *((_DWORD *)P + 4 * v5 + 4);
    v31 = (char *)P + 16 * v5;
    if ( (v30 & 0xC0000000) == 0xC0000000 )
    {
      v3 = (void *)*((_QWORD *)v31 + 1);
      if ( v4 )
        break;
    }
    if ( (v30 & 0x20) == 0 || (v4 = (void *)*((_QWORD *)v31 + 1), !v3) )
    {
      if ( ++v5 < *(_DWORD *)P )
        continue;
    }
    if ( !v4 )
      goto LABEL_5;
    break;
  }
  if ( SeQueryInformationToken(v40.PrimaryToken, TokenSessionId, (PVOID *)&v39) < 0
    || SeQueryInformationToken(v40.PrimaryToken, TokenAppContainerSid, &v37) < 0 )
  {
LABEL_5:
    SeReleaseSubjectContext(&v40);
    ExFreePoolWithTag(TokenInformation, 0);
    v6 = P;
LABEL_6:
    ExFreePoolWithTag(v6, 0);
    return 0;
  }
  SeReleaseSubjectContext(&v40);
  AccessMask = 0x10000000;
  RtlMapGenericMask(&AccessMask, a2);
  v8 = AccessMask;
  SeAliasAdminsSid = SeExports->SeAliasAdminsSid;
  v10 = RtlLengthSid(SeAliasAdminsSid);
  v12 = (struct _ACL *)Win32AllocPoolWithQuotaZInitImpl(v11, v10 + 8, 0x65737355u);
  v13 = v12;
  if ( !v12 )
  {
    ExFreePoolWithTag(TokenInformation, 0);
    ExFreePoolWithTag(P, 0);
    goto LABEL_32;
  }
  v38 = v10 + 8;
  *(_WORD *)&v12->AclRevision = 0;
  v12->AclSize = v10 + 8;
  *(_DWORD *)&v12->AceCount = v8;
  RtlCopySid(v10, &v12[1], SeAliasAdminsSid);
  v14 = (struct _ACL *)AllocAce(v13, SeExports->SeLocalSystemSid, (__int64)&v38);
  v15 = v14;
  if ( !v14 )
  {
    ExFreePoolWithTag(TokenInformation, 0);
    ExFreePoolWithTag(P, 0);
    goto LABEL_30;
  }
  v16 = (struct _ACL *)AllocAce(v14, *(PSID *)TokenInformation, (__int64)&v38);
  if ( !v16 )
  {
    ExFreePoolWithTag(TokenInformation, 0);
    ExFreePoolWithTag(P, 0);
    v29 = v15;
    goto LABEL_31;
  }
  v17 = RtlLengthRequiredSid(3u);
  v18 = (struct _ACL *)Win32AllocPoolZInitImpl(0x100u, v17, 0x65737355u);
  v13 = v18;
  if ( !v18 )
  {
    ExFreePoolWithTag(TokenInformation, 0);
    ExFreePoolWithTag(P, 0);
    v29 = v16;
    goto LABEL_31;
  }
  if ( RtlInitializeSid(v18, &IdentifierAuthority, 3u) < 0 )
    goto LABEL_49;
  v13[1] = (struct _ACL)90LL;
  *(_DWORD *)&v13[2].AclRevision = v39;
  v19 = (struct _ACL *)AllocAce(v16, v13, (__int64)&v38);
  if ( !v19 )
    goto LABEL_49;
  if ( *(_QWORD *)v37 )
  {
    v32 = AllocAce(v19, *(PSID *)v37, (__int64)&v38);
    if ( !v32 )
      goto LABEL_34;
    v19 = (struct _ACL *)v32;
  }
  AccessMask = -1073741824;
  RtlMapGenericMask(&AccessMask, GenericMapping);
  if ( !v3 )
  {
    v16 = v19;
    goto LABEL_21;
  }
  v16 = (struct _ACL *)AllocAce(v19, v3, (__int64)&v38);
  if ( !v16 )
  {
LABEL_34:
    ExFreePoolWithTag(TokenInformation, 0);
    ExFreePoolWithTag(P, 0);
LABEL_53:
    v28 = v19;
    goto LABEL_29;
  }
LABEL_21:
  v20 = v38 + 8;
  v21 = (struct _ACL *)Win32AllocPoolZInitImpl(0x100u, v38 + 8, 0x65737355u);
  v19 = v21;
  if ( !v21 )
  {
LABEL_49:
    ExFreePoolWithTag(TokenInformation, 0);
    ExFreePoolWithTag(P, 0);
    v28 = v16;
    goto LABEL_29;
  }
  if ( RtlCreateAcl(v21, v20, 2u) < 0
    || (RtlAddAce(v19, 2u, 0, v16, v19->AclSize - 8),
        v22 = RtlLengthSid(v4) + 16,
        v23 = (struct _ACL *)Win32AllocPoolZInitImpl(0x100u, v22, 0x65737355u),
        (v24 = v23) == 0) )
  {
    ExFreePoolWithTag(TokenInformation, 0);
    ExFreePoolWithTag(P, 0);
    GreDeleteFastMutex(v16);
    goto LABEL_53;
  }
  if ( RtlCreateAcl(v23, v22, 2u) < 0
    || (LODWORD(LabelSid) = 7, RtlAddMandatoryAce(v24, 2u, 0, (ULONG)v4, 0x11u, LabelSid) < 0)
    || (v25 = SecurityDescriptor, RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v19, 0) < 0) )
  {
    v27 = TokenInformation;
    goto LABEL_28;
  }
  v26 = RtlSetSaclSecurityDescriptor(v25, 1u, v24, 0);
  v27 = TokenInformation;
  if ( v26 < 0 )
  {
LABEL_28:
    ExFreePoolWithTag(v27, 0);
    ExFreePoolWithTag(P, 0);
    GreDeleteFastMutex(v16);
    GreDeleteFastMutex(v19);
    v28 = v24;
LABEL_29:
    GreDeleteFastMutex(v28);
LABEL_30:
    v29 = v13;
LABEL_31:
    GreDeleteFastMutex(v29);
LABEL_32:
    v6 = v37;
    goto LABEL_6;
  }
  ExFreePoolWithTag(TokenInformation, 0);
  ExFreePoolWithTag(P, 0);
  GreDeleteFastMutex(v16);
  GreDeleteFastMutex(v13);
  ExFreePoolWithTag(v37, 0);
  return 1;
}

```

## disassembly

```asm
0x14014eb84  mov     [rsp-8+arg_10], rbx
0x14014eb89  push    rbp
0x14014eb8a  push    rsi
0x14014eb8b  push    rdi
0x14014eb8c  push    r12
0x14014eb8e  push    r13
0x14014eb90  push    r14
0x14014eb92  push    r15
0x14014eb94  lea     rbp, [rsp-27h]
0x14014eb99  sub     rsp, 0A0h
0x14014eba0  mov     rax, cs:__security_cookie
0x14014eba7  xor     rax, rsp
0x14014ebaa  mov     [rbp+57h+var_40], rax
0x14014ebae  xor     edi, edi
0x14014ebb0  mov     [rbp+57h+GenericMapping], rdx
0x14014ebb4  xorps   xmm0, xmm0
0x14014ebb7  mov     [rbp+57h+SecurityDescriptor], rcx
0x14014ebbb  mov     rbx, rdx
0x14014ebbe  mov     [rbp+57h+AccessMask], edi
0x14014ebc1  movups  xmmword ptr [rbp+57h+var_78], xmm0
0x14014ebc5  lea     esi, [rdi+1]
0x14014ebc8  mov     [rbp+57h+TokenInformation], rdi
0x14014ebcc  mov     edx, esi; Revision
0x14014ebce  mov     [rbp+57h+P], rdi
0x14014ebd2  movups  xmmword ptr [rbp+57h+var_78+10h], xmm0
0x14014ebd6  mov     dword ptr [rbp+57h+var_80+4], edi
0x14014ebd9  mov     dword ptr [rbp+57h+IdentifierAuthority.Value], edi
0x14014ebdc  mov     word ptr [rbp+57h+IdentifierAuthority.Value+4], 500h
0x14014ebe2  mov     [rbp+57h+var_88], rdi
0x14014ebe6  call    cs:__imp_RtlCreateSecurityDescriptor
0x14014ebed  nop     dword ptr [rax+rax+00h]
0x14014ebf2  test    eax, eax
0x14014ebf4  js      loc_14014EC93
0x14014ebfa  lea     rcx, [rbp+57h+var_78]; SubjectContext
0x14014ebfe  call    cs:__imp_SeCaptureSubjectContext
0x14014ec05  nop     dword ptr [rax+rax+00h]
0x14014ec0a  mov     rcx, qword ptr [rbp+57h+var_78+10h]; Token
0x14014ec0e  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x14014ec12  mov     edx, esi; TokenInformationClass
0x14014ec14  call    cs:__imp_SeQueryInformationToken
0x14014ec1b  nop     dword ptr [rax+rax+00h]
0x14014ec20  test    eax, eax
0x14014ec22  js      loc_14014ECBD
0x14014ec28  mov     rcx, qword ptr [rbp+57h+var_78+10h]; Token
0x14014ec2c  lea     r8, [rbp+57h+P]; TokenInformation
0x14014ec30  lea     edx, [rdi+2]; TokenInformationClass
0x14014ec33  call    cs:__imp_SeQueryInformationToken
0x14014ec3a  nop     dword ptr [rax+rax+00h]
0x14014ec3f  test    eax, eax
0x14014ec41  js      loc_14014F188
0x14014ec47  mov     r8, [rbp+57h+P]
0x14014ec4b  mov     r14d, edi
0x14014ec4e  mov     r15d, edi
0x14014ec51  mov     ecx, edi
0x14014ec53  mov     r9d, [r8]
0x14014ec56  test    r9d, r9d
0x14014ec59  jnz     loc_14014F1A1
0x14014ec5f  lea     rcx, [rbp+57h+var_78]; SubjectContext
0x14014ec63  call    cs:__imp_SeReleaseSubjectContext
0x14014ec6a  nop     dword ptr [rax+rax+00h]
0x14014ec6f  mov     rcx, [rbp+57h+TokenInformation]; P
0x14014ec73  xor     edx, edx; Tag
0x14014ec75  call    cs:__imp_ExFreePoolWithTag
0x14014ec7c  nop     dword ptr [rax+rax+00h]
0x14014ec81  mov     rcx, [rbp+57h+P]; P
0x14014ec85  xor     edx, edx; Tag
0x14014ec87  call    cs:__imp_ExFreePoolWithTag
0x14014ec8e  nop     dword ptr [rax+rax+00h]
0x14014ec93  xor     eax, eax
0x14014ec95  mov     rcx, [rbp+57h+var_40]
0x14014ec99  xor     rcx, rsp; StackCookie
0x14014ec9c  call    __security_check_cookie
0x14014eca1  mov     rbx, [rsp+0D0h+arg_10]
0x14014eca9  add     rsp, 0A0h
0x14014ecb0  pop     r15
0x14014ecb2  pop     r14
0x14014ecb4  pop     r13
0x14014ecb6  pop     r12
0x14014ecb8  pop     rdi
0x14014ecb9  pop     rsi
0x14014ecba  pop     rbp
0x14014ecbb  retn
0x14014ecbd  lea     rcx, [rbp+57h+var_78]; SubjectContext
0x14014ecc1  call    cs:__imp_SeReleaseSubjectContext
0x14014ecc8  nop     dword ptr [rax+rax+00h]
0x14014eccd  jmp     short loc_14014EC93
0x14014eccf  test    r15, r15
0x14014ecd2  jz      short loc_14014EC5F
0x14014ecd4  mov     rcx, qword ptr [rbp+57h+var_78+10h]; Token
0x14014ecd8  lea     r8, [rbp+57h+var_80+4]; TokenInformation
0x14014ecdc  mov     edx, 0Ch; TokenInformationClass
0x14014ece1  call    cs:__imp_SeQueryInformationToken
0x14014ece8  nop     dword ptr [rax+rax+00h]
0x14014eced  test    eax, eax
0x14014ecef  js      loc_14014EC5F
0x14014ecf5  mov     rcx, qword ptr [rbp+57h+var_78+10h]; Token
0x14014ecf9  lea     r8, [rbp+57h+var_88]; TokenInformation
0x14014ecfd  mov     edx, 1Fh; TokenInformationClass
0x14014ed02  call    cs:__imp_SeQueryInformationToken
0x14014ed09  nop     dword ptr [rax+rax+00h]
0x14014ed0e  lea     rcx, [rbp+57h+var_78]; SubjectContext
0x14014ed12  test    eax, eax
0x14014ed14  js      loc_14014EC63
0x14014ed1a  call    cs:__imp_SeReleaseSubjectContext
0x14014ed21  nop     dword ptr [rax+rax+00h]
0x14014ed26  mov     rdx, rbx; GenericMapping
0x14014ed29  mov     [rbp+57h+AccessMask], 10000000h
0x14014ed30  lea     rcx, [rbp+57h+AccessMask]; AccessMask
0x14014ed34  call    cs:__imp_RtlMapGenericMask
0x14014ed3b  nop     dword ptr [rax+rax+00h]
0x14014ed40  mov     rax, cs:__imp_SeExports
0x14014ed47  mov     r12d, [rbp+57h+AccessMask]
0x14014ed4b  mov     rcx, [rax]
0x14014ed4e  mov     rsi, [rcx+110h]
0x14014ed55  mov     rcx, rsi; Sid
0x14014ed58  call    cs:__imp_RtlLengthSid
0x14014ed5f  nop     dword ptr [rax+rax+00h]
0x14014ed64  mov     r8d, 65737355h; unsigned int
0x14014ed6a  mov     r13d, eax
0x14014ed6d  lea     edi, [rax+8]
0x14014ed70  mov     edx, edi; unsigned __int64
0x14014ed72  call    ?Win32AllocPoolWithQuotaZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolWithQuotaZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x14014ed77  mov     rbx, rax
0x14014ed7a  test    rax, rax
0x14014ed7d  jz      loc_14014F118
0x14014ed83  lea     rdx, [rax+8]; DestinationSid
0x14014ed87  mov     dword ptr [rbp+57h+var_80], edi
0x14014ed8a  mov     r8, rsi; SourceSid
0x14014ed8d  mov     word ptr [rax], 0
0x14014ed92  mov     ecx, r13d; DestinationSidLength
0x14014ed95  mov     [rax+2], di
0x14014ed99  mov     [rax+4], r12d
0x14014ed9d  call    cs:__imp_RtlCopySid
0x14014eda4  nop     dword ptr [rax+rax+00h]
0x14014eda9  mov     rcx, cs:__imp_SeExports
0x14014edb0  xor     r8d, r8d
0x14014edb3  mov     r9d, [rbp+57h+AccessMask]
0x14014edb7  xor     edx, edx
0x14014edb9  mov     rax, [rcx]
0x14014edbc  lea     rcx, [rbp+57h+var_80]
0x14014edc0  mov     [rsp+0D0h+LabelSid], rcx; __int64
0x14014edc5  mov     rcx, rbx; Buffer
0x14014edc8  mov     rax, [rax+108h]
0x14014edcf  mov     qword ptr [rsp+0D0h+AceListLength], rax; Sid
0x14014edd4  call    AllocAce
0x14014edd9  xor     edx, edx; Tag
0x14014eddb  mov     rsi, rax
0x14014edde  test    rax, rax
0x14014ede1  jz      loc_14014F1A9
0x14014ede7  mov     r9d, [rbp+57h+AccessMask]
0x14014edeb  lea     rax, [rbp+57h+var_80]
0x14014edef  mov     [rsp+0D0h+LabelSid], rax; __int64
0x14014edf4  xor     r8d, r8d
0x14014edf7  mov     rax, [rbp+57h+TokenInformation]
0x14014edfb  mov     rcx, [rax]
0x14014edfe  mov     qword ptr [rsp+0D0h+AceListLength], rcx; Sid
0x14014ee03  mov     rcx, rsi; Buffer
0x14014ee06  call    AllocAce
0x14014ee0b  mov     rdi, rax
0x14014ee0e  test    rax, rax
0x14014ee11  jz      loc_14014F0EC
0x14014ee17  mov     ecx, 3; SubAuthorityCount
0x14014ee1c  call    cs:__imp_RtlLengthRequiredSid
0x14014ee23  nop     dword ptr [rax+rax+00h]
0x14014ee28  mov     r13d, 65737355h
0x14014ee2e  mov     r12d, 100h
0x14014ee34  mov     edx, eax; unsigned __int64
0x14014ee36  mov     r8d, r13d; unsigned int
0x14014ee39  mov     ecx, r12d; unsigned __int64
0x14014ee3c  call    ?Win32AllocPoolZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x14014ee41  mov     rbx, rax
0x14014ee44  test    rax, rax
0x14014ee47  jz      loc_14014F1D0
0x14014ee4d  mov     r8b, 3; SubAuthorityCount
0x14014ee50  lea     rdx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x14014ee54  mov     rcx, rax; Sid
0x14014ee57  call    cs:__imp_RtlInitializeSid
0x14014ee5e  nop     dword ptr [rax+rax+00h]
0x14014ee63  xor     edx, edx
0x14014ee65  test    eax, eax
0x14014ee67  js      loc_14014F1FE
0x14014ee6d  mov     qword ptr [rbx+8], 5Ah ; 'Z'
0x14014ee75  xor     r8d, r8d
0x14014ee78  mov     eax, dword ptr [rbp+57h+var_80+4]
0x14014ee7b  mov     rcx, rdi; Buffer
0x14014ee7e  mov     [rbx+10h], eax
0x14014ee81  lea     rax, [rbp+57h+var_80]
0x14014ee85  mov     r9d, [rbp+57h+AccessMask]
0x14014ee89  mov     [rsp+0D0h+LabelSid], rax; __int64
0x14014ee8e  mov     qword ptr [rsp+0D0h+AceListLength], rbx; Sid
0x14014ee93  call    AllocAce
0x14014ee98  mov     rsi, rax
0x14014ee9b  test    rax, rax
0x14014ee9e  jz      loc_14014F1FC
0x14014eea4  mov     rax, [rbp+57h+var_88]
0x14014eea8  mov     rcx, [rax]
0x14014eeab  test    rcx, rcx
0x14014eeae  jnz     loc_14014F228
0x14014eeb4  mov     rdx, [rbp+57h+GenericMapping]; GenericMapping
0x14014eeb8  lea     rcx, [rbp+57h+AccessMask]; AccessMask
0x14014eebc  mov     [rbp+57h+AccessMask], 0C0000000h
0x14014eec3  call    cs:__imp_RtlMapGenericMask
0x14014eeca  nop     dword ptr [rax+rax+00h]
0x14014eecf  test    r14, r14
0x14014eed2  jnz     loc_14014F04E
0x14014eed8  mov     rdi, rsi
0x14014eedb  mov     r14d, dword ptr [rbp+57h+var_80]
0x14014eedf  mov     r8d, r13d; unsigned int
0x14014eee2  add     r14d, 8
0x14014eee6  mov     rcx, r12; unsigned __int64
0x14014eee9  mov     edx, r14d; unsigned __int64
0x14014eeec  call    ?Win32AllocPoolZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x14014eef1  mov     rsi, rax
0x14014eef4  test    rax, rax
0x14014eef7  jz      loc_14014F1FC
0x14014eefd  mov     r13d, 2
0x14014ef03  mov     edx, r14d; AclLength
0x14014ef06  mov     r8d, r13d; AclRevision
0x14014ef09  mov     rcx, rax; Acl
0x14014ef0c  call    cs:__imp_RtlCreateAcl
0x14014ef13  nop     dword ptr [rax+rax+00h]
0x14014ef18  test    eax, eax
0x14014ef1a  js      loc_14014F258
0x14014ef20  movzx   eax, word ptr [rsi+2]
0x14014ef24  mov     r9, rdi; AceList
0x14014ef27  sub     eax, 8
0x14014ef2a  xor     r8d, r8d; StartingAceIndex
0x14014ef2d  mov     edx, r13d; AceRevision
0x14014ef30  mov     [rsp+0D0h+AceListLength], eax; AceListLength
0x14014ef34  mov     rcx, rsi; Acl
0x14014ef37  call    cs:__imp_RtlAddAce
0x14014ef3e  nop     dword ptr [rax+rax+00h]
0x14014ef43  mov     rcx, r15; Sid
0x14014ef46  call    cs:__imp_RtlLengthSid
0x14014ef4d  nop     dword ptr [rax+rax+00h]
0x14014ef52  mov     ecx, 100h; unsigned __int64
0x14014ef57  mov     r8d, 65737355h; unsigned int
0x14014ef5d  lea     r12d, [rax+10h]
0x14014ef61  mov     edx, r12d; unsigned __int64
0x14014ef64  call    ?Win32AllocPoolZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x14014ef69  mov     r14, rax
0x14014ef6c  test    rax, rax
0x14014ef6f  jz      loc_14014F258
0x14014ef75  mov     r8d, r13d; AclRevision
0x14014ef78  mov     edx, r12d; AclLength
0x14014ef7b  mov     rcx, rax; Acl
0x14014ef7e  call    cs:__imp_RtlCreateAcl
0x14014ef85  nop     dword ptr [rax+rax+00h]
0x14014ef8a  test    eax, eax
0x14014ef8c  js      loc_14014F28C
0x14014ef92  mov     dword ptr [rsp+0D0h+LabelSid], 7; LabelSid
0x14014ef9a  mov     r9, r15; MandatoryFlags
0x14014ef9d  xor     r8d, r8d; Flags
0x14014efa0  mov     byte ptr [rsp+0D0h+AceListLength], 11h; AceType
0x14014efa5  mov     edx, r13d; Revision
0x14014efa8  mov     rcx, r14; Acl
0x14014efab  call    cs:__imp_RtlAddMandatoryAce
0x14014efb2  nop     dword ptr [rax+rax+00h]
0x14014efb7  test    eax, eax
0x14014efb9  js      loc_14014F28C
0x14014efbf  mov     r15, [rbp+57h+SecurityDescriptor]
0x14014efc3  xor     r9d, r9d; DaclDefaulted
0x14014efc6  mov     rcx, r15; SecurityDescriptor
0x14014efc9  mov     r8, rsi; Dacl
0x14014efcc  mov     dl, 1; DaclPresent
0x14014efce  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x14014efd5  nop     dword ptr [rax+rax+00h]
0x14014efda  test    eax, eax
0x14014efdc  js      loc_14014F28C
0x14014efe2  xor     r9d, r9d; SaclDefaulted
0x14014efe5  mov     r8, r14; Sacl
0x14014efe8  mov     dl, 1; SaclPresent
0x14014efea  mov     rcx, r15; SecurityDescriptor
0x14014efed  call    cs:__imp_RtlSetSaclSecurityDescriptor
0x14014eff4  nop     dword ptr [rax+rax+00h]
0x14014eff9  mov     rcx, [rbp+57h+TokenInformation]; P
0x14014effd  xor     edx, edx; Tag
0x14014efff  test    eax, eax
0x14014f001  jns     loc_14014F0A2
0x14014f007  call    cs:__imp_ExFreePoolWithTag
0x14014f00e  nop     dword ptr [rax+rax+00h]
0x14014f013  mov     rcx, [rbp+57h+P]; P
0x14014f017  xor     edx, edx; Tag
0x14014f019  call    cs:__imp_ExFreePoolWithTag
0x14014f020  nop     dword ptr [rax+rax+00h]
0x14014f025  mov     rcx, rdi; Buffer
0x14014f028  call    GreDeleteFastMutex
0x14014f02d  mov     rcx, rsi; Buffer
0x14014f030  call    GreDeleteFastMutex
0x14014f035  mov     rcx, r14; Buffer
0x14014f038  call    GreDeleteFastMutex
0x14014f03d  mov     rcx, rbx; Buffer
0x14014f040  call    GreDeleteFastMutex
0x14014f045  mov     rcx, [rbp+57h+var_88]
0x14014f049  jmp     loc_14014EC85
0x14014f04e  mov     r9d, [rbp+57h+AccessMask]
0x14014f052  lea     rax, [rbp+57h+var_80]
0x14014f056  mov     [rsp+0D0h+LabelSid], rax; __int64
0x14014f05b  xor     r8d, r8d
0x14014f05e  xor     edx, edx
  ... truncated ...
```
