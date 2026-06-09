# RSetServiceObjectSecurity

- ea: `0x140081f50`
- end: `0x1400824bf`
- name: `RSetServiceObjectSecurity`
- size: `1391`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x140003e54`
- `0x140004c58`
- `0x1400083f0`
- `0x140008548`
- `0x14000bebc`
- `0x140013b0c`
- `0x140015900`
- `0x14001c1a0`
- `0x14001c87c`
- `0x14001f99c`
- `0x140020d84`
- `0x1400274f0`
- `0x14002a368`
- `0x140042d30`
- `0x14004401c`
- `0x140081f50`
- `0x140092420`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x1400820b0`
- `RPCRT4!RpcImpersonateClient` at `0x1400820b0`
- `RPCRT4!RpcRevertToSelf` at `0x1400820e5`
- `RPCRT4!RpcRevertToSelf` at `0x1400820e5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14008247a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14008247a`
- `ntdll!RtlSetSecurityObject` at `0x14008235e`
- `ntdll!RtlSetSecurityObject` at `0x14008235e`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x140082016`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x140082016`
- `ntdll!RtlAreAllAccessesGranted` at `0x140082074`
- `ntdll!RtlAreAllAccessesGranted` at `0x140082074`
- `ntdll!NtOpenThreadToken` at `0x1400820dc`
- `ntdll!NtOpenThreadToken` at `0x1400820dc`
- `ntdll!NtClose` at `0x140082489`
- `ntdll!NtClose` at `0x140082489`
- `ntdll!RtlNtStatusToDosError` at `0x140082172`
- `ntdll!RtlNtStatusToDosError` at `0x1400821f8`
- `ntdll!RtlNtStatusToDosError` at `0x14008239d`
- `ntdll!RtlNtStatusToDosError` at `0x140082172`
- `ntdll!RtlNtStatusToDosError` at `0x1400821f8`
- `ntdll!RtlNtStatusToDosError` at `0x14008239d`
- `ntdll!RtlFreeHeap` at `0x14008243b`
- `ntdll!RtlFreeHeap` at `0x14008246b`
- `ntdll!RtlFreeHeap` at `0x1400824a6`
- `ntdll!RtlFreeHeap` at `0x14008243b`
- `ntdll!RtlFreeHeap` at `0x14008246b`
- `ntdll!RtlFreeHeap` at `0x1400824a6`
- `ntdll!RtlLengthSecurityDescriptor` at `0x1400822ca`
- `ntdll!RtlLengthSecurityDescriptor` at `0x1400822ca`
- `ntdll!RtlAllocateHeap` at `0x140081fec`
- `ntdll!RtlAllocateHeap` at `0x1400822e8`
- `ntdll!RtlAllocateHeap` at `0x140081fec`
- `ntdll!RtlAllocateHeap` at `0x1400822e8`

## pseudocode

