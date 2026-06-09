# SampBuildNewProtection(ulong,void * *,ulong *,_GENERIC_MAPPING *,uchar,_SAMP_PROTECTION *)

- ea: `0x180040aa4`
- end: `0x180040e64`
- name: `?SampBuildNewProtection@@YAJKPEAPEAXPEAKPEAU_GENERIC_MAPPING@@EPEAU_SAMP_PROTECTION@@@Z`
- size: `960`
- prototype: `__int64 __fastcall(unsigned int, void **, unsigned int *, struct _GENERIC_MAPPING *, unsigned __int8 DaclPresent, struct _SAMP_PROTECTION *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18003fad4`

## callees

- `0x180040aa4`

## import_xrefs

- `ntdll!RtlSubAuthorityCountSid` at `0x180040e40`
- `ntdll!RtlSubAuthorityCountSid` at `0x180040e40`
- `ntdll!RtlGetAce` at `0x180040e28`
- `ntdll!RtlGetAce` at `0x180040e28`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x180040e0c`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x180040e0c`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x180040da1`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x180040dd7`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x180040da1`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x180040dd7`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x180040d82`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x180040d82`
- `ntdll!RtlAddAuditAccessAce` at `0x180040d34`
- `ntdll!RtlAddAuditAccessAce` at `0x180040d66`
- `ntdll!RtlAddAuditAccessAce` at `0x180040d34`
- `ntdll!RtlAddAuditAccessAce` at `0x180040d66`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180040c97`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180040c97`
- `ntdll!RtlAddAccessAllowedAce` at `0x180040c76`
- `ntdll!RtlAddAccessAllowedAce` at `0x180040c76`
- `ntdll!RtlMapGenericMask` at `0x180040c5c`
- `ntdll!RtlMapGenericMask` at `0x180040c5c`
- `ntdll!RtlCreateAcl` at `0x180040c32`
- `ntdll!RtlCreateAcl` at `0x180040cfd`
- `ntdll!RtlCreateAcl` at `0x180040c32`
- `ntdll!RtlCreateAcl` at `0x180040cfd`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x180040b29`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x180040b29`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x180040b0f`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x180040b0f`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180040af1`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180040af1`
- `ntdll!RtlSubAuthoritySid` at `0x180040e4f`
- `ntdll!RtlSubAuthoritySid` at `0x180040e4f`
- `ntdll!RtlFreeHeap` at `0x180040b9b`
- `ntdll!RtlFreeHeap` at `0x180040bd4`
- `ntdll!RtlFreeHeap` at `0x180040bed`
- `ntdll!RtlFreeHeap` at `0x180040c06`
- `ntdll!RtlFreeHeap` at `0x180040b9b`
- `ntdll!RtlFreeHeap` at `0x180040bd4`
- `ntdll!RtlFreeHeap` at `0x180040bed`
- `ntdll!RtlFreeHeap` at `0x180040c06`
- `ntdll!RtlAllocateHeap` at `0x180040b72`
- `ntdll!RtlAllocateHeap` at `0x180040cdd`
- `ntdll!RtlAllocateHeap` at `0x180040dba`
- `ntdll!RtlAllocateHeap` at `0x180040b72`
- `ntdll!RtlAllocateHeap` at `0x180040cdd`
- `ntdll!RtlAllocateHeap` at `0x180040dba`
- `ntdll!RtlLengthSid` at `0x180040b46`
- `ntdll!RtlLengthSid` at `0x180040cae`
- `ntdll!RtlLengthSid` at `0x180040cbd`
- `ntdll!RtlLengthSid` at `0x180040b46`
- `ntdll!RtlLengthSid` at `0x180040cae`
- `ntdll!RtlLengthSid` at `0x180040cbd`

## pseudocode

