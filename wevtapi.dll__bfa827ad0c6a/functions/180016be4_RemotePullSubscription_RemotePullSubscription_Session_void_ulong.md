# RemotePullSubscription::RemotePullSubscription(Session *,void *,ulong)

- ea: `0x180016be4`
- end: `0x18001703e`
- name: `??0RemotePullSubscription@@QEAA@PEAVSession@@PEAXK@Z`
- size: `1114`
- prototype: `RemotePullSubscription *__fastcall(PVOID pv, struct Session *, void *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800216c4`

## callees

- `0x1800158d4`
- `0x180016b88`
- `0x180016be4`
- `0x180022d64`
- `0x180023548`
- `0x180025514`
- `0x180038fa4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180016c62`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180016c8c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180016c62`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180016c8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016d46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016e42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016d46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016e42`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180016f55`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180016f55`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180016e1b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180016e1b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180016d0f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180016d18`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180016d0f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180016d18`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180016dd9`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180016dd9`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180016e08`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180016e08`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180016d3c`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180016d3c`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180016ec2`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180016ec2`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
RemotePullSubscription *__fastcall RemotePullSubscription::RemotePullSubscription(
        char *pv,
        struct Session *a2,
        char *a3,
        int a4)
{
  HANDLE *v7; // rdi
  HANDLE CurrentProcess; // rbx
  HANDLE v9; // rax
  DWORD LastError; // ebx
  struct _TP_CALLBACK_ENVIRON_V3 *v11; // rbx
  PTP_WAIT ThreadpoolWait; // rax
  struct _TP_WAIT *v13; // rcx
  DWORD v14; // ebx
  unsigned int v15; // eax
  unsigned int v16; // ebx
  void *v17; // rdx
  __int128 pExceptionObject; // [rsp+40h] [rbp-30h] BYREF
  __int64 v20; // [rsp+50h] [rbp-20h]
  int v21; // [rsp+58h] [rbp-18h]
  int v22; // [rsp+5Ch] [rbp-14h]
  int v23; // [rsp+60h] [rbp-10h]
  LPVOID Context; // [rsp+B8h] [rbp+48h] BYREF
  LPINIT_ONCE lpInitOnce; // [rsp+C0h] [rbp+50h] BYREF
  WINBOOL fPending; // [rsp+C8h] [rbp+58h] BYREF

  *(_QWORD *)pv = &wmi::RefBase::`vftable';
  *((_DWORD *)pv + 2) = 0;
  *((_QWORD *)pv + 2) = 0;
  *((_DWORD *)pv + 6) = 0;
  *((_WORD *)pv + 14) = 3;
  pv[30] = 1;
  *(_QWORD *)pv = &RemotePullSubscription::`vftable';
  *((_QWORD *)pv + 4) = a2;
  if ( a2 )
    _InterlockedIncrement((volatile signed __int32 *)a2 + 2);
  *((_QWORD *)pv + 5) = 0;
  *((_QWORD *)pv + 6) = 0;
  *((_QWORD *)pv + 7) = 0;
  memset_0(pv + 64, 0, 0x70u);
  *((_QWORD *)pv + 22) = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)pv + 23) = 0;
  *((_QWORD *)pv + 24) = 0;
  *((_QWORD *)pv + 25) = CreateEventW(0, 1, 1, 0);
  *((_QWORD *)pv + 26) = 0;
  *((_QWORD *)pv + 27) = 0;
  *((_DWORD *)pv + 56) = 0;
  pv[228] = 0;
  *((_DWORD *)pv + 66) = a4 | 0x10000000;
  *((_DWORD *)pv + 67) = 0;
  *((_WORD *)pv + 136) = 0;
  if ( (unsigned __int64)(a3 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_158a74e732e63b8ecd72ac50aa116150_Traceguids, 87);
    }
    pExceptionObject = 0;
    v20 = 0;
    v21 = 87;
    v22 = -1;
    v23 = 67;
    throw (EvtException *)&pExceptionObject;
  }
  if ( *((_QWORD *)pv + 25) == -1
    || *((_QWORD *)pv + 25) == 0
    || *((_QWORD *)pv + 22) == -1
    || *((_QWORD *)pv + 22) == 0 )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_158a74e732e63b8ecd72ac50aa116150_Traceguids, 6);
    }
    pExceptionObject = 0;
    v20 = 0;
    v21 = 6;
    v22 = -1;
    v23 = 75;
    throw (EvtException *)&pExceptionObject;
  }
  v7 = (HANDLE *)tlx::replace<tlx::file_handle_traits>(pv + 192);
  CurrentProcess = GetCurrentProcess();
  v9 = GetCurrentProcess();
  if ( !DuplicateHandle(v9, a3, CurrentProcess, v7, 0, 0, 2u) )
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 1287;
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_158a74e732e63b8ecd72ac50aa116150_Traceguids, LastError);
    }
    pExceptionObject = 0;
    v20 = 0;
    v21 = LastError;
    v22 = -1;
    v23 = 82;
    throw (EvtException *)&pExceptionObject;
  }
  fPending = 0;
  Context = 0;
  InitOnceBeginInitialize(&stru_18004B748, 0, &fPending, &Context);
  v11 = (struct _TP_CALLBACK_ENVIRON_V3 *)Context;
  if ( !Context )
  {
    lpInitOnce = &stru_18004B748;
    v11 = (struct _TP_CALLBACK_ENVIRON_V3 *)tlx::_LazyImpl<TpCallbackEnvironment,tlx::lazy_construct<TpCallbackEnvironment>,tlx::static_lazy<TpCallbackEnvironment,0,tlx::lazy_construct<TpCallbackEnvironment>>>::_Initializer::_Construct(&lpInitOnce);
    if ( lpInitOnce )
      InitOnceComplete(lpInitOnce, 4u, 0);
  }
  ThreadpoolWait = CreateThreadpoolWait(RemotePullSubscription::RpcServerNotificationTpCallback, pv, v11);
  v13 = (struct _TP_WAIT *)*((_QWORD *)pv + 23);
  *((_QWORD *)pv + 23) = ThreadpoolWait;
  if ( v13 )
    RemotePushSubscription::WaitAndCloseThreadpoolWait(v13);
  if ( !*((_QWORD *)pv + 23) )
  {
    v14 = GetLastError();
    if ( !v14 )
      v14 = 1287;
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_158a74e732e63b8ecd72ac50aa116150_Traceguids, v14);
    }
    pExceptionObject = 0;
    v20 = 0;
    v21 = v14;
    v22 = -1;
    v23 = 88;
    throw (EvtException *)&pExceptionObject;
  }
  v15 = RpcAsyncInitializeHandle((PRPC_ASYNC_STATE)(pv + 64), 0x70u);
  v16 = v15;
  if ( v15 )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_158a74e732e63b8ecd72ac50aa116150_Traceguids, v15);
    }
    pExceptionObject = 0;
    v20 = 0;
    v21 = v16;
    v22 = -1;
    v23 = 94;
    throw (EvtException *)&pExceptionObject;
  }
  *((_QWORD *)pv + 11) = pv;
  *((_DWORD *)pv + 27) = 1;
  v17 = (void *)*((_QWORD *)pv + 22);
  *((_QWORD *)pv + 14) = v17;
  SetThreadpoolWait(*((PTP_WAIT *)pv + 23), v17, 0);
  return (RemotePullSubscription *)pv;
}

