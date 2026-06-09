# RemotePushSubscription::RemotePushSubscription(Session *,ulong (*)(_EVT_SUBSCRIBE_NOTIFY_ACTION,void *,void *),void *,ulong)

- ea: `0x180015084`
- end: `0x180015499`
- name: `??0RemotePushSubscription@@QEAA@PEAVSession@@P6AKW4_EVT_SUBSCRIBE_NOTIFY_ACTION@@PEAX2@Z2K@Z`
- size: `1045`
- prototype: `RemotePushSubscription *__usercall@<rax>(PVOID pv@<rcx>, struct Session *@<rdx>, unsigned int (*)(enum _EVT_SUBSCRIBE_NOTIFY_ACTION, void *, void *)@<r8>, void *@<r9>, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180021140`

## callees

- `0x18000a020`
- `0x180015084`
- `0x1800158d4`
- `0x180015f0c`
- `0x180016b88`
- `0x180023548`
- `0x180025514`
- `0x180038fa4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800150ee`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180015108`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800150ee`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180015108`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015355`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015355`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800152ac`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800152ac`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180015254`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180015254`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001521b`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001521b`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001534a`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001534a`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18001527f`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18001527f`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
RemotePushSubscription *__fastcall RemotePushSubscription::RemotePushSubscription(
        char *pv,
        struct Session *a2,
        unsigned int (*a3)(enum _EVT_SUBSCRIBE_NOTIFY_ACTION, void *, void *),
        void *a4,
        WINBOOL fPending)
{
  void *v7; // rax
  Event *v8; // rax
  struct _TP_CALLBACK_ENVIRON_V3 *v9; // rdi
  PTP_WAIT ThreadpoolWait; // rax
  struct _TP_WAIT *v11; // rcx
  unsigned int v12; // edi
  void *v13; // rdx
  DWORD LastError; // ebx
  __int128 pExceptionObject; // [rsp+20h] [rbp-30h] BYREF
  __int64 v17; // [rsp+30h] [rbp-20h]
  int v18; // [rsp+38h] [rbp-18h]
  int v19; // [rsp+3Ch] [rbp-14h]
  int v20; // [rsp+40h] [rbp-10h]
  LPVOID Context; // [rsp+88h] [rbp+38h] BYREF
  LPINIT_ONCE lpInitOnce; // [rsp+90h] [rbp+40h] BYREF

  *(_QWORD *)pv = &wmi::RefBase::`vftable';
  *((_DWORD *)pv + 2) = 0;
  *((_QWORD *)pv + 2) = 0;
  *((_DWORD *)pv + 6) = 0;
  *((_WORD *)pv + 14) = 2;
  pv[30] = 1;
  *(_QWORD *)pv = &RemotePushSubscription::`vftable';
  *((_QWORD *)pv + 4) = a3;
  *((_QWORD *)pv + 5) = a4;
  *((_QWORD *)pv + 6) = a2;
  if ( a2 )
    _InterlockedIncrement((volatile signed __int32 *)a2 + 2);
  *((_QWORD *)pv + 7) = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)pv + 8) = 0;
  *((_QWORD *)pv + 9) = CreateEventW(0, 1, 1, 0);
  memset_0(pv + 80, 0, 0x70u);
  v7 = operator new(0x90u);
  Context = v7;
  if ( v7 )
    v8 = Event::Event((Event *)v7);
  else
    v8 = 0;
  *((_QWORD *)pv + 24) = v8;
  if ( v8 )
    _InterlockedIncrement((volatile signed __int32 *)v8 + 2);
  *((_QWORD *)pv + 25) = 0;
  *((_QWORD *)pv + 26) = 0;
  *((_QWORD *)pv + 27) = 0;
  *((_QWORD *)pv + 28) = 0;
  *((_QWORD *)pv + 29) = 0;
  *((_QWORD *)pv + 30) = 0;
  *((_QWORD *)pv + 31) = 0;
  *((_QWORD *)pv + 32) = 0;
  *((_QWORD *)pv + 33) = 0;
  *((_QWORD *)pv + 34) = 0;
  *((_QWORD *)pv + 35) = 0;
  *((_DWORD *)pv + 72) = 0;
  pv[292] = 0;
  *((_DWORD *)pv + 82) = fPending & 0xEFFFFFFF;
  *(_QWORD *)(pv + 332) = 10;
  *((_DWORD *)pv + 85) = 0;
  *((_WORD *)pv + 172) = 0;
  if ( !a3 )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_ace92e4ac21938b1819d9fbab7cc40fd_Traceguids, 87);
    }
    pExceptionObject = 0;
    v17 = 0;
    v18 = 87;
    v19 = -1;
    v20 = 68;
    throw (EvtException *)&pExceptionObject;
  }
  if ( *((_QWORD *)pv + 9) == -1 || *((_QWORD *)pv + 9) == 0 || *((_QWORD *)pv + 7) == -1 || *((_QWORD *)pv + 7) == 0 )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_ace92e4ac21938b1819d9fbab7cc40fd_Traceguids, 6);
    }
    pExceptionObject = 0;
    v17 = 0;
    v18 = 6;
    v19 = -1;
    v20 = 74;
    throw (EvtException *)&pExceptionObject;
  }
  fPending = 0;
  Context = 0;
  InitOnceBeginInitialize(&InitOnce, 0, &fPending, &Context);
  v9 = (struct _TP_CALLBACK_ENVIRON_V3 *)Context;
  if ( !Context )
  {
    lpInitOnce = &InitOnce;
    v9 = (struct _TP_CALLBACK_ENVIRON_V3 *)tlx::_LazyImpl<TpCallbackEnvironment,tlx::lazy_construct<TpCallbackEnvironment>,tlx::static_lazy<TpCallbackEnvironment,0,tlx::lazy_construct<TpCallbackEnvironment>>>::_Initializer::_Construct(&lpInitOnce);
    if ( lpInitOnce )
      InitOnceComplete(lpInitOnce, 4u, 0);
  }
  ThreadpoolWait = CreateThreadpoolWait(
                     (PTP_WAIT_CALLBACK)RemotePushSubscription::RpcServerNotificationTpCallback,
                     pv,
                     v9);
  v11 = (struct _TP_WAIT *)*((_QWORD *)pv + 8);
  *((_QWORD *)pv + 8) = ThreadpoolWait;
  if ( v11 )
    RemotePushSubscription::WaitAndCloseThreadpoolWait(v11);
  if ( !*((_QWORD *)pv + 8) )
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 1287;
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_ace92e4ac21938b1819d9fbab7cc40fd_Traceguids, LastError);
    }
    pExceptionObject = 0;
    v17 = 0;
    v18 = LastError;
    v19 = -1;
    v20 = 80;
    throw (EvtException *)&pExceptionObject;
  }
  v12 = RpcAsyncInitializeHandle((PRPC_ASYNC_STATE)(pv + 80), 0x70u);
  if ( v12 )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_ace92e4ac21938b1819d9fbab7cc40fd_Traceguids, v12);
    }
    pExceptionObject = 0;
    v17 = 0;
    v18 = v12;
    v19 = -1;
    v20 = 87;
    throw (EvtException *)&pExceptionObject;
  }
  *((_QWORD *)pv + 13) = pv;
  *((_DWORD *)pv + 31) = 1;
  v13 = (void *)*((_QWORD *)pv + 7);
  *((_QWORD *)pv + 16) = v13;
  SetThreadpoolWait(*((PTP_WAIT *)pv + 8), v13, 0);
  *(_BYTE *)(*((_QWORD *)pv + 24) + 30LL) = 0;
  return (RemotePushSubscription *)pv;
}

```

