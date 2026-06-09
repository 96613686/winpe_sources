# SampBuildSamProtection

- ea: `0x18008c120`
- end: `0x18008c6ab`
- name: `SampBuildSamProtection`
- size: `1419`
- prototype: `__int64 __usercall@<rax>(PSID Sid@<rcx>, PSID Group@<rdx>, __int64, PGENERIC_MAPPING GenericMapping, char, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18008af7c`

## callees

- `0x180027e24`
- `0x18008c120`

## import_xrefs

- `ntdll!RtlSubAuthorityCountSid` at `0x18008c62b`
- `ntdll!RtlSubAuthorityCountSid` at `0x18008c62b`
- `ntdll!RtlGetAce` at `0x18008c600`
- `ntdll!RtlGetAce` at `0x18008c600`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x18008c5ca`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x18008c5ca`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x18008c4e6`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x18008c553`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x18008c4e6`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x18008c553`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x18008c4ab`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x18008c4ab`
- `ntdll!RtlAddAuditAccessAce` at `0x18008c422`
- `ntdll!RtlAddAuditAccessAce` at `0x18008c473`
- `ntdll!RtlAddAuditAccessAce` at `0x18008c422`
- `ntdll!RtlAddAuditAccessAce` at `0x18008c473`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18008c33a`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18008c33a`
- `ntdll!RtlAddAccessAllowedAce` at `0x18008c2fa`
- `ntdll!RtlAddAccessAllowedAce` at `0x18008c2fa`
- `ntdll!RtlMapGenericMask` at `0x18008c2df`
- `ntdll!RtlMapGenericMask` at `0x18008c2df`
- `ntdll!RtlCreateAcl` at `0x18008c298`
- `ntdll!RtlCreateAcl` at `0x18008c3d7`
- `ntdll!RtlCreateAcl` at `0x18008c298`
- `ntdll!RtlCreateAcl` at `0x18008c3d7`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x18008c1fe`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x18008c1fe`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x18008c1d1`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x18008c1d1`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18008c188`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18008c188`
- `ntdll!RtlSubAuthoritySid` at `0x18008c63b`
- `ntdll!RtlSubAuthoritySid` at `0x18008c63b`
- `ntdll!RtlFreeHeap` at `0x18008c592`
- `ntdll!RtlFreeHeap` at `0x18008c5ab`
- `ntdll!RtlFreeHeap` at `0x18008c592`
- `ntdll!RtlFreeHeap` at `0x18008c5ab`
- `ntdll!RtlAllocateHeap` at `0x18008c261`
- `ntdll!RtlAllocateHeap` at `0x18008c39e`
- `ntdll!RtlAllocateHeap` at `0x18008c4ff`
- `ntdll!RtlAllocateHeap` at `0x18008c261`
- `ntdll!RtlAllocateHeap` at `0x18008c39e`
- `ntdll!RtlAllocateHeap` at `0x18008c4ff`
- `ntdll!RtlLengthSid` at `0x18008c237`
- `ntdll!RtlLengthSid` at `0x18008c36b`
- `ntdll!RtlLengthSid` at `0x18008c376`
- `ntdll!RtlLengthSid` at `0x18008c237`
- `ntdll!RtlLengthSid` at `0x18008c36b`
- `ntdll!RtlLengthSid` at `0x18008c376`

## pseudocode