```c
__int64 __fastcall SampBuildNewProtection(
        unsigned int a1,
        void **a2,
        unsigned int *a3,
        struct _GENERIC_MAPPING *a4,
        unsigned __int8 DaclPresent,
        struct _SAMP_PROTECTION *a6)
{
  void *v9; // r15
  struct _ACL *v10; // rsi
  NTSTATUS Acl; // edi
  __int64 v12; // rbx
  ULONG v13; // eax
  ULONG v14; // eax
  struct _ACL *Heap; // rax
  PULONG v16; // rdx
  unsigned __int8 v17; // r14
  struct _SAMP_PROTECTION *v18; // rcx
  ULONG v19; // eax
  __int64 i; // r14
  ULONG v22; // ebx
  struct _ACL *v23; // rax
  PVOID v24; // rax
  char *v25; // rbx
  PUCHAR v26; // rax
  ULONG AclSize; // [rsp+30h] [rbp-40h] BYREF
  DWORD AccessMask; // [rsp+34h] [rbp-3Ch] BYREF
  PACL Dacl; // [rsp+38h] [rbp-38h] BYREF
  PVOID Ace; // [rsp+40h] [rbp-30h] BYREF
  __int128 SecurityDescriptor; // [rsp+48h] [rbp-28h] BYREF
  PVOID v32[2]; // [rsp+58h] [rbp-18h]
  PVOID P; // [rsp+68h] [rbp-8h]

  P = 0;
  AclSize = 0;
  AccessMask = 0;
  SecurityDescriptor = 0;
  v9 = 0;
  v10 = 0;
  *(_OWORD *)v32 = 0;
  Acl = RtlCreateSecurityDescriptor(&SecurityDescriptor, 1u);
  if ( Acl < 0 )
    goto LABEL_8;
  Acl = RtlSetOwnerSecurityDescriptor(&SecurityDescriptor, Group, 0);
  if ( Acl < 0 )
    goto LABEL_8;
  Acl = RtlSetGroupSecurityDescriptor(&SecurityDescriptor, Group, 0);
  if ( Acl < 0 )
    goto LABEL_8;
  v12 = 0;
  v13 = 8;
  for ( AclSize = 8; (unsigned int)v12 < a1; AclSize = v13 )
  {
    v14 = RtlLengthSid(a2[v12]);
    v12 = (unsigned int)(v12 + 1);
    v13 = v14 + AclSize + 8;
  }
  Heap = (struct _ACL *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v13);
  v10 = Heap;
  if ( !Heap )
    goto LABEL_7;
  Acl = RtlCreateAcl(Heap, AclSize, 2u);
  if ( Acl < 0 )
    goto LABEL_8;
  for ( i = 0; (unsigned int)i < a1; i = (unsigned int)(i + 1) )
  {
    AccessMask = a3[i];
    RtlMapGenericMask(&AccessMask, a4);
    Acl = RtlAddAccessAllowedAce(v10, 2u, AccessMask, a2[i]);
    if ( Acl < 0 )
      goto LABEL_8;
  }
  Acl = RtlSetDaclSecurityDescriptor(&SecurityDescriptor, 1u, v10, 0);
  if ( Acl < 0 )
    goto LABEL_8;
  v22 = RtlLengthSid(SampAnonymousSid);
  AclSize = v22 + RtlLengthSid(Sid) + 24;
  v23 = (struct _ACL *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, AclSize);
  v10 = v23;
  if ( !v23 )
    goto LABEL_7;
  Acl = RtlCreateAcl(v23, AclSize, 2u);
  if ( Acl < 0 )
    goto LABEL_8;
  Acl = RtlAddAuditAccessAce(v10, 2u, a4->GenericWrite & 0xFEF8FFFF | 0x1050000, Sid, 1u, 1u);
  if ( Acl < 0 )
    goto LABEL_8;
  Acl = RtlAddAuditAccessAce(v10, 2u, a4->GenericWrite | 0x1FFFFF, SampAnonymousSid, 1u, 1u);
  if ( Acl < 0 )
    goto LABEL_8;
  Acl = RtlSetSaclSecurityDescriptor(&SecurityDescriptor, 1u, v10, 0);
  if ( Acl < 0 )
    goto LABEL_8;
  v10 = 0;
  AclSize = 0;
  RtlAbsoluteToSelfRelativeSD(&SecurityDescriptor, 0, &AclSize);
  v24 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, AclSize);
  v9 = v24;
  if ( v24 )
  {
    Acl = RtlAbsoluteToSelfRelativeSD(&SecurityDescriptor, v24, &AclSize);
    if ( Acl >= 0 )
    {
      v17 = DaclPresent;
      if ( DaclPresent != 1 )
      {
        v16 = 0;
        goto LABEL_9;
      }
      Ace = 0;
      Dacl = 0;
      DaclPresent = 0;
      Acl = RtlGetDaclSecurityDescriptor(v9, &DaclPresent, &Dacl, &DaclPresent);
      if ( Acl >= 0 )
      {
        Acl = RtlGetAce(Dacl, a1 - 1, &Ace);
        if ( Acl >= 0 )
        {
          v25 = (char *)Ace;
          v26 = RtlSubAuthorityCountSid((char *)Ace + 8);
          v16 = RtlSubAuthoritySid(v25 + 8, (unsigned int)*v26 - 1);
          goto LABEL_9;
        }
      }
    }
  }
  else
  {
LABEL_7:
    Acl = -1073741801;
  }
LABEL_8:
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
  v9 = 0;
  v16 = 0;
  v17 = 0;
  AclSize = 0;
LABEL_9:
  v18 = a6;
  v19 = AclSize;
  *((_QWORD *)a6 + 2) = v16;
  *(_DWORD *)v18 = v19;
  *((_QWORD *)v18 + 1) = v9;
  *((_BYTE *)v18 + 24) = v17;
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v32[1]);
  return (unsigned int)Acl;
}

```

