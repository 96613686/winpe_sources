# UserAllocDefaultCompositionSecurityDescriptor

- ea: `0x14007c4a0`
- end: `0x14007cbee`
- name: `UserAllocDefaultCompositionSecurityDescriptor`
- size: `1870`
- prototype: ``
- caller_count: `4`
- callee_count: `13`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140037b18`
- `0x1400bdea0`
- `0x14021b370`
- `0x14021b8f0`

## callees

- `0x14000988c`
- `0x14000b798`
- `0x14000c064`
- `0x14007b930`
- `0x14007bbc0`
- `0x14007c4a0`
- `0x14007df80`
- `0x14007f840`
- `0x14010c0d0`
- `0x14010c44c`
- `0x1401ade20`
- `0x140238a40`
- `0x140238f80`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14007c75a`
- `ntoskrnl!ZwClose` at `0x14007c75a`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x14007c610`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x14007c610`
- `ntoskrnl!RtlLengthSid` at `0x14007c4f1`
- `ntoskrnl!RtlLengthSid` at `0x14007c560`
- `ntoskrnl!RtlLengthSid` at `0x14007c93e`
- `ntoskrnl!RtlLengthSid` at `0x14007c4f1`
- `ntoskrnl!RtlLengthSid` at `0x14007c560`
- `ntoskrnl!RtlLengthSid` at `0x14007c93e`
- `ntoskrnl!RtlCreateAcl` at `0x14007c6ad`
- `ntoskrnl!RtlCreateAcl` at `0x14007c6ad`
- `ntoskrnl!RtlAddAce` at `0x14007c6d5`
- `ntoskrnl!RtlAddAce` at `0x14007c6d5`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14007c6f4`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14007c6f4`
- `ntoskrnl!ExAllocatePool2` at `0x14007c8dc`
- `ntoskrnl!ExAllocatePool2` at `0x14007ca7d`
- `ntoskrnl!ExAllocatePool2` at `0x14007cb11`
- `ntoskrnl!ExAllocatePool2` at `0x14007c8dc`
- `ntoskrnl!ExAllocatePool2` at `0x14007ca7d`
- `ntoskrnl!ExAllocatePool2` at `0x14007cb11`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14007c692`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14007c692`
- `ntoskrnl!RtlSetSaclSecurityDescriptor` at `0x14007c70d`
- `ntoskrnl!RtlSetSaclSecurityDescriptor` at `0x14007c70d`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x14007cb51`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x14007cb51`
- `ntoskrnl!ZwQueryInformationToken` at `0x14007c64c`
- `ntoskrnl!ZwQueryInformationToken` at `0x14007c7dc`
- `ntoskrnl!ZwQueryInformationToken` at `0x14007c825`
- `ntoskrnl!ZwQueryInformationToken` at `0x14007c8a1`
- `ntoskrnl!ZwQueryInformationToken` at `0x14007c922`
- `ntoskrnl!ZwQueryInformationToken` at `0x14007c64c`
- `ntoskrnl!ZwQueryInformationToken` at `0x14007c7dc`
- `ntoskrnl!ZwQueryInformationToken` at `0x14007c825`
- `ntoskrnl!ZwQueryInformationToken` at `0x14007c8a1`
- `ntoskrnl!ZwQueryInformationToken` at `0x14007c922`
- `ntoskrnl!RtlCopySid` at `0x14007c538`
- `ntoskrnl!RtlCopySid` at `0x14007c5dd`
- `ntoskrnl!RtlCopySid` at `0x14007c9c5`
- `ntoskrnl!RtlCopySid` at `0x14007c538`
- `ntoskrnl!RtlCopySid` at `0x14007c5dd`
- `ntoskrnl!RtlCopySid` at `0x14007c9c5`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x14007c721`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x14007c721`
- `ntoskrnl!RtlSetGroupSecurityDescriptor` at `0x14007c735`
- `ntoskrnl!RtlSetGroupSecurityDescriptor` at `0x14007c735`
- `WIN32K!W32GetUserSessionState` at `0x14007c8b3`
- `WIN32K!W32GetUserSessionState` at `0x14007c8b3`

## pseudocode

