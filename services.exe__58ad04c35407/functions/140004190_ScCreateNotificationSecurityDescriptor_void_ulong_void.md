# ScCreateNotificationSecurityDescriptor(void *,ulong,void * *)

- ea: `0x140004190`
- end: `0x140004421`
- name: `?ScCreateNotificationSecurityDescriptor@@YAKPEAXKPEAPEAX@Z`
- size: `657`
- prototype: `unsigned int __fastcall(PSECURITY_DESCRIPTOR SecurityDescriptor, unsigned int, void **)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400033b0`
- `0x140005464`

## callees

- `0x140004190`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1400041f8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1400041f8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1400043e4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1400043e4`
- `ntdll!RtlMapGenericMask` at `0x14000431a`
- `ntdll!RtlMapGenericMask` at `0x14000431a`
- `ntdll!RtlCreateSecurityDescriptor` at `0x140004215`
- `ntdll!RtlCreateSecurityDescriptor` at `0x140004215`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x140004238`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x140004238`
- `ntdll!RtlGetGroupSecurityDescriptor` at `0x140004249`
- `ntdll!RtlGetGroupSecurityDescriptor` at `0x140004249`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x14000425b`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x14000425b`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x140004270`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x140004270`
- `ntdll!RtlCreateAcl` at `0x1400042d3`
- `ntdll!RtlCreateAcl` at `0x1400042d3`
- `ntdll!RtlAddAccessAllowedAce` at `0x1400042ee`
- `ntdll!RtlAddAccessAllowedAce` at `0x140004340`
- `ntdll!RtlAddAccessAllowedAce` at `0x1400042ee`
- `ntdll!RtlAddAccessAllowedAce` at `0x140004340`
- `ntdll!RtlGetAce` at `0x14000436d`
- `ntdll!RtlGetAce` at `0x14000436d`
- `ntdll!RtlAddAccessDeniedAce` at `0x14000435b`
- `ntdll!RtlAddAccessDeniedAce` at `0x14000435b`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x14000439a`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x1400043cc`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x14000439a`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x1400043cc`
- `ntdll!RtlGetOwnerSecurityDescriptor` at `0x140004226`
- `ntdll!RtlGetOwnerSecurityDescriptor` at `0x140004226`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x140004383`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x140004383`
- `ntdll!RtlLengthSid` at `0x14000427d`
- `ntdll!RtlLengthSid` at `0x14000427d`
- `ntdll!RtlFreeHeap` at `0x140004401`
- `ntdll!RtlFreeHeap` at `0x140004401`
- `ntdll!RtlAllocateHeap` at `0x1400042b6`
- `ntdll!RtlAllocateHeap` at `0x1400043b3`
- `ntdll!RtlAllocateHeap` at `0x1400042b6`
- `ntdll!RtlAllocateHeap` at `0x1400043b3`

## pseudocode

```c
__int64 __fastcall ScCreateNotificationSecurityDescriptor(PSECURITY_DESCRIPTOR SecurityDescriptor, int a2, void **a3)
{
  PSECURITY_DESCRIPTOR v5; // rbx
  int v6; // r14d
  struct _GENERIC_MAPPING *v7; // r15
  ULONG v8; // eax
  unsigned int v9; // edi
  int AclSize; // edx
  ULONG v11; // esi
  struct _ACL *Heap; // rax
  struct _ACL *v13; // rbx
  struct _ACL *v14; // rcx
  ULONG v15; // esi
  ULONG i; // edx
  PVOID v17; // rax
  void *v18; // rsi
  ULONG BufferLength; // [rsp+20h] [rbp-50h] BYREF
  DWORD AccessMask; // [rsp+24h] [rbp-4Ch] BYREF
  PSID Owner; // [rsp+28h] [rbp-48h] BYREF
  PVOID Ace; // [rsp+30h] [rbp-40h] BYREF
  PACL Dacl; // [rsp+38h] [rbp-38h] BYREF
  _OWORD SecurityDescriptora[2]; // [rsp+40h] [rbp-30h] BYREF
  __int64 v26; // [rsp+60h] [rbp-10h]
  unsigned __int8 OwnerDefaulted; // [rsp+B0h] [rbp+40h] BYREF
  unsigned __int8 DaclPresent; // [rsp+C8h] [rbp+58h] BYREF

  Owner = 0;
  DaclPresent = 0;
  OwnerDefaulted = 0;
  Dacl = 0;
  Ace = 0;
  v5 = SecurityDescriptor;
  v26 = 0;
  BufferLength = 0;
  AccessMask = 0;
  memset(SecurityDescriptora, 0, sizeof(SecurityDescriptora));
  if ( SecurityDescriptor )
  {
    v6 = 0;
    v7 = (struct _GENERIC_MAPPING *)&GenericMapping;
  }
  else
  {
    AcquireSRWLockShared(&ScManagerSdLock);
    v5 = ScManagerSd;
    v7 = (struct _GENERIC_MAPPING *)&stru_14009B9A8;
    v6 = 1;
  }
  RtlCreateSecurityDescriptor(SecurityDescriptora, 1u);
  RtlGetOwnerSecurityDescriptor(v5, &Owner, &OwnerDefaulted);
  RtlSetOwnerSecurityDescriptor(SecurityDescriptora, Owner, OwnerDefaulted);
  RtlGetGroupSecurityDescriptor(v5, &Owner, &OwnerDefaulted);
  RtlSetGroupSecurityDescriptor(SecurityDescriptora, Owner, OwnerDefaulted);
  RtlGetDaclSecurityDescriptor(v5, &DaclPresent, &Dacl, &OwnerDefaulted);
  v8 = RtlLengthSid(LocalSystemSid);
  v9 = 8;
  if ( DaclPresent && Dacl )
    AclSize = Dacl->AclSize;
  else
    AclSize = 8;
  v11 = AclSize + v8 + 12;
  Heap = (struct _ACL *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v11);
  v13 = Heap;
  if ( Heap )
  {
    RtlCreateAcl(Heap, v11, 2u);
    RtlAddAccessAllowedAce(v13, 2u, 0x10002u, LocalSystemSid);
    if ( DaclPresent )
    {
      v14 = Dacl;
      if ( Dacl )
      {
        v15 = 0;
        for ( i = 0; RtlGetAce(v14, i, &Ace) >= 0; i = v15 )
        {
          AccessMask = *((_DWORD *)Ace + 1);
          RtlMapGenericMask(&AccessMask, v7);
          if ( (a2 & AccessMask) != 0 )
          {
            if ( *(_BYTE *)Ace )
            {
              if ( *(_BYTE *)Ace == 1 )
                RtlAddAccessDeniedAce(v13, 2u, 1u, (char *)Ace + 8);
            }
            else
            {
              RtlAddAccessAllowedAce(v13, 2u, 1u, (char *)Ace + 8);
            }
          }
          v14 = Dacl;
          ++v15;
        }
      }
    }
    RtlSetDaclSecurityDescriptor(SecurityDescriptora, 1u, v13, 0);
    BufferLength = 0;
    RtlAbsoluteToSelfRelativeSD(SecurityDescriptora, 0, &BufferLength);
    v17 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, BufferLength);
    v18 = v17;
    if ( v17 )
    {
      RtlAbsoluteToSelfRelativeSD(SecurityDescriptora, v17, &BufferLength);
      v9 = 0;
      *a3 = v18;
    }
  }
  if ( v6 )
    ReleaseSRWLockShared(&ScManagerSdLock);
  if ( v13 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v13);
  return v9;
}