```

## disassembly

```asm
0x180016be4  mov     [rsp-38h+arg_0], rcx
0x180016be9  push    rbp
0x180016bea  push    rbx
0x180016beb  push    rsi
0x180016bec  push    rdi
0x180016bed  push    r12
0x180016bef  push    r14
0x180016bf1  push    r15
0x180016bf3  mov     rbp, rsp
0x180016bf6  sub     rsp, 70h
0x180016bfa  mov     ebx, r9d
0x180016bfd  mov     r14, r8
0x180016c00  mov     rsi, rcx
0x180016c03  lea     rax, ??_7RefBase@wmi@@6B@; const wmi::RefBase::`vftable'
0x180016c0a  mov     [rcx], rax
0x180016c0d  xor     r12d, r12d
0x180016c10  mov     [rcx+8], r12d
0x180016c14  mov     [rcx+10h], r12
0x180016c18  mov     [rcx+18h], r12d
0x180016c1c  mov     word ptr [rcx+1Ch], 3
0x180016c22  mov     byte ptr [rcx+1Eh], 1
0x180016c26  lea     rax, ??_7RemotePullSubscription@@6B@; const RemotePullSubscription::`vftable'
0x180016c2d  mov     [rcx], rax
0x180016c30  mov     [rcx+20h], rdx
0x180016c34  test    rdx, rdx
0x180016c37  jz      short loc_180016C3D
0x180016c39  lock inc dword ptr [rdx+8]
0x180016c3d  mov     [rcx+28h], r12
0x180016c41  mov     [rcx+30h], r12
0x180016c45  mov     [rcx+38h], r12
0x180016c49  xor     edx, edx; Val
0x180016c4b  lea     r8d, [rdx+70h]; Size
0x180016c4f  add     rcx, 40h ; '@'; void *
0x180016c53  call    memset_0
0x180016c58  xor     r9d, r9d; lpName
0x180016c5b  xor     r8d, r8d; bInitialState
0x180016c5e  xor     edx, edx; bManualReset
0x180016c60  xor     ecx, ecx; lpEventAttributes
0x180016c62  call    cs:__imp_CreateEventW
0x180016c68  mov     [rsi+0B0h], rax
0x180016c6f  mov     [rsi+0B8h], r12
0x180016c76  lea     rdi, [rsi+0C0h]
0x180016c7d  mov     [rdi], r12
0x180016c80  xor     r9d, r9d; lpName
0x180016c83  lea     edx, [r9+1]; bManualReset
0x180016c87  xor     ecx, ecx; lpEventAttributes
0x180016c89  mov     r8d, edx; bInitialState
0x180016c8c  call    cs:__imp_CreateEventW
0x180016c92  mov     [rsi+0C8h], rax
0x180016c99  mov     [rsi+0D0h], r12
0x180016ca0  mov     [rsi+0D8h], r12
0x180016ca7  mov     [rsi+0E0h], r12d
0x180016cae  mov     [rsi+0E4h], r12b
0x180016cb5  bts     ebx, 1Ch
0x180016cb9  mov     [rsi+108h], ebx
0x180016cbf  mov     [rsi+10Ch], r12d
0x180016cc6  mov     [rsi+110h], r12w
0x180016cce  lea     rax, [r14-1]
0x180016cd2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180016cd6  ja      loc_180016FD6
0x180016cdc  mov     rax, [rsi+0C8h]
0x180016ce3  inc     rax
0x180016ce6  cmp     rax, 1
0x180016cea  jbe     loc_180016F6E
0x180016cf0  mov     rax, [rsi+0B0h]
0x180016cf7  inc     rax
0x180016cfa  cmp     rax, 1
0x180016cfe  jbe     loc_180016F6E
0x180016d04  mov     rcx, rdi
0x180016d07  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x180016d0c  mov     rdi, rax
0x180016d0f  call    cs:__imp_GetCurrentProcess
0x180016d15  mov     rbx, rax
0x180016d18  call    cs:__imp_GetCurrentProcess
0x180016d1e  mov     [rsp+70h+dwOptions], 2; dwOptions
0x180016d26  mov     [rsp+70h+bInheritHandle], r12d; bInheritHandle
0x180016d2b  mov     [rsp+70h+dwDesiredAccess], r12d; dwDesiredAccess
0x180016d30  mov     r9, rdi; lpTargetHandle
0x180016d33  mov     r8, rbx; hTargetProcessHandle
0x180016d36  mov     rdx, r14; hSourceHandle
0x180016d39  mov     rcx, rax; hSourceProcessHandle
0x180016d3c  call    cs:__imp_DuplicateHandle
0x180016d42  test    eax, eax
0x180016d44  jnz     short loc_180016DBD
0x180016d46  call    cs:__imp_GetLastError
0x180016d4c  mov     ebx, eax
0x180016d4e  mov     eax, 507h
0x180016d53  test    ebx, ebx
0x180016d55  cmovz   ebx, eax
0x180016d58  lea     rcx, WPP_GLOBAL_Control
0x180016d5f  mov     rax, cs:WPP_GLOBAL_Control
0x180016d66  cmp     rax, rcx
0x180016d69  jz      short loc_180016D8F
0x180016d6b  test    byte ptr [rax+1Ch], 80h
0x180016d6f  jz      short loc_180016D8F
0x180016d71  cmp     byte ptr [rax+19h], 2
0x180016d75  jb      short loc_180016D8F
0x180016d77  mov     edx, 0Ch
0x180016d7c  mov     r9d, ebx
0x180016d7f  lea     r8, WPP_158a74e732e63b8ecd72ac50aa116150_Traceguids
0x180016d86  mov     rcx, [rax+10h]
0x180016d8a  call    WPP_SF_D
0x180016d8f  xorps   xmm0, xmm0
0x180016d92  movdqu  [rbp+pExceptionObject], xmm0
0x180016d97  mov     [rbp+var_20], r12
0x180016d9b  mov     [rbp+var_18], ebx
0x180016d9e  mov     [rbp+var_14], 0FFFFFFFFh
0x180016da5  mov     [rbp+var_10], 52h ; 'R'
0x180016dac  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180016db3  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180016db7  call    _CxxThrowException_0
0x180016dbd  mov     [rbp+fPending], r12d
0x180016dc1  mov     [rbp+Context], r12
0x180016dc5  lea     r9, [rbp+Context]; lpContext
0x180016dc9  lea     r8, [rbp+fPending]; fPending
0x180016dcd  xor     edx, edx; dwFlags
0x180016dcf  lea     rdi, stru_18004B748
0x180016dd6  mov     rcx, rdi; lpInitOnce
0x180016dd9  call    cs:__imp_InitOnceBeginInitialize
0x180016ddf  mov     rbx, [rbp+Context]
0x180016de3  test    rbx, rbx
0x180016de6  jnz     short loc_180016E0E
0x180016de8  mov     [rbp+lpInitOnce], rdi
0x180016dec  lea     rcx, [rbp+lpInitOnce]
0x180016df0  call    ?_Construct@_Initializer@?$_LazyImpl@UTpCallbackEnvironment@@V?$lazy_construct@UTpCallbackEnvironment@@@tlx@@V?$static_lazy@UTpCallbackEnvironment@@$0A@V?$lazy_construct@UTpCallbackEnvironment@@@tlx@@@3@@tlx@@QEAAPEAXXZ; tlx::_LazyImpl<TpCallbackEnvironment,tlx::lazy_construct<TpCallbackEnvironment>,tlx::static_lazy<TpCallbackEnvironment,0,tlx::lazy_construct<TpCallbackEnvironment>>>::_Initializer::_Construct(void)
0x180016df5  mov     rbx, rax
0x180016df8  mov     rcx, [rbp+lpInitOnce]; lpInitOnce
0x180016dfc  test    rcx, rcx
0x180016dff  jz      short loc_180016E0E
0x180016e01  xor     r8d, r8d; lpContext
0x180016e04  lea     edx, [r8+4]; dwFlags
0x180016e08  call    cs:__imp_InitOnceComplete
0x180016e0e  mov     r8, rbx; pcbe
0x180016e11  mov     rdx, rsi; pv
0x180016e14  lea     rcx, ?RpcServerNotificationTpCallback@RemotePullSubscription@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x180016e1b  call    cs:__imp_CreateThreadpoolWait
0x180016e21  mov     rcx, [rsi+0B8h]; pwa
0x180016e28  mov     [rsi+0B8h], rax
0x180016e2f  test    rcx, rcx
0x180016e32  jz      short loc_180016E39
0x180016e34  call    ?WaitAndCloseThreadpoolWait@RemotePushSubscription@@CAXPEAU_TP_WAIT@@@Z; RemotePushSubscription::WaitAndCloseThreadpoolWait(_TP_WAIT *)
0x180016e39  cmp     [rsi+0B8h], r12
0x180016e40  jnz     short loc_180016EB9
0x180016e42  call    cs:__imp_GetLastError
0x180016e48  mov     ebx, eax
0x180016e4a  mov     eax, 507h
0x180016e4f  test    ebx, ebx
0x180016e51  cmovz   ebx, eax
0x180016e54  lea     rcx, WPP_GLOBAL_Control
0x180016e5b  mov     rax, cs:WPP_GLOBAL_Control
0x180016e62  cmp     rax, rcx
0x180016e65  jz      short loc_180016E8B
0x180016e67  test    byte ptr [rax+1Ch], 80h
0x180016e6b  jz      short loc_180016E8B
0x180016e6d  cmp     byte ptr [rax+19h], 2
0x180016e71  jb      short loc_180016E8B
0x180016e73  mov     edx, 0Dh
0x180016e78  mov     r9d, ebx
0x180016e7b  lea     r8, WPP_158a74e732e63b8ecd72ac50aa116150_Traceguids
0x180016e82  mov     rcx, [rax+10h]
0x180016e86  call    WPP_SF_D
0x180016e8b  xorps   xmm0, xmm0
0x180016e8e  movdqu  [rbp+pExceptionObject], xmm0
0x180016e93  mov     [rbp+var_20], r12
0x180016e97  mov     [rbp+var_18], ebx
0x180016e9a  mov     [rbp+var_14], 0FFFFFFFFh
0x180016ea1  mov     [rbp+var_10], 58h ; 'X'
0x180016ea8  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180016eaf  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180016eb3  call    _CxxThrowException_0
0x180016eb9  mov     edx, 70h ; 'p'; Size
0x180016ebe  lea     rcx, [rsi+40h]; pAsync
0x180016ec2  call    cs:__imp_RpcAsyncInitializeHandle
0x180016ec8  mov     ebx, eax
0x180016eca  test    eax, eax
0x180016ecc  jz      short loc_180016F35
0x180016ece  lea     rcx, WPP_GLOBAL_Control
0x180016ed5  mov     r10, cs:WPP_GLOBAL_Control
0x180016edc  cmp     r10, rcx
0x180016edf  jz      short loc_180016F07
0x180016ee1  test    byte ptr [r10+1Ch], 80h
0x180016ee6  jz      short loc_180016F07
0x180016ee8  cmp     byte ptr [r10+19h], 2
0x180016eed  jb      short loc_180016F07
0x180016eef  mov     edx, 0Eh
0x180016ef4  mov     r9d, eax
0x180016ef7  lea     r8, WPP_158a74e732e63b8ecd72ac50aa116150_Traceguids
0x180016efe  mov     rcx, [r10+10h]
0x180016f02  call    WPP_SF_D
0x180016f07  xorps   xmm0, xmm0
0x180016f0a  movdqu  [rbp+pExceptionObject], xmm0
0x180016f0f  mov     [rbp+var_20], r12
0x180016f13  mov     [rbp+var_18], ebx
0x180016f16  mov     [rbp+var_14], 0FFFFFFFFh
0x180016f1d  mov     [rbp+var_10], 5Eh ; '^'
0x180016f24  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180016f2b  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180016f2f  call    _CxxThrowException_0
0x180016f35  mov     [rsi+58h], rsi
0x180016f39  mov     dword ptr [rsi+6Ch], 1
0x180016f40  mov     rdx, [rsi+0B0h]; h
0x180016f47  mov     [rsi+70h], rdx
0x180016f4b  xor     r8d, r8d; pftTimeout
0x180016f4e  mov     rcx, [rsi+0B8h]; pwa
0x180016f55  call    cs:__imp_SetThreadpoolWait
0x180016f5b  nop
0x180016f5c  mov     rax, rsi
0x180016f5f  add     rsp, 70h
0x180016f63  pop     r15
0x180016f65  pop     r14
0x180016f67  pop     r12
0x180016f69  pop     rdi
0x180016f6a  pop     rsi
0x180016f6b  pop     rbx
0x180016f6c  pop     rbp
0x180016f6d  retn
0x180016f6e  lea     rcx, WPP_GLOBAL_Control
0x180016f75  mov     ebx, 6
0x180016f7a  mov     rax, cs:WPP_GLOBAL_Control
0x180016f81  cmp     rax, rcx
0x180016f84  jz      short loc_180016FA8
0x180016f86  test    byte ptr [rax+1Ch], 80h
0x180016f8a  jz      short loc_180016FA8
0x180016f8c  cmp     byte ptr [rax+19h], 2
0x180016f90  jb      short loc_180016FA8
0x180016f92  lea     edx, [rbx+5]
0x180016f95  mov     r9d, ebx
0x180016f98  lea     r8, WPP_158a74e732e63b8ecd72ac50aa116150_Traceguids
0x180016f9f  mov     rcx, [rax+10h]
0x180016fa3  call    WPP_SF_D
0x180016fa8  xorps   xmm0, xmm0
0x180016fab  movdqu  [rbp+pExceptionObject], xmm0
0x180016fb0  mov     [rbp+var_20], r12
0x180016fb4  mov     [rbp+var_18], ebx
0x180016fb7  mov     [rbp+var_14], 0FFFFFFFFh
0x180016fbe  mov     [rbp+var_10], 4Bh ; 'K'
0x180016fc5  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180016fcc  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180016fd0  call    _CxxThrowException_0
0x180016fd6  lea     rcx, WPP_GLOBAL_Control
0x180016fdd  mov     ebx, 57h ; 'W'
0x180016fe2  mov     rax, cs:WPP_GLOBAL_Control
0x180016fe9  cmp     rax, rcx
0x180016fec  jz      short loc_180017010
0x180016fee  test    byte ptr [rax+1Ch], 80h
0x180016ff2  jz      short loc_180017010
0x180016ff4  cmp     byte ptr [rax+19h], 2
0x180016ff8  jb      short loc_180017010
0x180016ffa  lea     edx, [rbx-4Dh]
0x180016ffd  mov     r9d, ebx
0x180017000  lea     r8, WPP_158a74e732e63b8ecd72ac50aa116150_Traceguids
0x180017007  mov     rcx, [rax+10h]
0x18001700b  call    WPP_SF_D
0x180017010  xorps   xmm0, xmm0
0x180017013  movdqu  [rbp+pExceptionObject], xmm0
0x180017018  mov     [rbp+var_20], r12
0x18001701c  mov     [rbp+var_18], ebx
0x18001701f  mov     [rbp+var_14], 0FFFFFFFFh
0x180017026  mov     [rbp+var_10], 43h ; 'C'
0x18001702d  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180017034  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180017038  call    _CxxThrowException_0
```
