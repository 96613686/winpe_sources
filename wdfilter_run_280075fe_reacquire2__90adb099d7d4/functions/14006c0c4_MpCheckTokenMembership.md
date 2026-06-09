# MpCheckTokenMembership

- ea: `0x14006c0c4`
- end: `0x14006c3b2`
- name: `MpCheckTokenMembership`
- size: `750`
- prototype: `__int64 __fastcall(HANDLE ExistingTokenHandle, PSID Sid)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14006bfb0`

## callees

- `0x1400118d0`
- `0x140011bc0`
- `0x14006c0c4`

## import_xrefs

- `ntoskrnl!SeReleaseSubjectContext` at `0x14006c2f2`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14006c2f2`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14006c15b`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14006c15b`
- `ntoskrnl!SeTokenObjectType` at `0x14006c29f`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14006c2d5`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14006c2d5`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x14006c189`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x14006c189`
- `ntoskrnl!SeAccessCheck` at `0x14006c248`
- `ntoskrnl!SeAccessCheck` at `0x14006c248`
- `ntoskrnl!RtlSetGroupSecurityDescriptor` at `0x14006c19f`
- `ntoskrnl!RtlSetGroupSecurityDescriptor` at `0x14006c19f`
- `ntoskrnl!ZwDuplicateToken` at `0x14006c37f`
- `ntoskrnl!ZwDuplicateToken` at `0x14006c37f`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14006c173`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14006c173`
- `ntoskrnl!RtlCreateAcl` at `0x14006c1b8`
- `ntoskrnl!RtlCreateAcl` at `0x14006c1b8`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14006c1d4`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14006c1d4`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14006c1ed`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14006c1ed`
- `ntoskrnl!ZwClose` at `0x14006c291`
- `ntoskrnl!ZwClose` at `0x14006c291`
- `ntoskrnl!ObfDereferenceObject` at `0x14006c25e`
- `ntoskrnl!ObfDereferenceObject` at `0x14006c25e`

## pseudocode

```c
__int64 __fastcall MpCheckTokenMembership(HANDLE ExistingTokenHandle, PSID Sid, _BYTE *a3)
{
  char v6; // di
  NTSTATUS v7; // ebx
  HANDLE Handle; // [rsp+58h] [rbp-A8h] BYREF
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+60h] [rbp-A0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-80h] BYREF
  int AccessStatus; // [rsp+B0h] [rbp-50h] BYREF
  DWORD GrantedAccess; // [rsp+B4h] [rbp-4Ch] BYREF
  __int64 v14; // [rsp+B8h] [rbp-48h] BYREF
  int v15; // [rsp+C0h] [rbp-40h]
  _OWORD SecurityDescriptor[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v17; // [rsp+E8h] [rbp-18h]
  _ACL Acl[12]; // [rsp+F0h] [rbp-10h] BYREF

  GrantedAccess = 0;
  AccessStatus = 0;
  memset(Acl, 0, 0x54u);
  Handle = 0;
  v6 = 0;
  v14 = 0;
  v15 = 0;
  v17 = 0;
  *a3 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  if ( ExistingTokenHandle )
  {
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.ObjectName = 0;
    ObjectAttributes.SecurityDescriptor = 0;
    ObjectAttributes.Length = 48;
    ObjectAttributes.SecurityQualityOfService = &v14;
    ObjectAttributes.Attributes = 512;
    v14 = 0x20000000CLL;
    LOWORD(v15) = 1;
    v7 = ZwDuplicateToken(ExistingTokenHandle, 8u, &ObjectAttributes, 0, TokenImpersonation, &Handle);
    if ( v7 < 0 )
      return (unsigned int)v7;
  }
  else
  {
    SeCaptureSubjectContext(&SubjectContext);
    v6 = 1;
  }
  RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
  RtlSetOwnerSecurityDescriptor(SecurityDescriptor, Sid, 0);
  RtlSetGroupSecurityDescriptor(SecurityDescriptor, Sid, 0);
  RtlCreateAcl(Acl, 0x54u, 2u);
  RtlAddAccessAllowedAce(Acl, 2u, 1u, Sid);
  RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, Acl, 0);
  if ( v6
    || (memset(&SubjectContext, 0, sizeof(SubjectContext)),
        v7 = ObReferenceObjectByHandle(Handle, 8u, (POBJECT_TYPE)SeTokenObjectType, 0, &SubjectContext.PrimaryToken, 0),
        v7 >= 0) )
  {
    SeAccessCheck(
      SecurityDescriptor,
      &SubjectContext,
      0,
      1u,
      0,
      0,
      (PGENERIC_MAPPING)&GenericMapping,
      1,
      &GrantedAccess,
      &AccessStatus);
    if ( !v6 )
      ObfDereferenceObject(SubjectContext.PrimaryToken);
    v7 = 0;
    if ( AccessStatus )
    {
      if ( AccessStatus == -1073741790 )
        goto LABEL_8;
    }
    else if ( GrantedAccess == 1 )
    {
      *a3 = 1;
      goto LABEL_8;
    }
    v7 = AccessStatus;
LABEL_8:
    if ( v6 )
      SeReleaseSubjectContext(&SubjectContext);
  }
  if ( Handle )
    ZwClose(Handle);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14006c0c4  mov     [rsp-8+arg_18], rbx
