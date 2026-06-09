# SampGetNewAccountSecurityNt4

- ea: `0x18008c6c0`
- end: `0x18008cced`
- name: `SampGetNewAccountSecurityNt4`
- size: `1581`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18008ac58`

## callees

- `0x18001cfa0`
- `0x18001d0d0`
- `0x180027e24`
- `0x18002cd80`
- `0x18008c6c0`
- `0x1800bb788`

## import_xrefs

- `ntdll!RtlAddAce` at `0x18008cb87`
- `ntdll!RtlAddAce` at `0x18008cb87`
- `ntdll!NtOpenThreadToken` at `0x18008c93f`
- `ntdll!NtOpenThreadToken` at `0x18008c93f`
- `ntdll!RtlSetSecurityObject` at `0x18008cbe9`
- `ntdll!RtlSetSecurityObject` at `0x18008cbe9`
- `ntdll!NtQueryInformationToken` at `0x18008c971`
- `ntdll!NtQueryInformationToken` at `0x18008c9c5`
- `ntdll!NtQueryInformationToken` at `0x18008ca9d`
- `ntdll!NtQueryInformationToken` at `0x18008c971`
- `ntdll!NtQueryInformationToken` at `0x18008c9c5`
- `ntdll!NtQueryInformationToken` at `0x18008ca9d`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x18008c8bf`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x18008cb1e`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x18008c8bf`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x18008cb1e`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18008cbb8`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18008cbb8`
- `ntdll!RtlSubAuthoritySid` at `0x18008c9ec`
- `ntdll!RtlSubAuthoritySid` at `0x18008ca01`
- `ntdll!RtlSubAuthoritySid` at `0x18008c9ec`
- `ntdll!RtlSubAuthoritySid` at `0x18008ca01`
- `ntdll!RtlInitializeSid` at `0x18008c9e0`
- `ntdll!RtlInitializeSid` at `0x18008c9e0`
- `ntdll!RtlFreeHeap` at `0x18008cc4a`
- `ntdll!RtlFreeHeap` at `0x18008cc4a`
- `ntdll!RtlAllocateHeap` at `0x18008c836`
- `ntdll!RtlAllocateHeap` at `0x18008c836`
- `ntdll!RtlCopySid` at `0x18008cb04`
- `ntdll!RtlCopySid` at `0x18008cb04`
- `ntdll!RtlLengthSid` at `0x18008cab0`
- `ntdll!RtlLengthSid` at `0x18008caf5`
- `ntdll!RtlLengthSid` at `0x18008cab0`
- `ntdll!RtlLengthSid` at `0x18008caf5`
- `ntdll!RtlEqualSid` at `0x18008ca2d`
- `ntdll!RtlEqualSid` at `0x18008ca43`
- `ntdll!RtlEqualSid` at `0x18008ca2d`
- `ntdll!RtlEqualSid` at `0x18008ca43`
- `ntdll!NtClose` at `0x18008cb94`
- `ntdll!NtClose` at `0x18008cb94`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008c997`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008ca6f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008cac4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008cb3e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008cc06`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008c997`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008ca6f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008cac4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008cb3e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008cc06`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008cc58`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008cc66`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008cc74`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008cc82`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008cc58`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008cc66`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008cc74`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008cc82`

## pseudocode

```c
__int64 __fastcall SampGetNewAccountSecurityNt4(
        int a1,
        char a2,
        char a3,
        char a4,
        int a5,
        unsigned int a6,
        _QWORD *a7,
        _DWORD *a8)
{
  PSID *v8; // r15
  char *v10; // rdx
  const void *v11; // r13
  _DWORD *v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rax
  PVOID Heap; // rax
  NTSTATUS DaclSecurityDescriptor; // ebx
  _WORD *v18; // rdi
  struct _ACL *v19; // r14
  _DWORD *v20; // rsi
  WORD AceCount; // ax
  ULONG v22; // eax
  __int64 i; // rax
  ULONG v24; // ebx
  PSID v25; // rbx
  ULONG v26; // eax
  ULONG v27; // ebx
  struct _ACL *v28; // rax
  HLOCAL v29; // rax
  unsigned __int8 DaclPresent; // [rsp+30h] [rbp-A1h] BYREF
  char v31; // [rsp+31h] [rbp-A0h]
  unsigned __int8 DaclDefaulted; // [rsp+32h] [rbp-9Fh] BYREF
  char v33; // [rsp+33h] [rbp-9Eh]
  ULONG TokenInformationLength; // [rsp+34h] [rbp-9Dh] BYREF
  ULONG AceListLength; // [rsp+38h] [rbp-99h]
  unsigned int v36; // [rsp+3Ch] [rbp-95h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+40h] [rbp-91h] BYREF
  PACL Dacl; // [rsp+48h] [rbp-89h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp-81h] BYREF
  _QWORD *v40; // [rsp+58h] [rbp-79h]
  PSID Sid1; // [rsp+60h] [rbp-71h]
  _OWORD ModificationDescriptor[2]; // [rsp+68h] [rbp-69h] BYREF
  struct _ACL *v43; // [rsp+88h] [rbp-49h]
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+90h] [rbp-41h] BYREF
  struct _GENERIC_MAPPING GenericMapping; // [rsp+98h] [rbp-39h] BYREF
  _BYTE Sid[32]; // [rsp+A8h] [rbp-29h] BYREF

  v8 = 0;
  memset(ModificationDescriptor, 0, sizeof(ModificationDescriptor));
  v33 = a3;
  v10 = (char *)SampDefinedDomains + 1360 * a6;
  v31 = a4;
  v40 = a7;
  v11 = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  v43 = 0;
  TokenHandle = (void *)-1LL;
  TokenInformationLength = 0;
  Dacl = 0;
  SecurityDescriptor = 0;
  DaclPresent = 0;
  DaclDefaulted = 0;
  v36 = 0;
  GenericMapping = 0;
  if ( a1 == 2 )
  {
    v13 = 56;
    if ( a2 != 1 )
      v13 = 72;
    v11 = *(const void **)&v10[v13];
    v14 = 108;
    if ( a2 != 1 )
      v14 = 116;
    *a8 = *(_DWORD *)&v10[v14];
    GenericMapping.GenericRead = 131088;
    GenericMapping.GenericWrite = 131086;
    GenericMapping.GenericExecute = 131073;
  }
  else
  {
    if ( a1 != 3 )
    {
      if ( a1 == 4 )
      {
        if ( a2 == 1 )
        {
          v11 = (const void *)*((_QWORD *)v10 + 6);
          *a8 = *((_DWORD *)v10 + 26);
          v12 = (_DWORD *)*((_QWORD *)v10 + 11);
        }
        else
        {
          v11 = (const void *)*((_QWORD *)v10 + 8);
          *a8 = *((_DWORD *)v10 + 28);
          v12 = (_DWORD *)*((_QWORD *)v10 + 12);
        }
        *v12 = a5;
        GenericMapping.GenericRead = 131866;
        GenericMapping.GenericWrite = 131140;
        GenericMapping.GenericExecute = 131137;
        GenericMapping.GenericAll = 985087;
      }
      goto LABEL_15;
    }
    v11 = (const void *)*((_QWORD *)v10 + 10);
    *a8 = *((_DWORD *)v10 + 30);
    GenericMapping.GenericRead = 131076;
    GenericMapping.GenericWrite = 131091;
    GenericMapping.GenericExecute = 131080;
  }
  GenericMapping.GenericAll = 983071;