```c
__int64 __fastcall SampBuildSamProtection(
        PSID Sid,
        PSID Group,
        unsigned int a3,
        __int64 a4,
        __int64 a5,
        PGENERIC_MAPPING GenericMapping,
        char a7,
        ULONG *a8,
        _QWORD *a9,
        PULONG *a10)
{
  bool v12; // r15
  NTSTATUS DaclSecurityDescriptor; // ebx
  PUNICODE_STRING v16; // rcx
  __int64 v17; // rdx
  ULONG v19; // eax
  unsigned int v20; // ebx
  ULONG v21; // eax
  struct _ACL *Heap; // rax
  PUNICODE_STRING v23; // rcx
  __int64 v24; // rdx
  __int64 i; // rdi
  ULONG v26; // ebx
  ULONG v27; // eax
  ULONG v28; // ecx
  struct _ACL *v29; // rax
  PVOID v30; // rax
  void *v31; // rsi
  unsigned int v32; // edi
  PUNICODE_STRING v33; // rcx
  __int64 v34; // rdx
  PULONG v35; // rbx
  char *v36; // rbx
  PUCHAR v37; // rax
  unsigned __int8 DaclPresent[4]; // [rsp+30h] [rbp-51h] BYREF
  ULONG AclSize; // [rsp+34h] [rbp-4Dh] BYREF
  DWORD AccessMask; // [rsp+38h] [rbp-49h] BYREF
  PACL Acl; // [rsp+40h] [rbp-41h] BYREF
  PVOID Ace; // [rsp+48h] [rbp-39h] BYREF
  __int128 SecurityDescriptor; // [rsp+50h] [rbp-31h] BYREF
  PVOID v44[2]; // [rsp+60h] [rbp-21h]
  PVOID P; // [rsp+70h] [rbp-11h]

  P = 0;
  Acl = 0;
  Ace = 0;
  AclSize = 0;
  DaclPresent[0] = 0;
  AccessMask = 0;
  v12 = SampProductType != NtProductLanManNt;
  SecurityDescriptor = 0;
  *(_OWORD *)v44 = 0;
  DaclSecurityDescriptor = RtlCreateSecurityDescriptor(&SecurityDescriptor, 1u);
  if ( DaclSecurityDescriptor < 0 )
  {
    v16 = WPP_GLOBAL_Control;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    {
      v17 = 12;
      goto LABEL_4;
    }
    return (unsigned int)DaclSecurityDescriptor;
  }
  DaclSecurityDescriptor = RtlSetOwnerSecurityDescriptor(&SecurityDescriptor, Group, 0);
  if ( DaclSecurityDescriptor < 0 )
  {
    v16 = WPP_GLOBAL_Control;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    {
      v17 = 13;
      goto LABEL_4;
    }
    return (unsigned int)DaclSecurityDescriptor;
  }
  DaclSecurityDescriptor = RtlSetGroupSecurityDescriptor(&SecurityDescriptor, Group, 0);
  if ( DaclSecurityDescriptor < 0 )
  {
    v16 = WPP_GLOBAL_Control;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    {
      v17 = 14;
      goto LABEL_4;
    }
    return (unsigned int)DaclSecurityDescriptor;
  }
  v19 = 8;
  v20 = 0;
  for ( AclSize = 8; v20 < a3; AclSize = v19 )
  {
    v21 = RtlLengthSid(*(PSID *)(a4 + 8LL * v20++));
    v19 = AclSize + 8 + v21;
  }
  Heap = (struct _ACL *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v19);
  Acl = Heap;
  if ( Heap )
  {
    DaclSecurityDescriptor = RtlCreateAcl(Heap, AclSize, 2u);
    if ( DaclSecurityDescriptor < 0 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
      {
        v17 = 16;
        goto LABEL_4;
      }
      return (unsigned int)DaclSecurityDescriptor;
    }
    for ( i = 0; (unsigned int)i < a3; i = (unsigned int)(i + 1) )
    {
      AccessMask = *(_DWORD *)(a5 + 4 * i);
      RtlMapGenericMask(&AccessMask, GenericMapping);
      DaclSecurityDescriptor = RtlAddAccessAllowedAce(Acl, 2u, AccessMask, *(PSID *)(a4 + 8 * i));
      if ( DaclSecurityDescriptor < 0 )
      {
        v16 = WPP_GLOBAL_Control;
        if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) == 0 )
          return (unsigned int)DaclSecurityDescriptor;
        v17 = 17;
        goto LABEL_4;
      }
    }
    DaclSecurityDescriptor = RtlSetDaclSecurityDescriptor(&SecurityDescriptor, 1u, Acl, 0);
    if ( DaclSecurityDescriptor < 0 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) == 0 )
        return (unsigned int)DaclSecurityDescriptor;
      v17 = 18;
LABEL_4:
      WPP_SF_Dd(
        v16[3].Buffer,
        v17,
        WPP_18fb10c206133c98d7a2b000be93359d_Traceguids,
        (unsigned int)DaclSecurityDescriptor,
        DaclSecurityDescriptor);
      return (unsigned int)DaclSecurityDescriptor;
    }
    v26 = RtlLengthSid(SampAnonymousSid);
    v27 = RtlLengthSid(Sid);
    v28 = v27 + 24;
    if ( !v12 )
      v28 = v27 + 16;
    AclSize = v26 + v28;
    v29 = (struct _ACL *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v26 + v28);
    Acl = v29;
    if ( !v29 )
    {
      v23 = WPP_GLOBAL_Control;
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) == 0 )
        return 3221225626LL;
      v24 = 19;
      goto LABEL_50;
    }
    DaclSecurityDescriptor = RtlCreateAcl(v29, AclSize, 2u);
    if ( DaclSecurityDescriptor < 0 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) == 0 )
        return (unsigned int)DaclSecurityDescriptor;
      v17 = 20;
      goto LABEL_4;
    }
    DaclSecurityDescriptor = RtlAddAuditAccessAce(
                               Acl,
                               2u,
                               GenericMapping->GenericWrite & 0xFEF8FFFF | 0x1050000,
                               Sid,
                               1u,
                               1u);
    if ( DaclSecurityDescriptor < 0 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) == 0 )
        return (unsigned int)DaclSecurityDescriptor;
      v17 = 21;
      goto LABEL_4;
    }
    if ( v12 )
    {
      DaclSecurityDescriptor = RtlAddAuditAccessAce(
                                 Acl,
                                 2u,
                                 GenericMapping->GenericWrite | 0x1FFFFF,
                                 SampAnonymousSid,
                                 1u,
                                 1u);
      if ( DaclSecurityDescriptor < 0 )
      {
        v16 = WPP_GLOBAL_Control;
        if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) == 0 )
          return (unsigned int)DaclSecurityDescriptor;
        v17 = 22;
        goto LABEL_4;
      }
    }
    DaclSecurityDescriptor = RtlSetSaclSecurityDescriptor(&SecurityDescriptor, 1u, Acl, 0);
    if ( DaclSecurityDescriptor < 0 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) == 0 )
        return (unsigned int)DaclSecurityDescriptor;
      v17 = 23;
      goto LABEL_4;
    }
    AclSize = 0;
    RtlAbsoluteToSelfRelativeSD(&SecurityDescriptor, 0, &AclSize);
    v30 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, AclSize);
    v31 = v30;
    if ( !v30 )
    {
      v23 = WPP_GLOBAL_Control;
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) == 0 )
        return 3221225626LL;
      v24 = 24;
      goto LABEL_50;
    }
    v32 = RtlAbsoluteToSelfRelativeSD(&SecurityDescriptor, v30, &AclSize);
    if ( (v32 & 0x80000000) != 0 )
    {
      v33 = WPP_GLOBAL_Control;
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
      {
        v34 = 25;
LABEL_67:
        WPP_SF_Dd(v33[3].Buffer, v34, WPP_18fb10c206133c98d7a2b000be93359d_Traceguids, v32, v32);
        return v32;
      }
      return v32;
    }
    v35 = 0;
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v44[1]);
    if ( a7 == 1 )
    {
      DaclSecurityDescriptor = RtlGetDaclSecurityDescriptor(v31, DaclPresent, &Acl, DaclPresent);
      if ( DaclSecurityDescriptor < 0 )
      {
        v16 = WPP_GLOBAL_Control;
        if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) == 0 )
          return (unsigned int)DaclSecurityDescriptor;
        v17 = 26;
        goto LABEL_4;
      }
      v32 = RtlGetAce(Acl, a3 - 1, &Ace);
      if ( (v32 & 0x80000000) != 0 )
      {
        v33 = WPP_GLOBAL_Control;
        if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
        {
          v34 = 27;
          goto LABEL_67;
        }
        return v32;
      }
      v36 = (char *)Ace;
      v37 = RtlSubAuthorityCountSid((char *)Ace + 8);
      v35 = RtlSubAuthoritySid(v36 + 8, (unsigned int)*v37 - 1);
    }
    *a8 = AclSize;
    *a9 = v31;
    if ( a10 )
      *a10 = v35;
    v33 = WPP_GLOBAL_Control;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) == 0 )
      return v32;
    v34 = 28;
    goto LABEL_67;
  }
  v23 = WPP_GLOBAL_Control;
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
  {
    v24 = 15;
LABEL_50:
    WPP_SF_Dd(v23[3].Buffer, v24, WPP_18fb10c206133c98d7a2b000be93359d_Traceguids, 3221225626LL, -1073741670);
  }
  return 3221225626LL;
}

```