```c
__int64 __fastcall RSetServiceObjectSecurity(ACCESS_MASK *a1, char a2, _DWORD *a3, unsigned int a4)
{
  ULONG v4; // ebx
  SIZE_T v5; // r12
  void *v6; // rdi
  _QWORD *v10; // rcx
  SECURITY_INFORMATION v11; // r15d
  _DWORD *v12; // r14
  _DWORD *Heap; // rax
  int v14; // edx
  ACCESS_MASK v15; // ecx
  __int64 v16; // rsi
  RPC_STATUS v17; // eax
  ULONG v18; // r12d
  int v19; // r13d
  unsigned int v20; // eax
  int v21; // eax
  __int64 v22; // r8
  NTSTATUS v23; // ebx
  unsigned int v24; // eax
  int v25; // r8d
  PRPC_ASYNC_STATE v26; // rcx
  int v27; // edx
  void **v28; // rcx
  ULONG v29; // eax
  size_t v30; // rsi
  PVOID v31; // rax
  NTSTATUS v32; // eax
  NTSTATUS v33; // ebx
  unsigned int v34; // eax
  PRPC_ASYNC_STATE v35; // rcx
  __int64 v36; // rdx
  int v38; // [rsp+30h] [rbp-28h] BYREF
  void *v39; // [rsp+38h] [rbp-20h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-18h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp-10h] BYREF

  v4 = 0;
  v5 = a4;
  TokenHandle = 0;
  v6 = 0;
  v38 = 0;
  v39 = 0;
  hKey = 0;
  ScSetTcpKeepalive();
  if ( !(unsigned int)ScIsValidScManagerOrServiceHandle(a1, (enum SC_HANDLE_TYPE *)&v38) )
  {
    v4 = 6;
    goto LABEL_82;
  }
  if ( v38 == 1 && (unsigned int)ScCheckServiceProtectedProcess(v10, 0) )
  {
    v4 = 5;
    goto LABEL_82;
  }
  v11 = a2 & 0x9F;
  if ( v11 )
  {
    v12 = a3;
    v4 = 8;
    if ( ((unsigned __int8)a3 & 7) != 0 )
    {
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v5);
      v12 = Heap;
      if ( !Heap )
        goto LABEL_80;
      memmove(Heap, a3, v5);
    }
    if ( !RtlValidRelativeSecurityDescriptor(v12, v5, v11) )
      goto LABEL_11;
    v14 = ((v11 & 0x88) != 0 ? 0x1000000 : 0) | 0x80000;
    if ( (v11 & 0x13) == 0 )
      v14 = (v11 & 0x88) != 0 ? 0x1000000 : 0;
    v15 = v14 | 0x40000;
    if ( (v11 & 4) == 0 )
      v15 = v14;
    if ( (v11 & 1) != 0 && !v12[1] || (v11 & 2) != 0 && !v12[2] )
    {
LABEL_11:
      v4 = 87;
      goto LABEL_80;
    }
    if ( !RtlAreAllAccessesGranted(a1[2], v15) )
    {
      v4 = 5;
      goto LABEL_80;
    }
    v16 = 0;
    if ( v38 == 1 )
    {
      v16 = *((_QWORD *)a1 + 2);
      if ( (*(_DWORD *)(v16 + 52) & 1) != 0 )
      {
        v4 = 1072;
        goto LABEL_80;
      }
    }
    if ( (v11 & 1) != 0 )
    {
      v17 = RpcImpersonateClient(0);
      v18 = v17;
      if ( v17 )
      {
        ScLogImpersonateFailureEvent(v17);
LABEL_28:
        v4 = v18;
        goto LABEL_80;
      }
      v19 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 1u, &TokenHandle);
      v20 = RpcRevertToSelf();
      v18 = v20;
      if ( v20 )
      {
        if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 12, WPP_8f086be6c6f937952c5e847c48275da5_Traceguids, v20);
        }
        ScLogEvent(5u, L"RpcRevertToSelf", v18);
        goto LABEL_28;
      }
      if ( v19 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 13, WPP_8f086be6c6f937952c5e847c48275da5_Traceguids, (unsigned int)v19);
        }
        v4 = RtlNtStatusToDosError(v19);
        goto LABEL_80;
      }
    }
    if ( v38 == 1 )
    {
      CScmLock::LockAutoExclusive(v16 + 312, &v38);
      v21 = CServiceRecord::SetSecurityObject((CServiceRecord *)v16, v11, v12, TokenHandle, &v39);
      v23 = v21;
      if ( v21 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        {
          WPP_SF_Sd(
            WPP_GLOBAL_Control->StubInfo,
            14,
            (unsigned int)WPP_8f086be6c6f937952c5e847c48275da5_Traceguids,
            *(_QWORD *)(v16 + 56),
            v21);
        }
        v4 = RtlNtStatusToDosError(v23);
        goto LABEL_45;
      }
      v24 = CServiceRecord::OpenServiceConfigKey((CServiceRecord *)v16, 0x20006u, v22, &hKey);
      v4 = v24;
      if ( v24 )
      {
        v26 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        {
          goto LABEL_51;
        }
        v27 = 15;
      }
      else
      {
        v24 = ScWriteSd(hKey, *(void **)(v16 + 144));
        v4 = v24;
        if ( !v24 )
        {
LABEL_45:
          CScmSyncLockExclusive::InternalUnlock((CScmSyncLockExclusive *)&v38);
          v6 = v39;
          goto LABEL_80;
        }
        v26 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        {
          goto LABEL_51;
        }
        v27 = 16;
      }
      WPP_SF_Sd(
        v26->StubInfo,
        v27,
        (unsigned int)WPP_8f086be6c6f937952c5e847c48275da5_Traceguids,
        *(_QWORD *)(v16 + 56),
        v24);
LABEL_51:
      CServiceRecord::SetServiceSd((CServiceRecord *)v16, v39, v25);
      v28 = (void **)&v38;
LABEL_79:
      CScmSyncLockExclusive::InternalUnlock((CScmSyncLockExclusive *)v28);
LABEL_80:
      if ( v12 != a3 )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v12);
      goto LABEL_82;
    }
    CScmLock::LockAutoExclusive(&ScManagerSdLock, &v39);
    if ( ScManagerSd )
    {
      v29 = RtlLengthSecurityDescriptor(ScManagerSd);
      if ( v29 )
      {
        v30 = v29;
        v31 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v29);
        v6 = v31;
        if ( !v31 )
        {
          if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->StubInfo, 17, WPP_8f086be6c6f937952c5e847c48275da5_Traceguids);
          }
          goto LABEL_78;
        }
        memmove(v31, ScManagerSd, v30);
      }
    }
    v32 = RtlSetSecurityObject(v11, v12, &ScManagerSd, (PGENERIC_MAPPING)&stru_14009B9A8, TokenHandle);
    v33 = v32;
    if ( v32 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 18, WPP_8f086be6c6f937952c5e847c48275da5_Traceguids, (unsigned int)v32);
      v4 = RtlNtStatusToDosError(v33);
      goto LABEL_78;
    }
    v34 = ScOpenScManagerSecurityKey(0x20006u, &hKey);
    v4 = v34;
    if ( v34 )
    {
      v35 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        goto LABEL_77;
      v36 = 19;
    }
    else
    {
      v34 = ScWriteSd(hKey, ScManagerSd);
      v4 = v34;
      if ( !v34 )
      {
LABEL_78:
        v28 = &v39;
        goto LABEL_79;
      }
      v35 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
      {
LABEL_77:
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, ScManagerSd);
        ScManagerSd = v6;
        v6 = 0;
        goto LABEL_78;
      }
      v36 = 20;
    }
    WPP_SF_d(v35->StubInfo, v36, WPP_8f086be6c6f937952c5e847c48275da5_Traceguids, v34);
    goto LABEL_77;
  }
LABEL_82:
  if ( hKey )
    RegCloseKey(hKey);
  if ( TokenHandle )
    NtClose(TokenHandle);
  if ( v6 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
  return v4;
}

```