LABEL_15:
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, (unsigned int)*a8);
  SecurityDescriptor = Heap;
  if ( !Heap )
  {
    *a7 = 0;
    *a8 = 0;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
      WPP_SF_Dd(
        WPP_GLOBAL_Control[3].Buffer,
        30,
        WPP_18fb10c206133c98d7a2b000be93359d_Traceguids,
        3221225626LL,
        -1073741670);
    return 3221225626LL;
  }
  DaclSecurityDescriptor = 0;
  v18 = 0;
  v19 = 0;
  v20 = 0;
  memcpy_0(Heap, v11, (unsigned int)*a8);
  if ( v31 )
  {
    DaclSecurityDescriptor = RtlGetDaclSecurityDescriptor(SecurityDescriptor, &DaclPresent, &Dacl, &DaclDefaulted);
    if ( DaclSecurityDescriptor < 0 )
      goto LABEL_55;
    if ( !DaclPresent || !Dacl || (AceCount = Dacl->AceCount) == 0 )
    {
      DaclSecurityDescriptor = -1073741593;
      goto LABEL_55;
    }
    Dacl->AceCount = AceCount - 1;
  }
  v22 = 0;
  AceListLength = 0;
  if ( v33 )
  {
LABEL_52:
    *a8 += v22;
    v29 = LocalAlloc(0x40u, (unsigned int)*a8);
    *v40 = v29;
    if ( v29 )
      memcpy_0(v29, SecurityDescriptor, (unsigned int)*a8);
    else
      DaclSecurityDescriptor = -1073741670;
    goto LABEL_55;
  }
  DaclSecurityDescriptor = SampImpersonateClient(&v36);
  if ( DaclSecurityDescriptor < 0 )
    goto LABEL_55;
  DaclSecurityDescriptor = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 1u, &TokenHandle);
  SampRevertToSelf(v36);
  if ( DaclSecurityDescriptor < 0 )
    goto LABEL_55;
  DaclSecurityDescriptor = NtQueryInformationToken(TokenHandle, TokenGroups, 0, 0, &TokenInformationLength);
  if ( DaclSecurityDescriptor == -1073741789 && TokenInformationLength )
  {
    v20 = LocalAlloc(0x40u, TokenInformationLength);
    if ( !v20 )
      goto LABEL_45;
    DaclSecurityDescriptor = NtQueryInformationToken(
                               TokenHandle,
                               TokenGroups,
                               v20,
                               TokenInformationLength,
                               &TokenInformationLength);
    if ( DaclSecurityDescriptor < 0 )
      goto LABEL_47;
    RtlInitializeSid(Sid, &IdentifierAuthority, 2u);
    *RtlSubAuthoritySid(Sid, 0) = 32;
    *RtlSubAuthoritySid(Sid, 1u) = 548;
    for ( i = 0; ; i = v36 + 1 )
    {
      v36 = i;
      if ( (unsigned int)i >= *v20 )
        break;
      Sid1 = *(PSID *)&v20[4 * i + 2];
      if ( RtlEqualSid(Sid1, SampAdministratorsAliasSid) || RtlEqualSid(Sid1, Sid) )
        goto LABEL_47;
    }
    TokenInformationLength = 76;
    v8 = (PSID *)LocalAlloc(0x40u, 0x4Cu);
    if ( !v8 )
      goto LABEL_45;
    DaclSecurityDescriptor = NtQueryInformationToken(
                               TokenHandle,
                               TokenOwner,
                               v8,
                               TokenInformationLength,
                               &TokenInformationLength);
    if ( DaclSecurityDescriptor < 0 )
      goto LABEL_47;
    v24 = RtlLengthSid(*v8) + 8;
    AceListLength = v24;
    v18 = LocalAlloc(0x40u, v24);
    if ( !v18 )
      goto LABEL_45;
    *v18 = 0;
    v18[1] = v24;
    *((_DWORD *)v18 + 1) = 985087;
    if ( v31 )
      *((_DWORD *)v18 + 1) = 196804;
    v25 = *v8;
    v26 = RtlLengthSid(*v8);
    RtlCopySid(v26, v18 + 4, v25);
    DaclSecurityDescriptor = RtlGetDaclSecurityDescriptor(SecurityDescriptor, &DaclPresent, &Dacl, &DaclDefaulted);
    if ( DaclSecurityDescriptor >= 0 )
    {
      v27 = AceListLength;
      v28 = (struct _ACL *)LocalAlloc(0x40u, AceListLength + Dacl->AclSize);
      v19 = v28;
      if ( !v28 )
      {
LABEL_45:
        DaclSecurityDescriptor = -1073741670;
        goto LABEL_47;
      }
      memcpy_0(v28, Dacl, Dacl->AclSize);
      v19->AclSize = Dacl->AclSize + v27;
      DaclSecurityDescriptor = RtlAddAce(v19, 2u, 1u, v18, v27);
    }
  }
