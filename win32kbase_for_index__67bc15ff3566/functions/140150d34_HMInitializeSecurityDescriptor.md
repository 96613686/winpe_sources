# HMInitializeSecurityDescriptor

- ea: `0x140150d34`
- end: `0x140151447`
- name: `HMInitializeSecurityDescriptor`
- size: `1811`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140150b10`
- `0x140150ca0`

## callees

- `0x14007b930`
- `0x14007df80`
- `0x14007efd0`
- `0x14007f840`
- `0x140150d34`
- `0x1402388e0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140150e25`
- `ntoskrnl!ExFreePoolWithTag` at `0x140150e37`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401511b7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401511c9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14015122f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140151241`
- `ntoskrnl!ExFreePoolWithTag` at `0x140151252`
- `ntoskrnl!ExFreePoolWithTag` at `0x140151264`
- `ntoskrnl!ExFreePoolWithTag` at `0x140151286`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401512a2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401512b4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401512ce`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401512e0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14015135d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14015136f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140151386`
- `ntoskrnl!ExFreePoolWithTag` at `0x140151398`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401513b2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401513c4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14015140e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140151420`
- `ntoskrnl!ExFreePoolWithTag` at `0x140150e25`
- `ntoskrnl!ExFreePoolWithTag` at `0x140150e37`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401511b7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401511c9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14015122f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140151241`
- `ntoskrnl!ExFreePoolWithTag` at `0x140151252`
- `ntoskrnl!ExFreePoolWithTag` at `0x140151264`
- `ntoskrnl!ExFreePoolWithTag` at `0x140151286`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401512a2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401512b4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401512ce`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401512e0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14015135d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14015136f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140151386`
- `ntoskrnl!ExFreePoolWithTag` at `0x140151398`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401513b2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401513c4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14015140e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140151420`
- `ntoskrnl!SeQueryInformationToken` at `0x140150dc4`
- `ntoskrnl!SeQueryInformationToken` at `0x140150de3`
- `ntoskrnl!SeQueryInformationToken` at `0x140150e91`
- `ntoskrnl!SeQueryInformationToken` at `0x140150eb2`
- `ntoskrnl!SeQueryInformationToken` at `0x140150dc4`
- `ntoskrnl!SeQueryInformationToken` at `0x140150de3`
- `ntoskrnl!SeQueryInformationToken` at `0x140150e91`
- `ntoskrnl!SeQueryInformationToken` at `0x140150eb2`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140150dae`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140150dae`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140150e13`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140150e71`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140150eca`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14015133c`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140150e13`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140150e71`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140150eca`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14015133c`
- `ntoskrnl!SeExports` at `0x140150ef0`
- `ntoskrnl!SeExports` at `0x140150f59`
- `ntoskrnl!RtlLengthSid` at `0x140150f08`
- `ntoskrnl!RtlLengthSid` at `0x1401510f6`
- `ntoskrnl!RtlLengthSid` at `0x140150f08`
- `ntoskrnl!RtlLengthSid` at `0x1401510f6`
- `ntoskrnl!RtlCreateAcl` at `0x1401510bc`
- `ntoskrnl!RtlCreateAcl` at `0x14015112e`
- `ntoskrnl!RtlCreateAcl` at `0x1401510bc`
- `ntoskrnl!RtlCreateAcl` at `0x14015112e`
- `ntoskrnl!RtlAddAce` at `0x1401510e7`
- `ntoskrnl!RtlAddAce` at `0x1401510e7`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14015117e`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14015117e`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140150fcc`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140150fcc`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140150d96`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140150d96`
- `ntoskrnl!RtlMapGenericMask` at `0x140150ee4`
- `ntoskrnl!RtlMapGenericMask` at `0x140151073`
- `ntoskrnl!RtlMapGenericMask` at `0x140150ee4`
- `ntoskrnl!RtlMapGenericMask` at `0x140151073`
- `ntoskrnl!RtlInitializeSid` at `0x140151007`
- `ntoskrnl!RtlInitializeSid` at `0x140151007`
- `ntoskrnl!RtlAddMandatoryAce` at `0x14015115b`
- `ntoskrnl!RtlAddMandatoryAce` at `0x14015115b`
- `ntoskrnl!RtlSetSaclSecurityDescriptor` at `0x14015119d`
- `ntoskrnl!RtlSetSaclSecurityDescriptor` at `0x14015119d`
- `ntoskrnl!RtlCopySid` at `0x140150f4d`
- `ntoskrnl!RtlCopySid` at `0x140150f4d`

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
0x140150d34  mov     [rsp-8+arg_10], rbx
0x140150d39  push    rbp
0x140150d3a  push    rsi
0x140150d3b  push    rdi
0x140150d3c  push    r12
0x140150d3e  push    r13
0x140150d40  push    r14
0x140150d42  push    r15
0x140150d44  lea     rbp, [rsp-27h]
0x140150d49  sub     rsp, 0A0h
0x140150d50  mov     rax, cs:__security_cookie
0x140150d57  xor     rax, rsp
0x140150d5a  mov     [rbp+57h+var_40], rax
0x140150d5e  xor     edi, edi
0x140150d60  mov     [rbp+57h+GenericMapping], rdx
0x140150d64  xorps   xmm0, xmm0
0x140150d67  mov     [rbp+57h+SecurityDescriptor], rcx
0x140150d6b  mov     rbx, rdx
0x140150d6e  mov     [rbp+57h+AccessMask], edi
0x140150d71  movups  xmmword ptr [rbp+57h+var_78], xmm0
0x140150d75  lea     esi, [rdi+1]
0x140150d78  mov     [rbp+57h+TokenInformation], rdi
0x140150d7c  mov     edx, esi; Revision
0x140150d7e  mov     [rbp+57h+P], rdi
0x140150d82  movups  xmmword ptr [rbp+57h+var_78+10h], xmm0
0x140150d86  mov     dword ptr [rbp+57h+var_80+4], edi
0x140150d89  mov     dword ptr [rbp+57h+IdentifierAuthority.Value], edi
0x140150d8c  mov     word ptr [rbp+57h+IdentifierAuthority.Value+4], 500h
0x140150d92  mov     [rbp+57h+var_88], rdi
0x140150d96  call    cs:__imp_RtlCreateSecurityDescriptor
0x140150d9d  nop     dword ptr [rax+rax+00h]
0x140150da2  test    eax, eax
0x140150da4  js      loc_140150E43
0x140150daa  lea     rcx, [rbp+57h+var_78]; SubjectContext
0x140150dae  call    cs:__imp_SeCaptureSubjectContext
0x140150db5  nop     dword ptr [rax+rax+00h]
0x140150dba  mov     rcx, qword ptr [rbp+57h+var_78+10h]; Token
0x140150dbe  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x140150dc2  mov     edx, esi; TokenInformationClass
0x140150dc4  call    cs:__imp_SeQueryInformationToken
0x140150dcb  nop     dword ptr [rax+rax+00h]
0x140150dd0  test    eax, eax
0x140150dd2  js      loc_140150E6D
0x140150dd8  mov     rcx, qword ptr [rbp+57h+var_78+10h]; Token
0x140150ddc  lea     r8, [rbp+57h+P]; TokenInformation
0x140150de0  lea     edx, [rdi+2]; TokenInformationClass
0x140150de3  call    cs:__imp_SeQueryInformationToken
0x140150dea  nop     dword ptr [rax+rax+00h]
0x140150def  test    eax, eax
0x140150df1  js      loc_140151338
0x140150df7  mov     r8, [rbp+57h+P]
0x140150dfb  mov     r14d, edi
0x140150dfe  mov     r15d, edi
0x140150e01  mov     ecx, edi
0x140150e03  mov     r9d, [r8]
0x140150e06  test    r9d, r9d
0x140150e09  jnz     loc_140151351
0x140150e0f  lea     rcx, [rbp+57h+var_78]; SubjectContext
0x140150e13  call    cs:__imp_SeReleaseSubjectContext
0x140150e1a  nop     dword ptr [rax+rax+00h]
0x140150e1f  mov     rcx, [rbp+57h+TokenInformation]; P
0x140150e23  xor     edx, edx; Tag
0x140150e25  call    cs:__imp_ExFreePoolWithTag
0x140150e2c  nop     dword ptr [rax+rax+00h]
0x140150e31  mov     rcx, [rbp+57h+P]; P
0x140150e35  xor     edx, edx; Tag
0x140150e37  call    cs:__imp_ExFreePoolWithTag
0x140150e3e  nop     dword ptr [rax+rax+00h]
0x140150e43  xor     eax, eax
0x140150e45  mov     rcx, [rbp+57h+var_40]
0x140150e49  xor     rcx, rsp; StackCookie
0x140150e4c  call    __security_check_cookie
0x140150e51  mov     rbx, [rsp+0D0h+arg_10]
0x140150e59  add     rsp, 0A0h
0x140150e60  pop     r15
0x140150e62  pop     r14
0x140150e64  pop     r13
0x140150e66  pop     r12
0x140150e68  pop     rdi
0x140150e69  pop     rsi
0x140150e6a  pop     rbp
0x140150e6b  retn
0x140150e6d  lea     rcx, [rbp+57h+var_78]; SubjectContext
0x140150e71  call    cs:__imp_SeReleaseSubjectContext
0x140150e78  nop     dword ptr [rax+rax+00h]
0x140150e7d  jmp     short loc_140150E43
0x140150e7f  test    r15, r15
0x140150e82  jz      short loc_140150E0F
0x140150e84  mov     rcx, qword ptr [rbp+57h+var_78+10h]; Token
0x140150e88  lea     r8, [rbp+57h+var_80+4]; TokenInformation
0x140150e8c  mov     edx, 0Ch; TokenInformationClass
0x140150e91  call    cs:__imp_SeQueryInformationToken
0x140150e98  nop     dword ptr [rax+rax+00h]
0x140150e9d  test    eax, eax
0x140150e9f  js      loc_140150E0F
0x140150ea5  mov     rcx, qword ptr [rbp+57h+var_78+10h]; Token
0x140150ea9  lea     r8, [rbp+57h+var_88]; TokenInformation
0x140150ead  mov     edx, 1Fh; TokenInformationClass
0x140150eb2  call    cs:__imp_SeQueryInformationToken
0x140150eb9  nop     dword ptr [rax+rax+00h]
0x140150ebe  lea     rcx, [rbp+57h+var_78]; SubjectContext
0x140150ec2  test    eax, eax
0x140150ec4  js      loc_140150E13
0x140150eca  call    cs:__imp_SeReleaseSubjectContext
0x140150ed1  nop     dword ptr [rax+rax+00h]
0x140150ed6  mov     rdx, rbx; GenericMapping
0x140150ed9  mov     [rbp+57h+AccessMask], 10000000h
0x140150ee0  lea     rcx, [rbp+57h+AccessMask]; AccessMask
0x140150ee4  call    cs:__imp_RtlMapGenericMask
0x140150eeb  nop     dword ptr [rax+rax+00h]
0x140150ef0  mov     rax, cs:__imp_SeExports
0x140150ef7  mov     r12d, [rbp+57h+AccessMask]
0x140150efb  mov     rcx, [rax]
0x140150efe  mov     rsi, [rcx+110h]
0x140150f05  mov     rcx, rsi; Sid
0x140150f08  call    cs:__imp_RtlLengthSid
0x140150f0f  nop     dword ptr [rax+rax+00h]
0x140150f14  mov     r8d, 65737355h; unsigned int
0x140150f1a  mov     r13d, eax
0x140150f1d  lea     edi, [rax+8]
0x140150f20  mov     edx, edi; unsigned __int64
0x140150f22  call    ?Win32AllocPoolWithQuotaZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolWithQuotaZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x140150f27  mov     rbx, rax
0x140150f2a  test    rax, rax
0x140150f2d  jz      loc_1401512C8
0x140150f33  lea     rdx, [rax+8]; DestinationSid
0x140150f37  mov     dword ptr [rbp+57h+var_80], edi
0x140150f3a  mov     r8, rsi; SourceSid
0x140150f3d  mov     word ptr [rax], 0
0x140150f42  mov     ecx, r13d; DestinationSidLength
0x140150f45  mov     [rax+2], di
0x140150f49  mov     [rax+4], r12d
0x140150f4d  call    cs:__imp_RtlCopySid
0x140150f54  nop     dword ptr [rax+rax+00h]
0x140150f59  mov     rcx, cs:__imp_SeExports
0x140150f60  xor     r8d, r8d
0x140150f63  mov     r9d, [rbp+57h+AccessMask]
0x140150f67  xor     edx, edx
0x140150f69  mov     rax, [rcx]
0x140150f6c  lea     rcx, [rbp+57h+var_80]
0x140150f70  mov     [rsp+0D0h+LabelSid], rcx; __int64
0x140150f75  mov     rcx, rbx; Buffer
0x140150f78  mov     rax, [rax+108h]
0x140150f7f  mov     qword ptr [rsp+0D0h+AceListLength], rax; Sid
0x140150f84  call    AllocAce
0x140150f89  xor     edx, edx; Tag
0x140150f8b  mov     rsi, rax
0x140150f8e  test    rax, rax
0x140150f91  jz      loc_140151359
0x140150f97  mov     r9d, [rbp+57h+AccessMask]
0x140150f9b  lea     rax, [rbp+57h+var_80]
0x140150f9f  mov     [rsp+0D0h+LabelSid], rax; __int64
0x140150fa4  xor     r8d, r8d
0x140150fa7  mov     rax, [rbp+57h+TokenInformation]
0x140150fab  mov     rcx, [rax]
0x140150fae  mov     qword ptr [rsp+0D0h+AceListLength], rcx; Sid
0x140150fb3  mov     rcx, rsi; Buffer
0x140150fb6  call    AllocAce
0x140150fbb  mov     rdi, rax
0x140150fbe  test    rax, rax
0x140150fc1  jz      loc_14015129C
0x140150fc7  mov     ecx, 3; SubAuthorityCount
0x140150fcc  call    cs:__imp_RtlLengthRequiredSid
0x140150fd3  nop     dword ptr [rax+rax+00h]
0x140150fd8  mov     r13d, 65737355h
0x140150fde  mov     r12d, 100h
0x140150fe4  mov     edx, eax; unsigned __int64
0x140150fe6  mov     r8d, r13d; unsigned int
0x140150fe9  mov     ecx, r12d; unsigned __int64
0x140150fec  call    ?Win32AllocPoolZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x140150ff1  mov     rbx, rax
0x140150ff4  test    rax, rax
0x140150ff7  jz      loc_140151380
0x140150ffd  mov     r8b, 3; SubAuthorityCount
0x140151000  lea     rdx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x140151004  mov     rcx, rax; Sid
0x140151007  call    cs:__imp_RtlInitializeSid
0x14015100e  nop     dword ptr [rax+rax+00h]
0x140151013  xor     edx, edx
0x140151015  test    eax, eax
0x140151017  js      loc_1401513AE
0x14015101d  mov     qword ptr [rbx+8], 5Ah ; 'Z'
0x140151025  xor     r8d, r8d
0x140151028  mov     eax, dword ptr [rbp+57h+var_80+4]
0x14015102b  mov     rcx, rdi; Buffer
0x14015102e  mov     [rbx+10h], eax
0x140151031  lea     rax, [rbp+57h+var_80]
0x140151035  mov     r9d, [rbp+57h+AccessMask]
0x140151039  mov     [rsp+0D0h+LabelSid], rax; __int64
0x14015103e  mov     qword ptr [rsp+0D0h+AceListLength], rbx; Sid
0x140151043  call    AllocAce
0x140151048  mov     rsi, rax
0x14015104b  test    rax, rax
0x14015104e  jz      loc_1401513AC
0x140151054  mov     rax, [rbp+57h+var_88]
0x140151058  mov     rcx, [rax]
0x14015105b  test    rcx, rcx
0x14015105e  jnz     loc_1401513D8
0x140151064  mov     rdx, [rbp+57h+GenericMapping]; GenericMapping
0x140151068  lea     rcx, [rbp+57h+AccessMask]; AccessMask
0x14015106c  mov     [rbp+57h+AccessMask], 0C0000000h
0x140151073  call    cs:__imp_RtlMapGenericMask
0x14015107a  nop     dword ptr [rax+rax+00h]
0x14015107f  test    r14, r14
0x140151082  jnz     loc_1401511FE
0x140151088  mov     rdi, rsi
0x14015108b  mov     r14d, dword ptr [rbp+57h+var_80]
0x14015108f  mov     r8d, r13d; unsigned int
0x140151092  add     r14d, 8
0x140151096  mov     rcx, r12; unsigned __int64
0x140151099  mov     edx, r14d; unsigned __int64
0x14015109c  call    ?Win32AllocPoolZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x1401510a1  mov     rsi, rax
0x1401510a4  test    rax, rax
0x1401510a7  jz      loc_1401513AC
0x1401510ad  mov     r13d, 2
0x1401510b3  mov     edx, r14d; AclLength
0x1401510b6  mov     r8d, r13d; AclRevision
0x1401510b9  mov     rcx, rax; Acl
0x1401510bc  call    cs:__imp_RtlCreateAcl
0x1401510c3  nop     dword ptr [rax+rax+00h]
0x1401510c8  test    eax, eax
0x1401510ca  js      loc_140151408
0x1401510d0  movzx   eax, word ptr [rsi+2]
0x1401510d4  mov     r9, rdi; AceList
0x1401510d7  sub     eax, 8
0x1401510da  xor     r8d, r8d; StartingAceIndex
0x1401510dd  mov     edx, r13d; AceRevision
0x1401510e0  mov     [rsp+0D0h+AceListLength], eax; AceListLength
0x1401510e4  mov     rcx, rsi; Acl
0x1401510e7  call    cs:__imp_RtlAddAce
0x1401510ee  nop     dword ptr [rax+rax+00h]
0x1401510f3  mov     rcx, r15; Sid
0x1401510f6  call    cs:__imp_RtlLengthSid
0x1401510fd  nop     dword ptr [rax+rax+00h]
0x140151102  mov     ecx, 100h; unsigned __int64
0x140151107  mov     r8d, 65737355h; unsigned int
0x14015110d  lea     r12d, [rax+10h]
0x140151111  mov     edx, r12d; unsigned __int64
0x140151114  call    ?Win32AllocPoolZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x140151119  mov     r14, rax
0x14015111c  test    rax, rax
0x14015111f  jz      loc_140151408
0x140151125  mov     r8d, r13d; AclRevision
0x140151128  mov     edx, r12d; AclLength
0x14015112b  mov     rcx, rax; Acl
0x14015112e  call    cs:__imp_RtlCreateAcl
0x140151135  nop     dword ptr [rax+rax+00h]
0x14015113a  test    eax, eax
0x14015113c  js      loc_14015143C
0x140151142  mov     dword ptr [rsp+0D0h+LabelSid], 7; LabelSid
0x14015114a  mov     r9, r15; MandatoryFlags
0x14015114d  xor     r8d, r8d; Flags
0x140151150  mov     byte ptr [rsp+0D0h+AceListLength], 11h; AceType
0x140151155  mov     edx, r13d; Revision
0x140151158  mov     rcx, r14; Acl
0x14015115b  call    cs:__imp_RtlAddMandatoryAce
0x140151162  nop     dword ptr [rax+rax+00h]
0x140151167  test    eax, eax
0x140151169  js      loc_14015143C
0x14015116f  mov     r15, [rbp+57h+SecurityDescriptor]
0x140151173  xor     r9d, r9d; DaclDefaulted
0x140151176  mov     rcx, r15; SecurityDescriptor
0x140151179  mov     r8, rsi; Dacl
0x14015117c  mov     dl, 1; DaclPresent
0x14015117e  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x140151185  nop     dword ptr [rax+rax+00h]
0x14015118a  test    eax, eax
0x14015118c  js      loc_14015143C
0x140151192  xor     r9d, r9d; SaclDefaulted
0x140151195  mov     r8, r14; Sacl
0x140151198  mov     dl, 1; SaclPresent
0x14015119a  mov     rcx, r15; SecurityDescriptor
0x14015119d  call    cs:__imp_RtlSetSaclSecurityDescriptor
0x1401511a4  nop     dword ptr [rax+rax+00h]
0x1401511a9  mov     rcx, [rbp+57h+TokenInformation]; P
0x1401511ad  xor     edx, edx; Tag
0x1401511af  test    eax, eax
0x1401511b1  jns     loc_140151252
0x1401511b7  call    cs:__imp_ExFreePoolWithTag
0x1401511be  nop     dword ptr [rax+rax+00h]
0x1401511c3  mov     rcx, [rbp+57h+P]; P
0x1401511c7  xor     edx, edx; Tag
0x1401511c9  call    cs:__imp_ExFreePoolWithTag
0x1401511d0  nop     dword ptr [rax+rax+00h]
0x1401511d5  mov     rcx, rdi; Buffer
0x1401511d8  call    GreDeleteFastMutex
0x1401511dd  mov     rcx, rsi; Buffer
0x1401511e0  call    GreDeleteFastMutex
0x1401511e5  mov     rcx, r14; Buffer
0x1401511e8  call    GreDeleteFastMutex
0x1401511ed  mov     rcx, rbx; Buffer
0x1401511f0  call    GreDeleteFastMutex
0x1401511f5  mov     rcx, [rbp+57h+var_88]
0x1401511f9  jmp     loc_140150E35
0x1401511fe  mov     r9d, [rbp+57h+AccessMask]
0x140151202  lea     rax, [rbp+57h+var_80]
0x140151206  mov     [rsp+0D0h+LabelSid], rax; __int64
0x14015120b  xor     r8d, r8d
0x14015120e  xor     edx, edx
  ... truncated ...
```
