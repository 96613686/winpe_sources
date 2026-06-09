# UserAllocDefaultCompositionSecurityDescriptor

- ea: `0x14004ac40`
- end: `0x14004b38e`
- name: `UserAllocDefaultCompositionSecurityDescriptor`
- size: `1870`
- prototype: ``
- caller_count: `4`
- callee_count: `13`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140030fbc`
- `0x1400cb070`
- `0x14021aac0`
- `0x14021b040`

## callees

- `0x140009cfc`
- `0x14000bc78`
- `0x14000c544`
- `0x14004a0d0`
- `0x14004a360`
- `0x14004ac40`
- `0x14004c720`
- `0x14004dfe0`
- `0x140104ed0`
- `0x1401051dc`
- `0x1401acde0`
- `0x1402382c0`
- `0x140238800`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14004aefa`
- `ntoskrnl!ZwClose` at `0x14004aefa`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x14004adb0`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x14004adb0`
- `ntoskrnl!RtlLengthSid` at `0x14004ac91`
- `ntoskrnl!RtlLengthSid` at `0x14004ad00`
- `ntoskrnl!RtlLengthSid` at `0x14004b0de`
- `ntoskrnl!RtlLengthSid` at `0x14004ac91`
- `ntoskrnl!RtlLengthSid` at `0x14004ad00`
- `ntoskrnl!RtlLengthSid` at `0x14004b0de`
- `ntoskrnl!RtlCreateAcl` at `0x14004ae4d`
- `ntoskrnl!RtlCreateAcl` at `0x14004ae4d`
- `ntoskrnl!RtlAddAce` at `0x14004ae75`
- `ntoskrnl!RtlAddAce` at `0x14004ae75`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14004ae94`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14004ae94`
- `ntoskrnl!ExAllocatePool2` at `0x14004b07c`
- `ntoskrnl!ExAllocatePool2` at `0x14004b21d`
- `ntoskrnl!ExAllocatePool2` at `0x14004b2b1`
- `ntoskrnl!ExAllocatePool2` at `0x14004b07c`
- `ntoskrnl!ExAllocatePool2` at `0x14004b21d`
- `ntoskrnl!ExAllocatePool2` at `0x14004b2b1`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14004ae32`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14004ae32`
- `ntoskrnl!RtlSetSaclSecurityDescriptor` at `0x14004aead`
- `ntoskrnl!RtlSetSaclSecurityDescriptor` at `0x14004aead`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x14004b2f1`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x14004b2f1`
- `ntoskrnl!ZwQueryInformationToken` at `0x14004adec`
- `ntoskrnl!ZwQueryInformationToken` at `0x14004af7c`
- `ntoskrnl!ZwQueryInformationToken` at `0x14004afc5`
- `ntoskrnl!ZwQueryInformationToken` at `0x14004b041`
- `ntoskrnl!ZwQueryInformationToken` at `0x14004b0c2`
- `ntoskrnl!ZwQueryInformationToken` at `0x14004adec`
- `ntoskrnl!ZwQueryInformationToken` at `0x14004af7c`
- `ntoskrnl!ZwQueryInformationToken` at `0x14004afc5`
- `ntoskrnl!ZwQueryInformationToken` at `0x14004b041`
- `ntoskrnl!ZwQueryInformationToken` at `0x14004b0c2`
- `ntoskrnl!RtlCopySid` at `0x14004acd8`
- `ntoskrnl!RtlCopySid` at `0x14004ad7d`
- `ntoskrnl!RtlCopySid` at `0x14004b165`
- `ntoskrnl!RtlCopySid` at `0x14004acd8`
- `ntoskrnl!RtlCopySid` at `0x14004ad7d`
- `ntoskrnl!RtlCopySid` at `0x14004b165`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x14004aec1`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x14004aec1`
- `ntoskrnl!RtlSetGroupSecurityDescriptor` at `0x14004aed5`
- `ntoskrnl!RtlSetGroupSecurityDescriptor` at `0x14004aed5`
- `WIN32K!W32GetUserSessionState` at `0x14004b053`
- `WIN32K!W32GetUserSessionState` at `0x14004b053`

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
0x14004ac40  mov     [rsp-8+arg_8], rdx
0x14004ac45  mov     [rsp-8+arg_0], ecx
0x14004ac49  push    rbp
0x14004ac4a  push    rbx
0x14004ac4b  push    rsi
0x14004ac4c  push    rdi
0x14004ac4d  push    r12
0x14004ac4f  push    r13
0x14004ac51  push    r14
0x14004ac53  push    r15
0x14004ac55  lea     rbp, [rsp-18h]
0x14004ac5a  sub     rsp, 118h
0x14004ac61  xor     edi, edi
0x14004ac63  lea     rcx, [rsp+150h+Sid]; void **
0x14004ac68  xor     r12d, r12d
0x14004ac6b  mov     [rsp+150h+Sid], rdi
0x14004ac70  mov     [rsp+150h+SourceSid], r12
0x14004ac75  mov     [rsp+150h+TokenHandle], rdi
0x14004ac7a  mov     [rdx], rdi
0x14004ac7d  call    ?AllocateLocalSystemSid@@YAJPEAPEAX@Z; AllocateLocalSystemSid(void * *)
0x14004ac82  mov     esi, eax
0x14004ac84  test    eax, eax
0x14004ac86  js      loc_14004AEF0
0x14004ac8c  mov     rcx, [rsp+150h+Sid]; Sid
0x14004ac91  call    cs:__imp_RtlLengthSid
0x14004ac98  nop     dword ptr [rax+rax+00h]
0x14004ac9d  mov     r8d, 65737355h; unsigned int
0x14004aca3  mov     ebx, eax
0x14004aca5  lea     r14d, [rax+8]
0x14004aca9  mov     edx, r14d; unsigned __int64
0x14004acac  call    ?Win32AllocPoolWithQuotaZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolWithQuotaZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x14004acb1  mov     rdi, rax
0x14004acb4  test    rax, rax
0x14004acb7  jz      loc_14004B1E9
0x14004acbd  mov     r8, [rsp+150h+Sid]; SourceSid
0x14004acc2  lea     rdx, [rax+8]; DestinationSid
0x14004acc6  mov     ecx, ebx; DestinationSidLength
0x14004acc8  mov     [rax], r12w
0x14004accc  mov     [rax+2], r14w
0x14004acd1  mov     dword ptr [rax+4], 10000000h
0x14004acd8  call    cs:__imp_RtlCopySid
0x14004acdf  nop     dword ptr [rax+rax+00h]
0x14004ace4  lea     rcx, [rsp+150h+SourceSid]
0x14004ace9  call    AllocateWindowManagerSid
0x14004acee  mov     r12, [rsp+150h+SourceSid]
0x14004acf3  mov     esi, eax
0x14004acf5  test    eax, eax
0x14004acf7  js      loc_14004AEF0
0x14004acfd  mov     rcx, r12; Sid
0x14004ad00  call    cs:__imp_RtlLengthSid
0x14004ad07  nop     dword ptr [rax+rax+00h]
0x14004ad0c  mov     r13d, eax
0x14004ad0f  lea     r15d, [rax+8]
0x14004ad13  lea     ecx, [r15+r14]; unsigned __int64
0x14004ad17  cmp     ecx, r14d
0x14004ad1a  jb      loc_14004AF54
0x14004ad20  mov     edx, ecx; unsigned __int64
0x14004ad22  mov     r8d, 65737355h; unsigned int
0x14004ad28  call    ?Win32AllocPoolWithQuotaZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolWithQuotaZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x14004ad2d  mov     rbx, rax
0x14004ad30  test    rax, rax
0x14004ad33  jz      loc_14004AF54
0x14004ad39  mov     r8d, r14d; Size
0x14004ad3c  mov     rdx, rdi; Src
0x14004ad3f  mov     rcx, rax; void *
0x14004ad42  call    memmove
0x14004ad47  mov     rcx, rdi; Buffer
0x14004ad4a  call    GreDeleteFastMutex
0x14004ad4f  lea     eax, [r15+r14]
0x14004ad53  mov     word ptr [r14+rbx], 0
0x14004ad5a  lea     rdx, [r14+8]
0x14004ad5e  mov     [rbp+50h+AceListLength], eax
0x14004ad61  add     rdx, rbx; DestinationSid
0x14004ad64  mov     [rsp+150h+var_120], eax
0x14004ad68  mov     r8, r12; SourceSid
0x14004ad6b  mov     [r14+rbx+2], r15w
0x14004ad71  mov     ecx, r13d; DestinationSidLength
0x14004ad74  mov     dword ptr [r14+rbx+4], 3
0x14004ad7d  call    cs:__imp_RtlCopySid
0x14004ad84  nop     dword ptr [rax+rax+00h]
0x14004ad89  mov     edi, [rbp+50h+arg_0]
0x14004ad8c  test    edi, edi
0x14004ad8e  jz      loc_14004B386
0x14004ad94  lea     r9, [rsp+150h+TokenHandle]; TokenHandle
0x14004ad99  mov     [rsp+150h+TokenInformation], 0
0x14004ada1  mov     edx, 8; DesiredAccess
0x14004ada6  mov     r8d, 200h; HandleAttributes
0x14004adac  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x14004adb0  call    cs:__imp_ZwOpenProcessTokenEx
0x14004adb7  nop     dword ptr [rax+rax+00h]
0x14004adbc  mov     esi, eax
0x14004adbe  test    eax, eax
0x14004adc0  js      loc_14004B1B6
0x14004adc6  mov     rcx, [rsp+150h+TokenHandle]; TokenHandle
0x14004adcb  lea     rax, [rsp+150h+var_F8]
0x14004add0  mov     r9d, 4; TokenInformationLength
0x14004add6  mov     [rsp+150h+var_F8], 0
0x14004adde  lea     r8, [rsp+150h+TokenInformation]; TokenInformation
0x14004ade3  mov     [rsp+150h+ReturnLength], rax; ReturnLength
0x14004ade8  lea     edx, [r9+19h]; TokenInformationClass
0x14004adec  call    cs:__imp_ZwQueryInformationToken
0x14004adf3  nop     dword ptr [rax+rax+00h]
0x14004adf8  cmp     [rsp+150h+TokenInformation], 0
0x14004adfd  jnz     loc_14004AF5B
0x14004ae03  mov     rdi, rbx
0x14004ae06  mov     r13d, 65737355h
0x14004ae0c  jmp     loc_14004B020
0x14004ae11  mov     edx, eax; unsigned __int64
0x14004ae13  mov     r8d, 65737355h; unsigned int
0x14004ae19  call    ?Win32AllocPoolWithQuotaZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolWithQuotaZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x14004ae1e  mov     r14, rax
0x14004ae21  test    rax, rax
0x14004ae24  jz      loc_14004AF49
0x14004ae2a  mov     edx, 1; Revision
0x14004ae2f  mov     rcx, rax; SecurityDescriptor
0x14004ae32  call    cs:__imp_RtlCreateSecurityDescriptor
0x14004ae39  nop     dword ptr [rax+rax+00h]
0x14004ae3e  lea     r15, [r14+28h]
0x14004ae42  mov     r8d, 2; AclRevision
0x14004ae48  mov     rcx, r15; Acl
0x14004ae4b  mov     edx, ebx; AclLength
0x14004ae4d  call    cs:__imp_RtlCreateAcl
0x14004ae54  nop     dword ptr [rax+rax+00h]
0x14004ae59  test    eax, eax
0x14004ae5b  js      loc_14004B1DC
0x14004ae61  mov     r9, rdi; AceList
0x14004ae64  mov     dword ptr [rsp+150h+ReturnLength], r13d; AceListLength
0x14004ae69  or      r8d, 0FFFFFFFFh; StartingAceIndex
0x14004ae6d  mov     edx, 2; AceRevision
0x14004ae72  mov     rcx, r15; Acl
0x14004ae75  call    cs:__imp_RtlAddAce
0x14004ae7c  nop     dword ptr [rax+rax+00h]
0x14004ae81  test    eax, eax
0x14004ae83  js      loc_14004B1DC
0x14004ae89  xor     r9d, r9d; DaclDefaulted
0x14004ae8c  mov     r8, r15; Dacl
0x14004ae8f  mov     dl, 1; DaclPresent
0x14004ae91  mov     rcx, r14; SecurityDescriptor
0x14004ae94  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x14004ae9b  nop     dword ptr [rax+rax+00h]
0x14004aea0  xor     r9d, r9d; SaclDefaulted
0x14004aea3  xor     r8d, r8d; Sacl
0x14004aea6  xor     edx, edx; SaclPresent
0x14004aea8  mov     rcx, r14; SecurityDescriptor
0x14004aeab  mov     ebx, eax
0x14004aead  call    cs:__imp_RtlSetSaclSecurityDescriptor
0x14004aeb4  nop     dword ptr [rax+rax+00h]
0x14004aeb9  xor     r8d, r8d; OwnerDefaulted
0x14004aebc  xor     edx, edx; Owner
0x14004aebe  mov     rcx, r14; SecurityDescriptor
0x14004aec1  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x14004aec8  nop     dword ptr [rax+rax+00h]
0x14004aecd  xor     r8d, r8d; GroupDefaulted
0x14004aed0  xor     edx, edx; Group
0x14004aed2  mov     rcx, r14; SecurityDescriptor
0x14004aed5  call    cs:__imp_RtlSetGroupSecurityDescriptor
0x14004aedc  nop     dword ptr [rax+rax+00h]
0x14004aee1  test    ebx, ebx
0x14004aee3  js      loc_14004B1DC
0x14004aee9  mov     rax, [rbp+50h+arg_8]
0x14004aeed  mov     [rax], r14
0x14004aef0  mov     rcx, [rsp+150h+TokenHandle]; Handle
0x14004aef5  test    rcx, rcx
0x14004aef8  jz      short loc_14004AF06
0x14004aefa  call    cs:__imp_ZwClose
0x14004af01  nop     dword ptr [rax+rax+00h]
0x14004af06  cmp     [rsp+150h+Sid], 0
0x14004af0c  jz      short loc_14004AF18
0x14004af0e  mov     rcx, [rsp+150h+Sid]; Buffer
0x14004af13  call    GreDeleteFastMutex
0x14004af18  test    r12, r12
0x14004af1b  jz      short loc_14004AF25
0x14004af1d  mov     rcx, r12; Buffer
0x14004af20  call    GreDeleteFastMutex
0x14004af25  test    rdi, rdi
0x14004af28  jz      short loc_14004AF32
0x14004af2a  mov     rcx, rdi; Buffer
0x14004af2d  call    GreDeleteFastMutex
0x14004af32  mov     eax, esi
0x14004af34  add     rsp, 118h
0x14004af3b  pop     r15
0x14004af3d  pop     r14
0x14004af3f  pop     r13
0x14004af41  pop     r12
0x14004af43  pop     rdi
0x14004af44  pop     rsi
0x14004af45  pop     rbx
0x14004af46  pop     rbp
0x14004af47  retn
0x14004af49  mov     rax, [rbp+50h+arg_8]
0x14004af4d  mov     qword ptr [rax], 0
0x14004af54  mov     esi, 0C0000017h
0x14004af59  jmp     short loc_14004AEF0
0x14004af5b  mov     rcx, [rsp+150h+TokenHandle]; TokenHandle
0x14004af60  lea     rax, [rbp+50h+TokenInformationLength]
0x14004af64  xor     r9d, r9d; TokenInformationLength
0x14004af67  mov     [rbp+50h+TokenInformationLength], 0
0x14004af6e  xor     r8d, r8d; TokenInformation
0x14004af71  mov     [rsp+150h+ReturnLength], rax; ReturnLength
0x14004af76  lea     esi, [r9+1Fh]
0x14004af7a  mov     edx, esi; TokenInformationClass
0x14004af7c  call    cs:__imp_ZwQueryInformationToken
0x14004af83  nop     dword ptr [rax+rax+00h]
0x14004af88  mov     edx, [rbp+50h+TokenInformationLength]; unsigned __int64
0x14004af8b  mov     r13d, 65737355h
0x14004af91  mov     r8d, r13d; unsigned int
0x14004af94  call    ?Win32AllocPoolWithQuotaZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolWithQuotaZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x14004af99  mov     r14, rax
0x14004af9c  test    rax, rax
0x14004af9f  jz      loc_14004B1B1
0x14004afa5  mov     r9d, [rbp+50h+TokenInformationLength]; TokenInformationLength
0x14004afa9  lea     rax, [rsp+150h+var_F4]
0x14004afae  mov     rcx, [rsp+150h+TokenHandle]; TokenHandle
0x14004afb3  mov     r8, r14; TokenInformation
0x14004afb6  mov     edx, esi; TokenInformationClass
0x14004afb8  mov     [rsp+150h+ReturnLength], rax; ReturnLength
0x14004afbd  mov     [rsp+150h+var_F4], 0
0x14004afc5  call    cs:__imp_ZwQueryInformationToken
0x14004afcc  nop     dword ptr [rax+rax+00h]
0x14004afd1  mov     esi, eax
0x14004afd3  test    eax, eax
0x14004afd5  js      loc_14004B37E
0x14004afdb  lea     rax, [rsp+150h+var_120]
0x14004afe0  mov     r9d, edi
0x14004afe3  mov     [rsp+150h+var_128], rax; __int64
0x14004afe8  xor     r8d, r8d
0x14004afeb  mov     rax, [r14]
0x14004afee  xor     edx, edx
0x14004aff0  mov     rcx, rbx; Buffer
0x14004aff3  mov     [rsp+150h+ReturnLength], rax; Sid
0x14004aff8  call    AllocAce
0x14004affd  mov     rdi, rax
0x14004b000  test    rax, rax
0x14004b003  jz      loc_14004B372
0x14004b009  mov     ebx, [rsp+150h+var_120]
0x14004b00d  mov     [rbp+50h+AceListLength], ebx
0x14004b010  mov     rcx, r14; Buffer
0x14004b013  call    GreDeleteFastMutex
0x14004b018  test    esi, esi
0x14004b01a  js      loc_14004AEF0
0x14004b020  mov     rcx, [rsp+150h+TokenHandle]; TokenHandle
0x14004b025  lea     rax, [rsp+150h+var_120]
0x14004b02a  xor     r9d, r9d; TokenInformationLength
0x14004b02d  mov     [rsp+150h+var_120], 0
0x14004b035  xor     r8d, r8d; TokenInformation
0x14004b038  mov     [rsp+150h+ReturnLength], rax; ReturnLength
0x14004b03d  lea     edx, [r9+1]; TokenInformationClass
0x14004b041  call    cs:__imp_ZwQueryInformationToken
0x14004b048  nop     dword ptr [rax+rax+00h]
0x14004b04d  mov     ebx, [rsp+150h+var_120]
0x14004b051  mov     esi, eax
0x14004b053  call    cs:__imp_W32GetUserSessionState
0x14004b05a  nop     dword ptr [rax+rax+00h]
0x14004b05f  lea     r14, [rax+11950h]
0x14004b066  mov     eax, [r14]
0x14004b069  test    eax, eax
0x14004b06b  jnz     loc_14004B1F0
0x14004b071  mov     r8d, r13d
0x14004b074  mov     rdx, rbx
0x14004b077  mov     ecx, 101h
0x14004b07c  call    cs:__imp_ExAllocatePool2
0x14004b083  nop     dword ptr [rax+rax+00h]
0x14004b088  mov     rbx, rax
0x14004b08b  test    rax, rax
0x14004b08e  jz      short loc_14004B095
0x14004b090  lock inc qword ptr [r14+70h]
0x14004b095  test    rbx, rbx
0x14004b098  jz      loc_14004B17C
0x14004b09e  mov     r9d, [rsp+150h+var_120]; TokenInformationLength
0x14004b0a3  lea     rax, [rsp+150h+var_F0]
0x14004b0a8  mov     rcx, [rsp+150h+TokenHandle]; TokenHandle
0x14004b0ad  mov     r8, rbx; TokenInformation
0x14004b0b0  mov     edx, 1; TokenInformationClass
0x14004b0b5  mov     [rsp+150h+ReturnLength], rax; ReturnLength
0x14004b0ba  mov     [rsp+150h+var_F0], 0
0x14004b0c2  call    cs:__imp_ZwQueryInformationToken
0x14004b0c9  nop     dword ptr [rax+rax+00h]
0x14004b0ce  mov     esi, eax
0x14004b0d0  test    eax, eax
0x14004b0d2  js      loc_14004B174
0x14004b0d8  mov     r13, [rbx]
0x14004b0db  mov     rcx, r13; Sid
0x14004b0de  call    cs:__imp_RtlLengthSid
0x14004b0e5  nop     dword ptr [rax+rax+00h]
0x14004b0ea  mov     [rsp+150h+DestinationSidLength], eax
0x14004b0ee  lea     r12d, [rax+8]
0x14004b0f2  test    rdi, rdi
0x14004b0f5  jz      loc_14004B1BE
0x14004b0fb  mov     r15d, [rbp+50h+AceListLength]
0x14004b0ff  lea     eax, [r12+r15]
0x14004b103  cmp     eax, r15d
0x14004b106  jb      loc_14004B1AA
0x14004b10c  mov     edx, eax; unsigned __int64
0x14004b10e  mov     r8d, 65737355h; unsigned int
0x14004b114  call    ?Win32AllocPoolWithQuotaZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolWithQuotaZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x14004b119  mov     r14, rax
0x14004b11c  test    rax, rax
0x14004b11f  jz      loc_14004B1AA
0x14004b125  mov     r8d, r15d; Size
0x14004b128  mov     rdx, rdi; Src
  ... truncated ...
```