LABEL_47:
  NtClose(TokenHandle);
  if ( DaclSecurityDescriptor >= 0 )
  {
    v22 = AceListLength;
    if ( v19 )
    {
      DaclSecurityDescriptor = RtlCreateSecurityDescriptor(ModificationDescriptor, 1u);
      if ( DaclSecurityDescriptor < 0 )
        goto LABEL_55;
      v43 = v19;
      WORD1(ModificationDescriptor[0]) = 4;
      DaclSecurityDescriptor = RtlSetSecurityObject(4u, ModificationDescriptor, &SecurityDescriptor, &GenericMapping, 0);
      if ( DaclSecurityDescriptor < 0 )
        goto LABEL_55;
      v22 = AceListLength;
    }
    goto LABEL_52;
  }
LABEL_55:
  if ( SecurityDescriptor )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, SecurityDescriptor);
  if ( v20 )
    LocalFree(v20);
  if ( v8 )
    LocalFree(v8);
  if ( v18 )
    LocalFree(v18);
  if ( v19 )
    LocalFree(v19);
  if ( DaclSecurityDescriptor < 0 )
  {
    *v40 = 0;
    *a8 = 0;
  }
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control[3].Buffer,
      31,
      WPP_18fb10c206133c98d7a2b000be93359d_Traceguids,
      (unsigned int)DaclSecurityDescriptor,
      DaclSecurityDescriptor);
  return (unsigned int)DaclSecurityDescriptor;
}

