# SocketTransport::InternalAccept(std::shared_ptr<TransportIoContext> const &)

- ea: `0x1400606c0`
- end: `0x140060c0b`
- name: `?InternalAccept@SocketTransport@@AEAAXAEBV?$shared_ptr@VTransportIoContext@@@std@@@Z`
- size: `1355`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x140060180`

## callees

- `0x140005360`
- `0x140006098`
- `0x14000ddac`
- `0x14000f93c`
- `0x1400341ac`
- `0x14005de58`
- `0x14005efac`
- `0x14005f2e4`
- `0x14005f850`
- `0x140060248`
- `0x1400606c0`
- `0x140061454`
- `0x140062518`
- `0x1400fe010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14006079b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14006079b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14006075a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14006075a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140060812`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14006094e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400609a3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400609ef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140060812`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14006094e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400609a3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400609ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400607ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006093b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140060990`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400609dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140060a6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400607ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006093b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140060990`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400609dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140060a6e`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x140060a08`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x140060a08`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x14006092a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x1400609c7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x14006092a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x1400609c7`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x140060aee`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x140060aee`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x140060946`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x1400609e7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x140060946`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x1400609e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140060760`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140060760`
- `WS2_32!WSASocketW` at `0x1400607ec`
- `WS2_32!WSASocketW` at `0x14006097d`
- `WS2_32!WSASocketW` at `0x1400607ec`
- `WS2_32!WSASocketW` at `0x14006097d`
- `WS2_32!__imp_bind` at `0x1400608ec`
- `WS2_32!__imp_bind` at `0x1400608ec`
- `WS2_32!__imp_closesocket` at `0x14006080a`
- `WS2_32!__imp_closesocket` at `0x14006099b`
- `WS2_32!__imp_closesocket` at `0x14006080a`
- `WS2_32!__imp_closesocket` at `0x14006099b`
- `WS2_32!__imp_htons` at `0x1400608d7`
- `WS2_32!__imp_htons` at `0x1400608d7`
- `WS2_32!__imp_listen` at `0x140060904`
- `WS2_32!__imp_listen` at `0x140060904`
- `WS2_32!__imp_setsockopt` at `0x140060853`
- `WS2_32!__imp_setsockopt` at `0x140060853`
- `WS2_32!__imp_WSAGetLastError` at `0x140060b2f`
- `WS2_32!__imp_WSAGetLastError` at `0x140060b51`
- `WS2_32!__imp_WSAGetLastError` at `0x140060b73`
- `WS2_32!__imp_WSAGetLastError` at `0x140060b95`
- `WS2_32!__imp_WSAGetLastError` at `0x140060bd0`
- `WS2_32!__imp_WSAGetLastError` at `0x140060b2f`
- `WS2_32!__imp_WSAGetLastError` at `0x140060b51`
- `WS2_32!__imp_WSAGetLastError` at `0x140060b73`
- `WS2_32!__imp_WSAGetLastError` at `0x140060b95`
- `WS2_32!__imp_WSAGetLastError` at `0x140060bd0`

## string_xrefs

