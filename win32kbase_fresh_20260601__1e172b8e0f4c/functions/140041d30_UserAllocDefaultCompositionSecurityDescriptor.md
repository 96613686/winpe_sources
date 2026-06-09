# UserAllocDefaultCompositionSecurityDescriptor

- ea: `0x140041d30`
- end: `0x14004247e`
- name: `UserAllocDefaultCompositionSecurityDescriptor`
- size: `1870`
- prototype: ``
- caller_count: `4`
- callee_count: `13`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140027d3c`
- `0x14005ab60`
- `0x14021b2e0`
- `0x14021b860`

## callees

- `0x1400411c0`
- `0x140041450`
- `0x140041d30`
- `0x140043810`
- `0x140045220`
- `0x14008e14c`
- `0x1400900c8`
- `0x140090964`
- `0x140109660`
- `0x14010996c`
- `0x1401ad340`
- `0x140238c40`
- `0x140239180`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140041fea`
- `ntoskrnl!ZwClose` at `0x140041fea`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x140041ea0`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x140041ea0`
- `ntoskrnl!RtlLengthSid` at `0x140041d81`
- `ntoskrnl!RtlLengthSid` at `0x140041df0`
- `ntoskrnl!RtlLengthSid` at `0x1400421ce`
- `ntoskrnl!RtlLengthSid` at `0x140041d81`
- `ntoskrnl!RtlLengthSid` at `0x140041df0`
- `ntoskrnl!RtlLengthSid` at `0x1400421ce`
- `ntoskrnl!RtlCreateAcl` at `0x140041f3d`
- `ntoskrnl!RtlCreateAcl` at `0x140041f3d`
- `ntoskrnl!RtlAddAce` at `0x140041f65`
- `ntoskrnl!RtlAddAce` at `0x140041f65`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140041f84`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140041f84`
- `ntoskrnl!ExAllocatePool2` at `0x14004216c`
- `ntoskrnl!ExAllocatePool2` at `0x14004230d`
- `ntoskrnl!ExAllocatePool2` at `0x1400423a1`
- `ntoskrnl!ExAllocatePool2` at `0x14004216c`
- `ntoskrnl!ExAllocatePool2` at `0x14004230d`
- `ntoskrnl!ExAllocatePool2` at `0x1400423a1`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140041f22`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140041f22`
- `ntoskrnl!RtlSetSaclSecurityDescriptor` at `0x140041f9d`
- `ntoskrnl!RtlSetSaclSecurityDescriptor` at `0x140041f9d`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x1400423e1`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x1400423e1`
- `ntoskrnl!ZwQueryInformationToken` at `0x140041edc`
- `ntoskrnl!ZwQueryInformationToken` at `0x14004206c`
- `ntoskrnl!ZwQueryInformationToken` at `0x1400420b5`
- `ntoskrnl!ZwQueryInformationToken` at `0x140042131`
- `ntoskrnl!ZwQueryInformationToken` at `0x1400421b2`
- `ntoskrnl!ZwQueryInformationToken` at `0x140041edc`
- `ntoskrnl!ZwQueryInformationToken` at `0x14004206c`
- `ntoskrnl!ZwQueryInformationToken` at `0x1400420b5`
- `ntoskrnl!ZwQueryInformationToken` at `0x140042131`
- `ntoskrnl!ZwQueryInformationToken` at `0x1400421b2`
- `ntoskrnl!RtlCopySid` at `0x140041dc8`
- `ntoskrnl!RtlCopySid` at `0x140041e6d`
- `ntoskrnl!RtlCopySid` at `0x140042255`
- `ntoskrnl!RtlCopySid` at `0x140041dc8`
- `ntoskrnl!RtlCopySid` at `0x140041e6d`
- `ntoskrnl!RtlCopySid` at `0x140042255`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x140041fb1`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x140041fb1`
- `ntoskrnl!RtlSetGroupSecurityDescriptor` at `0x140041fc5`
- `ntoskrnl!RtlSetGroupSecurityDescriptor` at `0x140041fc5`
- `WIN32K!W32GetUserSessionState` at `0x140042143`
- `WIN32K!W32GetUserSessionState` at `0x140042143`

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
0x140041d30  mov     [rsp-8+arg_8], rdx
0x140041d35  mov     [rsp-8+arg_0], ecx
0x140041d39  push    rbp
0x140041d3a  push    rbx
0x140041d3b  push    rsi
0x140041d3c  push    rdi
0x140041d3d  push    r12
0x140041d3f  push    r13
0x140041d41  push    r14
0x140041d43  push    r15
0x140041d45  lea     rbp, [rsp-18h]
0x140041d4a  sub     rsp, 118h
0x140041d51  xor     edi, edi
0x140041d53  lea     rcx, [rsp+150h+Sid]; void **
0x140041d58  xor     r12d, r12d
0x140041d5b  mov     [rsp+150h+Sid], rdi
0x140041d60  mov     [rsp+150h+SourceSid], r12
0x140041d65  mov     [rsp+150h+TokenHandle], rdi
0x140041d6a  mov     [rdx], rdi
0x140041d6d  call    ?AllocateLocalSystemSid@@YAJPEAPEAX@Z; AllocateLocalSystemSid(void * *)
0x140041d72  mov     esi, eax
0x140041d74  test    eax, eax
0x140041d76  js      loc_140041FE0
0x140041d7c  mov     rcx, [rsp+150h+Sid]; Sid
0x140041d81  call    cs:__imp_RtlLengthSid
0x140041d88  nop     dword ptr [rax+rax+00h]
0x140041d8d  mov     r8d, 65737355h; unsigned int
0x140041d93  mov     ebx, eax
0x140041d95  lea     r14d, [rax+8]
0x140041d99  mov     edx, r14d; unsigned __int64
0x140041d9c  call    ?Win32AllocPoolWithQuotaZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolWithQuotaZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x140041da1  mov     rdi, rax
0x140041da4  test    rax, rax
0x140041da7  jz      loc_1400422D9
0x140041dad  mov     r8, [rsp+150h+Sid]; SourceSid
0x140041db2  lea     rdx, [rax+8]; DestinationSid
0x140041db6  mov     ecx, ebx; DestinationSidLength
0x140041db8  mov     [rax], r12w
0x140041dbc  mov     [rax+2], r14w
0x140041dc1  mov     dword ptr [rax+4], 10000000h
0x140041dc8  call    cs:__imp_RtlCopySid
0x140041dcf  nop     dword ptr [rax+rax+00h]
0x140041dd4  lea     rcx, [rsp+150h+SourceSid]
0x140041dd9  call    AllocateWindowManagerSid
0x140041dde  mov     r12, [rsp+150h+SourceSid]
0x140041de3  mov     esi, eax
0x140041de5  test    eax, eax
0x140041de7  js      loc_140041FE0
0x140041ded  mov     rcx, r12; Sid
0x140041df0  call    cs:__imp_RtlLengthSid
0x140041df7  nop     dword ptr [rax+rax+00h]
0x140041dfc  mov     r13d, eax
0x140041dff  lea     r15d, [rax+8]
0x140041e03  lea     ecx, [r15+r14]; unsigned __int64
0x140041e07  cmp     ecx, r14d
0x140041e0a  jb      loc_140042044
0x140041e10  mov     edx, ecx; unsigned __int64
0x140041e12  mov     r8d, 65737355h; unsigned int
0x140041e18  call    ?Win32AllocPoolWithQuotaZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolWithQuotaZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x140041e1d  mov     rbx, rax
0x140041e20  test    rax, rax
0x140041e23  jz      loc_140042044
0x140041e29  mov     r8d, r14d; Size
0x140041e2c  mov     rdx, rdi; Src
0x140041e2f  mov     rcx, rax; void *
0x140041e32  call    memmove
0x140041e37  mov     rcx, rdi; Buffer
0x140041e3a  call    GreDeleteFastMutex
0x140041e3f  lea     eax, [r15+r14]
0x140041e43  mov     word ptr [r14+rbx], 0
0x140041e4a  lea     rdx, [r14+8]
0x140041e4e  mov     [rbp+50h+AceListLength], eax
0x140041e51  add     rdx, rbx; DestinationSid
0x140041e54  mov     [rsp+150h+var_120], eax
0x140041e58  mov     r8, r12; SourceSid
0x140041e5b  mov     [r14+rbx+2], r15w
0x140041e61  mov     ecx, r13d; DestinationSidLength
0x140041e64  mov     dword ptr [r14+rbx+4], 3
0x140041e6d  call    cs:__imp_RtlCopySid
0x140041e74  nop     dword ptr [rax+rax+00h]
0x140041e79  mov     edi, [rbp+50h+arg_0]
0x140041e7c  test    edi, edi
0x140041e7e  jz      loc_140042476
0x140041e84  lea     r9, [rsp+150h+TokenHandle]; TokenHandle
0x140041e89  mov     [rsp+150h+TokenInformation], 0
0x140041e91  mov     edx, 8; DesiredAccess
0x140041e96  mov     r8d, 200h; HandleAttributes
0x140041e9c  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x140041ea0  call    cs:__imp_ZwOpenProcessTokenEx
0x140041ea7  nop     dword ptr [rax+rax+00h]
0x140041eac  mov     esi, eax
0x140041eae  test    eax, eax
0x140041eb0  js      loc_1400422A6
0x140041eb6  mov     rcx, [rsp+150h+TokenHandle]; TokenHandle
0x140041ebb  lea     rax, [rsp+150h+var_F8]
0x140041ec0  mov     r9d, 4; TokenInformationLength
0x140041ec6  mov     [rsp+150h+var_F8], 0
0x140041ece  lea     r8, [rsp+150h+TokenInformation]; TokenInformation
0x140041ed3  mov     [rsp+150h+ReturnLength], rax; ReturnLength
0x140041ed8  lea     edx, [r9+19h]; TokenInformationClass
0x140041edc  call    cs:__imp_ZwQueryInformationToken
0x140041ee3  nop     dword ptr [rax+rax+00h]
0x140041ee8  cmp     [rsp+150h+TokenInformation], 0
0x140041eed  jnz     loc_14004204B
0x140041ef3  mov     rdi, rbx
0x140041ef6  mov     r13d, 65737355h
0x140041efc  jmp     loc_140042110
0x140041f01  mov     edx, eax; unsigned __int64
0x140041f03  mov     r8d, 65737355h; unsigned int
0x140041f09  call    ?Win32AllocPoolWithQuotaZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolWithQuotaZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x140041f0e  mov     r14, rax
0x140041f11  test    rax, rax
0x140041f14  jz      loc_140042039
0x140041f1a  mov     edx, 1; Revision
0x140041f1f  mov     rcx, rax; SecurityDescriptor
0x140041f22  call    cs:__imp_RtlCreateSecurityDescriptor
0x140041f29  nop     dword ptr [rax+rax+00h]
0x140041f2e  lea     r15, [r14+28h]
0x140041f32  mov     r8d, 2; AclRevision
0x140041f38  mov     rcx, r15; Acl
0x140041f3b  mov     edx, ebx; AclLength
0x140041f3d  call    cs:__imp_RtlCreateAcl
0x140041f44  nop     dword ptr [rax+rax+00h]
0x140041f49  test    eax, eax
0x140041f4b  js      loc_1400422CC
0x140041f51  mov     r9, rdi; AceList
0x140041f54  mov     dword ptr [rsp+150h+ReturnLength], r13d; AceListLength
0x140041f59  or      r8d, 0FFFFFFFFh; StartingAceIndex
0x140041f5d  mov     edx, 2; AceRevision
0x140041f62  mov     rcx, r15; Acl
0x140041f65  call    cs:__imp_RtlAddAce
0x140041f6c  nop     dword ptr [rax+rax+00h]
0x140041f71  test    eax, eax
0x140041f73  js      loc_1400422CC
0x140041f79  xor     r9d, r9d; DaclDefaulted
0x140041f7c  mov     r8, r15; Dacl
0x140041f7f  mov     dl, 1; DaclPresent
0x140041f81  mov     rcx, r14; SecurityDescriptor
0x140041f84  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x140041f8b  nop     dword ptr [rax+rax+00h]
0x140041f90  xor     r9d, r9d; SaclDefaulted
0x140041f93  xor     r8d, r8d; Sacl
0x140041f96  xor     edx, edx; SaclPresent
0x140041f98  mov     rcx, r14; SecurityDescriptor
0x140041f9b  mov     ebx, eax
0x140041f9d  call    cs:__imp_RtlSetSaclSecurityDescriptor
0x140041fa4  nop     dword ptr [rax+rax+00h]
0x140041fa9  xor     r8d, r8d; OwnerDefaulted
0x140041fac  xor     edx, edx; Owner
0x140041fae  mov     rcx, r14; SecurityDescriptor
0x140041fb1  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x140041fb8  nop     dword ptr [rax+rax+00h]
0x140041fbd  xor     r8d, r8d; GroupDefaulted
0x140041fc0  xor     edx, edx; Group
0x140041fc2  mov     rcx, r14; SecurityDescriptor
0x140041fc5  call    cs:__imp_RtlSetGroupSecurityDescriptor
0x140041fcc  nop     dword ptr [rax+rax+00h]
0x140041fd1  test    ebx, ebx
0x140041fd3  js      loc_1400422CC
0x140041fd9  mov     rax, [rbp+50h+arg_8]
0x140041fdd  mov     [rax], r14
0x140041fe0  mov     rcx, [rsp+150h+TokenHandle]; Handle
0x140041fe5  test    rcx, rcx
0x140041fe8  jz      short loc_140041FF6
0x140041fea  call    cs:__imp_ZwClose
0x140041ff1  nop     dword ptr [rax+rax+00h]
0x140041ff6  cmp     [rsp+150h+Sid], 0
0x140041ffc  jz      short loc_140042008
0x140041ffe  mov     rcx, [rsp+150h+Sid]; Buffer
0x140042003  call    GreDeleteFastMutex
0x140042008  test    r12, r12
0x14004200b  jz      short loc_140042015
0x14004200d  mov     rcx, r12; Buffer
0x140042010  call    GreDeleteFastMutex
0x140042015  test    rdi, rdi
0x140042018  jz      short loc_140042022
0x14004201a  mov     rcx, rdi; Buffer
0x14004201d  call    GreDeleteFastMutex
0x140042022  mov     eax, esi
0x140042024  add     rsp, 118h
0x14004202b  pop     r15
0x14004202d  pop     r14
0x14004202f  pop     r13
0x140042031  pop     r12
0x140042033  pop     rdi
0x140042034  pop     rsi
0x140042035  pop     rbx
0x140042036  pop     rbp
0x140042037  retn
0x140042039  mov     rax, [rbp+50h+arg_8]
0x14004203d  mov     qword ptr [rax], 0
0x140042044  mov     esi, 0C0000017h
0x140042049  jmp     short loc_140041FE0
0x14004204b  mov     rcx, [rsp+150h+TokenHandle]; TokenHandle
0x140042050  lea     rax, [rbp+50h+TokenInformationLength]
0x140042054  xor     r9d, r9d; TokenInformationLength
0x140042057  mov     [rbp+50h+TokenInformationLength], 0
0x14004205e  xor     r8d, r8d; TokenInformation
0x140042061  mov     [rsp+150h+ReturnLength], rax; ReturnLength
0x140042066  lea     esi, [r9+1Fh]
0x14004206a  mov     edx, esi; TokenInformationClass
0x14004206c  call    cs:__imp_ZwQueryInformationToken
0x140042073  nop     dword ptr [rax+rax+00h]
0x140042078  mov     edx, [rbp+50h+TokenInformationLength]; unsigned __int64
0x14004207b  mov     r13d, 65737355h
0x140042081  mov     r8d, r13d; unsigned int
0x140042084  call    ?Win32AllocPoolWithQuotaZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolWithQuotaZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x140042089  mov     r14, rax
0x14004208c  test    rax, rax
0x14004208f  jz      loc_1400422A1
0x140042095  mov     r9d, [rbp+50h+TokenInformationLength]; TokenInformationLength
0x140042099  lea     rax, [rsp+150h+var_F4]
0x14004209e  mov     rcx, [rsp+150h+TokenHandle]; TokenHandle
0x1400420a3  mov     r8, r14; TokenInformation
0x1400420a6  mov     edx, esi; TokenInformationClass
0x1400420a8  mov     [rsp+150h+ReturnLength], rax; ReturnLength
0x1400420ad  mov     [rsp+150h+var_F4], 0
0x1400420b5  call    cs:__imp_ZwQueryInformationToken
0x1400420bc  nop     dword ptr [rax+rax+00h]
0x1400420c1  mov     esi, eax
0x1400420c3  test    eax, eax
0x1400420c5  js      loc_14004246E
0x1400420cb  lea     rax, [rsp+150h+var_120]
0x1400420d0  mov     r9d, edi
0x1400420d3  mov     [rsp+150h+var_128], rax; __int64
0x1400420d8  xor     r8d, r8d
0x1400420db  mov     rax, [r14]
0x1400420de  xor     edx, edx
0x1400420e0  mov     rcx, rbx; Buffer
0x1400420e3  mov     [rsp+150h+ReturnLength], rax; Sid
0x1400420e8  call    AllocAce
0x1400420ed  mov     rdi, rax
0x1400420f0  test    rax, rax
0x1400420f3  jz      loc_140042462
0x1400420f9  mov     ebx, [rsp+150h+var_120]
0x1400420fd  mov     [rbp+50h+AceListLength], ebx
0x140042100  mov     rcx, r14; Buffer
0x140042103  call    GreDeleteFastMutex
0x140042108  test    esi, esi
0x14004210a  js      loc_140041FE0
0x140042110  mov     rcx, [rsp+150h+TokenHandle]; TokenHandle
0x140042115  lea     rax, [rsp+150h+var_120]
0x14004211a  xor     r9d, r9d; TokenInformationLength
0x14004211d  mov     [rsp+150h+var_120], 0
0x140042125  xor     r8d, r8d; TokenInformation
0x140042128  mov     [rsp+150h+ReturnLength], rax; ReturnLength
0x14004212d  lea     edx, [r9+1]; TokenInformationClass
0x140042131  call    cs:__imp_ZwQueryInformationToken
0x140042138  nop     dword ptr [rax+rax+00h]
0x14004213d  mov     ebx, [rsp+150h+var_120]
0x140042141  mov     esi, eax
0x140042143  call    cs:__imp_W32GetUserSessionState
0x14004214a  nop     dword ptr [rax+rax+00h]
0x14004214f  lea     r14, [rax+11950h]
0x140042156  mov     eax, [r14]
0x140042159  test    eax, eax
0x14004215b  jnz     loc_1400422E0
0x140042161  mov     r8d, r13d
0x140042164  mov     rdx, rbx
0x140042167  mov     ecx, 101h
0x14004216c  call    cs:__imp_ExAllocatePool2
0x140042173  nop     dword ptr [rax+rax+00h]
0x140042178  mov     rbx, rax
0x14004217b  test    rax, rax
0x14004217e  jz      short loc_140042185
0x140042180  lock inc qword ptr [r14+70h]
0x140042185  test    rbx, rbx
0x140042188  jz      loc_14004226C
0x14004218e  mov     r9d, [rsp+150h+var_120]; TokenInformationLength
0x140042193  lea     rax, [rsp+150h+var_F0]
0x140042198  mov     rcx, [rsp+150h+TokenHandle]; TokenHandle
0x14004219d  mov     r8, rbx; TokenInformation
0x1400421a0  mov     edx, 1; TokenInformationClass
0x1400421a5  mov     [rsp+150h+ReturnLength], rax; ReturnLength
0x1400421aa  mov     [rsp+150h+var_F0], 0
0x1400421b2  call    cs:__imp_ZwQueryInformationToken
0x1400421b9  nop     dword ptr [rax+rax+00h]
0x1400421be  mov     esi, eax
0x1400421c0  test    eax, eax
0x1400421c2  js      loc_140042264
0x1400421c8  mov     r13, [rbx]
0x1400421cb  mov     rcx, r13; Sid
0x1400421ce  call    cs:__imp_RtlLengthSid
0x1400421d5  nop     dword ptr [rax+rax+00h]
0x1400421da  mov     [rsp+150h+DestinationSidLength], eax
0x1400421de  lea     r12d, [rax+8]
0x1400421e2  test    rdi, rdi
0x1400421e5  jz      loc_1400422AE
0x1400421eb  mov     r15d, [rbp+50h+AceListLength]
0x1400421ef  lea     eax, [r12+r15]
0x1400421f3  cmp     eax, r15d
0x1400421f6  jb      loc_14004229A
0x1400421fc  mov     edx, eax; unsigned __int64
0x1400421fe  mov     r8d, 65737355h; unsigned int
0x140042204  call    ?Win32AllocPoolWithQuotaZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolWithQuotaZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x140042209  mov     r14, rax
0x14004220c  test    rax, rax
0x14004220f  jz      loc_14004229A
0x140042215  mov     r8d, r15d; Size
0x140042218  mov     rdx, rdi; Src
  ... truncated ...
```