```

## disassembly

```asm
0x18008c6c0  push    rbp
0x18008c6c2  push    rbx
0x18008c6c3  push    rsi
0x18008c6c4  push    rdi
0x18008c6c5  push    r12
0x18008c6c7  push    r13
0x18008c6c9  push    r14
0x18008c6cb  push    r15
0x18008c6cd  lea     rbp, [rsp-7]
0x18008c6d2  sub     rsp, 0D8h
0x18008c6d9  mov     rax, cs:__security_cookie
0x18008c6e0  xor     rax, rsp
0x18008c6e3  mov     [rbp+3Fh+var_48], rax
0x18008c6e7  mov     eax, [rbp+3Fh+arg_28]
0x18008c6ea  xor     r15d, r15d
0x18008c6ed  mov     rbx, [rbp+3Fh+arg_30]
0x18008c6f1  xorps   xmm0, xmm0
0x18008c6f4  mov     r12, [rbp+3Fh+arg_38]
0x18008c6fb  mov     r11b, dl
0x18008c6fe  imul    rdx, rax, 550h
0x18008c705  movups  [rbp+3Fh+ModificationDescriptor], xmm0
0x18008c709  movups  [rbp+3Fh+var_98], xmm0
0x18008c70d  mov     r10d, ecx
0x18008c710  mov     [rsp+110h+var_DD], r8b
0x18008c715  add     rdx, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x18008c71c  lea     r8d, [r15+1]
0x18008c720  xor     ecx, ecx
0x18008c722  mov     [rsp+110h+var_DF], r9b
0x18008c727  mov     [rbp+3Fh+var_B8], rbx
0x18008c72b  mov     r13d, r15d
0x18008c72e  mov     dword ptr [rbp+3Fh+IdentifierAuthority.Value], r15d
0x18008c732  mov     word ptr [rbp+3Fh+IdentifierAuthority.Value+4], 500h
0x18008c738  mov     [rbp+3Fh+var_88], rcx
0x18008c73c  mov     [rsp+110h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x18008c745  mov     [rsp+110h+TokenInformationLength], r15d
0x18008c74a  mov     [rsp+110h+Dacl], r15
0x18008c74f  mov     [rsp+110h+SecurityDescriptor], r15
0x18008c754  mov     [rsp+110h+DaclPresent], r15b
0x18008c759  mov     [rsp+110h+DaclDefaulted], r15b
0x18008c75e  mov     [rsp+110h+var_D4], r15d
0x18008c763  movups  xmmword ptr [rbp+3Fh+GenericMapping.GenericRead], xmm0
0x18008c767  sub     r10d, 2
0x18008c76b  jz      short loc_18008C7E5
0x18008c76d  sub     r10d, r8d
0x18008c770  jz      short loc_18008C7C3
0x18008c772  cmp     r10d, r8d
0x18008c775  jnz     loc_18008C823
0x18008c77b  cmp     r11b, r8b
0x18008c77e  jnz     short loc_18008C791
0x18008c780  mov     r13, [rdx+30h]
0x18008c784  mov     eax, [rdx+68h]
0x18008c787  mov     [r12], eax
0x18008c78b  mov     rcx, [rdx+58h]
0x18008c78f  jmp     short loc_18008C7A0
0x18008c791  mov     r13, [rdx+40h]
0x18008c795  mov     eax, [rdx+70h]
0x18008c798  mov     [r12], eax
0x18008c79c  mov     rcx, [rdx+60h]
0x18008c7a0  mov     eax, [rbp+3Fh+arg_20]
0x18008c7a3  mov     [rcx], eax
0x18008c7a5  mov     [rbp+3Fh+GenericMapping.GenericRead], 2031Ah
0x18008c7ac  mov     [rbp+3Fh+GenericMapping.GenericWrite], 20044h
0x18008c7b3  mov     [rbp+3Fh+GenericMapping.GenericExecute], 20041h
0x18008c7ba  mov     [rbp+3Fh+GenericMapping.GenericAll], 0F07FFh
0x18008c7c1  jmp     short loc_18008C823
0x18008c7c3  mov     r13, [rdx+50h]
0x18008c7c7  mov     eax, [rdx+78h]
0x18008c7ca  mov     [r12], eax
0x18008c7ce  mov     [rbp+3Fh+GenericMapping.GenericRead], 20004h
0x18008c7d5  mov     [rbp+3Fh+GenericMapping.GenericWrite], 20013h
0x18008c7dc  mov     [rbp+3Fh+GenericMapping.GenericExecute], 20008h
0x18008c7e3  jmp     short loc_18008C81C
0x18008c7e5  mov     eax, 38h ; '8'
0x18008c7ea  cmp     r11b, r8b
0x18008c7ed  lea     ecx, [rax+10h]
0x18008c7f0  cmovnz  eax, ecx
0x18008c7f3  mov     r13, [rax+rdx]
0x18008c7f7  lea     eax, [rcx+24h]
0x18008c7fa  lea     ecx, [rax+8]
0x18008c7fd  cmovnz  eax, ecx
0x18008c800  mov     eax, [rax+rdx]
0x18008c803  mov     [r12], eax
0x18008c807  mov     [rbp+3Fh+GenericMapping.GenericRead], 20010h
0x18008c80e  mov     [rbp+3Fh+GenericMapping.GenericWrite], 2000Eh
0x18008c815  mov     [rbp+3Fh+GenericMapping.GenericExecute], 20001h
0x18008c81c  mov     [rbp+3Fh+GenericMapping.GenericAll], 0F001Fh
0x18008c823  mov     rcx, gs:60h
0x18008c82c  xor     edx, edx; Flags
0x18008c82e  mov     r8d, [r12]; Size
0x18008c832  mov     rcx, [rcx+30h]; HeapHandle
0x18008c836  call    cs:__imp_RtlAllocateHeap
0x18008c83c  mov     [rsp+110h+SecurityDescriptor], rax
0x18008c841  test    rax, rax
0x18008c844  jnz     short loc_18008C889
0x18008c846  mov     [rbx], r15
0x18008c849  mov     [r12], r15d
0x18008c84d  mov     rcx, cs:WPP_GLOBAL_Control
0x18008c854  mov     r13d, 0C000009Ah
0x18008c85a  test    dword ptr [rcx+44h], 20000h
0x18008c861  jz      short loc_18008C881
0x18008c863  mov     rcx, [rcx+38h]
0x18008c867  lea     edx, [rax+1Eh]
0x18008c86a  mov     r9d, 0C000009Ah
0x18008c870  mov     dword ptr [rsp+110h+ReturnLength], r13d
0x18008c875  lea     r8, WPP_18fb10c206133c98d7a2b000be93359d_Traceguids
0x18008c87c  call    WPP_SF_Dd
0x18008c881  mov     eax, r13d
0x18008c884  jmp     loc_18008CCCD
0x18008c889  mov     r8d, [r12]; Size
0x18008c88d  mov     rdx, r13; Src
0x18008c890  mov     rcx, rax; void *
0x18008c893  mov     ebx, r15d
0x18008c896  mov     rdi, r15
0x18008c899  mov     r14, r15
0x18008c89c  mov     rsi, r15
0x18008c89f  call    memcpy_0
0x18008c8a4  cmp     [rsp+110h+var_DF], r15b
0x18008c8a9  jz      short loc_18008C901
0x18008c8ab  mov     rcx, [rsp+110h+SecurityDescriptor]; SecurityDescriptor
0x18008c8b0  lea     r9, [rsp+110h+DaclDefaulted]; DaclDefaulted
0x18008c8b5  lea     r8, [rsp+110h+Dacl]; Dacl
0x18008c8ba  lea     rdx, [rsp+110h+DaclPresent]; DaclPresent
0x18008c8bf  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x18008c8c5  mov     ebx, eax
0x18008c8c7  test    eax, eax
0x18008c8c9  js      loc_18008CC2E
0x18008c8cf  cmp     [rsp+110h+DaclPresent], sil
0x18008c8d4  jz      loc_18008CA59
0x18008c8da  mov     rcx, [rsp+110h+Dacl]
0x18008c8df  test    rcx, rcx
0x18008c8e2  jz      loc_18008CA59
0x18008c8e8  movzx   eax, word ptr [rcx+4]
0x18008c8ec  mov     edx, 1
0x18008c8f1  cmp     ax, dx
0x18008c8f4  jb      loc_18008CA59
0x18008c8fa  sub     ax, dx
0x18008c8fd  mov     [rcx+4], ax
0x18008c901  xor     eax, eax
0x18008c903  mov     r13d, 0C000009Ah
0x18008c909  mov     [rsp+110h+AceListLength], eax
0x18008c90d  cmp     [rsp+110h+var_DD], al
0x18008c911  jnz     loc_18008CBF9
0x18008c917  lea     rcx, [rsp+110h+var_D4]
0x18008c91c  call    SampImpersonateClient
0x18008c921  mov     ebx, eax
0x18008c923  test    eax, eax
0x18008c925  js      loc_18008CC2E
0x18008c92b  lea     r9, [rsp+110h+TokenHandle]; TokenHandle
0x18008c930  mov     r8b, 1; OpenAsSelf
0x18008c933  mov     edx, 8; DesiredAccess
0x18008c938  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18008c93f  call    cs:__imp_NtOpenThreadToken
0x18008c945  mov     ecx, [rsp+110h+var_D4]
0x18008c949  mov     ebx, eax
0x18008c94b  call    SampRevertToSelf
0x18008c950  test    ebx, ebx
0x18008c952  js      loc_18008CC2E
0x18008c958  mov     rcx, [rsp+110h+TokenHandle]; TokenHandle
0x18008c95d  lea     rax, [rsp+110h+TokenInformationLength]
0x18008c962  xor     r9d, r9d; TokenInformationLength
0x18008c965  mov     [rsp+110h+ReturnLength], rax; ReturnLength
0x18008c96a  xor     r8d, r8d; TokenInformation
0x18008c96d  lea     edx, [r9+2]; TokenInformationClass
0x18008c971  call    cs:__imp_NtQueryInformationToken
0x18008c977  mov     ebx, eax
0x18008c979  cmp     eax, 0C0000023h
0x18008c97e  jnz     loc_18008CB8F
0x18008c984  mov     eax, [rsp+110h+TokenInformationLength]
0x18008c988  test    eax, eax
0x18008c98a  jz      loc_18008CB8F
0x18008c990  mov     edx, eax; uBytes
0x18008c992  mov     ecx, 40h ; '@'; uFlags
0x18008c997  call    cs:__imp_LocalAlloc
0x18008c99d  mov     rsi, rax
0x18008c9a0  test    rax, rax
0x18008c9a3  jz      loc_18008CB4C
0x18008c9a9  mov     r9d, [rsp+110h+TokenInformationLength]; TokenInformationLength
0x18008c9ae  lea     rax, [rsp+110h+TokenInformationLength]
0x18008c9b3  mov     rcx, [rsp+110h+TokenHandle]; TokenHandle
0x18008c9b8  mov     r8, rsi; TokenInformation
0x18008c9bb  mov     edx, 2; TokenInformationClass
0x18008c9c0  mov     [rsp+110h+ReturnLength], rax; ReturnLength
0x18008c9c5  call    cs:__imp_NtQueryInformationToken
0x18008c9cb  mov     ebx, eax
0x18008c9cd  test    eax, eax
0x18008c9cf  js      loc_18008CB8F
0x18008c9d5  mov     r8b, 2; SubAuthorityCount
0x18008c9d8  lea     rdx, [rbp+3Fh+IdentifierAuthority]; IdentifierAuthority
0x18008c9dc  lea     rcx, [rbp+3Fh+Sid]; Sid
0x18008c9e0  call    cs:__imp_RtlInitializeSid
0x18008c9e6  xor     edx, edx; SubAuthority
0x18008c9e8  lea     rcx, [rbp+3Fh+Sid]; Sid
0x18008c9ec  call    cs:__imp_RtlSubAuthoritySid
0x18008c9f2  mov     edx, 1; SubAuthority
0x18008c9f7  lea     rcx, [rbp+3Fh+Sid]; Sid
0x18008c9fb  mov     dword ptr [rax], 20h ; ' '
0x18008ca01  call    cs:__imp_RtlSubAuthoritySid
0x18008ca07  mov     dword ptr [rax], 224h
0x18008ca0d  xor     eax, eax
0x18008ca0f  mov     [rsp+110h+var_D4], eax
0x18008ca13  cmp     eax, [rsi]
0x18008ca15  jnb     short loc_18008CA63
0x18008ca17  mov     rdx, cs:SampAdministratorsAliasSid; Sid2
0x18008ca1e  add     rax, rax
0x18008ca21  mov     rax, [rsi+rax*8+8]
0x18008ca26  mov     rcx, rax; Sid1
0x18008ca29  mov     [rbp+3Fh+Sid1], rax
0x18008ca2d  call    cs:__imp_RtlEqualSid
0x18008ca33  test    al, al
0x18008ca35  jnz     loc_18008CB8F
0x18008ca3b  mov     rcx, [rbp+3Fh+Sid1]; Sid1
0x18008ca3f  lea     rdx, [rbp+3Fh+Sid]; Sid2
0x18008ca43  call    cs:__imp_RtlEqualSid
0x18008ca49  test    al, al
0x18008ca4b  jnz     loc_18008CB8F
0x18008ca51  mov     eax, [rsp+110h+var_D4]
0x18008ca55  inc     eax
0x18008ca57  jmp     short loc_18008CA0F
0x18008ca59  mov     ebx, 0C00000E7h
0x18008ca5e  jmp     loc_18008CC2E
0x18008ca63  mov     edx, 4Ch ; 'L'; uBytes
0x18008ca68  mov     [rsp+110h+TokenInformationLength], edx
0x18008ca6c  lea     ecx, [rdx-0Ch]; uFlags
0x18008ca6f  call    cs:__imp_LocalAlloc
0x18008ca75  mov     r15, rax
0x18008ca78  test    rax, rax
0x18008ca7b  jz      loc_18008CB4C
0x18008ca81  mov     r9d, [rsp+110h+TokenInformationLength]; TokenInformationLength
0x18008ca86  lea     rax, [rsp+110h+TokenInformationLength]
0x18008ca8b  mov     rcx, [rsp+110h+TokenHandle]; TokenHandle
0x18008ca90  mov     r8, r15; TokenInformation
0x18008ca93  mov     edx, 4; TokenInformationClass
0x18008ca98  mov     [rsp+110h+ReturnLength], rax; ReturnLength
0x18008ca9d  call    cs:__imp_NtQueryInformationToken
0x18008caa3  mov     ebx, eax
0x18008caa5  test    eax, eax
0x18008caa7  js      loc_18008CB8F
0x18008caad  mov     rcx, [r15]; Sid
0x18008cab0  call    cs:__imp_RtlLengthSid
0x18008cab6  mov     ecx, 40h ; '@'; uFlags
0x18008cabb  lea     ebx, [rax+8]
0x18008cabe  mov     edx, ebx; uBytes
0x18008cac0  mov     [rsp+110h+AceListLength], ebx
0x18008cac4  call    cs:__imp_LocalAlloc
0x18008caca  mov     rdi, rax
0x18008cacd  xor     eax, eax
0x18008cacf  test    rdi, rdi
0x18008cad2  jz      short loc_18008CB4C
0x18008cad4  mov     [rdi], ax
0x18008cad7  mov     [rdi+2], bx
0x18008cadb  mov     dword ptr [rdi+4], 0F07FFh
0x18008cae2  cmp     [rsp+110h+var_DF], al
0x18008cae6  jz      short loc_18008CAEF
0x18008cae8  mov     dword ptr [rdi+4], 300C4h
0x18008caef  mov     rbx, [r15]
0x18008caf2  mov     rcx, rbx; Sid
0x18008caf5  call    cs:__imp_RtlLengthSid
0x18008cafb  lea     rdx, [rdi+8]; DestinationSid
0x18008caff  mov     r8, rbx; SourceSid
0x18008cb02  mov     ecx, eax; DestinationSidLength
0x18008cb04  call    cs:__imp_RtlCopySid
0x18008cb0a  mov     rcx, [rsp+110h+SecurityDescriptor]; SecurityDescriptor
0x18008cb0f  lea     r9, [rsp+110h+DaclDefaulted]; DaclDefaulted
0x18008cb14  lea     r8, [rsp+110h+Dacl]; Dacl
0x18008cb19  lea     rdx, [rsp+110h+DaclPresent]; DaclPresent
0x18008cb1e  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x18008cb24  mov     ebx, eax
0x18008cb26  test    eax, eax
0x18008cb28  js      short loc_18008CB8F
0x18008cb2a  mov     rax, [rsp+110h+Dacl]
0x18008cb2f  mov     ecx, 40h ; '@'; uFlags
0x18008cb34  mov     ebx, [rsp+110h+AceListLength]
0x18008cb38  movzx   edx, word ptr [rax+2]
0x18008cb3c  add     edx, ebx; uBytes
0x18008cb3e  call    cs:__imp_LocalAlloc
0x18008cb44  mov     r14, rax
0x18008cb47  test    rax, rax
0x18008cb4a  jnz     short loc_18008CB51
0x18008cb4c  mov     ebx, r13d
0x18008cb4f  jmp     short loc_18008CB8F
0x18008cb51  mov     rdx, [rsp+110h+Dacl]; Src
0x18008cb56  mov     rcx, r14; void *
0x18008cb59  movzx   r8d, word ptr [rdx+2]; Size
0x18008cb5e  call    memcpy_0
0x18008cb63  mov     rax, [rsp+110h+Dacl]
0x18008cb68  movzx   ecx, bx
0x18008cb6b  mov     edx, 2; AceRevision
0x18008cb70  mov     dword ptr [rsp+110h+ReturnLength], ebx; AceListLength
0x18008cb74  mov     r9, rdi; AceList
0x18008cb77  add     cx, [rax+2]
0x18008cb7b  mov     [r14+2], cx
0x18008cb80  lea     r8d, [rdx-1]; StartingAceIndex
0x18008cb84  mov     rcx, r14; Acl
0x18008cb87  call    cs:__imp_RtlAddAce
0x18008cb8d  mov     ebx, eax
0x18008cb8f  mov     rcx, [rsp+110h+TokenHandle]; Handle
0x18008cb94  call    cs:__imp_NtClose
0x18008cb9a  test    ebx, ebx
0x18008cb9c  js      loc_18008CC2E
0x18008cba2  mov     eax, [rsp+110h+AceListLength]
  ... truncated ...
```