## disassembly

```asm
0x180040aa4  mov     [rsp-38h+arg_0], rbx
0x180040aa9  mov     [rsp-38h+arg_10], r8
0x180040aae  mov     [rsp-38h+arg_8], rdx
0x180040ab3  push    rbp
0x180040ab4  push    rsi
0x180040ab5  push    rdi
0x180040ab6  push    r12
0x180040ab8  push    r13
0x180040aba  push    r14
0x180040abc  push    r15
0x180040abe  mov     rbp, rsp
0x180040ac1  sub     rsp, 70h
0x180040ac5  xor     eax, eax
0x180040ac7  xorps   xmm0, xmm0
0x180040aca  mov     r14, rdx
0x180040acd  mov     [rbp+P], rax
0x180040ad1  mov     r13d, ecx
0x180040ad4  mov     [rbp+AclSize], eax
0x180040ad7  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x180040adb  mov     [rbp+AccessMask], eax
0x180040ade  lea     edx, [rax+1]; Revision
0x180040ae1  mov     r12, r9
0x180040ae4  movups  [rbp+SecurityDescriptor], xmm0
0x180040ae8  xor     r15d, r15d
0x180040aeb  xor     esi, esi
0x180040aed  movups  xmmword ptr [rbp+var_18], xmm0
0x180040af1  call    cs:__imp_RtlCreateSecurityDescriptor
0x180040af7  mov     edi, eax
0x180040af9  test    eax, eax
0x180040afb  js      loc_180040B89
0x180040b01  mov     rdx, cs:Group; Owner
0x180040b08  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x180040b0c  xor     r8d, r8d; OwnerDefaulted
0x180040b0f  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x180040b15  mov     edi, eax
0x180040b17  test    eax, eax
0x180040b19  js      short loc_180040B89
0x180040b1b  mov     rdx, cs:Group; Group
0x180040b22  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x180040b26  xor     r8d, r8d; GroupDefaulted
0x180040b29  call    cs:__imp_RtlSetGroupSecurityDescriptor
0x180040b2f  mov     edi, eax
0x180040b31  test    eax, eax
0x180040b33  js      short loc_180040B89
0x180040b35  xor     ebx, ebx
0x180040b37  lea     eax, [rsi+8]
0x180040b3a  mov     [rbp+AclSize], eax
0x180040b3d  test    r13d, r13d
0x180040b40  jz      short loc_180040B60
0x180040b42  mov     rcx, [r14+rbx*8]; Sid
0x180040b46  call    cs:__imp_RtlLengthSid
0x180040b4c  mov     ecx, eax
0x180040b4e  inc     ebx
0x180040b50  mov     eax, [rbp+AclSize]
0x180040b53  add     eax, 8
0x180040b56  add     eax, ecx
0x180040b58  mov     [rbp+AclSize], eax
0x180040b5b  cmp     ebx, r13d
0x180040b5e  jb      short loc_180040B42
0x180040b60  mov     rcx, gs:60h
0x180040b69  xor     edx, edx; Flags
0x180040b6b  mov     r8d, eax; Size
0x180040b6e  mov     rcx, [rcx+30h]; HeapHandle
0x180040b72  call    cs:__imp_RtlAllocateHeap
0x180040b78  mov     rsi, rax
0x180040b7b  test    rax, rax
0x180040b7e  jnz     loc_180040C26
0x180040b84  mov     edi, 0C0000017h
0x180040b89  mov     rcx, gs:60h
0x180040b92  mov     r8, r15; P
0x180040b95  xor     edx, edx; Flags
0x180040b97  mov     rcx, [rcx+30h]; HeapHandle
0x180040b9b  call    cs:__imp_RtlFreeHeap
0x180040ba1  xor     r15d, r15d
0x180040ba4  xor     edx, edx
0x180040ba6  xor     r14b, r14b
0x180040ba9  mov     [rbp+AclSize], r15d
0x180040bad  mov     rcx, [rbp+arg_28]
0x180040bb1  mov     r8, rsi; P
0x180040bb4  mov     eax, [rbp+AclSize]
0x180040bb7  mov     [rcx+10h], rdx
0x180040bbb  xor     edx, edx; Flags
0x180040bbd  mov     [rcx], eax
0x180040bbf  mov     [rcx+8], r15
0x180040bc3  mov     [rcx+18h], r14b
0x180040bc7  mov     rcx, gs:60h
0x180040bd0  mov     rcx, [rcx+30h]; HeapHandle
0x180040bd4  call    cs:__imp_RtlFreeHeap
0x180040bda  mov     rcx, gs:60h
0x180040be3  xor     edx, edx; Flags
0x180040be5  mov     r8, [rbp+P]; P
0x180040be9  mov     rcx, [rcx+30h]; HeapHandle
0x180040bed  call    cs:__imp_RtlFreeHeap
0x180040bf3  mov     rcx, gs:60h
0x180040bfc  xor     edx, edx; Flags
0x180040bfe  mov     r8, [rbp+var_18+8]; P
0x180040c02  mov     rcx, [rcx+30h]; HeapHandle
0x180040c06  call    cs:__imp_RtlFreeHeap
0x180040c0c  mov     rbx, [rsp+70h+arg_0]
0x180040c14  mov     eax, edi
0x180040c16  add     rsp, 70h
0x180040c1a  pop     r15
0x180040c1c  pop     r14
0x180040c1e  pop     r13
0x180040c20  pop     r12
0x180040c22  pop     rdi
0x180040c23  pop     rsi
0x180040c24  pop     rbp
0x180040c25  retn
0x180040c26  mov     edx, [rbp+AclSize]; AclSize
0x180040c29  mov     r8d, 2; AclRevision
0x180040c2f  mov     rcx, rsi; Acl
0x180040c32  call    cs:__imp_RtlCreateAcl
0x180040c38  mov     edi, eax
0x180040c3a  test    eax, eax
0x180040c3c  js      loc_180040B89
0x180040c42  xor     r14d, r14d
0x180040c45  cmp     r14d, r13d
0x180040c48  jnb     short loc_180040C8B
0x180040c4a  mov     rax, [rbp+arg_10]
0x180040c4e  lea     rcx, [rbp+AccessMask]; AccessMask
0x180040c52  mov     rdx, r12; GenericMapping
0x180040c55  mov     eax, [rax+r14*4]
0x180040c59  mov     [rbp+AccessMask], eax
0x180040c5c  call    cs:__imp_RtlMapGenericMask
0x180040c62  mov     rax, [rbp+arg_8]
0x180040c66  mov     edx, 2; Revision
0x180040c6b  mov     r8d, [rbp+AccessMask]; AccessMask
0x180040c6f  mov     rcx, rsi; Acl
0x180040c72  mov     r9, [rax+r14*8]; Sid
0x180040c76  call    cs:__imp_RtlAddAccessAllowedAce
0x180040c7c  mov     edi, eax
0x180040c7e  test    eax, eax
0x180040c80  js      loc_180040B89
0x180040c86  inc     r14d
0x180040c89  jmp     short loc_180040C45
0x180040c8b  xor     r9d, r9d; DaclDefaulted
0x180040c8e  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x180040c92  mov     r8, rsi; Dacl
0x180040c95  mov     dl, 1; DaclPresent
0x180040c97  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x180040c9d  mov     edi, eax
0x180040c9f  test    eax, eax
0x180040ca1  js      loc_180040B89
0x180040ca7  mov     rcx, cs:SampAnonymousSid; Sid
0x180040cae  call    cs:__imp_RtlLengthSid
0x180040cb4  mov     rcx, cs:Sid; Sid
0x180040cbb  mov     ebx, eax
0x180040cbd  call    cs:__imp_RtlLengthSid
0x180040cc3  xor     edx, edx; Flags
0x180040cc5  lea     ecx, [rax+18h]
0x180040cc8  add     ecx, ebx
0x180040cca  mov     [rbp+AclSize], ecx
0x180040ccd  mov     r8d, ecx; Size
0x180040cd0  mov     rcx, gs:60h
0x180040cd9  mov     rcx, [rcx+30h]; HeapHandle
0x180040cdd  call    cs:__imp_RtlAllocateHeap
0x180040ce3  mov     rsi, rax
0x180040ce6  test    rax, rax
0x180040ce9  jz      loc_180040B84
0x180040cef  mov     edx, [rbp+AclSize]; AclSize
0x180040cf2  mov     ebx, 2
0x180040cf7  mov     r8d, ebx; AclRevision
0x180040cfa  mov     rcx, rax; Acl
0x180040cfd  call    cs:__imp_RtlCreateAcl
0x180040d03  mov     edi, eax
0x180040d05  test    eax, eax
0x180040d07  js      loc_180040B89
0x180040d0d  mov     r8d, [r12+4]
0x180040d12  mov     edx, ebx; Revision
0x180040d14  mov     r9, cs:Sid; Sid
0x180040d1b  btr     r8d, 11h
0x180040d20  or      r8d, 1050000h; AccessMask
0x180040d27  mov     [rsp+70h+Failure], 1; Failure
0x180040d2c  mov     rcx, rsi; Acl
0x180040d2f  mov     [rsp+70h+Success], 1; Success
0x180040d34  call    cs:__imp_RtlAddAuditAccessAce
0x180040d3a  mov     edi, eax
0x180040d3c  test    eax, eax
0x180040d3e  js      loc_180040B89
0x180040d44  mov     r8d, [r12+4]
0x180040d49  mov     edx, ebx; Revision
0x180040d4b  mov     r9, cs:SampAnonymousSid; Sid
0x180040d52  or      r8d, 1FFFFFh; AccessMask
0x180040d59  mov     [rsp+70h+Failure], 1; Failure
0x180040d5e  mov     rcx, rsi; Acl
0x180040d61  mov     [rsp+70h+Success], 1; Success
0x180040d66  call    cs:__imp_RtlAddAuditAccessAce
0x180040d6c  mov     edi, eax
0x180040d6e  test    eax, eax
0x180040d70  js      loc_180040B89
0x180040d76  xor     r9d, r9d; SaclDefaulted
0x180040d79  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x180040d7d  mov     r8, rsi; Sacl
0x180040d80  mov     dl, 1; SaclPresent
0x180040d82  call    cs:__imp_RtlSetSaclSecurityDescriptor
0x180040d88  mov     edi, eax
0x180040d8a  test    eax, eax
0x180040d8c  js      loc_180040B89
0x180040d92  xor     esi, esi
0x180040d94  lea     r8, [rbp+AclSize]; BufferLength
0x180040d98  xor     edx, edx; SelfRelativeSecurityDescriptor
0x180040d9a  mov     [rbp+AclSize], esi
0x180040d9d  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x180040da1  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x180040da7  mov     rcx, gs:60h
0x180040db0  xor     edx, edx; Flags
0x180040db2  mov     r8d, [rbp+AclSize]; Size
0x180040db6  mov     rcx, [rcx+30h]; HeapHandle
0x180040dba  call    cs:__imp_RtlAllocateHeap
0x180040dc0  mov     r15, rax
0x180040dc3  test    rax, rax
0x180040dc6  jz      loc_180040B84
0x180040dcc  lea     r8, [rbp+AclSize]; BufferLength
0x180040dd0  mov     rdx, rax; SelfRelativeSecurityDescriptor
0x180040dd3  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x180040dd7  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x180040ddd  mov     edi, eax
0x180040ddf  test    eax, eax
0x180040de1  js      loc_180040B89
0x180040de7  mov     r14b, [rbp+DaclPresent]
0x180040deb  cmp     r14b, 1
0x180040def  jnz     short loc_180040E5D
0x180040df1  lea     r9, [rbp+DaclPresent]; DaclDefaulted
0x180040df5  mov     [rbp+Ace], rsi
0x180040df9  lea     r8, [rbp+Dacl]; Dacl
0x180040dfd  mov     [rbp+Dacl], rsi
0x180040e01  lea     rdx, [rbp+DaclPresent]; DaclPresent
0x180040e05  mov     [rbp+DaclPresent], sil
0x180040e09  mov     rcx, r15; SecurityDescriptor
0x180040e0c  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x180040e12  mov     edi, eax
0x180040e14  test    eax, eax
0x180040e16  js      loc_180040B89
0x180040e1c  mov     rcx, [rbp+Dacl]; Acl
0x180040e20  lea     edx, [r13-1]; AceIndex
0x180040e24  lea     r8, [rbp+Ace]; Ace
0x180040e28  call    cs:__imp_RtlGetAce
0x180040e2e  mov     edi, eax
0x180040e30  test    eax, eax
0x180040e32  js      loc_180040B89
0x180040e38  mov     rbx, [rbp+Ace]
0x180040e3c  lea     rcx, [rbx+8]; Sid
0x180040e40  call    cs:__imp_RtlSubAuthorityCountSid
0x180040e46  lea     rcx, [rbx+8]; Sid
0x180040e4a  movzx   edx, byte ptr [rax]
0x180040e4d  dec     edx; SubAuthority
0x180040e4f  call    cs:__imp_RtlSubAuthoritySid
0x180040e55  mov     rdx, rax
0x180040e58  jmp     loc_180040BAD
0x180040e5d  xor     edx, edx
0x180040e5f  jmp     loc_180040BAD
```
