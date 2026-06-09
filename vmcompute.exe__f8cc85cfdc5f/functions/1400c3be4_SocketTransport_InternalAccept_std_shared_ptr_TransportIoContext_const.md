# SocketTransport::InternalAccept(std::shared_ptr<TransportIoContext> const &)

- ea: `0x1400c3be4`
- end: `0x1400c40d9`
- name: `?InternalAccept@SocketTransport@@AEAAXAEBV?$shared_ptr@VTransportIoContext@@@std@@@Z`
- size: `1269`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140257090`

## callees

- `0x140022ca0`
- `0x140022d94`
- `0x14004c898`
- `0x140061c3c`
- `0x14006c9c4`
- `0x140080180`
- `0x1400c3be4`
- `0x1400c4154`
- `0x1400e2c0c`
- `0x1400e9724`
- `0x1400ec27c`
- `0x1400fe974`
- `0x1401332f0`
- `0x140134048`
- `0x1402c4010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400c3cd0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400c3cd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400c4046`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400c4046`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x1400c3eed`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x1400c3fa0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x1400c3eed`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x1400c3fa0`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x1400c3fd9`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x1400c3fd9`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x1400c405e`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x1400c405e`
- `WS2_32!WSASocketW` at `0x1400c3d29`
- `WS2_32!WSASocketW` at `0x1400c3f44`
- `WS2_32!WSASocketW` at `0x1400c3d29`
- `WS2_32!WSASocketW` at `0x1400c3f44`
- `WS2_32!__imp_bind` at `0x1400c3e5d`
- `WS2_32!__imp_bind` at `0x1400c3e5d`
- `WS2_32!__imp_htons` at `0x1400c3e43`
- `WS2_32!__imp_htons` at `0x1400c3e43`
- `WS2_32!__imp_listen` at `0x1400c3e9e`
- `WS2_32!__imp_listen` at `0x1400c3e9e`
- `WS2_32!__imp_setsockopt` at `0x1400c3d97`
- `WS2_32!__imp_setsockopt` at `0x1400c3d97`
- `WS2_32!__imp_WSAGetLastError` at `0x1400c3d46`
- `WS2_32!__imp_WSAGetLastError` at `0x1400c3da7`
- `WS2_32!__imp_WSAGetLastError` at `0x1400c3e6e`
- `WS2_32!__imp_WSAGetLastError` at `0x1400c3eae`
- `WS2_32!__imp_WSAGetLastError` at `0x1400c3f61`
- `WS2_32!__imp_WSAGetLastError` at `0x1400c3d46`
- `WS2_32!__imp_WSAGetLastError` at `0x1400c3da7`
- `WS2_32!__imp_WSAGetLastError` at `0x1400c3e6e`
- `WS2_32!__imp_WSAGetLastError` at `0x1400c3eae`
- `WS2_32!__imp_WSAGetLastError` at `0x1400c3f61`

## string_xrefs

- `0x1400c3c9e`: `onecore\vm\compute\common\transport\sockettransport.cpp`
- `0x1400c3d5c`: `onecore\vm\compute\common\transport\sockettransport.cpp`
- `0x1400c3dbd`: `onecore\vm\compute\common\transport\sockettransport.cpp`
- `0x1400c3e84`: `onecore\vm\compute\common\transport\sockettransport.cpp`
- `0x1400c3ec4`: `onecore\vm\compute\common\transport\sockettransport.cpp`
- `0x1400c3f11`: `onecore\vm\compute\common\transport\sockettransport.cpp`
- `0x1400c3f77`: `onecore\vm\compute\common\transport\sockettransport.cpp`
- `0x1400c3fc4`: `onecore\vm\compute\common\transport\sockettransport.cpp`
- `0x1400c4074`: `onecore\vm\compute\common\transport\sockettransport.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall SocketTransport::InternalAccept(char *pv, __int64 *a2)
{
  SOCKET *v4; // r14
  SOCKET v5; // rax
  unsigned int Error; // eax
  unsigned int v7; // eax
  int v8; // ebx
  u_short v9; // cx
  unsigned int v10; // eax
  unsigned int v11; // eax
  PTP_IO *v12; // rsi
  PTP_IO ThreadpoolIo; // rax
  const char *v14; // r9
  HANDLE *v15; // r15
  SOCKET v16; // rax
  unsigned int v17; // eax
  PTP_IO v18; // rax
  const char *v19; // r9
  __int64 v20; // rax
  DWORD LastError; // ebx
  GROUP g; // [rsp+20h] [rbp-E0h]
  GROUP ga; // [rsp+20h] [rbp-E0h]
  GROUP gb; // [rsp+20h] [rbp-E0h]
  GROUP gc; // [rsp+20h] [rbp-E0h]
  _QWORD v26[4]; // [rsp+50h] [rbp-B0h] BYREF
  char v27; // [rsp+70h] [rbp-90h] BYREF
  char optval[8]; // [rsp+78h] [rbp-88h] BYREF
  struct sockaddr name[8]; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v30[42]; // [rsp+100h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  memset_0(v30, 0, sizeof(v30));
  *(_QWORD *)optval = pv;
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v30);
  v30[0] = &ComputeService::Diagnostics::TraceProvider::SocketTransport_Connect::`vftable';
  ComputeService::Diagnostics::TraceProvider::SocketTransport_Connect::StartActivity<SocketTransport *,unsigned short const (&)[7]>(
    v30,
    optval,
    L"Accept");
  memset_0(name, 0, sizeof(name));
  Vml::VmSlimReaderWriterLock::AcquireExclusive((Vml::VmSlimReaderWriterLock *)(pv + 200));
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
  v27 = 1;
  v26[3] = 256;
  v26[0] = pv;
  v26[1] = &v27;
  v26[2] = a2;
  v4 = (SOCKET *)(pv + 112);
  v5 = WSASocketW(*((_DWORD *)pv + 25), 1, *((_DWORD *)pv + 26), 0, 0, 1u);
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&int closesocket(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,-1,unsigned __int64>>::reset(
    pv + 112,
    v5);
  if ( *((_QWORD *)pv + 14) == -1 )
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
      if ( setsockopt(*v4, 1, 4, optval, 4) )
      {
        v7 = WSAGetLastError();
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x1F7,
          (unsigned int)"onecore\\vm\\compute\\common\\transport\\sockettransport.cpp",
          (const char *)v7,
          ga);
      }
    }
  }
  memset_0(name[0].sa_data, 0, 0x7Eu);
  if ( *((_DWORD *)pv + 25) == 34 )
  {
    v8 = 36;
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
      v8 = 16;
      name[0].sa_family = 2;
      *(_DWORD *)&name[0].sa_data[2] = *((_DWORD *)pv + 4);
      v9 = *((_WORD *)pv + 10);
    }
    else
    {
      v8 = 28;
      name[0].sa_family = 23;
      *(struct sockaddr *)&name[0].sa_data[6] = *((struct sockaddr *)pv + 2);
      v9 = *((_WORD *)pv + 24);
    }
    *(_WORD *)name[0].sa_data = htons(v9);
  }
  if ( bind(*v4, name, v8) == -1 )
  {
    v10 = WSAGetLastError();
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x21F,
      (unsigned int)"onecore\\vm\\compute\\common\\transport\\sockettransport.cpp",
      (const char *)v10,
      ga);
  }
  if ( listen(*v4, 0x7FFFFFFF) )
  {
    v11 = WSAGetLastError();
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x227,
      (unsigned int)"onecore\\vm\\compute\\common\\transport\\sockettransport.cpp",
      (const char *)v11,
      ga);
  }
  v12 = (PTP_IO *)(pv + 128);
  ThreadpoolIo = CreateThreadpoolIo((HANDLE)*v4, SocketTransport::IoCompletionCallback, pv, 0);
  wil::details::unique_storage<wil::details::resource_policy<_TP_IO *,void (*)(_TP_IO *),&void CloseThreadpoolIo(_TP_IO *),wistd::integral_constant<unsigned __int64,0>,_TP_IO *,_TP_IO *,0,std::nullptr_t>>::reset(
    pv + 128,
    ThreadpoolIo);
  if ( !*((_QWORD *)pv + 16) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x234,
      (unsigned int)"onecore\\vm\\compute\\common\\transport\\sockettransport.cpp",
      v14);
  v15 = (HANDLE *)(pv + 120);
  v16 = WSASocketW(*((_DWORD *)pv + 25), 1, *((_DWORD *)pv + 26), 0, 0, 1u);
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&int closesocket(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,-1,unsigned __int64>>::reset(
    pv + 120,
    v16);
  if ( *((_QWORD *)pv + 15) == -1 )
  {
    v17 = WSAGetLastError();
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x243,
      (unsigned int)"onecore\\vm\\compute\\common\\transport\\sockettransport.cpp",
      (const char *)v17,
      gb);
  }
  v18 = CreateThreadpoolIo(*v15, SocketTransport::IoCompletionCallback, pv, 0);
  wil::details::unique_storage<wil::details::resource_policy<_TP_IO *,void (*)(_TP_IO *),&void CloseThreadpoolIo(_TP_IO *),wistd::integral_constant<unsigned __int64,0>,_TP_IO *,_TP_IO *,0,std::nullptr_t>>::reset(
    pv + 136,
    v18);
  if ( !*((_QWORD *)pv + 17) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x250,
      (unsigned int)"onecore\\vm\\compute\\common\\transport\\sockettransport.cpp",
      v19);
  StartThreadpoolIo(*v12);
  v20 = *a2;
  *(_OWORD *)(v20 + 88) = 0;
  *(_OWORD *)(v20 + 104) = 0;
  *(_DWORD *)(*a2 + 16) = 1;
  gc = *((_DWORD *)pv + 44);
  if ( !(*((unsigned int (__fastcall **)(SOCKET, HANDLE, _QWORD, _QWORD))pv + 23))(*v4, *v15, *((_QWORD *)pv + 19), 0) )
  {
    LastError = GetLastError();
    if ( LastError != 997 )
    {
      CancelThreadpoolIo(*v12);
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x268,
        (unsigned int)"onecore\\vm\\compute\\common\\transport\\sockettransport.cpp",
        (const char *)LastError,
        gc);
    }
  }
  v27 = 0;
  pv[109] = 1;
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v30);
  wil::details::ScopeExitFnGuard__lambda_55063b63aab1b5e21bc99534019a7834___::operator()(v26);
  ComputeService::Diagnostics::TraceProvider::SocketTransport_Connect::~SocketTransport_Connect((ComputeService::Diagnostics::TraceProvider::SocketTransport_Connect *)v30);
}

```