```

## disassembly

```asm
0x140004190  mov     [rsp-38h+arg_8], rbx
0x140004195  push    rbp
0x140004196  push    rsi
0x140004197  push    rdi
0x140004198  push    r12
0x14000419a  push    r13
0x14000419c  push    r14
0x14000419e  push    r15
0x1400041a0  mov     rbp, rsp
0x1400041a3  sub     rsp, 70h
0x1400041a7  xor     esi, esi
0x1400041a9  xor     eax, eax
0x1400041ab  mov     [rbp+Owner], rsi
0x1400041af  xorps   xmm0, xmm0
0x1400041b2  mov     [rbp+DaclPresent], sil
0x1400041b6  mov     r12, r8
0x1400041b9  mov     [rbp+OwnerDefaulted], sil
0x1400041bd  mov     r13d, edx
0x1400041c0  mov     [rbp+Dacl], rsi
0x1400041c4  lea     edi, [rsi+1]
0x1400041c7  mov     [rbp+Ace], rsi
0x1400041cb  mov     rbx, rcx
0x1400041ce  mov     [rbp+var_10], rax
0x1400041d2  mov     [rbp+BufferLength], esi
0x1400041d5  mov     [rbp+AccessMask], esi
0x1400041d8  movups  [rbp+SecurityDescriptor], xmm0
0x1400041dc  movups  [rbp+var_20], xmm0
0x1400041e0  test    rcx, rcx
0x1400041e3  jz      short loc_1400041F1
0x1400041e5  mov     r14d, esi
0x1400041e8  lea     r15, GenericMapping
0x1400041ef  jmp     short loc_14000420F
0x1400041f1  lea     rcx, ?ScManagerSdLock@@3VCScmLock@@A; SRWLock
0x1400041f8  call    cs:__imp_AcquireSRWLockShared
0x1400041fe  mov     rbx, cs:?ScManagerSd@@3PEAXEA; void * ScManagerSd
0x140004205  lea     r15, stru_14009B9A8
0x14000420c  mov     r14d, edi
0x14000420f  mov     edx, edi; Revision
0x140004211  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140004215  call    cs:__imp_RtlCreateSecurityDescriptor
0x14000421b  lea     r8, [rbp+OwnerDefaulted]; OwnerDefaulted
0x14000421f  mov     rcx, rbx; SecurityDescriptor
0x140004222  lea     rdx, [rbp+Owner]; Owner
0x140004226  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x14000422c  mov     r8b, [rbp+OwnerDefaulted]; OwnerDefaulted
0x140004230  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140004234  mov     rdx, [rbp+Owner]; Owner
0x140004238  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x14000423e  lea     r8, [rbp+OwnerDefaulted]; GroupDefaulted
0x140004242  mov     rcx, rbx; SecurityDescriptor
0x140004245  lea     rdx, [rbp+Owner]; Group
0x140004249  call    cs:__imp_RtlGetGroupSecurityDescriptor
0x14000424f  mov     r8b, [rbp+OwnerDefaulted]; GroupDefaulted
0x140004253  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140004257  mov     rdx, [rbp+Owner]; Group
0x14000425b  call    cs:__imp_RtlSetGroupSecurityDescriptor
0x140004261  lea     r9, [rbp+OwnerDefaulted]; DaclDefaulted
0x140004265  mov     rcx, rbx; SecurityDescriptor
0x140004268  lea     r8, [rbp+Dacl]; Dacl
0x14000426c  lea     rdx, [rbp+DaclPresent]; DaclPresent
0x140004270  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x140004276  mov     rcx, cs:LocalSystemSid; Sid
0x14000427d  call    cs:__imp_RtlLengthSid
0x140004283  mov     edi, 8
0x140004288  cmp     [rbp+DaclPresent], sil
0x14000428c  jz      short loc_14000429D
0x14000428e  mov     rcx, [rbp+Dacl]
0x140004292  test    rcx, rcx
0x140004295  jz      short loc_14000429D
0x140004297  movzx   edx, word ptr [rcx+2]
0x14000429b  jmp     short loc_14000429F
0x14000429d  mov     edx, edi
0x14000429f  mov     rcx, gs:60h
0x1400042a8  lea     esi, [rax+0Ch]
0x1400042ab  add     esi, edx
0x1400042ad  mov     edx, edi; Flags
0x1400042af  mov     r8d, esi; Size
0x1400042b2  mov     rcx, [rcx+30h]; HeapHandle
0x1400042b6  call    cs:__imp_RtlAllocateHeap
0x1400042bc  mov     rbx, rax
0x1400042bf  test    rax, rax
0x1400042c2  jz      loc_1400043D8
0x1400042c8  mov     r8d, 2; AclRevision
0x1400042ce  mov     edx, esi; AclSize
0x1400042d0  mov     rcx, rax; Acl
0x1400042d3  call    cs:__imp_RtlCreateAcl
0x1400042d9  mov     r9, cs:LocalSystemSid; Sid
0x1400042e0  mov     edx, 2; Revision
0x1400042e5  mov     r8d, 10002h; AccessMask
0x1400042eb  mov     rcx, rbx; Acl
0x1400042ee  call    cs:__imp_RtlAddAccessAllowedAce
0x1400042f4  cmp     [rbp+DaclPresent], 0
0x1400042f8  jz      short loc_140004377
0x1400042fa  mov     rcx, [rbp+Dacl]
0x1400042fe  test    rcx, rcx
0x140004301  jz      short loc_140004377
0x140004303  xor     esi, esi
0x140004305  xor     edx, edx
0x140004307  jmp     short loc_140004369
0x140004309  mov     rax, [rbp+Ace]
0x14000430d  mov     rdx, r15; GenericMapping
0x140004310  mov     ecx, [rax+4]
0x140004313  mov     [rbp+AccessMask], ecx
0x140004316  lea     rcx, [rbp+AccessMask]; AccessMask
0x14000431a  call    cs:__imp_RtlMapGenericMask
0x140004320  test    [rbp+AccessMask], r13d
0x140004324  jz      short loc_140004361
0x140004326  mov     r9, [rbp+Ace]
0x14000432a  mov     al, [r9]
0x14000432d  test    al, al
0x14000432f  jnz     short loc_140004348
0x140004331  mov     edx, 2; Revision
0x140004336  add     r9, rdi; Sid
0x140004339  mov     rcx, rbx; Acl
0x14000433c  lea     r8d, [rdx-1]; AccessMask
0x140004340  call    cs:__imp_RtlAddAccessAllowedAce
0x140004346  jmp     short loc_140004361
0x140004348  cmp     al, 1
0x14000434a  jnz     short loc_140004361
0x14000434c  mov     edx, 2; Revision
0x140004351  add     r9, rdi; Sid
0x140004354  mov     rcx, rbx; Acl
0x140004357  lea     r8d, [rdx-1]; AccessMask
0x14000435b  call    cs:__imp_RtlAddAccessDeniedAce
0x140004361  mov     rcx, [rbp+Dacl]; Acl
0x140004365  inc     esi
0x140004367  mov     edx, esi; AceIndex
0x140004369  lea     r8, [rbp+Ace]; Ace
0x14000436d  call    cs:__imp_RtlGetAce
0x140004373  test    eax, eax
0x140004375  jns     short loc_140004309
0x140004377  xor     r9d, r9d; DaclDefaulted
0x14000437a  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x14000437e  mov     r8, rbx; Dacl
0x140004381  mov     dl, 1; DaclPresent
0x140004383  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x140004389  lea     r8, [rbp+BufferLength]; BufferLength
0x14000438d  mov     [rbp+BufferLength], 0
0x140004394  xor     edx, edx; SelfRelativeSecurityDescriptor
0x140004396  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x14000439a  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x1400043a0  mov     rcx, gs:60h
0x1400043a9  xor     edx, edx; Flags
0x1400043ab  mov     r8d, [rbp+BufferLength]; Size
0x1400043af  mov     rcx, [rcx+30h]; HeapHandle
0x1400043b3  call    cs:__imp_RtlAllocateHeap
0x1400043b9  mov     rsi, rax
0x1400043bc  test    rax, rax
0x1400043bf  jz      short loc_1400043D8
0x1400043c1  lea     r8, [rbp+BufferLength]; BufferLength
0x1400043c5  mov     rdx, rax; SelfRelativeSecurityDescriptor
0x1400043c8  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x1400043cc  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x1400043d2  xor     edi, edi
0x1400043d4  mov     [r12], rsi
0x1400043d8  test    r14d, r14d
0x1400043db  jz      short loc_1400043EA
0x1400043dd  lea     rcx, ?ScManagerSdLock@@3VCScmLock@@A; SRWLock
0x1400043e4  call    cs:__imp_ReleaseSRWLockShared
0x1400043ea  test    rbx, rbx
0x1400043ed  jz      short loc_140004407
0x1400043ef  mov     rcx, gs:60h
0x1400043f8  mov     r8, rbx; P
0x1400043fb  xor     edx, edx; Flags
0x1400043fd  mov     rcx, [rcx+30h]; HeapHandle
0x140004401  call    cs:__imp_RtlFreeHeap
0x140004407  mov     rbx, [rsp+70h+arg_8]
0x14000440f  mov     eax, edi
0x140004411  add     rsp, 70h
0x140004415  pop     r15
0x140004417  pop     r14
0x140004419  pop     r13
0x14000441b  pop     r12
0x14000441d  pop     rdi
0x14000441e  pop     rsi
0x14000441f  pop     rbp
0x140004420  retn
```