0x14006c0c9  push    rbp
0x14006c0ca  push    rsi
0x14006c0cb  push    rdi
0x14006c0cc  push    r14
0x14006c0ce  push    r15
0x14006c0d0  lea     rbp, [rsp-60h]
0x14006c0d5  sub     rsp, 160h
0x14006c0dc  mov     rax, cs:__security_cookie
0x14006c0e3  xor     rax, rsp
0x14006c0e6  mov     [rbp+80h+var_30], rax
0x14006c0ea  mov     r15, rdx
0x14006c0ed  mov     [rbp+80h+var_CC], 0
0x14006c0f4  xor     edx, edx; Val
0x14006c0f6  mov     [rbp+80h+var_D0], 0
0x14006c0fd  mov     r14, r8
0x14006c100  mov     rsi, rcx
0x14006c103  lea     rcx, [rbp+80h+Acl]; void *
0x14006c107  lea     r8d, [rdx+54h]; Size
0x14006c10b  call    memset
0x14006c110  xorps   xmm0, xmm0
0x14006c113  mov     [rsp+180h+Handle], 0
0x14006c11c  xor     eax, eax
0x14006c11e  xor     dil, dil
0x14006c121  mov     [rbp+80h+var_C8], rax
0x14006c125  mov     [rbp+80h+var_C0], eax
0x14006c128  mov     [rbp+80h+var_98], rax
0x14006c12c  mov     [r14], al
0x14006c12f  movups  xmmword ptr [rbp+80h+ObjectAttributes.Length], xmm0
0x14006c133  movups  xmmword ptr [rbp+80h+ObjectAttributes.ObjectName], xmm0
0x14006c137  movups  xmmword ptr [rbp+80h+ObjectAttributes.SecurityDescriptor], xmm0
0x14006c13b  movups  [rbp+80h+SecurityDescriptor], xmm0
0x14006c13f  movups  [rbp+80h+var_A8], xmm0
0x14006c143  movups  xmmword ptr [rsp+180h+SubjectContext.ClientToken], xmm0
0x14006c148  movups  xmmword ptr [rsp+180h+SubjectContext.PrimaryToken], xmm0
0x14006c14d  test    rsi, rsi
0x14006c150  jnz     loc_14006C329
0x14006c156  lea     rcx, [rsp+180h+SubjectContext]; SubjectContext
0x14006c15b  call    cs:__imp_SeCaptureSubjectContext
0x14006c162  nop     dword ptr [rax+rax+00h]
0x14006c167  mov     dil, 1
0x14006c16a  mov     edx, 1; Revision
0x14006c16f  lea     rcx, [rbp+80h+SecurityDescriptor]; SecurityDescriptor
0x14006c173  call    cs:__imp_RtlCreateSecurityDescriptor
0x14006c17a  nop     dword ptr [rax+rax+00h]
0x14006c17f  xor     r8d, r8d; OwnerDefaulted
0x14006c182  lea     rcx, [rbp+80h+SecurityDescriptor]; SecurityDescriptor
0x14006c186  mov     rdx, r15; Owner
0x14006c189  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x14006c190  nop     dword ptr [rax+rax+00h]
0x14006c195  xor     r8d, r8d; GroupDefaulted
0x14006c198  lea     rcx, [rbp+80h+SecurityDescriptor]; SecurityDescriptor
0x14006c19c  mov     rdx, r15; Group
0x14006c19f  call    cs:__imp_RtlSetGroupSecurityDescriptor
0x14006c1a6  nop     dword ptr [rax+rax+00h]
0x14006c1ab  mov     edx, 54h ; 'T'; AclLength
0x14006c1b0  lea     rcx, [rbp+80h+Acl]; Acl
0x14006c1b4  lea     r8d, [rdx-52h]; AclRevision
0x14006c1b8  call    cs:__imp_RtlCreateAcl
0x14006c1bf  nop     dword ptr [rax+rax+00h]
0x14006c1c4  mov     edx, 2; AceRevision
0x14006c1c9  lea     rcx, [rbp+80h+Acl]; Acl
0x14006c1cd  mov     r9, r15; Sid
0x14006c1d0  lea     r8d, [rdx-1]; AccessMask
0x14006c1d4  call    cs:__imp_RtlAddAccessAllowedAce
0x14006c1db  nop     dword ptr [rax+rax+00h]
0x14006c1e0  xor     r9d, r9d; DaclDefaulted
0x14006c1e3  lea     r8, [rbp+80h+Acl]; Dacl
0x14006c1e7  mov     dl, 1; DaclPresent
0x14006c1e9  lea     rcx, [rbp+80h+SecurityDescriptor]; SecurityDescriptor
0x14006c1ed  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x14006c1f4  nop     dword ptr [rax+rax+00h]
0x14006c1f9  test    dil, dil
0x14006c1fc  jz      loc_14006C29F
0x14006c202  lea     rax, [rbp+80h+var_D0]
0x14006c206  mov     r9d, 1; DesiredAccess
0x14006c20c  mov     [rsp+180h+AccessStatus], rax; AccessStatus
0x14006c211  lea     rdx, [rsp+180h+SubjectContext]; SubjectSecurityContext
0x14006c216  lea     rax, [rbp+80h+var_CC]
0x14006c21a  xor     r8d, r8d; SubjectContextLocked
0x14006c21d  mov     [rsp+180h+GrantedAccess], rax; GrantedAccess
0x14006c222  lea     rcx, [rbp+80h+SecurityDescriptor]; SecurityDescriptor
0x14006c226  mov     [rsp+180h+AccessMode], 1; AccessMode
0x14006c22b  lea     rax, GenericMapping
0x14006c232  mov     [rsp+180h+GenericMapping], rax; GenericMapping
0x14006c237  mov     [rsp+180h+Privileges], 0; Privileges
0x14006c240  mov     [rsp+180h+PreviouslyGrantedAccess], 0; PreviouslyGrantedAccess
0x14006c248  call    cs:__imp_SeAccessCheck
0x14006c24f  nop     dword ptr [rax+rax+00h]
0x14006c254  test    dil, dil
0x14006c257  jnz     short loc_14006C26A
0x14006c259  mov     rcx, [rsp+180h+SubjectContext.PrimaryToken]; Object
0x14006c25e  call    cs:__imp_ObfDereferenceObject
0x14006c265  nop     dword ptr [rax+rax+00h]
0x14006c26a  mov     eax, [rbp+80h+var_D0]
0x14006c26d  xor     ebx, ebx
0x14006c26f  test    eax, eax
0x14006c271  jz      loc_14006C39C
0x14006c277  cmp     eax, 0C0000022h
0x14006c27c  jnz     loc_14006C3AB
0x14006c282  test    dil, dil
0x14006c285  jnz     short loc_14006C2ED
0x14006c287  mov     rcx, [rsp+180h+Handle]; Handle
0x14006c28c  test    rcx, rcx
0x14006c28f  jz      short loc_14006C303
0x14006c291  call    cs:__imp_ZwClose
0x14006c298  nop     dword ptr [rax+rax+00h]
0x14006c29d  jmp     short loc_14006C303
0x14006c29f  mov     r8, cs:__imp_SeTokenObjectType
0x14006c2a6  lea     rax, [rsp+180h+SubjectContext.PrimaryToken]
0x14006c2ab  mov     rcx, [rsp+180h+Handle]; Handle
0x14006c2b0  xorps   xmm0, xmm0
0x14006c2b3  xor     r9d, r9d; AccessMode
0x14006c2b6  mov     [rsp+180h+Privileges], 0; HandleInformation
0x14006c2bf  movups  xmmword ptr [rsp+180h+SubjectContext.ClientToken], xmm0
0x14006c2c4  mov     qword ptr [rsp+180h+PreviouslyGrantedAccess], rax; Object
0x14006c2c9  movups  xmmword ptr [rsp+180h+SubjectContext.PrimaryToken], xmm0
0x14006c2ce  mov     r8, [r8]; ObjectType
0x14006c2d1  lea     edx, [r9+8]; DesiredAccess
0x14006c2d5  call    cs:__imp_ObReferenceObjectByHandle
0x14006c2dc  nop     dword ptr [rax+rax+00h]
0x14006c2e1  mov     ebx, eax
0x14006c2e3  test    eax, eax
0x14006c2e5  jns     loc_14006C202
0x14006c2eb  jmp     short loc_14006C287
0x14006c2ed  lea     rcx, [rsp+180h+SubjectContext]; SubjectContext
0x14006c2f2  call    cs:__imp_SeReleaseSubjectContext
0x14006c2f9  nop     dword ptr [rax+rax+00h]
0x14006c2fe  test    rsi, rsi
0x14006c301  jz      short loc_14006C287
0x14006c303  mov     eax, ebx
0x14006c305  mov     rcx, [rbp+80h+var_30]
0x14006c309  xor     rcx, rsp; StackCookie
0x14006c30c  call    __security_check_cookie
0x14006c311  mov     rbx, [rsp+180h+arg_18]
0x14006c319  add     rsp, 160h
0x14006c320  pop     r15
0x14006c322  pop     r14
0x14006c324  pop     rdi
0x14006c325  pop     rsi
0x14006c326  pop     rbp
0x14006c327  retn
0x14006c329  mov     [rbp+80h+ObjectAttributes.RootDirectory], rax
0x14006c32d  lea     r8, [rbp+80h+ObjectAttributes]; ObjectAttributes
0x14006c331  mov     [rbp+80h+ObjectAttributes.ObjectName], rax
0x14006c335  xor     r9d, r9d; EffectiveOnly
0x14006c338  mov     [rbp+80h+ObjectAttributes.SecurityDescriptor], rax
0x14006c33c  mov     rcx, rsi; ExistingTokenHandle
0x14006c33f  lea     rax, [rbp+80h+var_C8]
0x14006c343  mov     [rbp+80h+ObjectAttributes.Length], 30h ; '0'
0x14006c34a  mov     [rbp+80h+ObjectAttributes.SecurityQualityOfService], rax
0x14006c34e  lea     rax, [rsp+180h+Handle]
0x14006c353  mov     [rsp+180h+Privileges], rax; NewTokenHandle
0x14006c358  lea     edx, [r9+8]; DesiredAccess
0x14006c35c  mov     [rsp+180h+PreviouslyGrantedAccess], 2; TokenType
0x14006c364  mov     [rbp+80h+ObjectAttributes.Attributes], 200h
0x14006c36b  mov     dword ptr [rbp+80h+var_C8], 0Ch
0x14006c372  mov     dword ptr [rbp+80h+var_C8+4], 2
0x14006c379  mov     word ptr [rbp+80h+var_C0], 1
0x14006c37f  call    cs:__imp_ZwDuplicateToken
0x14006c386  nop     dword ptr [rax+rax+00h]
0x14006c38b  mov     ebx, eax
0x14006c38d  test    eax, eax
0x14006c38f  js      loc_14006C303
0x14006c395  xor     esi, esi
0x14006c397  jmp     loc_14006C16A
0x14006c39c  cmp     [rbp+80h+var_CC], 1
0x14006c3a0  jnz     short loc_14006C3AB
0x14006c3a2  mov     byte ptr [r14], 1
0x14006c3a6  jmp     loc_14006C282
0x14006c3ab  mov     ebx, eax
0x14006c3ad  jmp     loc_14006C282
```
