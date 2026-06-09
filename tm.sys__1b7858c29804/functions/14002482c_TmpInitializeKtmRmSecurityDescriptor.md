# TmpInitializeKtmRmSecurityDescriptor

- ea: `0x14002482c`
- end: `0x140024b12`
- name: `TmpInitializeKtmRmSecurityDescriptor`
- size: `742`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140024080`

## callees

- `0x1400024e0`
- `0x14002482c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140024ab3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140024ac9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140024adf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140024b4c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140024b64`
- `ntoskrnl!ExFreePoolWithTag` at `0x140024b7c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140024ab3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140024ac9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140024adf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140024b4c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140024b64`
- `ntoskrnl!ExFreePoolWithTag` at `0x140024b7c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400248c2`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140024918`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002499c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400248c2`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140024918`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002499c`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140024a8d`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140024a8d`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1400248ec`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1400248ec`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140024901`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140024901`
- `ntoskrnl!RtlInitializeSid` at `0x14002493f`
- `ntoskrnl!RtlInitializeSid` at `0x14002493f`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140024967`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140024967`
- `ntoskrnl!RtlCreateAcl` at `0x1400249c4`
- `ntoskrnl!RtlCreateAcl` at `0x1400249c4`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400249ed`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400249ed`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140024a0f`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140024a0f`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140024a33`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140024a33`
- `ntoskrnl!SeAssignSecurity` at `0x140024a70`
- `ntoskrnl!SeAssignSecurity` at `0x140024a70`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140024aa2`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140024b3b`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140024aa2`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140024b3b`

## pseudocode

```c
bool TmpInitializeKtmRmSecurityDescriptor()
{
  unsigned __int8 *v0; // rsi
  struct _ACL *v1; // rdi
  struct _SECURITY_SUBJECT_CONTEXT *PoolWithTag; // rax
  struct _SECURITY_SUBJECT_CONTEXT *SubjectContext; // r14
  NTSTATUS Acl; // ebx
  ULONG v5; // eax
  unsigned __int8 *v6; // rax
  unsigned __int16 i; // bx
  ULONG v8; // ebx
  struct _ACL *v9; // rax
  _DWORD v11[6]; // [rsp+60h] [rbp-88h]
  _OWORD SecurityDescriptor[2]; // [rsp+78h] [rbp-70h] BYREF
  __int64 v13; // [rsp+98h] [rbp-50h]
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+A0h] [rbp-48h] BYREF

  v11[0] = 80;
  v11[1] = -1476609712;
  v11[2] = -907901543;
  v11[3] = -294573354;
  v11[4] = 342927828;
  v11[5] = 138088443;
  v0 = 0;
  v1 = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  v13 = 0;
  PoolWithTag = (struct _SECURITY_SUBJECT_CONTEXT *)ExAllocatePoolWithTag(PagedPool, 0x20u, 0x63536D54u);
  SubjectContext = PoolWithTag;
  if ( !PoolWithTag )
    goto LABEL_2;
  SeCaptureSubjectContext(PoolWithTag);
  v5 = RtlLengthRequiredSid(6u);
  v6 = (unsigned __int8 *)ExAllocatePoolWithTag(PagedPool, v5, 0x73526D54u);
  v0 = v6;
  if ( !v6 )
    goto LABEL_2;
  Acl = RtlInitializeSid(v6, &IdentifierAuthority, 6u);
  if ( Acl < 0 )
    goto LABEL_15;
  for ( i = 0; i < 6u; ++i )
    *RtlSubAuthoritySid(v0, i) = v11[i];
  v8 = (unsigned __int16)(4 * (v0[1] + 7));
  v9 = (struct _ACL *)ExAllocatePoolWithTag(PagedPool, (unsigned __int16)(4 * (v0[1] + 7)), 0x644E6D54u);
  v1 = v9;
  if ( !v9 )
  {
LABEL_2:
    Acl = -1073741670;
    goto LABEL_15;
  }
  Acl = RtlCreateAcl(v9, v8, 2u);
  if ( Acl >= 0 )
  {
    Acl = RtlAddAccessAllowedAce(v1, v1->AclRevision, 0x1F007Fu, v0);
    if ( Acl >= 0 )
    {
      Acl = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
      if ( Acl >= 0 )
      {
        Acl = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v1, 0);
        if ( Acl >= 0 )
        {
          Acl = SeAssignSecurity(
                  0,
                  SecurityDescriptor,
                  &TmpKtmRmDescriptor,
                  0,
                  SubjectContext,
                  (PGENERIC_MAPPING)&TmpResourceManagerMapping,
                  PagedPool);
          if ( Acl >= 0 )
            RtlLengthSecurityDescriptor(TmpKtmRmDescriptor);
        }
      }
    }
  }