- `0x140060afe`: `onecore\vm\compute\common\transport\sockettransport.cpp`
- `0x140060b1d`: `onecore\vm\compute\common\transport\sockettransport.cpp`
- `0x140060b3f`: `onecore\vm\compute\common\transport\sockettransport.cpp`
- `0x140060b61`: `onecore\vm\compute\common\transport\sockettransport.cpp`
- `0x140060b83`: `onecore\vm\compute\common\transport\sockettransport.cpp`
- `0x140060ba5`: `onecore\vm\compute\common\transport\sockettransport.cpp`
- `0x140060bbe`: `onecore\vm\compute\common\transport\sockettransport.cpp`
- `0x140060be0`: `onecore\vm\compute\common\transport\sockettransport.cpp`
- `0x140060bf9`: `onecore\vm\compute\common\transport\sockettransport.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SocketTransport::InternalAccept(char *pv, __int64 *a2)
{
  SOCKET v4; // rsi
  SOCKET v5; // r14
  DWORD LastError; // ebx
  int v7; // ebx
  u_short v8; // cx
  PTP_IO *v9; // r14
  PTP_IO ThreadpoolIo; // rsi
  const char *v11; // r9
  struct _TP_IO *v12; // r15
  DWORD v13; // ebx
  void *v14; // rsi
  SOCKET v15; // r15
  DWORD v16; // ebx
  PTP_IO v17; // rsi
  const char *v18; // r9
  struct _TP_IO *v19; // r15
  DWORD v20; // ebx
  __int64 v21; // rax
  DWORD v22; // ebx
  struct _TP_IO *v24; // rax
  unsigned int Error; // eax
  unsigned int v26; // eax
  unsigned int v27; // eax
  unsigned int v28; // eax
  unsigned int v29; // eax
  GROUP g; // [rsp+20h] [rbp-E0h]
  GROUP ga; // [rsp+20h] [rbp-E0h]
  GROUP gb; // [rsp+20h] [rbp-E0h]
  GROUP gc; // [rsp+20h] [rbp-E0h]
  _QWORD v34[4]; // [rsp+50h] [rbp-B0h] BYREF
  char v35; // [rsp+70h] [rbp-90h] BYREF
  char optval[8]; // [rsp+78h] [rbp-88h] BYREF
  struct sockaddr name[8]; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v38[42]; // [rsp+100h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  memset_0(v38, 0, sizeof(v38));
  *(_QWORD *)optval = pv;
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>(
    v38,
    "SocketTransport_Connect");
  v38[0] = &ComputeService::Diagnostics::TraceProvider::SocketTransport_Connect::`vftable';
  ComputeService::Diagnostics::TraceProvider::SocketTransport_Connect::StartActivity<SocketTransport *,unsigned short const (&)[7]>(
    v38,
    optval,
    L"Accept");
  memset_0(name, 0, sizeof(name));
  AcquireSRWLockExclusive((PSRWLOCK)pv + 25);
  *((_DWORD *)pv + 52) = GetCurrentThreadId();
  *(_QWORD *)optval = pv + 200;
  if ( *((_DWORD *)pv + 57) != 3 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x1B9,
      (unsigned int)"onecore\\vm\\compute\\common\\transport\\sockettransport.cpp",
      (const char *)0x139F,
      g);
  *((_DWORD *)pv + 57) = 5;
  SocketTransport::MapAdd(pv, a2);
  *((_DWORD *)pv + 52) = 0;
  ReleaseSRWLockExclusive((PSRWLOCK)pv + 25);
  v35 = 1;
  v34[3] = 256;
  v34[0] = pv;
  v34[1] = &v35;
  v34[2] = a2;
  v4 = WSASocketW(*((_DWORD *)pv + 25), 1, *((_DWORD *)pv + 26), 0, 0, 1u);
  v5 = *((_QWORD *)pv + 14);
  if ( v5 != -1 )
  {
    LastError = GetLastError();
    closesocket(v5);
    SetLastError(LastError);
  }
  *((_QWORD *)pv + 14) = v4;
  if ( v4 == -1 )
  {
    Error = WSAGetLastError();
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x1E7,
      (unsigned int)"onecore\\vm\\compute\\common\\transport\\sockettransport.cpp",
      (const char *)Error,
      ga);
  }
  if ( *((_DWORD *)pv + 24) == 2 )
  {
    if ( pv[92] )
    {
      *(_DWORD *)optval = (unsigned __int8)pv[92];
      if ( setsockopt(v4, 1, 4, optval, 4) )
      {
        v26 = WSAGetLastError();
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x1F7,
          (unsigned int)"onecore\\vm\\compute\\common\\transport\\sockettransport.cpp",
          (const char *)v26,
          ga);
      }
    }
  }
  memset_0(name[0].sa_data, 0, 0x7Eu);
  if ( *((_DWORD *)pv + 25) == 34 )
  {
    v7 = 36;
    name[0].sa_family = 34;
    *(_DWORD *)&name[0].sa_data[2] = *((_DWORD *)pv + 15);
    *(_QWORD *)&name[0].sa_data[6] = *((_QWORD *)pv + 8);
    *(_DWORD *)&name[1].sa_family = *((_DWORD *)pv + 18);
    *(struct sockaddr *)&name[1].sa_data[2] = *(struct sockaddr *)(pv + 76);
  }
  else
  {
    if ( *((_DWORD *)pv + 25) == 2 )
    {
      v7 = 16;
      name[0].sa_family = 2;
      *(_DWORD *)&name[0].sa_data[2] = *((_DWORD *)pv + 4);
      v8 = *((_WORD *)pv + 10);
    }
    else
    {
      v7 = 28;
      name[0].sa_family = 23;
      *(struct sockaddr *)&name[0].sa_data[6] = *((struct sockaddr *)pv + 2);
      v8 = *((_WORD *)pv + 24);
    }
    *(_WORD *)name[0].sa_data = htons(v8);
  }
  if ( bind(*((_QWORD *)pv + 14), name, v7) == -1 )
  {
    v27 = WSAGetLastError();
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x21F,
      (unsigned int)"onecore\\vm\\compute\\common\\transport\\sockettransport.cpp",
      (const char *)v27,
      ga);
  }
  if ( listen(*((_QWORD *)pv + 14), 0x7FFFFFFF) )
  {
    v28 = WSAGetLastError();
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x227,
      (unsigned int)"onecore\\vm\\compute\\common\\transport\\sockettransport.cpp",
      (const char *)v28,
      ga);
  }
  v9 = (PTP_IO *)(pv + 128);
  ThreadpoolIo = CreateThreadpoolIo(*((HANDLE *)pv + 14), SocketTransport::IoCompletionCallback, pv, 0);
  v12 = (struct _TP_IO *)*((_QWORD *)pv + 16);
  if ( v12 )
  {
    v13 = GetLastError();
    CloseThreadpoolIo(v12);
    SetLastError(v13);
  }
  *v9 = ThreadpoolIo;
  if ( !ThreadpoolIo )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x234,
      (unsigned int)"onecore\\vm\\compute\\common\\transport\\sockettransport.cpp",
      v11);
  v14 = (void *)WSASocketW(*((_DWORD *)pv + 25), 1, *((_DWORD *)pv + 26), 0, 0, 1u);
  v15 = *((_QWORD *)pv + 15);
  if ( v15 != -1 )
  {
    v16 = GetLastError();
    closesocket(v15);
    SetLastError(v16);
  }
  *((_QWORD *)pv + 15) = v14;
  if ( v14 == (void *)-1LL )
  {
    v29 = WSAGetLastError();
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x243,
      (unsigned int)"onecore\\vm\\compute\\common\\transport\\sockettransport.cpp",
      (const char *)v29,
      gb);
  }
  v17 = CreateThreadpoolIo(v14, SocketTransport::IoCompletionCallback, pv, 0);
  v19 = (struct _TP_IO *)*((_QWORD *)pv + 17);
  if ( v19 )
  {
    v20 = GetLastError();
    CloseThreadpoolIo(v19);
    SetLastError(v20);
  }
  *((_QWORD *)pv + 17) = v17;
  if ( !v17 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x250,
      (unsigned int)"onecore\\vm\\compute\\common\\transport\\sockettransport.cpp",
      v18);
  StartThreadpoolIo(*v9);
  v21 = *a2;
  *(_OWORD *)(v21 + 88) = 0;
  *(_OWORD *)(v21 + 104) = 0;
  *(_DWORD *)(*a2 + 16) = 1;
  gc = *((_DWORD *)pv + 44);
  if ( !(*((unsigned int (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))pv + 23))(
          *((_QWORD *)pv + 14),
          *((_QWORD *)pv + 15),
          *((_QWORD *)pv + 19),
          0) )
  {
    v22 = GetLastError();
    if ( v22 != 997 )
    {
      v24 = (struct _TP_IO *)std::shared_ptr<ComputeService::Management::ComputeSystem>::operator-><ComputeService::Management::ComputeSystem,0>((__int64)(pv + 128));
      CancelThreadpoolIo(v24);
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x268,
        (unsigned int)"onecore\\vm\\compute\\common\\transport\\sockettransport.cpp",
        (const char *)v22,
        gc);
    }
  }
  v35 = 0;
  pv[109] = 1;
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v38);
  wil::details::ScopeExitFnGuard__lambda_55063b63aab1b5e21bc99534019a7834___::operator()(v34);
  v38[0] = &ComputeService::Diagnostics::TraceProvider::SocketTransport_Connect::`vftable';
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v38);
  return wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>(v38);
}

```