## disassembly

```asm
0x180015084  mov     [rsp-28h+arg_18], rbx
0x180015089  mov     [rsp-28h+arg_0], rcx
0x18001508e  push    rbp
0x18001508f  push    rsi
0x180015090  push    rdi
0x180015091  push    r13
0x180015093  push    r14
0x180015095  mov     rbp, rsp
0x180015098  sub     rsp, 50h
0x18001509c  mov     rdi, r8
0x18001509f  mov     rbx, rcx
0x1800150a2  lea     rax, ??_7RefBase@wmi@@6B@; const wmi::RefBase::`vftable'
0x1800150a9  mov     [rcx], rax
0x1800150ac  xor     r14d, r14d
0x1800150af  mov     [rcx+8], r14d
0x1800150b3  mov     [rcx+10h], r14
0x1800150b7  mov     [rcx+18h], r14d
0x1800150bb  mov     word ptr [rcx+1Ch], 2
0x1800150c1  mov     byte ptr [rcx+1Eh], 1
0x1800150c5  lea     rax, ??_7RemotePushSubscription@@6B@; const RemotePushSubscription::`vftable'
0x1800150cc  mov     [rcx], rax
0x1800150cf  mov     [rcx+20h], r8
0x1800150d3  mov     [rcx+28h], r9
0x1800150d7  mov     [rcx+30h], rdx
0x1800150db  test    rdx, rdx
0x1800150de  jz      short loc_1800150E4
0x1800150e0  lock inc dword ptr [rdx+8]
0x1800150e4  xor     r9d, r9d; lpName
0x1800150e7  xor     r8d, r8d; bInitialState
0x1800150ea  xor     edx, edx; bManualReset
0x1800150ec  xor     ecx, ecx; lpEventAttributes
0x1800150ee  call    cs:__imp_CreateEventW
0x1800150f4  mov     [rbx+38h], rax
0x1800150f8  mov     [rbx+40h], r14
0x1800150fc  xor     r9d, r9d; lpName
0x1800150ff  lea     edx, [r9+1]; bManualReset
0x180015103  xor     ecx, ecx; lpEventAttributes
0x180015105  mov     r8d, edx; bInitialState
0x180015108  call    cs:__imp_CreateEventW
0x18001510e  mov     [rbx+48h], rax
0x180015112  xor     edx, edx; Val
0x180015114  lea     r8d, [rdx+70h]; Size
0x180015118  lea     rcx, [rbx+50h]; void *
0x18001511c  call    memset_0
0x180015121  mov     ecx, 90h; dwBytes
0x180015126  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001512b  mov     [rbp+Context], rax
0x18001512f  test    rax, rax
0x180015132  jz      loc_1800152D4
0x180015138  mov     rcx, rax; this
0x18001513b  call    ??0Event@@QEAA@XZ; Event::Event(void)
0x180015140  nop
0x180015141  mov     [rbx+0C0h], rax
0x180015148  test    rax, rax
0x18001514b  jz      short loc_180015151
0x18001514d  lock inc dword ptr [rax+8]
0x180015151  mov     [rbx+0C8h], r14
0x180015158  mov     [rbx+0D0h], r14
0x18001515f  mov     [rbx+0D8h], r14
0x180015166  mov     [rbx+0E0h], r14
0x18001516d  mov     [rbx+0E8h], r14
0x180015174  mov     [rbx+0F0h], r14
0x18001517b  mov     [rbx+0F8h], r14
0x180015182  mov     [rbx+100h], r14
0x180015189  mov     [rbx+108h], r14
0x180015190  mov     [rbx+110h], r14
0x180015197  mov     [rbx+118h], r14
0x18001519e  mov     [rbx+120h], r14d
0x1800151a5  mov     [rbx+124h], r14b
0x1800151ac  mov     eax, [rbp+fPending]
0x1800151af  btr     eax, 1Ch
0x1800151b3  mov     [rbx+148h], eax
0x1800151b9  mov     edx, 0Ah
0x1800151be  mov     [rbx+14Ch], rdx
0x1800151c5  mov     [rbx+154h], r14d
0x1800151cc  mov     [rbx+158h], r14w
0x1800151d4  test    rdi, rdi
0x1800151d7  jz      loc_1800152DC
0x1800151dd  mov     rax, [rbx+48h]
0x1800151e1  inc     rax
0x1800151e4  cmp     rax, 1
0x1800151e8  jbe     loc_180015431
0x1800151ee  mov     rax, [rbx+38h]
0x1800151f2  inc     rax
0x1800151f5  cmp     rax, 1
0x1800151f9  jbe     loc_180015431
0x1800151ff  mov     [rbp+fPending], r14d
0x180015203  mov     [rbp+Context], r14
0x180015207  lea     r9, [rbp+Context]; lpContext
0x18001520b  lea     r8, [rbp+fPending]; fPending
0x18001520f  xor     edx, edx; dwFlags
0x180015211  lea     r13, InitOnce
0x180015218  mov     rcx, r13; lpInitOnce
0x18001521b  call    cs:__imp_InitOnceBeginInitialize
0x180015221  mov     rdi, [rbp+Context]
0x180015225  test    rdi, rdi
0x180015228  jnz     short loc_180015247
0x18001522a  mov     [rbp+lpInitOnce], r13
0x18001522e  lea     rcx, [rbp+lpInitOnce]
0x180015232  call    ?_Construct@_Initializer@?$_LazyImpl@UTpCallbackEnvironment@@V?$lazy_construct@UTpCallbackEnvironment@@@tlx@@V?$static_lazy@UTpCallbackEnvironment@@$0A@V?$lazy_construct@UTpCallbackEnvironment@@@tlx@@@3@@tlx@@QEAAPEAXXZ; tlx::_LazyImpl<TpCallbackEnvironment,tlx::lazy_construct<TpCallbackEnvironment>,tlx::static_lazy<TpCallbackEnvironment,0,tlx::lazy_construct<TpCallbackEnvironment>>>::_Initializer::_Construct(void)
0x180015237  mov     rdi, rax
0x18001523a  mov     rcx, [rbp+lpInitOnce]; lpInitOnce
0x18001523e  test    rcx, rcx
0x180015241  jnz     loc_180015343
0x180015247  mov     r8, rdi; pcbe
0x18001524a  mov     rdx, rbx; pv
0x18001524d  lea     rcx, ?RpcServerNotificationTpCallback@RemotePushSubscription@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x180015254  call    cs:__imp_CreateThreadpoolWait
0x18001525a  mov     rcx, [rbx+40h]; pwa
0x18001525e  mov     [rbx+40h], rax
0x180015262  test    rcx, rcx
0x180015265  jz      short loc_18001526C
0x180015267  call    ?WaitAndCloseThreadpoolWait@RemotePushSubscription@@CAXPEAU_TP_WAIT@@@Z; RemotePushSubscription::WaitAndCloseThreadpoolWait(_TP_WAIT *)
0x18001526c  cmp     [rbx+40h], r14
0x180015270  jz      loc_180015355
0x180015276  mov     edx, 70h ; 'p'; Size
0x18001527b  lea     rcx, [rbx+50h]; pAsync
0x18001527f  call    cs:__imp_RpcAsyncInitializeHandle
0x180015285  mov     edi, eax
0x180015287  test    eax, eax
0x180015289  jnz     loc_1800153CC
0x18001528f  mov     [rbx+68h], rbx
0x180015293  mov     dword ptr [rbx+7Ch], 1
0x18001529a  mov     rdx, [rbx+38h]; h
0x18001529e  mov     [rbx+80h], rdx
0x1800152a5  xor     r8d, r8d; pftTimeout
0x1800152a8  mov     rcx, [rbx+40h]; pwa
0x1800152ac  call    cs:__imp_SetThreadpoolWait
0x1800152b2  mov     rax, [rbx+0C0h]
0x1800152b9  mov     [rax+1Eh], r14b
0x1800152bd  mov     rax, rbx
0x1800152c0  mov     rbx, [rsp+50h+arg_18]
0x1800152c8  add     rsp, 50h
0x1800152cc  pop     r14
0x1800152ce  pop     r13
0x1800152d0  pop     rdi
0x1800152d1  pop     rsi
0x1800152d2  pop     rbp
0x1800152d3  retn
0x1800152d4  mov     rax, r14
0x1800152d7  jmp     loc_180015141
0x1800152dc  lea     rax, WPP_GLOBAL_Control
0x1800152e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800152ea  cmp     rcx, rax
0x1800152ed  jz      short loc_180015311
0x1800152ef  test    byte ptr [rcx+1Ch], 40h
0x1800152f3  jz      short loc_180015311
0x1800152f5  cmp     byte ptr [rcx+19h], 2
0x1800152f9  jb      short loc_180015311
0x1800152fb  mov     r9d, 57h ; 'W'
0x180015301  lea     r8, WPP_ace92e4ac21938b1819d9fbab7cc40fd_Traceguids
0x180015308  mov     rcx, [rcx+10h]
0x18001530c  call    WPP_SF_D
0x180015311  xorps   xmm0, xmm0
0x180015314  movdqu  [rbp+pExceptionObject], xmm0
0x180015319  mov     [rbp+var_20], r14
0x18001531d  mov     [rbp+var_18], 57h ; 'W'
0x180015324  mov     [rbp+var_14], 0FFFFFFFFh
0x18001532b  mov     [rbp+var_10], 44h ; 'D'
0x180015332  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180015339  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001533d  call    _CxxThrowException_0
0x180015343  xor     r8d, r8d; lpContext
0x180015346  lea     edx, [r8+4]; dwFlags
0x18001534a  call    cs:__imp_InitOnceComplete
0x180015350  jmp     loc_180015247
0x180015355  call    cs:__imp_GetLastError
0x18001535b  mov     ebx, eax
0x18001535d  mov     eax, 507h
0x180015362  test    ebx, ebx
0x180015364  cmovz   ebx, eax
0x180015367  lea     rax, WPP_GLOBAL_Control
0x18001536e  mov     rcx, cs:WPP_GLOBAL_Control
0x180015375  cmp     rcx, rax
0x180015378  jz      short loc_18001539E
0x18001537a  test    byte ptr [rcx+1Ch], 40h
0x18001537e  jz      short loc_18001539E
0x180015380  cmp     byte ptr [rcx+19h], 2
0x180015384  jb      short loc_18001539E
0x180015386  mov     edx, 0Ch
0x18001538b  mov     r9d, ebx
0x18001538e  lea     r8, WPP_ace92e4ac21938b1819d9fbab7cc40fd_Traceguids
0x180015395  mov     rcx, [rcx+10h]
0x180015399  call    WPP_SF_D
0x18001539e  xorps   xmm0, xmm0
0x1800153a1  movdqu  [rbp+pExceptionObject], xmm0
0x1800153a6  mov     [rbp+var_20], r14
0x1800153aa  mov     [rbp+var_18], ebx
0x1800153ad  mov     [rbp+var_14], 0FFFFFFFFh
0x1800153b4  mov     [rbp+var_10], 50h ; 'P'
0x1800153bb  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800153c2  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800153c6  call    _CxxThrowException_0
0x1800153cc  lea     rax, WPP_GLOBAL_Control
0x1800153d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800153da  cmp     rcx, rax
0x1800153dd  jz      short loc_180015403
0x1800153df  test    byte ptr [rcx+1Ch], 40h
0x1800153e3  jz      short loc_180015403
0x1800153e5  cmp     byte ptr [rcx+19h], 2
0x1800153e9  jb      short loc_180015403
0x1800153eb  mov     edx, 0Dh
0x1800153f0  mov     r9d, edi
0x1800153f3  lea     r8, WPP_ace92e4ac21938b1819d9fbab7cc40fd_Traceguids
0x1800153fa  mov     rcx, [rcx+10h]
0x1800153fe  call    WPP_SF_D
0x180015403  xorps   xmm0, xmm0
0x180015406  movdqu  [rbp+pExceptionObject], xmm0
0x18001540b  mov     [rbp+var_20], r14
0x18001540f  mov     [rbp+var_18], edi
0x180015412  mov     [rbp+var_14], 0FFFFFFFFh
0x180015419  mov     [rbp+var_10], 57h ; 'W'
0x180015420  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180015427  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001542b  call    _CxxThrowException_0
0x180015431  lea     rax, WPP_GLOBAL_Control
0x180015438  mov     ebx, 6
0x18001543d  mov     rcx, cs:WPP_GLOBAL_Control
0x180015444  cmp     rcx, rax
0x180015447  jz      short loc_18001546B
0x180015449  test    byte ptr [rcx+1Ch], 40h
0x18001544d  jz      short loc_18001546B
0x18001544f  cmp     byte ptr [rcx+19h], 2
0x180015453  jb      short loc_18001546B
0x180015455  lea     edx, [rbx+5]
0x180015458  mov     r9d, ebx
0x18001545b  lea     r8, WPP_ace92e4ac21938b1819d9fbab7cc40fd_Traceguids
0x180015462  mov     rcx, [rcx+10h]
0x180015466  call    WPP_SF_D
0x18001546b  xorps   xmm0, xmm0
0x18001546e  movdqu  [rbp+pExceptionObject], xmm0
0x180015473  mov     [rbp+var_20], r14
0x180015477  mov     [rbp+var_18], ebx
0x18001547a  mov     [rbp+var_14], 0FFFFFFFFh
0x180015481  mov     [rbp+var_10], 4Ah ; 'J'
0x180015488  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18001548f  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180015493  call    _CxxThrowException_0
```