LABEL_15:
  if ( SubjectContext )
  {
    SeReleaseSubjectContext(SubjectContext);
    ExFreePoolWithTag(SubjectContext, 0);
  }
  if ( v1 )
    ExFreePoolWithTag(v1, 0);
  if ( v0 )
    ExFreePoolWithTag(v0, 0);
  return Acl >= 0;
}

```

## disassembly

```asm
0x14002482c  mov     r11, rsp
0x14002482f  push    rbx
0x140024830  push    rsi
0x140024831  push    rdi
0x140024832  push    r12
0x140024834  push    r13
0x140024836  push    r14
0x140024838  sub     rsp, 0B8h
0x14002483f  mov     rax, cs:__security_cookie
0x140024846  xor     rax, rsp
0x140024849  mov     [rsp+0E8h+var_40], rax
0x140024851  mov     [rsp+0E8h+var_88], 50h ; 'P'
0x140024859  mov     [rsp+0E8h+var_84], 0A7FCB950h
0x140024861  mov     [rsp+0E8h+var_80], 0C9E28599h
0x140024869  mov     [rsp+0E8h+var_7C], 0EE712AD6h
0x140024871  mov     [rsp+0E8h+var_78], 1470A9D4h
0x140024879  mov     [rsp+0E8h+var_74], 83B0FFBh
0x140024881  xor     esi, esi
0x140024883  mov     [rsp+0E8h+var_90], rsi
0x140024888  xor     edi, edi
0x14002488a  mov     [rsp+0E8h+var_98], rdi
0x14002488f  mov     [r11-48h], esi
0x140024893  mov     word ptr [r11-44h], 500h
0x14002489a  xorps   xmm0, xmm0
0x14002489d  xor     eax, eax
0x14002489f  movups  [rsp+0E8h+SecurityDescriptor], xmm0
0x1400248a4  movups  xmmword ptr [r11-60h], xmm0
0x1400248a9  mov     [r11-50h], rax
0x1400248ad  mov     [rsp+0E8h+var_A0], rax
0x1400248b2  lea     edx, [rsi+20h]; NumberOfBytes
0x1400248b5  mov     r8d, 63536D54h; Tag
0x1400248bb  lea     r12d, [rsi+1]
0x1400248bf  mov     ecx, r12d; PoolType
0x1400248c2  call    cs:__imp_ExAllocatePoolWithTag
0x1400248c9  nop     dword ptr [rax+rax+00h]
0x1400248ce  mov     r14, rax
0x1400248d1  mov     [rsp+0E8h+var_A0], rax
0x1400248d6  test    rax, rax
0x1400248d9  jnz     short loc_1400248E9
0x1400248db  mov     ebx, 0C000009Ah
0x1400248e0  mov     [rsp+0E8h+var_A8], ebx
0x1400248e4  jmp     loc_140024A9A
0x1400248e9  mov     rcx, r14; SubjectContext
0x1400248ec  call    cs:__imp_SeCaptureSubjectContext
0x1400248f3  nop     dword ptr [rax+rax+00h]
0x1400248f8  mov     r13d, 6
0x1400248fe  mov     ecx, r13d; SubAuthorityCount
0x140024901  call    cs:__imp_RtlLengthRequiredSid
0x140024908  nop     dword ptr [rax+rax+00h]
0x14002490d  mov     edx, eax; NumberOfBytes
0x14002490f  mov     r8d, 73526D54h; Tag
0x140024915  mov     ecx, r12d; PoolType
0x140024918  call    cs:__imp_ExAllocatePoolWithTag
0x14002491f  nop     dword ptr [rax+rax+00h]
0x140024924  mov     rsi, rax
0x140024927  mov     [rsp+0E8h+var_90], rax
0x14002492c  test    rax, rax
0x14002492f  jz      short loc_1400248DB
0x140024931  mov     r8b, r13b; SubAuthorityCount
0x140024934  lea     rdx, [rsp+0E8h+IdentifierAuthority]; IdentifierAuthority
0x14002493c  mov     rcx, rax; Sid
0x14002493f  call    cs:__imp_RtlInitializeSid
0x140024946  nop     dword ptr [rax+rax+00h]
0x14002494b  mov     ebx, eax
0x14002494d  mov     [rsp+0E8h+var_A8], eax
0x140024951  test    eax, eax
0x140024953  js      loc_140024A9A
0x140024959  xor     ebx, ebx
0x14002495b  cmp     bx, r13w
0x14002495f  jnb     short loc_140024982
0x140024961  movzx   edx, bx; SubAuthority
0x140024964  mov     rcx, rsi; Sid
0x140024967  call    cs:__imp_RtlSubAuthoritySid
0x14002496e  nop     dword ptr [rax+rax+00h]
0x140024973  movzx   ecx, bx
0x140024976  mov     edx, [rsp+rcx*4+0E8h+var_88]
0x14002497a  mov     [rax], edx
0x14002497c  add     bx, r12w
0x140024980  jmp     short loc_14002495B
0x140024982  movzx   eax, byte ptr [rsi+1]
0x140024986  add     ax, 7
0x14002498a  shl     ax, 2
0x14002498e  movzx   ebx, ax
0x140024991  mov     edx, ebx; NumberOfBytes
0x140024993  mov     r8d, 644E6D54h; Tag
0x140024999  mov     ecx, r12d; PoolType
0x14002499c  call    cs:__imp_ExAllocatePoolWithTag
0x1400249a3  nop     dword ptr [rax+rax+00h]
0x1400249a8  mov     rdi, rax
0x1400249ab  mov     [rsp+0E8h+var_98], rax
0x1400249b0  test    rax, rax
0x1400249b3  jz      loc_1400248DB
0x1400249b9  mov     edx, ebx; AclLength
0x1400249bb  mov     r8d, 2; AclRevision
0x1400249c1  mov     rcx, rax; Acl
0x1400249c4  call    cs:__imp_RtlCreateAcl
0x1400249cb  nop     dword ptr [rax+rax+00h]
0x1400249d0  mov     ebx, eax
0x1400249d2  mov     [rsp+0E8h+var_A8], eax
0x1400249d6  test    eax, eax
0x1400249d8  js      loc_140024A9A
0x1400249de  movzx   edx, byte ptr [rdi]; AceRevision
0x1400249e1  mov     r9, rsi; Sid
0x1400249e4  mov     r8d, 1F007Fh; AccessMask
0x1400249ea  mov     rcx, rdi; Acl
0x1400249ed  call    cs:__imp_RtlAddAccessAllowedAce
0x1400249f4  nop     dword ptr [rax+rax+00h]
0x1400249f9  mov     ebx, eax
0x1400249fb  mov     [rsp+0E8h+var_A8], eax
0x1400249ff  test    eax, eax
0x140024a01  js      loc_140024A9A
0x140024a07  mov     edx, r12d; Revision
0x140024a0a  lea     rcx, [rsp+0E8h+SecurityDescriptor]; SecurityDescriptor
0x140024a0f  call    cs:__imp_RtlCreateSecurityDescriptor
0x140024a16  nop     dword ptr [rax+rax+00h]
0x140024a1b  mov     ebx, eax
0x140024a1d  mov     [rsp+0E8h+var_A8], eax
0x140024a21  test    eax, eax
0x140024a23  js      short loc_140024A9A
0x140024a25  xor     r9d, r9d; DaclDefaulted
0x140024a28  mov     r8, rdi; Dacl
0x140024a2b  mov     dl, r12b; DaclPresent
0x140024a2e  lea     rcx, [rsp+0E8h+SecurityDescriptor]; SecurityDescriptor
0x140024a33  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x140024a3a  nop     dword ptr [rax+rax+00h]
0x140024a3f  mov     ebx, eax
0x140024a41  mov     [rsp+0E8h+var_A8], eax
0x140024a45  test    eax, eax
0x140024a47  js      short loc_140024A9A
0x140024a49  mov     [rsp+0E8h+PoolType], r12d; PoolType
0x140024a4e  lea     rax, TmpResourceManagerMapping
0x140024a55  mov     [rsp+0E8h+GenericMapping], rax; GenericMapping
0x140024a5a  mov     [rsp+0E8h+SubjectContext], r14; SubjectContext
0x140024a5f  xor     r9d, r9d; IsDirectoryObject
0x140024a62  lea     r8, TmpKtmRmDescriptor; NewDescriptor
0x140024a69  lea     rdx, [rsp+0E8h+SecurityDescriptor]; ExplicitDescriptor
0x140024a6e  xor     ecx, ecx; ParentDescriptor
0x140024a70  call    cs:__imp_SeAssignSecurity
0x140024a77  nop     dword ptr [rax+rax+00h]
0x140024a7c  mov     ebx, eax
0x140024a7e  mov     [rsp+0E8h+var_A8], eax
0x140024a82  test    eax, eax
0x140024a84  js      short loc_140024A9A
0x140024a86  mov     rcx, cs:TmpKtmRmDescriptor; SecurityDescriptor
0x140024a8d  call    cs:__imp_RtlLengthSecurityDescriptor
0x140024a94  nop     dword ptr [rax+rax+00h]
0x140024a99  nop
0x140024a9a  test    r14, r14
0x140024a9d  jz      short loc_140024ABF
0x140024a9f  mov     rcx, r14; SubjectContext
0x140024aa2  call    cs:__imp_SeReleaseSubjectContext
0x140024aa9  nop     dword ptr [rax+rax+00h]
0x140024aae  xor     edx, edx; Tag
0x140024ab0  mov     rcx, r14; P
0x140024ab3  call    cs:__imp_ExFreePoolWithTag
0x140024aba  nop     dword ptr [rax+rax+00h]
0x140024abf  test    rdi, rdi
0x140024ac2  jz      short loc_140024AD5
0x140024ac4  xor     edx, edx; Tag
0x140024ac6  mov     rcx, rdi; P
0x140024ac9  call    cs:__imp_ExFreePoolWithTag
0x140024ad0  nop     dword ptr [rax+rax+00h]
0x140024ad5  test    rsi, rsi
0x140024ad8  jz      short loc_140024AEB
0x140024ada  xor     edx, edx; Tag
0x140024adc  mov     rcx, rsi; P
0x140024adf  call    cs:__imp_ExFreePoolWithTag
0x140024ae6  nop     dword ptr [rax+rax+00h]
0x140024aeb  test    ebx, ebx
0x140024aed  setns   al
0x140024af0  mov     rcx, [rsp+0E8h+var_40]
0x140024af8  xor     rcx, rsp; StackCookie
0x140024afb  call    __security_check_cookie
0x140024b00  add     rsp, 0B8h
0x140024b07  pop     r14
0x140024b09  pop     r13
0x140024b0b  pop     r12
0x140024b0d  pop     rdi
0x140024b0e  pop     rsi
0x140024b0f  pop     rbx
0x140024b10  retn
0x140024b25  push    rbx
0x140024b27  push    rbp
0x140024b28  sub     rsp, 48h
0x140024b2c  mov     rbp, rdx
0x140024b2f  mov     rbx, [rbp+48h]
0x140024b33  test    rbx, rbx
0x140024b36  jz      short loc_140024B59
0x140024b38  mov     rcx, rbx; SubjectContext
0x140024b3b  call    cs:__imp_SeReleaseSubjectContext
0x140024b42  nop     dword ptr [rax+rax+00h]
0x140024b47  xor     edx, edx; Tag
0x140024b49  mov     rcx, rbx; P
0x140024b4c  call    cs:__imp_ExFreePoolWithTag
0x140024b53  nop     dword ptr [rax+rax+00h]
0x140024b58  nop
0x140024b59  mov     rcx, [rbp+50h]; P
0x140024b5d  test    rcx, rcx
0x140024b60  jz      short loc_140024B71
0x140024b62  xor     edx, edx; Tag
0x140024b64  call    cs:__imp_ExFreePoolWithTag
0x140024b6b  nop     dword ptr [rax+rax+00h]
0x140024b70  nop
0x140024b71  mov     rcx, [rbp+58h]; P
0x140024b75  test    rcx, rcx
0x140024b78  jz      short loc_140024B89
0x140024b7a  xor     edx, edx; Tag
0x140024b7c  call    cs:__imp_ExFreePoolWithTag
0x140024b83  nop     dword ptr [rax+rax+00h]
0x140024b88  nop
0x140024b89  add     rsp, 48h
0x140024b8d  pop     rbp
0x140024b8e  pop     rbx
0x140024b8f  retn
```