## disassembly

```asm
0x18008c120  mov     [rsp-8+arg_18], r9
0x18008c125  push    rbp
0x18008c126  push    rbx
0x18008c127  push    rsi
0x18008c128  push    rdi
0x18008c129  push    r12
0x18008c12b  push    r13
0x18008c12d  push    r14
0x18008c12f  push    r15
0x18008c131  lea     rbp, [rsp-7]
0x18008c136  sub     rsp, 88h
0x18008c13d  xor     r12d, r12d
0x18008c140  xor     eax, eax
0x18008c142  cmp     cs:?SampProductType@@3W4_NT_PRODUCT_TYPE@@A, 2; _NT_PRODUCT_TYPE SampProductType
0x18008c149  mov     r13, rcx
0x18008c14c  xorps   xmm0, xmm0
0x18008c14f  mov     [rbp+3Fh+P], rax
0x18008c153  mov     rdi, rdx
0x18008c156  mov     [rbp+3Fh+Acl], r12
0x18008c15a  lea     ecx, [rax+1]
0x18008c15d  mov     [rbp+3Fh+Ace], r12
0x18008c161  mov     r15d, ecx
0x18008c164  mov     [rbp+3Fh+AclSize], r12d
0x18008c168  mov     edx, ecx; Revision
0x18008c16a  mov     [rbp+3Fh+DaclPresent], r12b
0x18008c16e  lea     rcx, [rbp+3Fh+SecurityDescriptor]; SecurityDescriptor
0x18008c172  mov     [rbp+3Fh+AccessMask], r12d
0x18008c176  cmovz   r15d, r12d
0x18008c17a  mov     rsi, r9
0x18008c17d  mov     r14d, r8d
0x18008c180  movups  [rbp+3Fh+SecurityDescriptor], xmm0
0x18008c184  movups  xmmword ptr [rbp+3Fh+var_60], xmm0
0x18008c188  call    cs:__imp_RtlCreateSecurityDescriptor
0x18008c18e  mov     ebx, eax
0x18008c190  test    eax, eax
0x18008c192  jns     short loc_18008C1C7
0x18008c194  mov     rcx, cs:WPP_GLOBAL_Control
0x18008c19b  test    dword ptr [rcx+44h], 20000h
0x18008c1a2  jz      short loc_18008C1C0
0x18008c1a4  lea     edx, [r12+0Ch]
0x18008c1a9  mov     rcx, [rcx+38h]
0x18008c1ad  lea     r8, WPP_18fb10c206133c98d7a2b000be93359d_Traceguids
0x18008c1b4  mov     r9d, ebx
0x18008c1b7  mov     dword ptr [rsp+0C0h+Success], ebx
0x18008c1bb  call    WPP_SF_Dd
0x18008c1c0  mov     eax, ebx
0x18008c1c2  jmp     loc_18008C697
0x18008c1c7  xor     r8d, r8d; OwnerDefaulted
0x18008c1ca  lea     rcx, [rbp+3Fh+SecurityDescriptor]; SecurityDescriptor
0x18008c1ce  mov     rdx, rdi; Owner
0x18008c1d1  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x18008c1d7  mov     ebx, eax
0x18008c1d9  test    eax, eax
0x18008c1db  jns     short loc_18008C1F4
0x18008c1dd  mov     rcx, cs:WPP_GLOBAL_Control
0x18008c1e4  test    dword ptr [rcx+44h], 20000h
0x18008c1eb  jz      short loc_18008C1C0
0x18008c1ed  mov     edx, 0Dh
0x18008c1f2  jmp     short loc_18008C1A9
0x18008c1f4  xor     r8d, r8d; GroupDefaulted
0x18008c1f7  lea     rcx, [rbp+3Fh+SecurityDescriptor]; SecurityDescriptor
0x18008c1fb  mov     rdx, rdi; Group
0x18008c1fe  call    cs:__imp_RtlSetGroupSecurityDescriptor
0x18008c204  mov     ebx, eax
0x18008c206  test    eax, eax
0x18008c208  jns     short loc_18008C221
0x18008c20a  mov     rcx, cs:WPP_GLOBAL_Control
0x18008c211  test    dword ptr [rcx+44h], 20000h
0x18008c218  jz      short loc_18008C1C0
0x18008c21a  mov     edx, 0Eh
0x18008c21f  jmp     short loc_18008C1A9
0x18008c221  mov     eax, 8
0x18008c226  mov     ebx, r12d
0x18008c229  mov     [rbp+3Fh+AclSize], eax
0x18008c22c  test    r14d, r14d
0x18008c22f  jz      short loc_18008C24F
0x18008c231  mov     ecx, ebx
0x18008c233  mov     rcx, [rsi+rcx*8]; Sid
0x18008c237  call    cs:__imp_RtlLengthSid
0x18008c23d  mov     ecx, [rbp+3Fh+AclSize]
0x18008c240  inc     ebx
0x18008c242  add     ecx, 8
0x18008c245  add     eax, ecx
0x18008c247  mov     [rbp+3Fh+AclSize], eax
0x18008c24a  cmp     ebx, r14d
0x18008c24d  jb      short loc_18008C231
0x18008c24f  mov     rcx, gs:60h
0x18008c258  xor     edx, edx; Flags
0x18008c25a  mov     r8d, eax; Size
0x18008c25d  mov     rcx, [rcx+30h]; HeapHandle
0x18008c261  call    cs:__imp_RtlAllocateHeap
0x18008c267  mov     [rbp+3Fh+Acl], rax
0x18008c26b  test    rax, rax
0x18008c26e  jnz     short loc_18008C28C
0x18008c270  mov     rcx, cs:WPP_GLOBAL_Control
0x18008c277  test    dword ptr [rcx+44h], 20000h
0x18008c27e  jz      loc_18008C53E
0x18008c284  lea     edx, [rax+0Fh]
0x18008c287  jmp     loc_18008C520
0x18008c28c  mov     edx, [rbp+3Fh+AclSize]; AclSize
0x18008c28f  mov     r8d, 2; AclRevision
0x18008c295  mov     rcx, rax; Acl
0x18008c298  call    cs:__imp_RtlCreateAcl
0x18008c29e  mov     ebx, eax
0x18008c2a0  test    eax, eax
0x18008c2a2  jns     short loc_18008C2C2
0x18008c2a4  mov     rcx, cs:WPP_GLOBAL_Control
0x18008c2ab  test    dword ptr [rcx+44h], 20000h
0x18008c2b2  jz      loc_18008C1C0
0x18008c2b8  mov     edx, 10h
0x18008c2bd  jmp     loc_18008C1A9
0x18008c2c2  mov     r12, [rbp+3Fh+arg_20]
0x18008c2c6  xor     edi, edi
0x18008c2c8  mov     rsi, [rbp+3Fh+GenericMapping]
0x18008c2cc  cmp     edi, r14d
0x18008c2cf  jnb     short loc_18008C328
0x18008c2d1  mov     eax, [r12+rdi*4]
0x18008c2d5  lea     rcx, [rbp+3Fh+AccessMask]; AccessMask
0x18008c2d9  mov     rdx, rsi; GenericMapping
0x18008c2dc  mov     [rbp+3Fh+AccessMask], eax
0x18008c2df  call    cs:__imp_RtlMapGenericMask
0x18008c2e5  mov     rax, [rbp+3Fh+arg_18]
0x18008c2e9  mov     edx, 2; Revision
0x18008c2ee  mov     r8d, [rbp+3Fh+AccessMask]; AccessMask
0x18008c2f2  mov     rcx, [rbp+3Fh+Acl]; Acl
0x18008c2f6  mov     r9, [rax+rdi*8]; Sid
0x18008c2fa  call    cs:__imp_RtlAddAccessAllowedAce
0x18008c300  mov     ebx, eax
0x18008c302  test    eax, eax
0x18008c304  js      short loc_18008C30A
0x18008c306  inc     edi
0x18008c308  jmp     short loc_18008C2CC
0x18008c30a  mov     rcx, cs:WPP_GLOBAL_Control
0x18008c311  test    dword ptr [rcx+44h], 20000h
0x18008c318  jz      loc_18008C1C0
0x18008c31e  mov     edx, 11h
0x18008c323  jmp     loc_18008C1A9
0x18008c328  mov     r8, [rbp+3Fh+Acl]; Dacl
0x18008c32c  lea     rcx, [rbp+3Fh+SecurityDescriptor]; SecurityDescriptor
0x18008c330  xor     r9d, r9d; DaclDefaulted
0x18008c333  lea     r12d, [r9+1]
0x18008c337  mov     dl, r12b; DaclPresent
0x18008c33a  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x18008c340  mov     ebx, eax
0x18008c342  test    eax, eax
0x18008c344  jns     short loc_18008C364
0x18008c346  mov     rcx, cs:WPP_GLOBAL_Control
0x18008c34d  test    dword ptr [rcx+44h], 20000h
0x18008c354  jz      loc_18008C1C0
0x18008c35a  lea     edx, [r12+11h]
0x18008c35f  jmp     loc_18008C1A9
0x18008c364  mov     rcx, cs:SampAnonymousSid; Sid
0x18008c36b  call    cs:__imp_RtlLengthSid
0x18008c371  mov     rcx, r13; Sid
0x18008c374  mov     ebx, eax
0x18008c376  call    cs:__imp_RtlLengthSid
0x18008c37c  lea     ecx, [rax+18h]
0x18008c37f  test    r15b, r15b
0x18008c382  jnz     short loc_18008C387
0x18008c384  lea     ecx, [rax+10h]
0x18008c387  add     ecx, ebx
0x18008c389  xor     edx, edx; Flags
0x18008c38b  mov     [rbp+3Fh+AclSize], ecx
0x18008c38e  mov     r8d, ecx; Size
0x18008c391  mov     rcx, gs:60h
0x18008c39a  mov     rcx, [rcx+30h]; HeapHandle
0x18008c39e  call    cs:__imp_RtlAllocateHeap
0x18008c3a4  mov     [rbp+3Fh+Acl], rax
0x18008c3a8  test    rax, rax
0x18008c3ab  jnz     short loc_18008C3C9
0x18008c3ad  mov     rcx, cs:WPP_GLOBAL_Control
0x18008c3b4  test    dword ptr [rcx+44h], 20000h
0x18008c3bb  jz      loc_18008C53E
0x18008c3c1  lea     edx, [rax+13h]
0x18008c3c4  jmp     loc_18008C520
0x18008c3c9  mov     edx, [rbp+3Fh+AclSize]; AclSize
0x18008c3cc  mov     edi, 2
0x18008c3d1  mov     r8d, edi; AclRevision
0x18008c3d4  mov     rcx, rax; Acl
0x18008c3d7  call    cs:__imp_RtlCreateAcl
0x18008c3dd  mov     ebx, eax
0x18008c3df  test    eax, eax
0x18008c3e1  jns     short loc_18008C3FF
0x18008c3e3  mov     rcx, cs:WPP_GLOBAL_Control
0x18008c3ea  test    dword ptr [rcx+44h], 20000h
0x18008c3f1  jz      loc_18008C1C0
0x18008c3f7  lea     edx, [rdi+12h]
0x18008c3fa  jmp     loc_18008C1A9
0x18008c3ff  mov     r8d, [rsi+4]
0x18008c403  mov     r9, r13; Sid
0x18008c406  mov     rcx, [rbp+3Fh+Acl]; Acl
0x18008c40a  btr     r8d, 11h
0x18008c40f  or      r8d, 1050000h; AccessMask
0x18008c416  mov     [rsp+0C0h+Failure], r12b; Failure
0x18008c41b  mov     edx, edi; Revision
0x18008c41d  mov     [rsp+0C0h+Success], r12b; Success
0x18008c422  call    cs:__imp_RtlAddAuditAccessAce
0x18008c428  mov     ebx, eax
0x18008c42a  test    eax, eax
0x18008c42c  jns     short loc_18008C44C
0x18008c42e  mov     rcx, cs:WPP_GLOBAL_Control
0x18008c435  test    dword ptr [rcx+44h], 20000h
0x18008c43c  jz      loc_18008C1C0
0x18008c442  mov     edx, 15h
0x18008c447  jmp     loc_18008C1A9
0x18008c44c  test    r15b, r15b
0x18008c44f  jz      short loc_18008C49D
0x18008c451  mov     r8d, [rsi+4]
0x18008c455  mov     edx, edi; Revision
0x18008c457  mov     r9, cs:SampAnonymousSid; Sid
0x18008c45e  or      r8d, 1FFFFFh; AccessMask
0x18008c465  mov     rcx, [rbp+3Fh+Acl]; Acl
0x18008c469  mov     [rsp+0C0h+Failure], r12b; Failure
0x18008c46e  mov     [rsp+0C0h+Success], r12b; Success
0x18008c473  call    cs:__imp_RtlAddAuditAccessAce
0x18008c479  mov     ebx, eax
0x18008c47b  test    eax, eax
0x18008c47d  jns     short loc_18008C49D
0x18008c47f  mov     rcx, cs:WPP_GLOBAL_Control
0x18008c486  test    dword ptr [rcx+44h], 20000h
0x18008c48d  jz      loc_18008C1C0
0x18008c493  mov     edx, 16h
0x18008c498  jmp     loc_18008C1A9
0x18008c49d  mov     r8, [rbp+3Fh+Acl]; Sacl
0x18008c4a1  lea     rcx, [rbp+3Fh+SecurityDescriptor]; SecurityDescriptor
0x18008c4a5  xor     r9d, r9d; SaclDefaulted
0x18008c4a8  mov     dl, r12b; SaclPresent
0x18008c4ab  call    cs:__imp_RtlSetSaclSecurityDescriptor
0x18008c4b1  mov     ebx, eax
0x18008c4b3  test    eax, eax
0x18008c4b5  jns     short loc_18008C4D5
0x18008c4b7  mov     rcx, cs:WPP_GLOBAL_Control
0x18008c4be  test    dword ptr [rcx+44h], 20000h
0x18008c4c5  jz      loc_18008C1C0
0x18008c4cb  mov     edx, 17h
0x18008c4d0  jmp     loc_18008C1A9
0x18008c4d5  lea     r8, [rbp+3Fh+AclSize]; BufferLength
0x18008c4d9  mov     [rbp+3Fh+AclSize], 0
0x18008c4e0  xor     edx, edx; SelfRelativeSecurityDescriptor
0x18008c4e2  lea     rcx, [rbp+3Fh+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x18008c4e6  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x18008c4ec  mov     rcx, gs:60h
0x18008c4f5  xor     edx, edx; Flags
0x18008c4f7  mov     r8d, [rbp+3Fh+AclSize]; Size
0x18008c4fb  mov     rcx, [rcx+30h]; HeapHandle
0x18008c4ff  call    cs:__imp_RtlAllocateHeap
0x18008c505  mov     rsi, rax
0x18008c508  test    rax, rax
0x18008c50b  jnz     short loc_18008C548
0x18008c50d  mov     rcx, cs:WPP_GLOBAL_Control
0x18008c514  test    dword ptr [rcx+44h], 20000h
0x18008c51b  jz      short loc_18008C53E
0x18008c51d  lea     edx, [rax+18h]
0x18008c520  mov     rcx, [rcx+38h]
0x18008c524  lea     r8, WPP_18fb10c206133c98d7a2b000be93359d_Traceguids
0x18008c52b  mov     r9d, 0C000009Ah
0x18008c531  mov     dword ptr [rsp+0C0h+Success], 0C000009Ah
0x18008c539  call    WPP_SF_Dd
0x18008c53e  mov     eax, 0C000009Ah
0x18008c543  jmp     loc_18008C697
0x18008c548  lea     r8, [rbp+3Fh+AclSize]; BufferLength
0x18008c54c  mov     rdx, rsi; SelfRelativeSecurityDescriptor
0x18008c54f  lea     rcx, [rbp+3Fh+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x18008c553  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x18008c559  mov     edi, eax
0x18008c55b  test    eax, eax
0x18008c55d  jns     short loc_18008C57D
0x18008c55f  mov     rcx, cs:WPP_GLOBAL_Control
0x18008c566  test    dword ptr [rcx+44h], 20000h
0x18008c56d  jz      loc_18008C695
0x18008c573  mov     edx, 19h
0x18008c578  jmp     loc_18008C67E
0x18008c57d  mov     rcx, gs:60h
0x18008c586  xor     edx, edx; Flags
0x18008c588  mov     r8, [rbp+3Fh+P]; P
0x18008c58c  xor     ebx, ebx
0x18008c58e  mov     rcx, [rcx+30h]; HeapHandle
0x18008c592  call    cs:__imp_RtlFreeHeap
0x18008c598  mov     rcx, gs:60h
0x18008c5a1  xor     edx, edx; Flags
0x18008c5a3  mov     r8, [rbp+3Fh+var_60+8]; P
0x18008c5a7  mov     rcx, [rcx+30h]; HeapHandle
0x18008c5ab  call    cs:__imp_RtlFreeHeap
0x18008c5b1  cmp     [rbp+3Fh+arg_30], r12b
0x18008c5b5  jnz     loc_18008C644
0x18008c5bb  lea     r9, [rbp+3Fh+DaclPresent]; DaclDefaulted
0x18008c5bf  mov     rcx, rsi; SecurityDescriptor
0x18008c5c2  lea     r8, [rbp+3Fh+Acl]; Dacl
0x18008c5c6  lea     rdx, [rbp+3Fh+DaclPresent]; DaclPresent
0x18008c5ca  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x18008c5d0  mov     ebx, eax
0x18008c5d2  test    eax, eax
0x18008c5d4  jns     short loc_18008C5F4
0x18008c5d6  mov     rcx, cs:WPP_GLOBAL_Control
0x18008c5dd  test    dword ptr [rcx+44h], 20000h
0x18008c5e4  jz      loc_18008C1C0
0x18008c5ea  mov     edx, 1Ah
0x18008c5ef  jmp     loc_18008C1A9
0x18008c5f4  mov     rcx, [rbp+3Fh+Acl]; Acl
0x18008c5f8  lea     edx, [r14-1]; AceIndex
  ... truncated ...
```
