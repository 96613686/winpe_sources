# Initialize(ushort const *,_NT_PRODUCT_TYPE *,_POLICY_LSA_SERVER_ROLE *,_POLICY_ACCOUNT_DOMAIN_INFO *,_POLICY_PRIMARY_DOMAIN_INFO *)

- ea: `0x18003f354`
- end: `0x18003f84a`
- name: `?Initialize@@YAJPEBGPEAW4_NT_PRODUCT_TYPE@@PEAW4_POLICY_LSA_SERVER_ROLE@@PEAU_POLICY_ACCOUNT_DOMAIN_INFO@@PEAU_POLICY_PRIMARY_DOMAIN_INFO@@@Z`
- size: `1270`
- prototype: `NTSTATUS __fastcall(PCWSTR SourceString, enum _NT_PRODUCT_TYPE *, enum _POLICY_LSA_SERVER_ROLE *, struct _POLICY_ACCOUNT_DOMAIN_INFO *, struct _POLICY_PRIMARY_DOMAIN_INFO *)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180041430`

## callees

- `0x18002cd80`
- `0x180037284`
- `0x1800372ac`
- `0x18003f354`
- `0x18003fad4`
- `0x180041034`
- `0x1800413ac`

## import_xrefs

- `ntdll!RtlpNtCreateKey` at `0x18003f775`
- `ntdll!RtlpNtCreateKey` at `0x18003f775`
- `ntdll!RtlGetNtProductType` at `0x18003f692`
- `ntdll!RtlGetNtProductType` at `0x18003f692`
- `ntdll!RtlSubAuthoritySid` at `0x18003f412`
- `ntdll!RtlSubAuthoritySid` at `0x18003f46a`
- `ntdll!RtlSubAuthoritySid` at `0x18003f482`
- `ntdll!RtlSubAuthoritySid` at `0x18003f4d8`
- `ntdll!RtlSubAuthoritySid` at `0x18003f4f0`
- `ntdll!RtlSubAuthoritySid` at `0x18003f546`
- `ntdll!RtlSubAuthoritySid` at `0x18003f55e`
- `ntdll!RtlSubAuthoritySid` at `0x18003f5b4`
- `ntdll!RtlSubAuthoritySid` at `0x18003f5cc`
- `ntdll!RtlSubAuthoritySid` at `0x18003f624`
- `ntdll!RtlSubAuthoritySid` at `0x18003f412`
- `ntdll!RtlSubAuthoritySid` at `0x18003f46a`
- `ntdll!RtlSubAuthoritySid` at `0x18003f482`
- `ntdll!RtlSubAuthoritySid` at `0x18003f4d8`
- `ntdll!RtlSubAuthoritySid` at `0x18003f4f0`
- `ntdll!RtlSubAuthoritySid` at `0x18003f546`
- `ntdll!RtlSubAuthoritySid` at `0x18003f55e`
- `ntdll!RtlSubAuthoritySid` at `0x18003f5b4`
- `ntdll!RtlSubAuthoritySid` at `0x18003f5cc`
- `ntdll!RtlSubAuthoritySid` at `0x18003f624`
- `ntdll!RtlInitializeSid` at `0x18003f403`
- `ntdll!RtlInitializeSid` at `0x18003f45b`
- `ntdll!RtlInitializeSid` at `0x18003f4c9`
- `ntdll!RtlInitializeSid` at `0x18003f537`
- `ntdll!RtlInitializeSid` at `0x18003f5a5`
- `ntdll!RtlInitializeSid` at `0x18003f615`
- `ntdll!RtlInitializeSid` at `0x18003f403`
- `ntdll!RtlInitializeSid` at `0x18003f45b`
- `ntdll!RtlInitializeSid` at `0x18003f4c9`
- `ntdll!RtlInitializeSid` at `0x18003f537`
- `ntdll!RtlInitializeSid` at `0x18003f5a5`
- `ntdll!RtlInitializeSid` at `0x18003f615`
- `ntdll!RtlAllocateHeap` at `0x18003f3e3`
- `ntdll!RtlAllocateHeap` at `0x18003f43b`
- `ntdll!RtlAllocateHeap` at `0x18003f4a9`
- `ntdll!RtlAllocateHeap` at `0x18003f517`
- `ntdll!RtlAllocateHeap` at `0x18003f585`
- `ntdll!RtlAllocateHeap` at `0x18003f5f5`
- `ntdll!RtlAllocateHeap` at `0x18003f7d7`
- `ntdll!RtlAllocateHeap` at `0x18003f7ef`
- `ntdll!RtlAllocateHeap` at `0x18003f3e3`
- `ntdll!RtlAllocateHeap` at `0x18003f43b`
- `ntdll!RtlAllocateHeap` at `0x18003f4a9`
- `ntdll!RtlAllocateHeap` at `0x18003f517`
- `ntdll!RtlAllocateHeap` at `0x18003f585`
- `ntdll!RtlAllocateHeap` at `0x18003f5f5`
- `ntdll!RtlAllocateHeap` at `0x18003f7d7`
- `ntdll!RtlAllocateHeap` at `0x18003f7ef`
- `ntdll!RtlLengthRequiredSid` at `0x18003f3cb`
- `ntdll!RtlLengthRequiredSid` at `0x18003f423`
- `ntdll!RtlLengthRequiredSid` at `0x18003f491`
- `ntdll!RtlLengthRequiredSid` at `0x18003f4ff`
- `ntdll!RtlLengthRequiredSid` at `0x18003f56d`
- `ntdll!RtlLengthRequiredSid` at `0x18003f5dd`
- `ntdll!RtlLengthRequiredSid` at `0x18003f3cb`
- `ntdll!RtlLengthRequiredSid` at `0x18003f423`
- `ntdll!RtlLengthRequiredSid` at `0x18003f491`
- `ntdll!RtlLengthRequiredSid` at `0x18003f4ff`
- `ntdll!RtlLengthRequiredSid` at `0x18003f56d`
- `ntdll!RtlLengthRequiredSid` at `0x18003f5dd`
- `ntdll!RtlInitUnicodeString` at `0x18003f6e2`
- `ntdll!RtlInitUnicodeString` at `0x18003f72c`
- `ntdll!RtlInitUnicodeString` at `0x18003f6e2`
- `ntdll!RtlInitUnicodeString` at `0x18003f72c`
- `LSASRV!LsaIOpenPolicyTrusted` at `0x18003f651`
- `LSASRV!LsaIOpenPolicyTrusted` at `0x18003f651`