## disassembly

```asm
0x140081f50  mov     [rsp-40h+Src], r8
0x140081f55  push    rbp
0x140081f56  push    rbx
0x140081f57  push    rsi
0x140081f58  push    rdi
0x140081f59  push    r12
0x140081f5b  push    r13
0x140081f5d  push    r14
0x140081f5f  push    r15
0x140081f61  mov     rbp, rsp
0x140081f64  sub     rsp, 58h
0x140081f68  xor     ebx, ebx
0x140081f6a  mov     r12d, r9d
0x140081f6d  mov     [rbp+TokenHandle], rbx
0x140081f71  mov     edi, ebx
0x140081f73  mov     [rbp+var_28], ebx
0x140081f76  mov     rsi, r8
0x140081f79  mov     [rbp+var_20], rbx
0x140081f7d  mov     r15d, edx
0x140081f80  mov     [rbp+hKey], rbx
0x140081f84  mov     r13, rcx
0x140081f87  call    ?ScSetTcpKeepalive@@YAXXZ; ScSetTcpKeepalive(void)
0x140081f8c  lea     rdx, [rbp+var_28]; enum SC_HANDLE_TYPE *
0x140081f90  mov     rcx, r13; void *
0x140081f93  call    ?ScIsValidScManagerOrServiceHandle@@YAHPEAXPEAW4SC_HANDLE_TYPE@@@Z; ScIsValidScManagerOrServiceHandle(void *,SC_HANDLE_TYPE *)
0x140081f98  test    eax, eax
0x140081f9a  jnz     short loc_140081FA4
0x140081f9c  lea     ebx, [rdi+6]
0x140081f9f  jmp     loc_140082471
0x140081fa4  cmp     [rbp+var_28], 1
0x140081fa8  jnz     short loc_140081FBF
0x140081faa  xor     edx, edx; unsigned __int8
0x140081fac  call    ?ScCheckServiceProtectedProcess@@YAKPEAXE@Z; ScCheckServiceProtectedProcess(void *,uchar)
0x140081fb1  test    eax, eax
0x140081fb3  jz      short loc_140081FBF
0x140081fb5  mov     ebx, 5
0x140081fba  jmp     loc_140082471
0x140081fbf  and     r15d, 9Fh
0x140081fc6  jz      loc_140082471
0x140081fcc  mov     r14, rsi
0x140081fcf  mov     ebx, 8
0x140081fd4  test    sil, 7
0x140081fd8  jz      short loc_14008200D
0x140081fda  mov     rcx, gs:60h
0x140081fe3  mov     r8, r12; Size
0x140081fe6  mov     edx, ebx; Flags
0x140081fe8  mov     rcx, [rcx+30h]; HeapHandle
0x140081fec  call    cs:__imp_RtlAllocateHeap
0x140081ff2  mov     r14, rax
0x140081ff5  test    rax, rax
0x140081ff8  jz      loc_140082453
0x140081ffe  mov     rdx, [rbp+Src]; Src
0x140082002  mov     r8, r12; Size
0x140082005  mov     rcx, rax; void *
0x140082008  call    memmove
0x14008200d  mov     r8d, r15d; RequiredInformation
0x140082010  mov     edx, r12d; SecurityDescriptorLength
0x140082013  mov     rcx, r14; SecurityDescriptorInput
0x140082016  call    cs:__imp_RtlValidRelativeSecurityDescriptor
0x14008201c  test    al, al
0x14008201e  jnz     short loc_14008202A
0x140082020  mov     ebx, 57h ; 'W'
0x140082025  jmp     loc_140082453
0x14008202a  mov     eax, r15d
0x14008202d  mov     r12d, r15d
0x140082030  and     al, 88h
0x140082032  neg     al
0x140082034  sbb     ecx, ecx
0x140082036  and     ecx, 1000000h
0x14008203c  mov     edx, ecx
0x14008203e  bts     edx, 13h
0x140082042  test    r15b, 13h
0x140082046  cmovz   edx, ecx
0x140082049  mov     ecx, edx
0x14008204b  bts     ecx, 12h
0x14008204f  test    r15b, 4
0x140082053  cmovz   ecx, edx
0x140082056  and     r12d, 1
0x14008205a  jz      short loc_140082062
0x14008205c  cmp     [r14+4], edi
0x140082060  jz      short loc_140082020
0x140082062  test    r15b, 2
0x140082066  jz      short loc_14008206E
0x140082068  cmp     [r14+8], edi
0x14008206c  jz      short loc_140082020
0x14008206e  mov     edx, ecx; DesiredAccess
0x140082070  mov     ecx, [r13+8]; GrantedAccess
0x140082074  call    cs:__imp_RtlAreAllAccessesGranted
0x14008207a  test    al, al
0x14008207c  jnz     short loc_140082088
0x14008207e  mov     ebx, 5
0x140082083  jmp     loc_140082453
0x140082088  xor     esi, esi
0x14008208a  cmp     [rbp+var_28], 1
0x14008208e  jnz     short loc_1400820A5
0x140082090  mov     rsi, [r13+10h]
0x140082094  mov     eax, [rsi+34h]
0x140082097  test    al, 1
0x140082099  jz      short loc_1400820A5
0x14008209b  mov     ebx, 430h
0x1400820a0  jmp     loc_140082453
0x1400820a5  test    r12d, r12d
0x1400820a8  jz      loc_14008217F
0x1400820ae  xor     ecx, ecx; BindingHandle
0x1400820b0  call    cs:__imp_RpcImpersonateClient
0x1400820b6  mov     r12d, eax
0x1400820b9  test    eax, eax
0x1400820bb  jz      short loc_1400820CC
0x1400820bd  mov     ecx, eax; int
0x1400820bf  call    ?ScLogImpersonateFailureEvent@@YAXJ@Z; ScLogImpersonateFailureEvent(long)
0x1400820c4  mov     ebx, r12d
0x1400820c7  jmp     loc_140082453
0x1400820cc  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1400820d0  mov     r8b, 1; OpenAsSelf
0x1400820d3  mov     edx, ebx; DesiredAccess
0x1400820d5  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1400820dc  call    cs:__imp_NtOpenThreadToken
0x1400820e2  mov     r13d, eax
0x1400820e5  call    cs:__imp_RpcRevertToSelf
0x1400820eb  mov     r12d, eax
0x1400820ee  test    eax, eax
0x1400820f0  jz      short loc_140082139
0x1400820f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400820f9  lea     rdx, WPP_GLOBAL_Control
0x140082100  cmp     rcx, rdx
0x140082103  jz      short loc_140082123
0x140082105  test    byte ptr [rcx+1Ch], 1
0x140082109  jz      short loc_140082123
0x14008210b  mov     rcx, [rcx+10h]
0x14008210f  lea     r8, WPP_8f086be6c6f937952c5e847c48275da5_Traceguids
0x140082116  mov     edx, 0Ch
0x14008211b  mov     r9d, eax
0x14008211e  call    WPP_SF_d
0x140082123  mov     r8d, r12d
0x140082126  lea     rdx, aRpcreverttosel; "RpcRevertToSelf"
0x14008212d  mov     ecx, 5; unsigned int
0x140082132  call    ?ScLogEvent@@YAXKZZ; ScLogEvent(ulong,...)
0x140082137  jmp     short loc_1400820C4
0x140082139  test    r13d, r13d
0x14008213c  jns     short loc_14008217F
0x14008213e  mov     rcx, cs:WPP_GLOBAL_Control
0x140082145  lea     rdx, WPP_GLOBAL_Control
0x14008214c  cmp     rcx, rdx
0x14008214f  jz      short loc_14008216F
0x140082151  test    byte ptr [rcx+1Ch], 1
0x140082155  jz      short loc_14008216F
0x140082157  mov     rcx, [rcx+10h]
0x14008215b  lea     r8, WPP_8f086be6c6f937952c5e847c48275da5_Traceguids
0x140082162  mov     edx, 0Dh
0x140082167  mov     r9d, r13d
0x14008216a  call    WPP_SF_d
0x14008216f  mov     ecx, r13d; Status
0x140082172  call    cs:__imp_RtlNtStatusToDosError
0x140082178  mov     ebx, eax
0x14008217a  jmp     loc_140082453
0x14008217f  mov     r12d, 1
0x140082185  cmp     [rbp+var_28], r12d
0x140082189  jnz     loc_1400822AE
0x14008218f  lea     rcx, [rsi+138h]
0x140082196  lea     rdx, [rbp+var_28]
0x14008219a  call    ?LockAutoExclusive@CScmLock@@QEAA?AVCScmSyncLockExclusive@@XZ; CScmLock::LockAutoExclusive(void)
0x14008219f  mov     r9, [rbp+TokenHandle]; void *
0x1400821a3  lea     rax, [rbp+var_20]
0x1400821a7  mov     r8, r14; void *
0x1400821aa  mov     [rsp+58h+Token], rax; void **
0x1400821af  mov     edx, r15d; unsigned int
0x1400821b2  mov     rcx, rsi; this
0x1400821b5  call    ?SetSecurityObject@CServiceRecord@@QEAAJKPEAX0PEAPEAX@Z; CServiceRecord::SetSecurityObject(ulong,void *,void *,void * *)
0x1400821ba  mov     ebx, eax
0x1400821bc  test    eax, eax
0x1400821be  jns     short loc_140082212
0x1400821c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400821c7  lea     rdx, WPP_GLOBAL_Control
0x1400821ce  cmp     rcx, rdx
0x1400821d1  jz      short loc_1400821F6
0x1400821d3  test    [rcx+1Ch], r12b
0x1400821d7  jz      short loc_1400821F6
0x1400821d9  mov     r9, [rsi+38h]
0x1400821dd  lea     edx, [r12+0Dh]
0x1400821e2  mov     rcx, [rcx+10h]
0x1400821e6  lea     r8, WPP_8f086be6c6f937952c5e847c48275da5_Traceguids
0x1400821ed  mov     dword ptr [rsp+58h+Token], eax
0x1400821f1  call    WPP_SF_Sd
0x1400821f6  mov     ecx, ebx; Status
0x1400821f8  call    cs:__imp_RtlNtStatusToDosError
0x1400821fe  mov     ebx, eax
0x140082200  lea     rcx, [rbp+var_28]; this
0x140082204  call    ?InternalUnlock@CScmSyncLockExclusive@@IEAAXXZ; CScmSyncLockExclusive::InternalUnlock(void)
0x140082209  mov     rdi, [rbp+var_20]
0x14008220d  jmp     loc_140082453
0x140082212  lea     r9, [rbp+hKey]; HKEY *
0x140082216  mov     edx, 20006h; unsigned int
0x14008221b  mov     rcx, rsi; this
0x14008221e  call    ?OpenServiceConfigKey@CServiceRecord@@QEAAKKHPEAPEAUHKEY__@@@Z; CServiceRecord::OpenServiceConfigKey(ulong,int,HKEY__ * *)
0x140082223  mov     ebx, eax
0x140082225  test    eax, eax
0x140082227  jz      short loc_140082274
0x140082229  mov     rcx, cs:WPP_GLOBAL_Control
0x140082230  lea     rdx, WPP_GLOBAL_Control
0x140082237  cmp     rcx, rdx
0x14008223a  jz      short loc_14008225F
0x14008223c  test    [rcx+1Ch], r12b
0x140082240  jz      short loc_14008225F
0x140082242  mov     edx, 0Fh
0x140082247  mov     r9, [rsi+38h]
0x14008224b  lea     r8, WPP_8f086be6c6f937952c5e847c48275da5_Traceguids
0x140082252  mov     rcx, [rcx+10h]
0x140082256  mov     dword ptr [rsp+58h+Token], eax
0x14008225a  call    WPP_SF_Sd
0x14008225f  mov     rdx, [rbp+var_20]; void *
0x140082263  mov     rcx, rsi; this
0x140082266  call    ?SetServiceSd@CServiceRecord@@QEAAKPEAXH@Z; CServiceRecord::SetServiceSd(void *,int)
0x14008226b  lea     rcx, [rbp+var_28]
0x14008226f  jmp     loc_14008244E
0x140082274  mov     rdx, [rsi+90h]; void *
0x14008227b  mov     rcx, [rbp+hKey]; HKEY
0x14008227f  call    ?ScWriteSd@@YAKPEAUHKEY__@@PEAX@Z; ScWriteSd(HKEY__ *,void *)
0x140082284  mov     ebx, eax
0x140082286  test    eax, eax
0x140082288  jz      loc_140082200
0x14008228e  mov     rcx, cs:WPP_GLOBAL_Control
0x140082295  lea     rdx, WPP_GLOBAL_Control
0x14008229c  cmp     rcx, rdx
0x14008229f  jz      short loc_14008225F
0x1400822a1  test    [rcx+1Ch], r12b
0x1400822a5  jz      short loc_14008225F
0x1400822a7  mov     edx, 10h
0x1400822ac  jmp     short loc_140082247
0x1400822ae  lea     rdx, [rbp+var_20]
0x1400822b2  lea     rcx, ?ScManagerSdLock@@3VCScmLock@@A; CScmLock ScManagerSdLock
0x1400822b9  call    ?LockAutoExclusive@CScmLock@@QEAA?AVCScmSyncLockExclusive@@XZ; CScmLock::LockAutoExclusive(void)
0x1400822be  mov     rcx, cs:?ScManagerSd@@3PEAXEA; SecurityDescriptor
0x1400822c5  test    rcx, rcx
0x1400822c8  jz      short loc_140082341
0x1400822ca  call    cs:__imp_RtlLengthSecurityDescriptor
0x1400822d0  test    eax, eax
0x1400822d2  jz      short loc_140082341
0x1400822d4  mov     rcx, gs:60h
0x1400822dd  mov     edx, ebx; Flags
0x1400822df  mov     r8d, eax; Size
0x1400822e2  mov     esi, eax
0x1400822e4  mov     rcx, [rcx+30h]; HeapHandle
0x1400822e8  call    cs:__imp_RtlAllocateHeap
0x1400822ee  mov     rdi, rax
0x1400822f1  test    rax, rax
0x1400822f4  jnz     short loc_14008232F
0x1400822f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400822fd  lea     rdx, WPP_GLOBAL_Control
0x140082304  cmp     rcx, rdx
0x140082307  jz      loc_14008244A
0x14008230d  test    [rcx+1Ch], r12b
0x140082311  jz      loc_14008244A
0x140082317  mov     rcx, [rcx+10h]
0x14008231b  lea     edx, [rax+11h]
0x14008231e  lea     r8, WPP_8f086be6c6f937952c5e847c48275da5_Traceguids
0x140082325  call    WPP_SF_
0x14008232a  jmp     loc_14008244A
0x14008232f  mov     rdx, cs:?ScManagerSd@@3PEAXEA; Src
0x140082336  mov     r8, rsi; Size
0x140082339  mov     rcx, rax; void *
0x14008233c  call    memmove
0x140082341  mov     rax, [rbp+TokenHandle]
0x140082345  lea     r9, stru_14009B9A8; GenericMapping
0x14008234c  lea     r8, ?ScManagerSd@@3PEAXEA; ObjectsSecurityDescriptor
0x140082353  mov     [rsp+58h+Token], rax; Token
0x140082358  mov     rdx, r14; ModificationDescriptor
0x14008235b  mov     ecx, r15d; SecurityInformation
0x14008235e  call    cs:__imp_RtlSetSecurityObject
0x140082364  mov     ebx, eax
0x140082366  test    eax, eax
0x140082368  jns     short loc_1400823AA
0x14008236a  mov     rcx, cs:WPP_GLOBAL_Control
0x140082371  lea     rdx, WPP_GLOBAL_Control
0x140082378  cmp     rcx, rdx
0x14008237b  jz      short loc_14008239B
0x14008237d  test    [rcx+1Ch], r12b
0x140082381  jz      short loc_14008239B
0x140082383  mov     rcx, [rcx+10h]
0x140082387  lea     r8, WPP_8f086be6c6f937952c5e847c48275da5_Traceguids
0x14008238e  mov     edx, 12h
0x140082393  mov     r9d, eax
0x140082396  call    WPP_SF_d
0x14008239b  mov     ecx, ebx; Status
0x14008239d  call    cs:__imp_RtlNtStatusToDosError
0x1400823a3  mov     ebx, eax
0x1400823a5  jmp     loc_14008244A
0x1400823aa  lea     rdx, [rbp+hKey]; HKEY *
0x1400823ae  mov     ecx, 20006h; unsigned int
0x1400823b3  call    ?ScOpenScManagerSecurityKey@@YAKKPEAPEAUHKEY__@@@Z; ScOpenScManagerSecurityKey(ulong,HKEY__ * *)
0x1400823b8  mov     ebx, eax
0x1400823ba  test    eax, eax
0x1400823bc  jz      short loc_1400823DE
0x1400823be  mov     rcx, cs:WPP_GLOBAL_Control
0x1400823c5  lea     rdx, WPP_GLOBAL_Control
0x1400823cc  cmp     rcx, rdx
0x1400823cf  jz      short loc_140082425
0x1400823d1  test    [rcx+1Ch], r12b
0x1400823d5  jz      short loc_140082425
0x1400823d7  mov     edx, 13h
0x1400823dc  jmp     short loc_140082412
  ... truncated ...
```