## disassembly

```asm
0x1400606c0  mov     [rsp-8+arg_10], rbx
0x1400606c5  mov     [rsp-8+arg_18], rsi
0x1400606ca  push    rbp
0x1400606cb  push    rdi
0x1400606cc  push    r12
0x1400606ce  push    r14
0x1400606d0  push    r15
0x1400606d2  lea     rbp, [rsp-160h]
0x1400606da  sub     rsp, 260h
0x1400606e1  mov     rax, cs:__security_cookie
0x1400606e8  xor     rax, rsp
0x1400606eb  mov     [rbp+180h+var_30], rax
0x1400606f2  mov     r12, rdx
0x1400606f5  mov     rdi, rcx
0x1400606f8  xor     edx, edx; Val
0x1400606fa  mov     r8d, 150h; Size
0x140060700  lea     rcx, [rbp+180h+var_180]; void *
0x140060704  call    memset_0
0x140060709  mov     qword ptr [rsp+280h+optval], rdi
0x14006070e  lea     rdx, aSockettranspor; "SocketTransport_Connect"
0x140060715  lea     rcx, [rbp+180h+var_180]
0x140060719  call    ??0?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0BAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x14006071e  lea     rax, ??_7SocketTransport_Connect@TraceProvider@Diagnostics@ComputeService@@6B@; const ComputeService::Diagnostics::TraceProvider::SocketTransport_Connect::`vftable'
0x140060725  mov     [rbp+180h+var_180], rax
0x140060729  lea     r8, aAccept; "Accept"
0x140060730  lea     rdx, [rsp+280h+optval]
0x140060735  lea     rcx, [rbp+180h+var_180]
0x140060739  call    ??$StartActivity@PEAVSocketTransport@@AEAY06$$CBG@SocketTransport_Connect@TraceProvider@Diagnostics@ComputeService@@QEAAX$$QEAPEAVSocketTransport@@AEAY06$$CBG@Z; ComputeService::Diagnostics::TraceProvider::SocketTransport_Connect::StartActivity<SocketTransport *,ushort const (&)[7]>(SocketTransport * &&,ushort const (&)[7])
0x14006073e  nop
0x14006073f  xor     edx, edx; Val
0x140060741  mov     r8d, 80h; Size
0x140060747  lea     rcx, [rbp+180h+name]; void *
0x14006074b  call    memset_0
0x140060750  lea     rbx, [rdi+0C8h]
0x140060757  mov     rcx, rbx; SRWLock
0x14006075a  call    cs:__imp_AcquireSRWLockExclusive
0x140060760  call    cs:__imp_GetCurrentThreadId
0x140060766  mov     [rbx+8], eax
0x140060769  mov     qword ptr [rsp+280h+optval], rbx
0x14006076e  cmp     dword ptr [rdi+0E4h], 3
0x140060775  jnz     loc_140060B10
0x14006077b  mov     dword ptr [rdi+0E4h], 5
0x140060785  mov     rdx, r12
0x140060788  mov     rcx, rdi
0x14006078b  call    ?MapAdd@SocketTransport@@AEAAXAEBV?$shared_ptr@VTransportIoContext@@@std@@@Z; SocketTransport::MapAdd(std::shared_ptr<TransportIoContext> const &)
0x140060790  nop
0x140060791  mov     dword ptr [rbx+8], 0
0x140060798  mov     rcx, rbx; SRWLock
0x14006079b  call    cs:__imp_ReleaseSRWLockExclusive
0x1400607a1  mov     [rsp+280h+var_210], 1
0x1400607a6  xorps   xmm0, xmm0
0x1400607a9  movups  [rsp+280h+var_230], xmm0
0x1400607ae  movups  [rsp+280h+var_220], xmm0
0x1400607b3  mov     qword ptr [rsp+280h+var_230], rdi
0x1400607b8  lea     rax, [rsp+280h+var_210]
0x1400607bd  mov     qword ptr [rsp+280h+var_230+8], rax
0x1400607c2  mov     qword ptr [rsp+280h+var_220], r12
0x1400607c7  mov     word ptr [rsp+280h+var_220+8], 100h
0x1400607ce  mov     [rsp+280h+dwFlags], 1; dwFlags
0x1400607d6  mov     [rsp+280h+g], 0; unsigned int
0x1400607de  xor     r9d, r9d; lpProtocolInfo
0x1400607e1  mov     r8d, [rdi+68h]; protocol
0x1400607e5  lea     edx, [r9+1]; type
0x1400607e9  mov     ecx, [rdi+64h]; af
0x1400607ec  call    cs:__imp_WSASocketW
0x1400607f2  mov     rsi, rax
0x1400607f5  mov     r14, [rdi+70h]
0x1400607f9  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x1400607fd  jz      short loc_140060818
0x1400607ff  call    cs:__imp_GetLastError
0x140060805  mov     ebx, eax
0x140060807  mov     rcx, r14; s
0x14006080a  call    cs:__imp_closesocket
0x140060810  mov     ecx, ebx; dwErrCode
0x140060812  call    cs:__imp_SetLastError
0x140060818  mov     [rdi+70h], rsi
0x14006081c  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x140060820  jz      loc_140060B2F
0x140060826  mov     r14d, 2
0x14006082c  cmp     [rdi+60h], r14d
0x140060830  jnz     short loc_140060861
0x140060832  movzx   eax, byte ptr [rdi+5Ch]
0x140060836  test    al, al
0x140060838  jz      short loc_140060861
0x14006083a  mov     dword ptr [rsp+280h+optval], eax
0x14006083e  lea     r8d, [r14+2]; optname
0x140060842  mov     [rsp+280h+g], r8d; unsigned int
0x140060847  lea     r9, [rsp+280h+optval]; optval
0x14006084c  lea     edx, [r14-1]; level
0x140060850  mov     rcx, rsi; s
0x140060853  call    cs:__imp_setsockopt
0x140060859  test    eax, eax
0x14006085b  jnz     loc_140060B51
0x140060861  xor     edx, edx; Val
0x140060863  lea     r8d, [rdx+7Eh]; Size
0x140060867  lea     rcx, [rbp+180h+name+2]; void *
0x14006086b  call    memset_0
0x140060870  mov     eax, 22h ; '"'
0x140060875  cmp     [rdi+64h], eax
0x140060878  jnz     short loc_1400608A2
0x14006087a  lea     ebx, [rax+2]
0x14006087d  mov     word ptr [rbp+180h+name], ax
0x140060881  mov     eax, [rdi+3Ch]
0x140060884  mov     dword ptr [rbp+180h+name+4], eax
0x140060887  movsd   xmm0, qword ptr [rdi+40h]
0x14006088c  movsd   qword ptr [rbp+180h+name+8], xmm0
0x140060891  mov     eax, [rdi+48h]
0x140060894  mov     dword ptr [rbp+180h+name+10h], eax
0x140060897  movups  xmm0, xmmword ptr [rdi+4Ch]
0x14006089b  movdqu  xmmword ptr [rbp+180h+name+14h], xmm0
0x1400608a0  jmp     short loc_1400608E1
0x1400608a2  cmp     [rdi+64h], r14d
0x1400608a6  jnz     short loc_1400608BE
0x1400608a8  mov     ebx, 10h
0x1400608ad  mov     word ptr [rbp+180h+name], r14w
0x1400608b2  mov     eax, [rdi+10h]
0x1400608b5  mov     dword ptr [rbp+180h+name+4], eax
0x1400608b8  movzx   ecx, word ptr [rdi+14h]
0x1400608bc  jmp     short loc_1400608D7
0x1400608be  mov     ebx, 1Ch
0x1400608c3  lea     eax, [rbx-5]
0x1400608c6  mov     word ptr [rbp+180h+name], ax
0x1400608ca  movups  xmm0, xmmword ptr [rdi+20h]
0x1400608ce  movdqu  xmmword ptr [rbp+180h+name+8], xmm0
0x1400608d3  movzx   ecx, word ptr [rdi+30h]; hostshort
0x1400608d7  call    cs:__imp_htons
0x1400608dd  mov     word ptr [rbp+180h+name+2], ax
0x1400608e1  mov     r8d, ebx; namelen
0x1400608e4  lea     rdx, [rbp+180h+name]; name
0x1400608e8  mov     rcx, [rdi+70h]; s
0x1400608ec  call    cs:__imp_bind
0x1400608f2  cmp     eax, 0FFFFFFFFh
0x1400608f5  jz      loc_140060B73
0x1400608fb  mov     edx, 7FFFFFFFh; backlog
0x140060900  mov     rcx, [rdi+70h]; s
0x140060904  call    cs:__imp_listen
0x14006090a  test    eax, eax
0x14006090c  jnz     loc_140060B95
0x140060912  lea     r14, [rdi+80h]
0x140060919  xor     r9d, r9d; pcbe
0x14006091c  mov     r8, rdi; pv
0x14006091f  lea     rdx, ?IoCompletionCallback@SocketTransport@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX1K_KPEAU_TP_IO@@@Z; pfnio
0x140060926  mov     rcx, [rdi+70h]; fl
0x14006092a  call    cs:__imp_CreateThreadpoolIo
0x140060930  mov     rsi, rax
0x140060933  mov     r15, [r14]
0x140060936  test    r15, r15
0x140060939  jz      short loc_140060954
0x14006093b  call    cs:__imp_GetLastError
0x140060941  mov     ebx, eax
0x140060943  mov     rcx, r15; pio
0x140060946  call    cs:__imp_CloseThreadpoolIo
0x14006094c  mov     ecx, ebx; dwErrCode
0x14006094e  call    cs:__imp_SetLastError
0x140060954  mov     [r14], rsi
0x140060957  test    rsi, rsi
0x14006095a  jz      loc_140060BB7
0x140060960  mov     eax, 1
0x140060965  mov     [rsp+280h+dwFlags], eax; dwFlags
0x140060969  mov     [rsp+280h+g], 0; unsigned int
0x140060971  xor     r9d, r9d; lpProtocolInfo
0x140060974  mov     r8d, [rdi+68h]; protocol
0x140060978  mov     edx, eax; type
0x14006097a  mov     ecx, [rdi+64h]; af
0x14006097d  call    cs:__imp_WSASocketW
0x140060983  mov     rsi, rax
0x140060986  mov     r15, [rdi+78h]
0x14006098a  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x14006098e  jz      short loc_1400609A9
0x140060990  call    cs:__imp_GetLastError
0x140060996  mov     ebx, eax
0x140060998  mov     rcx, r15; s
0x14006099b  call    cs:__imp_closesocket
0x1400609a1  mov     ecx, ebx; dwErrCode
0x1400609a3  call    cs:__imp_SetLastError
0x1400609a9  mov     [rdi+78h], rsi
0x1400609ad  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x1400609b1  jz      loc_140060BD0
0x1400609b7  xor     r9d, r9d; pcbe
0x1400609ba  mov     r8, rdi; pv
0x1400609bd  lea     rdx, ?IoCompletionCallback@SocketTransport@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX1K_KPEAU_TP_IO@@@Z; pfnio
0x1400609c4  mov     rcx, rsi; fl
0x1400609c7  call    cs:__imp_CreateThreadpoolIo
0x1400609cd  mov     rsi, rax
0x1400609d0  mov     r15, [rdi+88h]
0x1400609d7  test    r15, r15
0x1400609da  jz      short loc_1400609F5
0x1400609dc  call    cs:__imp_GetLastError
0x1400609e2  mov     ebx, eax
0x1400609e4  mov     rcx, r15; pio
0x1400609e7  call    cs:__imp_CloseThreadpoolIo
0x1400609ed  mov     ecx, ebx; dwErrCode
0x1400609ef  call    cs:__imp_SetLastError
0x1400609f5  mov     [rdi+88h], rsi
0x1400609fc  test    rsi, rsi
0x1400609ff  jz      loc_140060BF2
0x140060a05  mov     rcx, [r14]; pio
0x140060a08  call    cs:__imp_StartThreadpoolIo
0x140060a0e  mov     rax, [r12]
0x140060a12  xorps   xmm0, xmm0
0x140060a15  movups  xmmword ptr [rax+58h], xmm0
0x140060a19  movups  xmmword ptr [rax+68h], xmm0
0x140060a1d  mov     rax, [r12]
0x140060a21  mov     dword ptr [rax+10h], 1
0x140060a28  mov     rax, [r12]
0x140060a2c  mov     edx, [rdi+0B0h]
0x140060a32  lea     rcx, [rax+58h]
0x140060a36  add     rax, 2Ch ; ','
0x140060a3a  mov     [rsp+280h+var_248], rcx
0x140060a3f  mov     [rsp+280h+var_250], rax
0x140060a44  mov     [rsp+280h+dwFlags], edx
0x140060a48  mov     [rsp+280h+g], edx; unsigned int
0x140060a4c  xor     r9d, r9d
0x140060a4f  mov     r8, [rdi+98h]
0x140060a56  mov     rdx, [rdi+78h]
0x140060a5a  mov     rcx, [rdi+70h]
0x140060a5e  mov     rax, [rdi+0B8h]
0x140060a65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140060a6a  test    eax, eax
0x140060a6c  jnz     short loc_140060A7D
0x140060a6e  call    cs:__imp_GetLastError
0x140060a74  mov     ebx, eax
0x140060a76  cmp     eax, 3E5h
0x140060a7b  jnz     short loc_140060AE3
0x140060a7d  mov     [rsp+280h+var_210], 0
0x140060a82  mov     byte ptr [rdi+6Dh], 1
0x140060a86  lea     rcx, [rbp+180h+var_180]
0x140060a8a  call    ?Stop@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0BAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140060a8f  nop
0x140060a90  lea     rcx, [rsp+280h+var_230]
0x140060a95  call    wil__details__ScopeExitFnGuard__lambda_55063b63aab1b5e21bc99534019a7834_____operator__
0x140060a9a  nop
0x140060a9b  lea     rax, ??_7SocketTransport_Connect@TraceProvider@Diagnostics@ComputeService@@6B@; const ComputeService::Diagnostics::TraceProvider::SocketTransport_Connect::`vftable'
0x140060aa2  mov     [rbp+180h+var_180], rax
0x140060aa6  lea     rcx, [rbp+180h+var_180]
0x140060aaa  call    ?Destroy@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0BAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x140060aaf  lea     rcx, [rbp+180h+var_180]
0x140060ab3  call    ??1?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0BAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x140060ab8  mov     rcx, [rbp+180h+var_30]
0x140060abf  xor     rcx, rsp; StackCookie
0x140060ac2  call    __security_check_cookie
0x140060ac7  lea     r11, [rsp+280h+var_20]
0x140060acf  mov     rbx, [r11+40h]
0x140060ad3  mov     rsi, [r11+48h]
0x140060ad7  mov     rsp, r11
0x140060ada  pop     r15
0x140060adc  pop     r14
0x140060ade  pop     r12
0x140060ae0  pop     rdi
0x140060ae1  pop     rbp
0x140060ae2  retn
0x140060ae3  mov     rcx, r14
0x140060ae6  call    ??$?CVComputeSystem@Management@ComputeService@@$0A@@?$shared_ptr@VComputeSystem@Management@ComputeService@@@std@@QEBAPEAVComputeSystem@Management@ComputeService@@XZ; std::shared_ptr<ComputeService::Management::ComputeSystem>::operator-><ComputeService::Management::ComputeSystem,0>(void)
0x140060aeb  mov     rcx, rax; pio
0x140060aee  call    cs:__imp_CancelThreadpoolIo
0x140060af4  mov     rcx, [rbp+188h]; this
0x140060afb  mov     r9d, ebx; char *
0x140060afe  lea     r8, aOnecoreVmCompu_18; "onecore\\vm\\compute\\common\\transport"...
0x140060b05  mov     edx, 268h; void *
0x140060b0a  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x140060b10  mov     rcx, [rbp+188h]; this
0x140060b17  mov     r9d, 139Fh; char *
0x140060b1d  lea     r8, aOnecoreVmCompu_18; "onecore\\vm\\compute\\common\\transport"...
0x140060b24  mov     edx, 1B9h; void *
0x140060b29  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x140060b2f  call    cs:__imp_WSAGetLastError
0x140060b35  mov     r9d, eax; char *
0x140060b38  mov     rcx, [rbp+188h]; this
0x140060b3f  lea     r8, aOnecoreVmCompu_18; "onecore\\vm\\compute\\common\\transport"...
0x140060b46  mov     edx, 1E7h; void *
0x140060b4b  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x140060b51  call    cs:__imp_WSAGetLastError
0x140060b57  mov     r9d, eax; char *
0x140060b5a  mov     rcx, [rbp+188h]; this
0x140060b61  lea     r8, aOnecoreVmCompu_18; "onecore\\vm\\compute\\common\\transport"...
0x140060b68  mov     edx, 1F7h; void *
0x140060b6d  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x140060b73  call    cs:__imp_WSAGetLastError
0x140060b79  mov     r9d, eax; char *
0x140060b7c  mov     rcx, [rbp+188h]; this
0x140060b83  lea     r8, aOnecoreVmCompu_18; "onecore\\vm\\compute\\common\\transport"...
0x140060b8a  mov     edx, 21Fh; void *
0x140060b8f  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x140060b95  call    cs:__imp_WSAGetLastError
0x140060b9b  mov     r9d, eax; char *
0x140060b9e  mov     rcx, [rbp+188h]; this
0x140060ba5  lea     r8, aOnecoreVmCompu_18; "onecore\\vm\\compute\\common\\transport"...
0x140060bac  mov     edx, 227h; void *
0x140060bb1  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x140060bb7  mov     rcx, [rbp+188h]; this
0x140060bbe  lea     r8, aOnecoreVmCompu_18; "onecore\\vm\\compute\\common\\transport"...
0x140060bc5  mov     edx, 234h; void *
0x140060bca  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140060bd0  call    cs:__imp_WSAGetLastError
0x140060bd6  mov     r9d, eax; char *
0x140060bd9  mov     rcx, [rbp+188h]; this
0x140060be0  lea     r8, aOnecoreVmCompu_18; "onecore\\vm\\compute\\common\\transport"...
0x140060be7  mov     edx, 243h; void *
0x140060bec  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x140060bf2  mov     rcx, [rbp+188h]; this
  ... truncated ...
```