## pseudocode

```c
NTSTATUS __fastcall Initialize(
        PCWSTR SourceString,
        enum _NT_PRODUCT_TYPE *a2,
        enum _POLICY_LSA_SERVER_ROLE *a3,
        struct _POLICY_ACCOUNT_DOMAIN_INFO *a4,
        struct _POLICY_PRIMARY_DOMAIN_INFO *a5)
{
  ULONG v9; // eax
  PVOID Heap; // rax
  ULONG v11; // eax
  PVOID v12; // rax
  PULONG v13; // rax
  PSID v14; // rcx
  ULONG v15; // eax
  PVOID v16; // rax
  PULONG v17; // rax
  PSID v18; // rcx
  ULONG v19; // eax
  PVOID v20; // rax
  PULONG v21; // rax
  PSID v22; // rcx
  ULONG v23; // eax
  PVOID v24; // rax
  PULONG v25; // rax
  PSID v26; // rcx
  ULONG v27; // eax
  PVOID v28; // rax
  NTSTATUS result; // eax
  PUNICODE_STRING v30; // rcx
  __int64 v31; // rdx
  int v32; // eax
  ULONG Disposition; // [rsp+30h] [rbp-51h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-49h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+48h] [rbp-39h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v36; // [rsp+78h] [rbp-9h] BYREF
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+80h] [rbp-1h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v38; // [rsp+88h] [rbp+7h] BYREF

  Disposition = 0;
  *(_DWORD *)v38.Value = 0;
  *(_WORD *)&v38.Value[4] = 1280;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 256;
  *(_DWORD *)v36.Value = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  *(_WORD *)&v36.Value[4] = 1280;
  DestinationString = 0;
  v9 = RtlLengthRequiredSid(1u);
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
  Sid = Heap;
  if ( !Heap )
    return -1073741801;
  RtlInitializeSid(Heap, &IdentifierAuthority, 1u);
  *RtlSubAuthoritySid(Sid, 0) = 0;
  v11 = RtlLengthRequiredSid(2u);
  v12 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v11);
  Group = v12;
  if ( !v12 )
    return -1073741801;
  RtlInitializeSid(v12, &v36, 2u);
  v13 = RtlSubAuthoritySid(Group, 0);
  v14 = Group;
  *v13 = 32;
  *RtlSubAuthoritySid(v14, 1u) = 544;
  v15 = RtlLengthRequiredSid(2u);
  v16 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v15);
  qword_1800EF7A0 = v16;
  if ( !v16 )
    return -1073741801;
  RtlInitializeSid(v16, &v36, 2u);
  v17 = RtlSubAuthoritySid(qword_1800EF7A0, 0);
  v18 = qword_1800EF7A0;
  *v17 = 32;
  *RtlSubAuthoritySid(v18, 1u) = 547;
  v19 = RtlLengthRequiredSid(2u);
  v20 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v19);
  qword_1800EF798 = v20;
  if ( !v20 )
    return -1073741801;
  RtlInitializeSid(v20, &v36, 2u);
  v21 = RtlSubAuthoritySid(qword_1800EF798, 0);
  v22 = qword_1800EF798;
  *v21 = 32;
  *RtlSubAuthoritySid(v22, 1u) = 545;
  v23 = RtlLengthRequiredSid(2u);
  v24 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v23);
  qword_1800EF7A8 = v24;
  if ( !v24 )
    return -1073741801;
  RtlInitializeSid(v24, &v36, 2u);
  v25 = RtlSubAuthoritySid(qword_1800EF7A8, 0);
  v26 = qword_1800EF7A8;
  *v25 = 32;
  *RtlSubAuthoritySid(v26, 1u) = 548;
  v27 = RtlLengthRequiredSid(1u);
  v28 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v27);
  qword_1800EF788 = v28;
  if ( !v28 )
    return -1073741801;
  RtlInitializeSid(v28, &v38, 1u);
  *RtlSubAuthoritySid(qword_1800EF788, 0) = 18;
  KeyName.MaximumLength = 2000;
  KeyName.Buffer = (PWSTR)qword_1800EF830;
  result = LsaIOpenPolicyTrusted(&qword_1800EF770);
  dword_1800EF708 = result;
  if ( result >= 0 )
  {
    if ( a2 )
    {
      ProductType = *a2;
    }
    else if ( !RtlGetNtProductType(&ProductType) )
    {
      if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
        WPP_SF_(WPP_GLOBAL_Control[3].Buffer, 11, WPP_f50d46da04da33107d90bf406b0e9591_Traceguids);
      return -1073741823;
    }
    RtlInitUnicodeString(&stru_1800EF810, L"Domains");
    result = SampGetDomainPolicy(a4);
    dword_1800EF708 = result;
    if ( result < 0 )
      return result;
    if ( a3 )
      v32 = *a3;
    else
      v32 = (ProductType != NtProductLanManNt) + 2;
    dword_1800EF778 = v32;
    SampGetPrimaryDomainInfo(a5);
    RtlInitUnicodeString(&DestinationString, SourceString);
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    result = RtlpNtCreateKey(&qword_1800F0958, 0x2001Du, &ObjectAttributes, 0, 0, &Disposition);
    dword_1800EF708 = result;
    if ( result >= 0 )
    {
      RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x100u);
      KeyName.Buffer = (PWSTR)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x100u);
      *(_DWORD *)&KeyName.Length = 0x1000000;
      result = InitializeSecurityDescriptors() == 0 ? 0xC0000001 : 0;
      dword_1800EF708 = result;
    }
    else
    {
      v30 = WPP_GLOBAL_Control;
      if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
      {
        v31 = 12;
        goto LABEL_26;
      }
    }
  }
  else
  {
    v30 = WPP_GLOBAL_Control;
    if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
    {
      v31 = 10;
LABEL_26:
      WPP_SF_d(v30[3].Buffer, v31, WPP_f50d46da04da33107d90bf406b0e9591_Traceguids, (unsigned int)result);
      return dword_1800EF708;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18003f354  mov     [rsp-8+arg_8], rbx
0x18003f359  push    rbp
0x18003f35a  push    rsi
0x18003f35b  push    rdi
0x18003f35c  push    r12
0x18003f35e  push    r13
0x18003f360  push    r14
0x18003f362  push    r15
0x18003f364  lea     rbp, [rsp-1Fh]
0x18003f369  sub     rsp, 0A0h
0x18003f370  mov     rax, cs:__security_cookie
0x18003f377  xor     rax, rsp
0x18003f37a  mov     [rbp+4Fh+var_40], rax
0x18003f37e  mov     r15, [rbp+4Fh+arg_20]
0x18003f382  xor     r12d, r12d
0x18003f385  xorps   xmm0, xmm0
0x18003f388  mov     [rbp+4Fh+var_A0], r12d
0x18003f38c  mov     r14, rcx
0x18003f38f  mov     dword ptr [rbp+4Fh+var_48.Value], r12d
0x18003f393  mov     rsi, r9
0x18003f396  mov     word ptr [rbp+4Fh+var_48.Value+4], 500h
0x18003f39c  lea     ecx, [r12+1]; SubAuthorityCount
0x18003f3a1  mov     dword ptr [rbp+4Fh+IdentifierAuthority.Value], r12d
0x18003f3a5  mov     rdi, r8
0x18003f3a8  mov     word ptr [rbp+4Fh+IdentifierAuthority.Value+4], 100h
0x18003f3ae  mov     rbx, rdx
0x18003f3b1  mov     dword ptr [rbp+4Fh+var_58.Value], r12d
0x18003f3b5  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.Length], xmm0
0x18003f3b9  mov     word ptr [rbp+4Fh+var_58.Value+4], 500h
0x18003f3bf  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.ObjectName], xmm0
0x18003f3c3  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x18003f3c7  movups  xmmword ptr [rbp+4Fh+DestinationString.Length], xmm0
0x18003f3cb  call    cs:__imp_RtlLengthRequiredSid
0x18003f3d1  mov     rcx, gs:60h
0x18003f3da  xor     edx, edx; Flags
0x18003f3dc  mov     r8d, eax; Size
0x18003f3df  mov     rcx, [rcx+30h]; HeapHandle
0x18003f3e3  call    cs:__imp_RtlAllocateHeap
0x18003f3e9  mov     cs:Sid, rax
0x18003f3f0  test    rax, rax
0x18003f3f3  jz      loc_18003F81E
0x18003f3f9  mov     r8b, 1; SubAuthorityCount
0x18003f3fc  lea     rdx, [rbp+4Fh+IdentifierAuthority]; IdentifierAuthority
0x18003f400  mov     rcx, rax; Sid
0x18003f403  call    cs:__imp_RtlInitializeSid
0x18003f409  mov     rcx, cs:Sid; Sid
0x18003f410  xor     edx, edx; SubAuthority
0x18003f412  call    cs:__imp_RtlSubAuthoritySid
0x18003f418  lea     r13d, [r12+2]
0x18003f41d  mov     ecx, r13d; SubAuthorityCount
0x18003f420  mov     [rax], r12d
0x18003f423  call    cs:__imp_RtlLengthRequiredSid
0x18003f429  mov     rcx, gs:60h
0x18003f432  xor     edx, edx; Flags
0x18003f434  mov     r8d, eax; Size
0x18003f437  mov     rcx, [rcx+30h]; HeapHandle
0x18003f43b  call    cs:__imp_RtlAllocateHeap
0x18003f441  mov     cs:Group, rax
0x18003f448  test    rax, rax
0x18003f44b  jz      loc_18003F81E
0x18003f451  mov     r8b, r13b; SubAuthorityCount
0x18003f454  lea     rdx, [rbp+4Fh+var_58]; IdentifierAuthority
0x18003f458  mov     rcx, rax; Sid
0x18003f45b  call    cs:__imp_RtlInitializeSid
0x18003f461  mov     rcx, cs:Group; Sid
0x18003f468  xor     edx, edx; SubAuthority
0x18003f46a  call    cs:__imp_RtlSubAuthoritySid
0x18003f470  mov     rcx, cs:Group; Sid
0x18003f477  lea     edx, [r12+1]; SubAuthority
0x18003f47c  mov     dword ptr [rax], 20h ; ' '
0x18003f482  call    cs:__imp_RtlSubAuthoritySid
0x18003f488  mov     ecx, r13d; SubAuthorityCount
0x18003f48b  mov     dword ptr [rax], 220h
0x18003f491  call    cs:__imp_RtlLengthRequiredSid
0x18003f497  mov     rcx, gs:60h
0x18003f4a0  xor     edx, edx; Flags
0x18003f4a2  mov     r8d, eax; Size
0x18003f4a5  mov     rcx, [rcx+30h]; HeapHandle
0x18003f4a9  call    cs:__imp_RtlAllocateHeap
0x18003f4af  mov     cs:qword_1800EF7A0, rax
0x18003f4b6  test    rax, rax
0x18003f4b9  jz      loc_18003F81E
0x18003f4bf  mov     r8b, r13b; SubAuthorityCount
0x18003f4c2  lea     rdx, [rbp+4Fh+var_58]; IdentifierAuthority
0x18003f4c6  mov     rcx, rax; Sid
0x18003f4c9  call    cs:__imp_RtlInitializeSid
0x18003f4cf  mov     rcx, cs:qword_1800EF7A0; Sid
0x18003f4d6  xor     edx, edx; SubAuthority
0x18003f4d8  call    cs:__imp_RtlSubAuthoritySid
0x18003f4de  mov     rcx, cs:qword_1800EF7A0; Sid
0x18003f4e5  lea     edx, [r12+1]; SubAuthority
0x18003f4ea  mov     dword ptr [rax], 20h ; ' '
0x18003f4f0  call    cs:__imp_RtlSubAuthoritySid
0x18003f4f6  mov     ecx, r13d; SubAuthorityCount
0x18003f4f9  mov     dword ptr [rax], 223h
0x18003f4ff  call    cs:__imp_RtlLengthRequiredSid
0x18003f505  mov     rcx, gs:60h
0x18003f50e  xor     edx, edx; Flags
0x18003f510  mov     r8d, eax; Size
0x18003f513  mov     rcx, [rcx+30h]; HeapHandle
0x18003f517  call    cs:__imp_RtlAllocateHeap
0x18003f51d  mov     cs:qword_1800EF798, rax
0x18003f524  test    rax, rax
0x18003f527  jz      loc_18003F81E
0x18003f52d  mov     r8b, r13b; SubAuthorityCount
0x18003f530  lea     rdx, [rbp+4Fh+var_58]; IdentifierAuthority
0x18003f534  mov     rcx, rax; Sid
0x18003f537  call    cs:__imp_RtlInitializeSid
0x18003f53d  mov     rcx, cs:qword_1800EF798; Sid
0x18003f544  xor     edx, edx; SubAuthority
0x18003f546  call    cs:__imp_RtlSubAuthoritySid
0x18003f54c  mov     rcx, cs:qword_1800EF798; Sid
0x18003f553  lea     edx, [r12+1]; SubAuthority
0x18003f558  mov     dword ptr [rax], 20h ; ' '
0x18003f55e  call    cs:__imp_RtlSubAuthoritySid
0x18003f564  mov     ecx, r13d; SubAuthorityCount
0x18003f567  mov     dword ptr [rax], 221h
0x18003f56d  call    cs:__imp_RtlLengthRequiredSid
0x18003f573  mov     rcx, gs:60h
0x18003f57c  xor     edx, edx; Flags
0x18003f57e  mov     r8d, eax; Size
0x18003f581  mov     rcx, [rcx+30h]; HeapHandle
0x18003f585  call    cs:__imp_RtlAllocateHeap
0x18003f58b  mov     cs:qword_1800EF7A8, rax
0x18003f592  test    rax, rax
0x18003f595  jz      loc_18003F81E
0x18003f59b  mov     r8b, r13b; SubAuthorityCount
0x18003f59e  lea     rdx, [rbp+4Fh+var_58]; IdentifierAuthority
0x18003f5a2  mov     rcx, rax; Sid
0x18003f5a5  call    cs:__imp_RtlInitializeSid
0x18003f5ab  mov     rcx, cs:qword_1800EF7A8; Sid
0x18003f5b2  xor     edx, edx; SubAuthority
0x18003f5b4  call    cs:__imp_RtlSubAuthoritySid
0x18003f5ba  mov     rcx, cs:qword_1800EF7A8; Sid
0x18003f5c1  lea     edx, [r12+1]; SubAuthority
0x18003f5c6  mov     dword ptr [rax], 20h ; ' '
0x18003f5cc  call    cs:__imp_RtlSubAuthoritySid
0x18003f5d2  lea     ecx, [r12+1]; SubAuthorityCount
0x18003f5d7  mov     dword ptr [rax], 224h
0x18003f5dd  call    cs:__imp_RtlLengthRequiredSid
0x18003f5e3  mov     rcx, gs:60h
0x18003f5ec  xor     edx, edx; Flags
0x18003f5ee  mov     r8d, eax; Size
0x18003f5f1  mov     rcx, [rcx+30h]; HeapHandle
0x18003f5f5  call    cs:__imp_RtlAllocateHeap
0x18003f5fb  mov     cs:qword_1800EF788, rax
0x18003f602  test    rax, rax
0x18003f605  jz      loc_18003F81E
0x18003f60b  mov     r8b, 1; SubAuthorityCount
0x18003f60e  lea     rdx, [rbp+4Fh+var_48]; IdentifierAuthority
0x18003f612  mov     rcx, rax; Sid
0x18003f615  call    cs:__imp_RtlInitializeSid
0x18003f61b  mov     rcx, cs:qword_1800EF788; Sid
0x18003f622  xor     edx, edx; SubAuthority
0x18003f624  call    cs:__imp_RtlSubAuthoritySid
0x18003f62a  lea     rcx, qword_1800EF770
0x18003f631  mov     dword ptr [rax], 12h
0x18003f637  mov     eax, 7D0h
0x18003f63c  mov     cs:KeyName.MaximumLength, ax
0x18003f643  lea     rax, qword_1800EF830
0x18003f64a  mov     cs:KeyName.Buffer, rax
0x18003f651  call    cs:__imp_LsaIOpenPolicyTrusted
0x18003f657  mov     cs:dword_1800EF708, eax
0x18003f65d  test    eax, eax
0x18003f65f  jns     short loc_18003F686
0x18003f661  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f668  test    byte ptr [rcx+44h], 1
0x18003f66c  jz      loc_18003F823
0x18003f672  cmp     [rcx+41h], r13b
0x18003f676  jb      loc_18003F823
0x18003f67c  lea     edx, [r12+0Ah]
0x18003f681  jmp     loc_18003F7A5
0x18003f686  test    rbx, rbx
0x18003f689  jnz     short loc_18003F6CC
0x18003f68b  lea     rcx, ProductType; ProductType
0x18003f692  call    cs:__imp_RtlGetNtProductType
0x18003f698  test    al, al
0x18003f69a  jnz     short loc_18003F6D4
0x18003f69c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f6a3  test    byte ptr [rcx+44h], 1
0x18003f6a7  jz      short loc_18003F6C2
0x18003f6a9  cmp     [rcx+41h], r13b
0x18003f6ad  jb      short loc_18003F6C2
0x18003f6af  mov     rcx, [rcx+38h]
0x18003f6b3  lea     edx, [rbx+0Bh]
0x18003f6b6  lea     r8, WPP_f50d46da04da33107d90bf406b0e9591_Traceguids
0x18003f6bd  call    WPP_SF_
0x18003f6c2  mov     eax, 0C0000001h
0x18003f6c7  jmp     loc_18003F823
0x18003f6cc  mov     eax, [rbx]
0x18003f6ce  mov     cs:ProductType, eax
0x18003f6d4  lea     rdx, aDomains; "Domains"
0x18003f6db  lea     rcx, stru_1800EF810; DestinationString
0x18003f6e2  call    cs:__imp_RtlInitUnicodeString
0x18003f6e8  mov     rcx, rsi; struct _POLICY_ACCOUNT_DOMAIN_INFO *
0x18003f6eb  call    ?SampGetDomainPolicy@@YAJPEAU_POLICY_ACCOUNT_DOMAIN_INFO@@@Z; SampGetDomainPolicy(_POLICY_ACCOUNT_DOMAIN_INFO *)
0x18003f6f0  mov     cs:dword_1800EF708, eax
0x18003f6f6  test    eax, eax
0x18003f6f8  js      loc_18003F823
0x18003f6fe  test    rdi, rdi
0x18003f701  jnz     short loc_18003F715
0x18003f703  cmp     cs:ProductType, r13d
0x18003f70a  mov     eax, r12d
0x18003f70d  setnz   al
0x18003f710  add     eax, r13d
0x18003f713  jmp     short loc_18003F717
0x18003f715  mov     eax, [rdi]
0x18003f717  mov     rcx, r15; struct _POLICY_PRIMARY_DOMAIN_INFO *
0x18003f71a  mov     cs:dword_1800EF778, eax
0x18003f720  call    ?SampGetPrimaryDomainInfo@@YAXPEAU_POLICY_PRIMARY_DOMAIN_INFO@@@Z; SampGetPrimaryDomainInfo(_POLICY_PRIMARY_DOMAIN_INFO *)
0x18003f725  mov     rdx, r14; SourceString
0x18003f728  lea     rcx, [rbp+4Fh+DestinationString]; DestinationString
0x18003f72c  call    cs:__imp_RtlInitUnicodeString
0x18003f732  lea     rax, [rbp+4Fh+DestinationString]
0x18003f736  mov     [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x18003f73d  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rax
0x18003f741  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x18003f745  lea     rax, [rbp+4Fh+var_A0]
0x18003f749  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], r12
0x18003f74d  xorps   xmm0, xmm0
0x18003f750  mov     [rsp+0D0h+Disposition], rax; Disposition
0x18003f755  xor     r9d, r9d; TitleIndex
0x18003f758  mov     [rsp+0D0h+Class], r12; Class
0x18003f75d  mov     edx, 2001Dh; DesiredAccess
0x18003f762  mov     [rbp+4Fh+ObjectAttributes.Attributes], 40h ; '@'
0x18003f769  lea     rcx, qword_1800F0958; KeyHandle
0x18003f770  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x18003f775  call    cs:__imp_RtlpNtCreateKey
0x18003f77b  mov     cs:dword_1800EF708, eax
0x18003f781  test    eax, eax
0x18003f783  jns     short loc_18003F7C0
0x18003f785  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f78c  test    byte ptr [rcx+44h], 1
0x18003f790  jz      loc_18003F823
0x18003f796  cmp     [rcx+41h], r13b
0x18003f79a  jb      loc_18003F823
0x18003f7a0  mov     edx, 0Ch
0x18003f7a5  mov     rcx, [rcx+38h]
0x18003f7a9  lea     r8, WPP_f50d46da04da33107d90bf406b0e9591_Traceguids
0x18003f7b0  mov     r9d, eax
0x18003f7b3  call    WPP_SF_d
0x18003f7b8  mov     eax, cs:dword_1800EF708
0x18003f7be  jmp     short loc_18003F823
0x18003f7c0  mov     rcx, gs:60h
0x18003f7c9  mov     ebx, 100h
0x18003f7ce  mov     r8d, ebx; Size
0x18003f7d1  xor     edx, edx; Flags
0x18003f7d3  mov     rcx, [rcx+30h]; HeapHandle
0x18003f7d7  call    cs:__imp_RtlAllocateHeap
0x18003f7dd  mov     rcx, gs:60h
0x18003f7e6  mov     r8d, ebx; Size
0x18003f7e9  xor     edx, edx; Flags
0x18003f7eb  mov     rcx, [rcx+30h]; HeapHandle
0x18003f7ef  call    cs:__imp_RtlAllocateHeap
0x18003f7f5  mov     cs:KeyName.Buffer, rax
0x18003f7fc  mov     dword ptr cs:KeyName.Length, 1000000h
0x18003f806  call    ?InitializeSecurityDescriptors@@YAEXZ; InitializeSecurityDescriptors(void)
0x18003f80b  neg     al
0x18003f80d  sbb     eax, eax
0x18003f80f  not     eax
0x18003f811  and     eax, 0C0000001h
0x18003f816  mov     cs:dword_1800EF708, eax
0x18003f81c  jmp     short loc_18003F823
0x18003f81e  mov     eax, 0C0000017h
0x18003f823  mov     rcx, [rbp+4Fh+var_40]
0x18003f827  xor     rcx, rsp; StackCookie
0x18003f82a  call    __security_check_cookie
0x18003f82f  mov     rbx, [rsp+0D0h+arg_8]
0x18003f837  add     rsp, 0A0h
0x18003f83e  pop     r15
0x18003f840  pop     r14
0x18003f842  pop     r13
0x18003f844  pop     r12
0x18003f846  pop     rdi
0x18003f847  pop     rsi
0x18003f848  pop     rbp
0x18003f849  retn
```