```c
__int64 __fastcall UserAllocDefaultCompositionSecurityDescriptor(int a1, struct _ACL **a2)
{
  void *v2; // rdi
  PSID v3; // r12
  NTSTATUS v4; // esi
  ULONG v5; // ebx
  unsigned __int64 v6; // r14
  unsigned __int64 v7; // rcx
  char *v8; // rax
  PSID v9; // r8
  int v10; // eax
  ULONG v11; // r13d
  ULONG v12; // r15d
  unsigned __int64 v13; // rcx
  char *v14; // rax
  char *v15; // rbx
  unsigned __int64 v16; // rcx
  struct _ACL *v17; // rax
  struct _ACL *v18; // r14
  NTSTATUS v19; // ebx
  unsigned __int64 v21; // rcx
  PSID *v22; // r14
  NTSTATUS v23; // eax
  unsigned __int64 v24; // rbx
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // r8
  __int64 v28; // r14
  int v29; // eax
  PSID *v30; // rbx
  PSID v31; // r13
  unsigned __int64 v32; // rcx
  ULONG v33; // r12d
  __int64 v34; // r15
  char *v35; // rax
  char *v36; // r14
  ULONG v37; // ecx
  PSID *Pool2; // rax
  unsigned __int64 i; // r15
  char v40; // r12
  ULONG v41; // [rsp+30h] [rbp-D0h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-C8h] BYREF
  int TokenInformation; // [rsp+40h] [rbp-C0h] BYREF
  PSID SourceSid; // [rsp+48h] [rbp-B8h] BYREF
  PSID Sid; // [rsp+50h] [rbp-B0h] BYREF
  ULONG ReturnLength; // [rsp+58h] [rbp-A8h] BYREF
  ULONG v47; // [rsp+5Ch] [rbp-A4h] BYREF
  ULONG v48; // [rsp+60h] [rbp-A0h] BYREF
  ULONG DestinationSidLength; // [rsp+64h] [rbp-9Ch]
  PVOID BackTrace[28]; // [rsp+70h] [rbp-90h] BYREF
  unsigned int AceListLength; // [rsp+170h] [rbp+70h]
  ULONG TokenInformationLength; // [rsp+178h] [rbp+78h] BYREF

  v2 = 0;
  v3 = 0;
  Sid = 0;
  SourceSid = 0;
  TokenHandle = 0;
  *a2 = 0;
  v4 = AllocateLocalSystemSid(&Sid);
  if ( v4 < 0 )
    goto LABEL_15;
  v5 = RtlLengthSid(Sid);
  v6 = v5 + 8;
  v8 = (char *)Win32AllocPoolWithQuotaZInitImpl(v7, v6, 0x65737355u);
  v2 = v8;
  if ( !v8 )
  {
    v2 = 0;
LABEL_25:
    v4 = -1073741801;
    goto LABEL_15;
  }
  v9 = Sid;
  *(_WORD *)v8 = 0;
  *((_WORD *)v8 + 1) = v6;
  *((_DWORD *)v8 + 1) = 0x10000000;
  RtlCopySid(v5, v8 + 8, v9);
  v10 = AllocateWindowManagerSid(&SourceSid);
  v3 = SourceSid;
  v4 = v10;
  if ( v10 < 0 )
    goto LABEL_15;
  v11 = RtlLengthSid(SourceSid);
  v12 = v11 + 8;
  v13 = v11 + 8 + (unsigned int)v6;
  if ( (unsigned int)v13 < (unsigned int)v6 )
    goto LABEL_25;
  v14 = (char *)Win32AllocPoolWithQuotaZInitImpl(v13, (unsigned int)v13, 0x65737355u);
  v15 = v14;
  if ( !v14 )
    goto LABEL_25;
  memmove(v14, v2, (unsigned int)v6);
  GreDeleteFastMutex(v2);
  *(_WORD *)&v15[v6] = 0;
  AceListLength = v12 + v6;
  v41 = v12 + v6;
  *(_WORD *)&v15[v6 + 2] = v12;
  *(_DWORD *)&v15[v6 + 4] = 3;
  RtlCopySid(v11, &v15[v6 + 8], v3);
  if ( !a1 )
  {
    v2 = v15;
LABEL_43:
    if ( AceListLength + 8 >= AceListLength && AceListLength + 48 >= AceListLength + 8 )
    {
      v17 = (struct _ACL *)Win32AllocPoolWithQuotaZInitImpl(v16, AceListLength + 48, 0x65737355u);
      v18 = v17;
      if ( v17 )
      {
        RtlCreateSecurityDescriptor(v17, 1u);
        if ( RtlCreateAcl(v18 + 5, AceListLength + 8, 2u) >= 0
          && RtlAddAce(v18 + 5, 2u, 0xFFFFFFFF, v2, AceListLength) >= 0 )
        {
          v19 = RtlSetDaclSecurityDescriptor(v18, 1u, v18 + 5, 0);
          RtlSetSaclSecurityDescriptor(v18, 0, 0, 0);
          RtlSetOwnerSecurityDescriptor(v18, 0, 0);
          RtlSetGroupSecurityDescriptor(v18, 0, 0);
          if ( v19 >= 0 )
          {
            *a2 = v18;
            goto LABEL_15;
          }
        }
        GreDeleteFastMutex(v18);
      }
    }
    *a2 = 0;
    goto LABEL_25;
  }
  TokenInformation = 0;
  v4 = ZwOpenProcessTokenEx((HANDLE)0xFFFFFFFFFFFFFFFFLL, 8u, 0x200u, &TokenHandle);
  if ( v4 < 0 )
    goto LABEL_48;
  ReturnLength = 0;
  ZwQueryInformationToken(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength);
  if ( !TokenInformation )
  {
    v2 = v15;
    goto LABEL_31;
  }
  TokenInformationLength = 0;
  ZwQueryInformationToken(TokenHandle, TokenAppContainerSid, 0, 0, &TokenInformationLength);
  v22 = (PSID *)Win32AllocPoolWithQuotaZInitImpl(v21, TokenInformationLength, 0x65737355u);
  if ( !v22 )
  {
    v4 = -1073741801;
LABEL_48:
    v2 = v15;
    goto LABEL_15;
  }
  v47 = 0;
  v4 = ZwQueryInformationToken(TokenHandle, TokenAppContainerSid, v22, TokenInformationLength, &v47);
  if ( v4 >= 0 )
  {
    v2 = (void *)AllocAce(v15, *v22, (__int64)&v41);
    if ( v2 )
    {
      AceListLength = v41;
      goto LABEL_30;
    }
    v4 = -1073741801;
    AceListLength = v41;
  }
  v2 = v15;
LABEL_30:
  GreDeleteFastMutex(v22);
  if ( v4 < 0 )
    goto LABEL_15;
LABEL_31:
  v41 = 0;
  v23 = ZwQueryInformationToken(TokenHandle, TokenUser, 0, 0, &v41);
  v24 = v41;
  v4 = v23;
  v28 = W32GetUserSessionState(v26, v25, v27) + 72016;
  v29 = *(_DWORD *)v28;
  if ( !*(_DWORD *)v28 )
    goto LABEL_32;
  if ( v29 == 1 )
  {
    if ( NSInstrumentation::CLeakTrackingAllocator::EnsurePoolTagIncrement(
           (NSInstrumentation::CLeakTrackingAllocator *)v28,
           0x65737355u)
      && v24 + 16 >= v24 )
    {
      Pool2 = (PSID *)ExAllocatePool2(257, v24 + 16, 1702064981);
      v30 = Pool2;
      if ( !Pool2
        || (_InterlockedIncrement64((volatile signed __int64 *)(v28 + 112)),
            *Pool2 = (PSID)1702064981,
            v30 = Pool2 + 2,
            Pool2 == (PSID *)-16LL) )
      {
        NSInstrumentation::CPointerHashTable::LookupInterlockedDecrement(
          *(NSInstrumentation::CPointerHashTable **)(v28 + 8),
          (const void *)0x65737355);
      }
LABEL_34:
      if ( !v30 )
        goto LABEL_42;
LABEL_35:
      v48 = 0;
      v4 = ZwQueryInformationToken(TokenHandle, TokenUser, v30, v41, &v48);
      if ( v4 < 0 )
        goto LABEL_41;
      v31 = *v30;
      DestinationSidLength = RtlLengthSid(*v30);
      v33 = DestinationSidLength + 8;
      if ( v2 )
      {
        v34 = AceListLength;
        if ( v33 + AceListLength >= AceListLength )
        {
          v35 = (char *)Win32AllocPoolWithQuotaZInitImpl(v32, v33 + AceListLength, 0x65737355u);
          v36 = v35;
          if ( v35 )
          {
            memmove(v35, v2, AceListLength);
            GreDeleteFastMutex(v2);
LABEL_40:
            *(_DWORD *)&v36[v34 + 4] = a1;
            v37 = DestinationSidLength;
            AceListLength = v33 + v34;
            *(_WORD *)&v36[v34] = 0;
            *(_WORD *)&v36[v34 + 2] = v33;
            RtlCopySid(v37, &v36[v34 + 8], v31);
            v2 = v36;
LABEL_41:
            GreDeleteFastMutex(v30);
            goto LABEL_42;
          }
        }
      }
      else
      {
        v36 = (char *)Win32AllocPoolWithQuotaZInitImpl(v32, v33, 0x65737355u);
        if ( v36 )
        {
          v34 = 0;
          goto LABEL_40;
        }
      }
      v4 = -1073741801;
      goto LABEL_41;
    }
  }
  else if ( v29 == 2 )
  {
    if ( (*(_DWORD *)(v28 + 80) & 0x65737355) != 0x65737355 )
    {
LABEL_32:
      v30 = (PSID *)ExAllocatePool2(257, v24, 1702064981);
      if ( v30 )
        _InterlockedIncrement64((volatile signed __int64 *)(v28 + 112));
      goto LABEL_34;
    }
    for ( i = 0; ; ++i )
    {
      if ( i >= *(unsigned int *)(v28 + 84) )
        goto LABEL_32;
      if ( *(_DWORD *)(v28 + 4 * i + 48) == 1702064981 )
        break;
    }
    if ( v24 < 0x1000 || (v40 = 0, (v24 & 0xFFF) != 0) )
    {
      v40 = 1;
      v24 += 16LL;
    }
    v30 = (PSID *)ExAllocatePool2(257, v24, 1702064981);
    if ( v30 )
    {
      _InterlockedIncrement64((volatile signed __int64 *)(v28 + 128));
      memset(BackTrace, 0, 0xA0u);
      RtlCaptureStackBackTrace(0, 0x14u, BackTrace, 0);
      if ( v40 && (unsigned __int64)((unsigned __int16)v30 & 0xFFF) + 16 < 0x1000 )
      {
        if ( (unsigned __int8)NSInstrumentation::CLeakTrackingAllocator::AssociateAllocationWithBacktrace<1>(
                                v28,
                                v30,
                                i,
                                BackTrace) )
        {
          v30 += 2;
          goto LABEL_34;
        }
      }
      else if ( (unsigned __int8)NSInstrumentation::CLeakTrackingAllocator::AssociateAllocationWithBacktrace<0>(
                                   v28,
                                   v30,
                                   i,
                                   BackTrace) )
      {
        goto LABEL_35;
      }
      _InterlockedIncrement64((volatile signed __int64 *)(v28 + 136));
      _lambda_2af9a864ca5eb776d3057466a2e51944_::_lambda_invoker_cdecl_<void *>(v30);
    }
  }
LABEL_42:
  v3 = SourceSid;
  if ( v4 >= 0 )
    goto LABEL_43;
LABEL_15:
  if ( TokenHandle )
    ZwClose(TokenHandle);
  if ( Sid )
    GreDeleteFastMutex(Sid);
  if ( v3 )
    GreDeleteFastMutex(v3);
  if ( v2 )
    GreDeleteFastMutex(v2);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14007c4a0  mov     [rsp-8+arg_8], rdx
0x14007c4a5  mov     [rsp-8+arg_0], ecx
0x14007c4a9  push    rbp
0x14007c4aa  push    rbx
0x14007c4ab  push    rsi
0x14007c4ac  push    rdi
0x14007c4ad  push    r12
0x14007c4af  push    r13
0x14007c4b1  push    r14
0x14007c4b3  push    r15
0x14007c4b5  lea     rbp, [rsp-18h]
0x14007c4ba  sub     rsp, 118h
0x14007c4c1  xor     edi, edi
0x14007c4c3  lea     rcx, [rsp+150h+Sid]; void **
0x14007c4c8  xor     r12d, r12d
0x14007c4cb  mov     [rsp+150h+Sid], rdi
0x14007c4d0  mov     [rsp+150h+SourceSid], r12
0x14007c4d5  mov     [rsp+150h+TokenHandle], rdi
0x14007c4da  mov     [rdx], rdi
0x14007c4dd  call    ?AllocateLocalSystemSid@@YAJPEAPEAX@Z; AllocateLocalSystemSid(void * *)
0x14007c4e2  mov     esi, eax
0x14007c4e4  test    eax, eax
0x14007c4e6  js      loc_14007C750
0x14007c4ec  mov     rcx, [rsp+150h+Sid]; Sid
0x14007c4f1  call    cs:__imp_RtlLengthSid
0x14007c4f8  nop     dword ptr [rax+rax+00h]
0x14007c4fd  mov     r8d, 65737355h; unsigned int
0x14007c503  mov     ebx, eax
0x14007c505  lea     r14d, [rax+8]
0x14007c509  mov     edx, r14d; unsigned __int64
0x14007c50c  call    ?Win32AllocPoolWithQuotaZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolWithQuotaZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x14007c511  mov     rdi, rax
0x14007c514  test    rax, rax
0x14007c517  jz      loc_14007CA49
0x14007c51d  mov     r8, [rsp+150h+Sid]; SourceSid
0x14007c522  lea     rdx, [rax+8]; DestinationSid
0x14007c526  mov     ecx, ebx; DestinationSidLength
0x14007c528  mov     [rax], r12w
0x14007c52c  mov     [rax+2], r14w
0x14007c531  mov     dword ptr [rax+4], 10000000h
0x14007c538  call    cs:__imp_RtlCopySid
0x14007c53f  nop     dword ptr [rax+rax+00h]
0x14007c544  lea     rcx, [rsp+150h+SourceSid]
0x14007c549  call    AllocateWindowManagerSid
0x14007c54e  mov     r12, [rsp+150h+SourceSid]
0x14007c553  mov     esi, eax
0x14007c555  test    eax, eax
0x14007c557  js      loc_14007C750
0x14007c55d  mov     rcx, r12; Sid
0x14007c560  call    cs:__imp_RtlLengthSid
0x14007c567  nop     dword ptr [rax+rax+00h]
0x14007c56c  mov     r13d, eax
0x14007c56f  lea     r15d, [rax+8]
0x14007c573  lea     ecx, [r15+r14]; unsigned __int64
0x14007c577  cmp     ecx, r14d
0x14007c57a  jb      loc_14007C7B4
0x14007c580  mov     edx, ecx; unsigned __int64
0x14007c582  mov     r8d, 65737355h; unsigned int
0x14007c588  call    ?Win32AllocPoolWithQuotaZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolWithQuotaZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x14007c58d  mov     rbx, rax
0x14007c590  test    rax, rax
0x14007c593  jz      loc_14007C7B4
0x14007c599  mov     r8d, r14d; Size
0x14007c59c  mov     rdx, rdi; Src
0x14007c59f  mov     rcx, rax; void *
0x14007c5a2  call    memmove
0x14007c5a7  mov     rcx, rdi; Buffer
0x14007c5aa  call    GreDeleteFastMutex
0x14007c5af  lea     eax, [r15+r14]
0x14007c5b3  mov     word ptr [r14+rbx], 0
0x14007c5ba  lea     rdx, [r14+8]
0x14007c5be  mov     [rbp+50h+AceListLength], eax
0x14007c5c1  add     rdx, rbx; DestinationSid
0x14007c5c4  mov     [rsp+150h+var_120], eax
0x14007c5c8  mov     r8, r12; SourceSid
0x14007c5cb  mov     [r14+rbx+2], r15w
0x14007c5d1  mov     ecx, r13d; DestinationSidLength
0x14007c5d4  mov     dword ptr [r14+rbx+4], 3
0x14007c5dd  call    cs:__imp_RtlCopySid
0x14007c5e4  nop     dword ptr [rax+rax+00h]
0x14007c5e9  mov     edi, [rbp+50h+arg_0]
0x14007c5ec  test    edi, edi
0x14007c5ee  jz      loc_14007CBE6
0x14007c5f4  lea     r9, [rsp+150h+TokenHandle]; TokenHandle
0x14007c5f9  mov     [rsp+150h+TokenInformation], 0
0x14007c601  mov     edx, 8; DesiredAccess
0x14007c606  mov     r8d, 200h; HandleAttributes
0x14007c60c  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x14007c610  call    cs:__imp_ZwOpenProcessTokenEx
0x14007c617  nop     dword ptr [rax+rax+00h]
0x14007c61c  mov     esi, eax
0x14007c61e  test    eax, eax
0x14007c620  js      loc_14007CA16
0x14007c626  mov     rcx, [rsp+150h+TokenHandle]; TokenHandle
0x14007c62b  lea     rax, [rsp+150h+var_F8]
0x14007c630  mov     r9d, 4; TokenInformationLength
0x14007c636  mov     [rsp+150h+var_F8], 0
0x14007c63e  lea     r8, [rsp+150h+TokenInformation]; TokenInformation
0x14007c643  mov     [rsp+150h+ReturnLength], rax; ReturnLength
0x14007c648  lea     edx, [r9+19h]; TokenInformationClass
0x14007c64c  call    cs:__imp_ZwQueryInformationToken
0x14007c653  nop     dword ptr [rax+rax+00h]
0x14007c658  cmp     [rsp+150h+TokenInformation], 0
0x14007c65d  jnz     loc_14007C7BB
0x14007c663  mov     rdi, rbx
0x14007c666  mov     r13d, 65737355h
0x14007c66c  jmp     loc_14007C880
0x14007c671  mov     edx, eax; unsigned __int64
0x14007c673  mov     r8d, 65737355h; unsigned int
0x14007c679  call    ?Win32AllocPoolWithQuotaZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolWithQuotaZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x14007c67e  mov     r14, rax
0x14007c681  test    rax, rax
0x14007c684  jz      loc_14007C7A9
0x14007c68a  mov     edx, 1; Revision
0x14007c68f  mov     rcx, rax; SecurityDescriptor
0x14007c692  call    cs:__imp_RtlCreateSecurityDescriptor
0x14007c699  nop     dword ptr [rax+rax+00h]
0x14007c69e  lea     r15, [r14+28h]
0x14007c6a2  mov     r8d, 2; AclRevision
0x14007c6a8  mov     rcx, r15; Acl
0x14007c6ab  mov     edx, ebx; AclLength
0x14007c6ad  call    cs:__imp_RtlCreateAcl
0x14007c6b4  nop     dword ptr [rax+rax+00h]
0x14007c6b9  test    eax, eax
0x14007c6bb  js      loc_14007CA3C
0x14007c6c1  mov     r9, rdi; AceList
0x14007c6c4  mov     dword ptr [rsp+150h+ReturnLength], r13d; AceListLength
0x14007c6c9  or      r8d, 0FFFFFFFFh; StartingAceIndex
0x14007c6cd  mov     edx, 2; AceRevision
0x14007c6d2  mov     rcx, r15; Acl
0x14007c6d5  call    cs:__imp_RtlAddAce
0x14007c6dc  nop     dword ptr [rax+rax+00h]
0x14007c6e1  test    eax, eax
0x14007c6e3  js      loc_14007CA3C
0x14007c6e9  xor     r9d, r9d; DaclDefaulted
0x14007c6ec  mov     r8, r15; Dacl
0x14007c6ef  mov     dl, 1; DaclPresent
0x14007c6f1  mov     rcx, r14; SecurityDescriptor
0x14007c6f4  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x14007c6fb  nop     dword ptr [rax+rax+00h]
0x14007c700  xor     r9d, r9d; SaclDefaulted
0x14007c703  xor     r8d, r8d; Sacl
0x14007c706  xor     edx, edx; SaclPresent
0x14007c708  mov     rcx, r14; SecurityDescriptor
0x14007c70b  mov     ebx, eax
0x14007c70d  call    cs:__imp_RtlSetSaclSecurityDescriptor
0x14007c714  nop     dword ptr [rax+rax+00h]
0x14007c719  xor     r8d, r8d; OwnerDefaulted
0x14007c71c  xor     edx, edx; Owner
0x14007c71e  mov     rcx, r14; SecurityDescriptor
0x14007c721  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x14007c728  nop     dword ptr [rax+rax+00h]
0x14007c72d  xor     r8d, r8d; GroupDefaulted
0x14007c730  xor     edx, edx; Group
0x14007c732  mov     rcx, r14; SecurityDescriptor
0x14007c735  call    cs:__imp_RtlSetGroupSecurityDescriptor
0x14007c73c  nop     dword ptr [rax+rax+00h]
0x14007c741  test    ebx, ebx
0x14007c743  js      loc_14007CA3C
0x14007c749  mov     rax, [rbp+50h+arg_8]
0x14007c74d  mov     [rax], r14
0x14007c750  mov     rcx, [rsp+150h+TokenHandle]; Handle
0x14007c755  test    rcx, rcx
0x14007c758  jz      short loc_14007C766
0x14007c75a  call    cs:__imp_ZwClose
0x14007c761  nop     dword ptr [rax+rax+00h]
0x14007c766  cmp     [rsp+150h+Sid], 0
0x14007c76c  jz      short loc_14007C778
0x14007c76e  mov     rcx, [rsp+150h+Sid]; Buffer
0x14007c773  call    GreDeleteFastMutex
0x14007c778  test    r12, r12
0x14007c77b  jz      short loc_14007C785
0x14007c77d  mov     rcx, r12; Buffer
0x14007c780  call    GreDeleteFastMutex
0x14007c785  test    rdi, rdi
0x14007c788  jz      short loc_14007C792
0x14007c78a  mov     rcx, rdi; Buffer
0x14007c78d  call    GreDeleteFastMutex
0x14007c792  mov     eax, esi
0x14007c794  add     rsp, 118h
0x14007c79b  pop     r15
0x14007c79d  pop     r14
0x14007c79f  pop     r13
0x14007c7a1  pop     r12
0x14007c7a3  pop     rdi
0x14007c7a4  pop     rsi
0x14007c7a5  pop     rbx
0x14007c7a6  pop     rbp
0x14007c7a7  retn
0x14007c7a9  mov     rax, [rbp+50h+arg_8]
0x14007c7ad  mov     qword ptr [rax], 0
0x14007c7b4  mov     esi, 0C0000017h
0x14007c7b9  jmp     short loc_14007C750
0x14007c7bb  mov     rcx, [rsp+150h+TokenHandle]; TokenHandle
0x14007c7c0  lea     rax, [rbp+50h+TokenInformationLength]
0x14007c7c4  xor     r9d, r9d; TokenInformationLength
0x14007c7c7  mov     [rbp+50h+TokenInformationLength], 0
0x14007c7ce  xor     r8d, r8d; TokenInformation
0x14007c7d1  mov     [rsp+150h+ReturnLength], rax; ReturnLength
0x14007c7d6  lea     esi, [r9+1Fh]
0x14007c7da  mov     edx, esi; TokenInformationClass
0x14007c7dc  call    cs:__imp_ZwQueryInformationToken
0x14007c7e3  nop     dword ptr [rax+rax+00h]
0x14007c7e8  mov     edx, [rbp+50h+TokenInformationLength]; unsigned __int64
0x14007c7eb  mov     r13d, 65737355h
0x14007c7f1  mov     r8d, r13d; unsigned int
0x14007c7f4  call    ?Win32AllocPoolWithQuotaZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolWithQuotaZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x14007c7f9  mov     r14, rax
0x14007c7fc  test    rax, rax
0x14007c7ff  jz      loc_14007CA11
0x14007c805  mov     r9d, [rbp+50h+TokenInformationLength]; TokenInformationLength
0x14007c809  lea     rax, [rsp+150h+var_F4]
0x14007c80e  mov     rcx, [rsp+150h+TokenHandle]; TokenHandle
0x14007c813  mov     r8, r14; TokenInformation
0x14007c816  mov     edx, esi; TokenInformationClass
0x14007c818  mov     [rsp+150h+ReturnLength], rax; ReturnLength
0x14007c81d  mov     [rsp+150h+var_F4], 0
0x14007c825  call    cs:__imp_ZwQueryInformationToken
0x14007c82c  nop     dword ptr [rax+rax+00h]
0x14007c831  mov     esi, eax
0x14007c833  test    eax, eax
0x14007c835  js      loc_14007CBDE
0x14007c83b  lea     rax, [rsp+150h+var_120]
0x14007c840  mov     r9d, edi
0x14007c843  mov     [rsp+150h+var_128], rax; __int64
0x14007c848  xor     r8d, r8d
0x14007c84b  mov     rax, [r14]
0x14007c84e  xor     edx, edx
0x14007c850  mov     rcx, rbx; Buffer
0x14007c853  mov     [rsp+150h+ReturnLength], rax; Sid
0x14007c858  call    AllocAce
0x14007c85d  mov     rdi, rax
0x14007c860  test    rax, rax
0x14007c863  jz      loc_14007CBD2
0x14007c869  mov     ebx, [rsp+150h+var_120]
0x14007c86d  mov     [rbp+50h+AceListLength], ebx
0x14007c870  mov     rcx, r14; Buffer
0x14007c873  call    GreDeleteFastMutex
0x14007c878  test    esi, esi
0x14007c87a  js      loc_14007C750
0x14007c880  mov     rcx, [rsp+150h+TokenHandle]; TokenHandle
0x14007c885  lea     rax, [rsp+150h+var_120]
0x14007c88a  xor     r9d, r9d; TokenInformationLength
0x14007c88d  mov     [rsp+150h+var_120], 0
0x14007c895  xor     r8d, r8d; TokenInformation
0x14007c898  mov     [rsp+150h+ReturnLength], rax; ReturnLength
0x14007c89d  lea     edx, [r9+1]; TokenInformationClass
0x14007c8a1  call    cs:__imp_ZwQueryInformationToken
0x14007c8a8  nop     dword ptr [rax+rax+00h]
0x14007c8ad  mov     ebx, [rsp+150h+var_120]
0x14007c8b1  mov     esi, eax
0x14007c8b3  call    cs:__imp_W32GetUserSessionState
0x14007c8ba  nop     dword ptr [rax+rax+00h]
0x14007c8bf  lea     r14, [rax+11950h]
0x14007c8c6  mov     eax, [r14]
0x14007c8c9  test    eax, eax
0x14007c8cb  jnz     loc_14007CA50
0x14007c8d1  mov     r8d, r13d
0x14007c8d4  mov     rdx, rbx
0x14007c8d7  mov     ecx, 101h
0x14007c8dc  call    cs:__imp_ExAllocatePool2
0x14007c8e3  nop     dword ptr [rax+rax+00h]
0x14007c8e8  mov     rbx, rax
0x14007c8eb  test    rax, rax
0x14007c8ee  jz      short loc_14007C8F5
0x14007c8f0  lock inc qword ptr [r14+70h]
0x14007c8f5  test    rbx, rbx
0x14007c8f8  jz      loc_14007C9DC
0x14007c8fe  mov     r9d, [rsp+150h+var_120]; TokenInformationLength
0x14007c903  lea     rax, [rsp+150h+var_F0]
0x14007c908  mov     rcx, [rsp+150h+TokenHandle]; TokenHandle
0x14007c90d  mov     r8, rbx; TokenInformation
0x14007c910  mov     edx, 1; TokenInformationClass
0x14007c915  mov     [rsp+150h+ReturnLength], rax; ReturnLength
0x14007c91a  mov     [rsp+150h+var_F0], 0
0x14007c922  call    cs:__imp_ZwQueryInformationToken
0x14007c929  nop     dword ptr [rax+rax+00h]
0x14007c92e  mov     esi, eax
0x14007c930  test    eax, eax
0x14007c932  js      loc_14007C9D4
0x14007c938  mov     r13, [rbx]
0x14007c93b  mov     rcx, r13; Sid
0x14007c93e  call    cs:__imp_RtlLengthSid
0x14007c945  nop     dword ptr [rax+rax+00h]
0x14007c94a  mov     [rsp+150h+DestinationSidLength], eax
0x14007c94e  lea     r12d, [rax+8]
0x14007c952  test    rdi, rdi
0x14007c955  jz      loc_14007CA1E
0x14007c95b  mov     r15d, [rbp+50h+AceListLength]
0x14007c95f  lea     eax, [r12+r15]
0x14007c963  cmp     eax, r15d
0x14007c966  jb      loc_14007CA0A
0x14007c96c  mov     edx, eax; unsigned __int64
0x14007c96e  mov     r8d, 65737355h; unsigned int
0x14007c974  call    ?Win32AllocPoolWithQuotaZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolWithQuotaZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x14007c979  mov     r14, rax
0x14007c97c  test    rax, rax
0x14007c97f  jz      loc_14007CA0A
0x14007c985  mov     r8d, r15d; Size
0x14007c988  mov     rdx, rdi; Src
  ... truncated ...
```