## disassembly

```asm
0x1400c3be4  mov     [rsp-8+arg_10], rbx
0x1400c3be9  mov     [rsp-8+arg_18], rsi
0x1400c3bee  push    rbp
0x1400c3bef  push    rdi
0x1400c3bf0  push    r12
0x1400c3bf2  push    r14
0x1400c3bf4  push    r15
0x1400c3bf6  lea     rbp, [rsp-160h]
0x1400c3bfe  sub     rsp, 260h
0x1400c3c05  mov     rax, cs:__security_cookie
0x1400c3c0c  xor     rax, rsp
0x1400c3c0f  mov     [rbp+180h+var_30], rax
0x1400c3c16  mov     r12, rdx
0x1400c3c19  mov     rdi, rcx
0x1400c3c1c  xor     edx, edx; Val
0x1400c3c1e  mov     r8d, 150h; Size
0x1400c3c24  lea     rcx, [rbp+180h+var_180]; void *
0x1400c3c28  call    memset_0
0x1400c3c2d  mov     qword ptr [rsp+280h+optval], rdi
0x1400c3c32  lea     rdx, aSockettranspor; "SocketTransport_Connect"
0x1400c3c39  lea     rcx, [rbp+180h+var_180]; struct wil::details::IFailureCallback *
0x1400c3c3d  call    ??0?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0BAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1400c3c42  lea     rax, ??_7SocketTransport_Connect@TraceProvider@Diagnostics@ComputeService@@6B@; const ComputeService::Diagnostics::TraceProvider::SocketTransport_Connect::`vftable'
0x1400c3c49  mov     [rbp+180h+var_180], rax
0x1400c3c4d  lea     r8, aAccept; "Accept"
0x1400c3c54  lea     rdx, [rsp+280h+optval]
0x1400c3c59  lea     rcx, [rbp+180h+var_180]
0x1400c3c5d  call    ??$StartActivity@PEAVSocketTransport@@AEAY06$$CBG@SocketTransport_Connect@TraceProvider@Diagnostics@ComputeService@@QEAAX$$QEAPEAVSocketTransport@@AEAY06$$CBG@Z; ComputeService::Diagnostics::TraceProvider::SocketTransport_Connect::StartActivity<SocketTransport *,ushort const (&)[7]>(SocketTransport * &&,ushort const (&)[7])
0x1400c3c62  nop
0x1400c3c63  xor     edx, edx; Val
0x1400c3c65  mov     r8d, 80h; Size
0x1400c3c6b  lea     rcx, [rbp+180h+name]; void *
0x1400c3c6f  call    memset_0
0x1400c3c74  lea     rbx, [rdi+0C8h]
0x1400c3c7b  mov     rcx, rbx; this
0x1400c3c7e  call    ?AcquireExclusive@VmSlimReaderWriterLock@Vml@@QEAAXXZ; Vml::VmSlimReaderWriterLock::AcquireExclusive(void)
0x1400c3c83  mov     qword ptr [rsp+280h+optval], rbx
0x1400c3c88  cmp     dword ptr [rdi+0E4h], 3
0x1400c3c8f  jz      short loc_1400C3CB0
0x1400c3c91  mov     rcx, [rbp+188h]; this
0x1400c3c98  mov     r9d, 139Fh; char *
0x1400c3c9e  lea     r8, aOnecoreVmCompu_44; "onecore\\vm\\compute\\common\\transport"...
0x1400c3ca5  mov     edx, 1B9h; void *
0x1400c3caa  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400c3cb0  mov     dword ptr [rdi+0E4h], 5
0x1400c3cba  mov     rdx, r12
0x1400c3cbd  mov     rcx, rdi
0x1400c3cc0  call    ?MapAdd@SocketTransport@@AEAAXAEBV?$shared_ptr@VTransportIoContext@@@std@@@Z; SocketTransport::MapAdd(std::shared_ptr<TransportIoContext> const &)
0x1400c3cc5  nop
0x1400c3cc6  mov     dword ptr [rbx+8], 0
0x1400c3ccd  mov     rcx, rbx; SRWLock
0x1400c3cd0  call    cs:__imp_ReleaseSRWLockExclusive
0x1400c3cd7  nop     dword ptr [rax+rax+00h]
0x1400c3cdc  mov     ebx, 1
0x1400c3ce1  mov     [rsp+280h+var_210], bl
0x1400c3ce5  xorps   xmm0, xmm0
0x1400c3ce8  movups  [rsp+280h+var_230], xmm0
0x1400c3ced  movups  [rsp+280h+var_220], xmm0
0x1400c3cf2  mov     qword ptr [rsp+280h+var_230], rdi
0x1400c3cf7  lea     rax, [rsp+280h+var_210]
0x1400c3cfc  mov     qword ptr [rsp+280h+var_230+8], rax
0x1400c3d01  mov     qword ptr [rsp+280h+var_220], r12
0x1400c3d06  mov     word ptr [rsp+280h+var_220+8], 100h
0x1400c3d0d  lea     r14, [rdi+70h]
0x1400c3d11  mov     [rsp+280h+dwFlags], ebx; dwFlags
0x1400c3d15  mov     [rsp+280h+g], 0; unsigned int
0x1400c3d1d  xor     r9d, r9d; lpProtocolInfo
0x1400c3d20  mov     r8d, [rdi+68h]; protocol
0x1400c3d24  mov     edx, ebx; type
0x1400c3d26  mov     ecx, [rdi+64h]; af
0x1400c3d29  call    cs:__imp_WSASocketW
0x1400c3d30  nop     dword ptr [rax+rax+00h]
0x1400c3d35  mov     rdx, rax
0x1400c3d38  mov     rcx, r14
0x1400c3d3b  call    ?reset@?$unique_storage@U?$resource_policy@_KP6AH_K@Z$1?closesocket@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0?0_K@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&closesocket(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,-1,unsigned __int64>>::reset(unsigned __int64)
0x1400c3d40  cmp     qword ptr [r14], 0FFFFFFFFFFFFFFFFh
0x1400c3d44  jnz     short loc_1400C3D6E
0x1400c3d46  call    cs:__imp_WSAGetLastError
0x1400c3d4d  nop     dword ptr [rax+rax+00h]
0x1400c3d52  mov     r9d, eax; char *
0x1400c3d55  mov     rcx, [rbp+188h]; this
0x1400c3d5c  lea     r8, aOnecoreVmCompu_44; "onecore\\vm\\compute\\common\\transport"...
0x1400c3d63  mov     edx, 1E7h; void *
0x1400c3d68  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400c3d6e  mov     esi, 2
0x1400c3d73  cmp     [rdi+60h], esi
0x1400c3d76  jnz     short loc_1400C3DCF
0x1400c3d78  movzx   eax, byte ptr [rdi+5Ch]
0x1400c3d7c  test    al, al
0x1400c3d7e  jz      short loc_1400C3DCF
0x1400c3d80  mov     dword ptr [rsp+280h+optval], eax
0x1400c3d84  lea     r8d, [rsi+2]; optname
0x1400c3d88  mov     [rsp+280h+g], r8d; unsigned int
0x1400c3d8d  lea     r9, [rsp+280h+optval]; optval
0x1400c3d92  mov     edx, ebx; level
0x1400c3d94  mov     rcx, [r14]; s
0x1400c3d97  call    cs:__imp_setsockopt
0x1400c3d9e  nop     dword ptr [rax+rax+00h]
0x1400c3da3  test    eax, eax
0x1400c3da5  jz      short loc_1400C3DCF
0x1400c3da7  call    cs:__imp_WSAGetLastError
0x1400c3dae  nop     dword ptr [rax+rax+00h]
0x1400c3db3  mov     r9d, eax; char *
0x1400c3db6  mov     rcx, [rbp+188h]; this
0x1400c3dbd  lea     r8, aOnecoreVmCompu_44; "onecore\\vm\\compute\\common\\transport"...
0x1400c3dc4  mov     edx, 1F7h; void *
0x1400c3dc9  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400c3dcf  xor     edx, edx; Val
0x1400c3dd1  lea     r8d, [rdx+7Eh]; Size
0x1400c3dd5  lea     rcx, [rbp+180h+name+2]; void *
0x1400c3dd9  call    memset_0
0x1400c3dde  mov     eax, 22h ; '"'
0x1400c3de3  cmp     [rdi+64h], eax
0x1400c3de6  jnz     short loc_1400C3E10
0x1400c3de8  lea     ebx, [rax+2]
0x1400c3deb  mov     word ptr [rbp+180h+name], ax
0x1400c3def  mov     eax, [rdi+3Ch]
0x1400c3df2  mov     dword ptr [rbp+180h+name+4], eax
0x1400c3df5  movsd   xmm0, qword ptr [rdi+40h]
0x1400c3dfa  movsd   qword ptr [rbp+180h+name+8], xmm0
0x1400c3dff  mov     eax, [rdi+48h]
0x1400c3e02  mov     dword ptr [rbp+180h+name+10h], eax
0x1400c3e05  movups  xmm0, xmmword ptr [rdi+4Ch]
0x1400c3e09  movdqu  xmmword ptr [rbp+180h+name+14h], xmm0
0x1400c3e0e  jmp     short loc_1400C3E53
0x1400c3e10  cmp     [rdi+64h], esi
0x1400c3e13  jnz     short loc_1400C3E2A
0x1400c3e15  mov     ebx, 10h
0x1400c3e1a  mov     word ptr [rbp+180h+name], si
0x1400c3e1e  mov     eax, [rdi+10h]
0x1400c3e21  mov     dword ptr [rbp+180h+name+4], eax
0x1400c3e24  movzx   ecx, word ptr [rdi+14h]
0x1400c3e28  jmp     short loc_1400C3E43
0x1400c3e2a  mov     ebx, 1Ch
0x1400c3e2f  lea     eax, [rbx-5]
0x1400c3e32  mov     word ptr [rbp+180h+name], ax
0x1400c3e36  movups  xmm0, xmmword ptr [rdi+20h]
0x1400c3e3a  movdqu  xmmword ptr [rbp+180h+name+8], xmm0
0x1400c3e3f  movzx   ecx, word ptr [rdi+30h]; hostshort
0x1400c3e43  call    cs:__imp_htons
0x1400c3e4a  nop     dword ptr [rax+rax+00h]
0x1400c3e4f  mov     word ptr [rbp+180h+name+2], ax
0x1400c3e53  mov     r8d, ebx; namelen
0x1400c3e56  lea     rdx, [rbp+180h+name]; name
0x1400c3e5a  mov     rcx, [r14]; s
0x1400c3e5d  call    cs:__imp_bind
0x1400c3e64  nop     dword ptr [rax+rax+00h]
0x1400c3e69  cmp     eax, 0FFFFFFFFh
0x1400c3e6c  jnz     short loc_1400C3E96
0x1400c3e6e  call    cs:__imp_WSAGetLastError
0x1400c3e75  nop     dword ptr [rax+rax+00h]
0x1400c3e7a  mov     r9d, eax; char *
0x1400c3e7d  mov     rcx, [rbp+188h]; this
0x1400c3e84  lea     r8, aOnecoreVmCompu_44; "onecore\\vm\\compute\\common\\transport"...
0x1400c3e8b  mov     edx, 21Fh; void *
0x1400c3e90  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400c3e96  mov     edx, 7FFFFFFFh; backlog
0x1400c3e9b  mov     rcx, [r14]; s
0x1400c3e9e  call    cs:__imp_listen
0x1400c3ea5  nop     dword ptr [rax+rax+00h]
0x1400c3eaa  test    eax, eax
0x1400c3eac  jz      short loc_1400C3ED6
0x1400c3eae  call    cs:__imp_WSAGetLastError
0x1400c3eb5  nop     dword ptr [rax+rax+00h]
0x1400c3eba  mov     r9d, eax; char *
0x1400c3ebd  mov     rcx, [rbp+188h]; this
0x1400c3ec4  lea     r8, aOnecoreVmCompu_44; "onecore\\vm\\compute\\common\\transport"...
0x1400c3ecb  mov     edx, 227h; void *
0x1400c3ed0  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400c3ed6  lea     rsi, [rdi+80h]
0x1400c3edd  xor     r9d, r9d; pcbe
0x1400c3ee0  mov     r8, rdi; pv
0x1400c3ee3  lea     rdx, ?IoCompletionCallback@SocketTransport@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX1K_KPEAU_TP_IO@@@Z; pfnio
0x1400c3eea  mov     rcx, [r14]; fl
0x1400c3eed  call    cs:__imp_CreateThreadpoolIo
0x1400c3ef4  nop     dword ptr [rax+rax+00h]
0x1400c3ef9  mov     rdx, rax
0x1400c3efc  mov     rcx, rsi
0x1400c3eff  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_IO@@P6AXPEAU1@@Z$1?CloseThreadpoolIo@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_IO@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_IO *,void (*)(_TP_IO *),&CloseThreadpoolIo(_TP_IO *),wistd::integral_constant<unsigned __int64,0>,_TP_IO *,_TP_IO *,0,std::nullptr_t>>::reset(_TP_IO *)
0x1400c3f04  cmp     qword ptr [rsi], 0
0x1400c3f08  jnz     short loc_1400C3F23
0x1400c3f0a  mov     rcx, [rbp+188h]; this
0x1400c3f11  lea     r8, aOnecoreVmCompu_44; "onecore\\vm\\compute\\common\\transport"...
0x1400c3f18  mov     edx, 234h; void *
0x1400c3f1d  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400c3f23  lea     r15, [rdi+78h]
0x1400c3f27  mov     eax, 1
0x1400c3f2c  mov     [rsp+280h+dwFlags], eax; dwFlags
0x1400c3f30  mov     [rsp+280h+g], 0; unsigned int
0x1400c3f38  xor     r9d, r9d; lpProtocolInfo
0x1400c3f3b  mov     r8d, [rdi+68h]; protocol
0x1400c3f3f  mov     edx, eax; type
0x1400c3f41  mov     ecx, [rdi+64h]; af
0x1400c3f44  call    cs:__imp_WSASocketW
0x1400c3f4b  nop     dword ptr [rax+rax+00h]
0x1400c3f50  mov     rdx, rax
0x1400c3f53  mov     rcx, r15
0x1400c3f56  call    ?reset@?$unique_storage@U?$resource_policy@_KP6AH_K@Z$1?closesocket@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0?0_K@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&closesocket(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,-1,unsigned __int64>>::reset(unsigned __int64)
0x1400c3f5b  cmp     qword ptr [r15], 0FFFFFFFFFFFFFFFFh
0x1400c3f5f  jnz     short loc_1400C3F89
0x1400c3f61  call    cs:__imp_WSAGetLastError
0x1400c3f68  nop     dword ptr [rax+rax+00h]
0x1400c3f6d  mov     r9d, eax; char *
0x1400c3f70  mov     rcx, [rbp+188h]; this
0x1400c3f77  lea     r8, aOnecoreVmCompu_44; "onecore\\vm\\compute\\common\\transport"...
0x1400c3f7e  mov     edx, 243h; void *
0x1400c3f83  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400c3f89  lea     rbx, [rdi+88h]
0x1400c3f90  xor     r9d, r9d; pcbe
0x1400c3f93  mov     r8, rdi; pv
0x1400c3f96  lea     rdx, ?IoCompletionCallback@SocketTransport@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX1K_KPEAU_TP_IO@@@Z; pfnio
0x1400c3f9d  mov     rcx, [r15]; fl
0x1400c3fa0  call    cs:__imp_CreateThreadpoolIo
0x1400c3fa7  nop     dword ptr [rax+rax+00h]
0x1400c3fac  mov     rdx, rax
0x1400c3faf  mov     rcx, rbx
0x1400c3fb2  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_IO@@P6AXPEAU1@@Z$1?CloseThreadpoolIo@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_IO@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_IO *,void (*)(_TP_IO *),&CloseThreadpoolIo(_TP_IO *),wistd::integral_constant<unsigned __int64,0>,_TP_IO *,_TP_IO *,0,std::nullptr_t>>::reset(_TP_IO *)
0x1400c3fb7  cmp     qword ptr [rbx], 0
0x1400c3fbb  jnz     short loc_1400C3FD6
0x1400c3fbd  mov     rcx, [rbp+188h]; this
0x1400c3fc4  lea     r8, aOnecoreVmCompu_44; "onecore\\vm\\compute\\common\\transport"...
0x1400c3fcb  mov     edx, 250h; void *
0x1400c3fd0  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400c3fd6  mov     rcx, [rsi]; pio
0x1400c3fd9  call    cs:__imp_StartThreadpoolIo
0x1400c3fe0  nop     dword ptr [rax+rax+00h]
0x1400c3fe5  mov     rax, [r12]
0x1400c3fe9  xorps   xmm0, xmm0
0x1400c3fec  movups  xmmword ptr [rax+58h], xmm0
0x1400c3ff0  movups  xmmword ptr [rax+68h], xmm0
0x1400c3ff4  mov     rax, [r12]
0x1400c3ff8  mov     dword ptr [rax+10h], 1
0x1400c3fff  mov     rax, [r12]
0x1400c4003  mov     r9d, [rdi+0B0h]
0x1400c400a  lea     r8, [rax+58h]
0x1400c400e  add     rax, 2Ch ; ','
0x1400c4012  mov     [rsp+280h+var_248], r8
0x1400c4017  mov     [rsp+280h+var_250], rax
0x1400c401c  mov     [rsp+280h+dwFlags], r9d
0x1400c4021  mov     [rsp+280h+g], r9d; unsigned int
0x1400c4026  xor     r9d, r9d
0x1400c4029  mov     r8, [rdi+98h]
0x1400c4030  mov     rdx, [r15]
0x1400c4033  mov     rcx, [r14]
0x1400c4036  mov     rax, [rdi+0B8h]
0x1400c403d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400c4042  test    eax, eax
0x1400c4044  jnz     short loc_1400C4086
0x1400c4046  call    cs:__imp_GetLastError
0x1400c404d  nop     dword ptr [rax+rax+00h]
0x1400c4052  mov     ebx, eax
0x1400c4054  cmp     eax, 3E5h
0x1400c4059  jz      short loc_1400C4086
0x1400c405b  mov     rcx, [rsi]; pio
0x1400c405e  call    cs:__imp_CancelThreadpoolIo
0x1400c4065  nop     dword ptr [rax+rax+00h]
0x1400c406a  mov     rcx, [rbp+188h]; this
0x1400c4071  mov     r9d, ebx; char *
0x1400c4074  lea     r8, aOnecoreVmCompu_44; "onecore\\vm\\compute\\common\\transport"...
0x1400c407b  mov     edx, 268h; void *
0x1400c4080  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400c4086  mov     [rsp+280h+var_210], 0
0x1400c408b  mov     byte ptr [rdi+6Dh], 1
0x1400c408f  lea     rcx, [rbp+180h+var_180]
0x1400c4093  call    ?Stop@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0BAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1400c4098  nop
0x1400c4099  lea     rcx, [rsp+280h+var_230]
0x1400c409e  call    wil__details__ScopeExitFnGuard__lambda_55063b63aab1b5e21bc99534019a7834_____operator__
0x1400c40a3  nop
0x1400c40a4  lea     rcx, [rbp+180h+var_180]; this
0x1400c40a8  call    ??1SocketTransport_Connect@TraceProvider@Diagnostics@ComputeService@@QEAA@XZ; ComputeService::Diagnostics::TraceProvider::SocketTransport_Connect::~SocketTransport_Connect(void)
0x1400c40ad  mov     rcx, [rbp+180h+var_30]
0x1400c40b4  xor     rcx, rsp; StackCookie
0x1400c40b7  call    __security_check_cookie
0x1400c40bc  lea     r11, [rsp+280h+var_20]
0x1400c40c4  mov     rbx, [r11+40h]
0x1400c40c8  mov     rsi, [r11+48h]
0x1400c40cc  mov     rsp, r11
0x1400c40cf  pop     r15
0x1400c40d1  pop     r14
0x1400c40d3  pop     r12
0x1400c40d5  pop     rdi
0x1400c40d6  pop     rbp
0x1400c40d7  retn
```
