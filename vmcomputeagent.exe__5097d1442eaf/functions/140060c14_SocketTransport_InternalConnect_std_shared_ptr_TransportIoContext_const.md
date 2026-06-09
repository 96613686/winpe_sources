# SocketTransport::InternalConnect(std::shared_ptr<TransportIoContext> const &)

- ea: `0x140060c14`
- end: `0x140061068`
- name: `?InternalConnect@SocketTransport@@AEAAXAEBV?$shared_ptr@VTransportIoContext@@@std@@@Z`
- size: `1108`
- prototype: `__int64 __fastcall(char *pv, __int64 *)`
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
- `0x14005df64`
- `0x14005efac`
- `0x14005f2e4`
- `0x14005f850`
- `0x140060248`
- `0x140060c14`
- `0x140061454`
- `0x140062518`
- `0x1400fe010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140060cfb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140060cfb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140060cb1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140060cb1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140060d7d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140060e5a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140060d7d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140060e5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140060d6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140060e47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140060d6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140060e47`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x140060f14`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x140060f14`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x140060e36`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x140060e36`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x140060fca`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x140060fca`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x140060e52`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x140060e52`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140060cb7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140060cb7`
- `WS2_32!WSASocketW` at `0x140060d57`
- `WS2_32!WSASocketW` at `0x140060d57`
- `WS2_32!__imp_bind` at `0x140060e0a`
- `WS2_32!__imp_bind` at `0x140060e0a`
- `WS2_32!__imp_closesocket` at `0x140060d75`
- `WS2_32!__imp_closesocket` at `0x140060d75`
- `WS2_32!__imp_htons` at `0x140060ee9`
- `WS2_32!__imp_htons` at `0x140060ee9`
- `WS2_32!__imp_WSAGetLastError` at `0x140060f4e`
- `WS2_32!__imp_WSAGetLastError` at `0x14006100b`
- `WS2_32!__imp_WSAGetLastError` at `0x14006102d`
- `WS2_32!__imp_WSAGetLastError` at `0x140060f4e`
- `WS2_32!__imp_WSAGetLastError` at `0x14006100b`
- `WS2_32!__imp_WSAGetLastError` at `0x14006102d`

## string_xrefs

- `0x140060fda`: `onecore\vm\compute\common\transport\sockettransport.cpp`
- `0x140060ff9`: `onecore\vm\compute\common\transport\sockettransport.cpp`
- `0x14006101b`: `onecore\vm\compute\common\transport\sockettransport.cpp`
- `0x14006103d`: `onecore\vm\compute\common\transport\sockettransport.cpp`
- `0x140061056`: `onecore\vm\compute\common\transport\sockettransport.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SocketTransport::InternalConnect(char *pv, __int64 *a2)
{
  __int64 *v2; // r12
  int *v4; // r15
  unsigned int v5; // r13d
  SOCKET v6; // rsi
  SOCKET v7; // r14
  DWORD LastError; // ebx
  int v9; // r8d
  struct _TP_IO **v10; // rsi
  const char *v11; // r9
  PTP_IO ThreadpoolIo; // r14
  struct _TP_IO *v13; // r12
  DWORD v14; // ebx
  u_short v15; // cx
  __int64 v16; // rax
  unsigned int v17; // ebx
  struct _TP_IO *v19; // rax
  unsigned int v20; // eax
  unsigned int Error; // eax
  GROUP g; // [rsp+20h] [rbp-E0h]
  GROUP ga; // [rsp+20h] [rbp-E0h]
  char *v24; // [rsp+40h] [rbp-C0h] BYREF
  __int64 *v25; // [rsp+48h] [rbp-B8h]
  _QWORD v26[4]; // [rsp+50h] [rbp-B0h] BYREF
  char v27; // [rsp+70h] [rbp-90h] BYREF
  _QWORD name[16]; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v29[42]; // [rsp+100h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  v2 = a2;
  v25 = a2;
  memset_0(v29, 0, sizeof(v29));
  v24 = pv;
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>(
    v29,
    "SocketTransport_Connect");
  v29[0] = &ComputeService::Diagnostics::TraceProvider::SocketTransport_Connect::`vftable';
  ComputeService::Diagnostics::TraceProvider::SocketTransport_Connect::StartActivity<SocketTransport *,unsigned short const (&)[8]>(
    v29,
    &v24,
    L"Connect");
  memset_0(name, 0, sizeof(name));
  AcquireSRWLockExclusive((PSRWLOCK)pv + 25);
  *((_DWORD *)pv + 52) = GetCurrentThreadId();
  v24 = pv + 200;
  if ( *((_DWORD *)pv + 57) != 3 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x296,
      (unsigned int)"onecore\\vm\\compute\\common\\transport\\sockettransport.cpp",
      (const char *)0x139F,
      g);
  *((_DWORD *)pv + 57) = 4;
  pv[109] = 1;
  SocketTransport::MapAdd(pv, v2);
  *((_DWORD *)pv + 52) = 0;
  ReleaseSRWLockExclusive((PSRWLOCK)pv + 25);
  v27 = 1;
  v26[3] = 256;
  v26[0] = pv;
  v26[1] = &v27;
  v26[2] = v2;
  v4 = (int *)(pv + 100);
  v5 = 36;
  if ( *((_QWORD *)pv + 15) == -1 )
  {
    v6 = WSASocketW(*v4, 1, *((_DWORD *)pv + 26), 0, 0, 1u);
    v7 = *((_QWORD *)pv + 15);
    if ( v7 != -1 )
    {
      LastError = GetLastError();
      closesocket(v7);
      SetLastError(LastError);
    }
    *((_QWORD *)pv + 15) = v6;
    if ( v6 == -1 )
    {
      Error = WSAGetLastError();
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x2C7,
        (unsigned int)"onecore\\vm\\compute\\common\\transport\\sockettransport.cpp",
        (const char *)Error,
        ga);
    }
    memset_0((char *)name + 2, 0, 0x7Eu);
    if ( *v4 == 34 )
    {
      v9 = 36;
      LOWORD(name[0]) = 34;
      HIDWORD(name[0]) = 0;
      memset(&name[1], 0, 28);
    }
    else if ( *v4 == 2 )
    {
      v9 = 16;
      name[0] = 2;
    }
    else
    {
      v9 = 28;
      LODWORD(name[0]) = 23;
      *(_OWORD *)&name[1] = 0;
    }
    if ( bind(v6, (const struct sockaddr *)name, v9) == -1 )
    {
      v20 = WSAGetLastError();
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x2EE,
        (unsigned int)"onecore\\vm\\compute\\common\\transport\\sockettransport.cpp",
        (const char *)v20,
        ga);
    }
  }
  v10 = (struct _TP_IO **)(pv + 136);
  if ( !*((_QWORD *)pv + 17) )
  {
    ThreadpoolIo = CreateThreadpoolIo(*((HANDLE *)pv + 15), SocketTransport::IoCompletionCallback, pv, 0);
    v13 = *v10;
    if ( *v10 )
    {
      v14 = GetLastError();
      CloseThreadpoolIo(v13);
      SetLastError(v14);
    }
    *v10 = ThreadpoolIo;
    if ( !ThreadpoolIo )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x2FE,
        (unsigned int)"onecore\\vm\\compute\\common\\transport\\sockettransport.cpp",
        v11);
    v2 = v25;
  }
  memset_0((char *)name + 2, 0, 0x7Eu);
  if ( *v4 == 34 )
  {
    LOWORD(name[0]) = 34;
    HIDWORD(name[0]) = *((_DWORD *)pv + 15);
    name[1] = *((_QWORD *)pv + 8);
    LODWORD(name[2]) = *((_DWORD *)pv + 18);
    *(_OWORD *)((char *)&name[2] + 4) = *(_OWORD *)(pv + 76);
  }
  else
  {
    if ( *v4 == 2 )
    {
      v5 = 16;
      LOWORD(name[0]) = 2;
      HIDWORD(name[0]) = *((_DWORD *)pv + 4);
      v15 = *((_WORD *)pv + 10);
    }
    else
    {
      v5 = 28;
      LOWORD(name[0]) = 23;
      *(_OWORD *)&name[1] = *((_OWORD *)pv + 2);
      v15 = *((_WORD *)pv + 24);
    }
    WORD1(name[0]) = htons(v15);
  }
  v16 = *v2;
  *(_OWORD *)(v16 + 88) = 0;
  *(_OWORD *)(v16 + 104) = 0;
  *(_DWORD *)(*v2 + 16) = 1;
  StartThreadpoolIo(*((PTP_IO *)pv + 17));
  if ( !(*((unsigned int (__fastcall **)(_QWORD, _QWORD *, _QWORD, _QWORD))pv + 24))(*((_QWORD *)pv + 15), name, v5, 0) )
  {
    v17 = WSAGetLastError();
    if ( v17 != 997 )
    {
      v19 = (struct _TP_IO *)std::shared_ptr<ComputeService::Management::ComputeSystem>::operator-><ComputeService::Management::ComputeSystem,0>(pv + 136);
      CancelThreadpoolIo(v19);
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x332,
        (unsigned int)"onecore\\vm\\compute\\common\\transport\\sockettransport.cpp",
        (const char *)v17,
        0);
    }
  }
  v27 = 0;
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v29);
  wil::details::ScopeExitFnGuard__lambda_55063b63aab1b5e21bc99534019a7834___::operator()(v26);
  v29[0] = &ComputeService::Diagnostics::TraceProvider::SocketTransport_Connect::`vftable';
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v29);
  return wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>(v29);
}

```

## disassembly

```asm
0x140060c14  mov     [rsp-8+arg_10], rbx
0x140060c19  push    rbp
0x140060c1a  push    rsi
0x140060c1b  push    rdi
0x140060c1c  push    r12
0x140060c1e  push    r13
0x140060c20  push    r14
0x140060c22  push    r15
0x140060c24  lea     rbp, [rsp-160h]
0x140060c2c  sub     rsp, 260h
0x140060c33  mov     rax, cs:__security_cookie
0x140060c3a  xor     rax, rsp
0x140060c3d  mov     [rbp+190h+var_40], rax
0x140060c44  mov     r12, rdx
0x140060c47  mov     [rsp+290h+var_248], rdx
0x140060c4c  mov     rdi, rcx
0x140060c4f  xor     edx, edx; Val
0x140060c51  mov     r8d, 150h; Size
0x140060c57  lea     rcx, [rbp+190h+var_190]; void *
0x140060c5b  call    memset_0
0x140060c60  mov     [rsp+290h+var_250], rdi
0x140060c65  lea     rdx, aSockettranspor; "SocketTransport_Connect"
0x140060c6c  lea     rcx, [rbp+190h+var_190]
0x140060c70  call    ??0?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0BAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140060c75  lea     rax, ??_7SocketTransport_Connect@TraceProvider@Diagnostics@ComputeService@@6B@; const ComputeService::Diagnostics::TraceProvider::SocketTransport_Connect::`vftable'
0x140060c7c  mov     [rbp+190h+var_190], rax
0x140060c80  lea     r8, aConnect; "Connect"
0x140060c87  lea     rdx, [rsp+290h+var_250]
0x140060c8c  lea     rcx, [rbp+190h+var_190]
0x140060c90  call    ??$StartActivity@PEAVSocketTransport@@AEAY07$$CBG@SocketTransport_Connect@TraceProvider@Diagnostics@ComputeService@@QEAAX$$QEAPEAVSocketTransport@@AEAY07$$CBG@Z; ComputeService::Diagnostics::TraceProvider::SocketTransport_Connect::StartActivity<SocketTransport *,ushort const (&)[8]>(SocketTransport * &&,ushort const (&)[8])
0x140060c95  nop
0x140060c96  xor     edx, edx; Val
0x140060c98  mov     r8d, 80h; Size
0x140060c9e  lea     rcx, [rbp+190h+name]; void *
0x140060ca2  call    memset_0
0x140060ca7  lea     rbx, [rdi+0C8h]
0x140060cae  mov     rcx, rbx; SRWLock
0x140060cb1  call    cs:__imp_AcquireSRWLockExclusive
0x140060cb7  call    cs:__imp_GetCurrentThreadId
0x140060cbd  mov     [rbx+8], eax
0x140060cc0  mov     [rsp+290h+var_250], rbx
0x140060cc5  cmp     dword ptr [rdi+0E4h], 3
0x140060ccc  jnz     loc_140060FEC
0x140060cd2  mov     dword ptr [rdi+0E4h], 4
0x140060cdc  mov     esi, 1
0x140060ce1  mov     [rdi+6Dh], sil
0x140060ce5  mov     rdx, r12
0x140060ce8  mov     rcx, rdi
0x140060ceb  call    ?MapAdd@SocketTransport@@AEAAXAEBV?$shared_ptr@VTransportIoContext@@@std@@@Z; SocketTransport::MapAdd(std::shared_ptr<TransportIoContext> const &)
0x140060cf0  nop
0x140060cf1  mov     dword ptr [rbx+8], 0
0x140060cf8  mov     rcx, rbx; SRWLock
0x140060cfb  call    cs:__imp_ReleaseSRWLockExclusive
0x140060d01  mov     [rsp+290h+var_220], sil
0x140060d06  xorps   xmm0, xmm0
0x140060d09  movups  [rsp+290h+var_240], xmm0
0x140060d0e  movups  [rsp+290h+var_230], xmm0
0x140060d13  mov     qword ptr [rsp+290h+var_240], rdi
0x140060d18  lea     rax, [rsp+290h+var_220]
0x140060d1d  mov     qword ptr [rsp+290h+var_240+8], rax
0x140060d22  mov     qword ptr [rsp+290h+var_230], r12
0x140060d27  xor     ebx, ebx
0x140060d29  mov     word ptr [rsp+290h+var_230+8], 100h
0x140060d30  lea     r15, [rdi+64h]
0x140060d34  lea     r13d, [rsi+23h]
0x140060d38  cmp     qword ptr [rdi+78h], 0FFFFFFFFFFFFFFFFh
0x140060d3d  jnz     loc_140060E19
0x140060d43  mov     [rsp+290h+dwFlags], esi; dwFlags
0x140060d47  mov     [rsp+290h+g], ebx; unsigned int
0x140060d4b  xor     r9d, r9d; lpProtocolInfo
0x140060d4e  mov     r8d, [rdi+68h]; protocol
0x140060d52  mov     edx, esi; type
0x140060d54  mov     ecx, [r15]; af
0x140060d57  call    cs:__imp_WSASocketW
0x140060d5d  mov     rsi, rax
0x140060d60  mov     r14, [rdi+78h]
0x140060d64  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x140060d68  jz      short loc_140060D85
0x140060d6a  call    cs:__imp_GetLastError
0x140060d70  mov     ebx, eax
0x140060d72  mov     rcx, r14; s
0x140060d75  call    cs:__imp_closesocket
0x140060d7b  mov     ecx, ebx; dwErrCode
0x140060d7d  call    cs:__imp_SetLastError
0x140060d83  xor     ebx, ebx
0x140060d85  mov     [rdi+78h], rsi
0x140060d89  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x140060d8d  jz      loc_14006102D
0x140060d93  xor     edx, edx; Val
0x140060d95  lea     r8d, [rdx+7Eh]; Size
0x140060d99  lea     rcx, [rbp+190h+name.sa_data]; void *
0x140060d9d  call    memset_0
0x140060da2  mov     eax, 22h ; '"'
0x140060da7  cmp     [r15], eax
0x140060daa  jnz     short loc_140060DD9
0x140060dac  mov     r8d, r13d
0x140060daf  mov     [rbp+190h+name.sa_family], ax
0x140060db3  mov     dword ptr [rbp+190h+name.sa_data+2], ebx
0x140060db6  movsd   xmm0, qword ptr cs:HV_GUID_ZERO.Data2
0x140060dbe  movsd   qword ptr [rbp+190h+name.sa_data+6], xmm0
0x140060dc3  mov     eax, dword ptr cs:HV_GUID_ZERO.Data4+4
0x140060dc9  mov     [rbp-70h], eax
0x140060dcc  mov     [rbp-6Ch], ebx
0x140060dcf  movsd   [rbp+190h+var_1F8], xmm0
0x140060dd4  mov     [rbp+190h+var_1F0], eax
0x140060dd7  jmp     short loc_140060E03
0x140060dd9  mov     r14d, 2
0x140060ddf  cmp     [r15], r14d
0x140060de2  jnz     short loc_140060DEE
0x140060de4  lea     r8d, [r14+0Eh]
0x140060de8  mov     qword ptr [rbp+190h+name.sa_family], r14
0x140060dec  jmp     short loc_140060E03
0x140060dee  mov     r8d, 1Ch; namelen
0x140060df4  mov     dword ptr [rbp+190h+name.sa_family], 17h
0x140060dfb  xorps   xmm0, xmm0
0x140060dfe  movdqu  xmmword ptr [rbp+190h+name.sa_data+6], xmm0
0x140060e03  lea     rdx, [rbp+190h+name]; name
0x140060e07  mov     rcx, rsi; s
0x140060e0a  call    cs:__imp_bind
0x140060e10  cmp     eax, 0FFFFFFFFh
0x140060e13  jz      loc_14006100B
0x140060e19  lea     rsi, [rdi+88h]
0x140060e20  cmp     [rsi], rbx
0x140060e23  jnz     short loc_140060E73
0x140060e25  xor     r9d, r9d; pcbe
0x140060e28  mov     r8, rdi; pv
0x140060e2b  lea     rdx, ?IoCompletionCallback@SocketTransport@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX1K_KPEAU_TP_IO@@@Z; pfnio
0x140060e32  mov     rcx, [rdi+78h]; fl
0x140060e36  call    cs:__imp_CreateThreadpoolIo
0x140060e3c  mov     r14, rax
0x140060e3f  mov     r12, [rsi]
0x140060e42  test    r12, r12
0x140060e45  jz      short loc_140060E62
0x140060e47  call    cs:__imp_GetLastError
0x140060e4d  mov     ebx, eax
0x140060e4f  mov     rcx, r12; pio
0x140060e52  call    cs:__imp_CloseThreadpoolIo
0x140060e58  mov     ecx, ebx; dwErrCode
0x140060e5a  call    cs:__imp_SetLastError
0x140060e60  xor     ebx, ebx
0x140060e62  mov     [rsi], r14
0x140060e65  test    r14, r14
0x140060e68  jz      loc_14006104F
0x140060e6e  mov     r12, [rsp+290h+var_248]
0x140060e73  xor     edx, edx; Val
0x140060e75  lea     r8d, [rdx+7Eh]; Size
0x140060e79  lea     rcx, [rbp+190h+name.sa_data]; void *
0x140060e7d  call    memset_0
0x140060e82  mov     eax, 22h ; '"'
0x140060e87  cmp     [r15], eax
0x140060e8a  jnz     short loc_140060EB1
0x140060e8c  mov     [rbp+190h+name.sa_family], ax
0x140060e90  mov     eax, [rdi+3Ch]
0x140060e93  mov     dword ptr [rbp+190h+name.sa_data+2], eax
0x140060e96  movsd   xmm0, qword ptr [rdi+40h]
0x140060e9b  movsd   qword ptr [rbp+190h+name.sa_data+6], xmm0
0x140060ea0  mov     eax, [rdi+48h]
0x140060ea3  mov     [rbp-70h], eax
0x140060ea6  movups  xmm0, xmmword ptr [rdi+4Ch]
0x140060eaa  movdqu  xmmword ptr [rbp-6Ch], xmm0
0x140060eaf  jmp     short loc_140060EF3
0x140060eb1  mov     eax, 2
0x140060eb6  cmp     [r15], eax
0x140060eb9  jnz     short loc_140060ECF
0x140060ebb  lea     r13d, [rax+0Eh]
0x140060ebf  mov     [rbp+190h+name.sa_family], ax
0x140060ec3  mov     eax, [rdi+10h]
0x140060ec6  mov     dword ptr [rbp+190h+name.sa_data+2], eax
0x140060ec9  movzx   ecx, word ptr [rdi+14h]
0x140060ecd  jmp     short loc_140060EE9
0x140060ecf  mov     eax, 17h
0x140060ed4  lea     r13d, [rax+5]
0x140060ed8  mov     [rbp+190h+name.sa_family], ax
0x140060edc  movups  xmm0, xmmword ptr [rdi+20h]
0x140060ee0  movdqu  xmmword ptr [rbp+190h+name.sa_data+6], xmm0
0x140060ee5  movzx   ecx, word ptr [rdi+30h]; hostshort
0x140060ee9  call    cs:__imp_htons
0x140060eef  mov     word ptr [rbp+190h+name.sa_data], ax
0x140060ef3  mov     rax, [r12]
0x140060ef7  xorps   xmm0, xmm0
0x140060efa  movups  xmmword ptr [rax+58h], xmm0
0x140060efe  movups  xmmword ptr [rax+68h], xmm0
0x140060f02  mov     rax, [r12]
0x140060f06  mov     dword ptr [rax+10h], 1
0x140060f0d  mov     rcx, [rdi+88h]; pio
0x140060f14  call    cs:__imp_StartThreadpoolIo
0x140060f1a  mov     rdx, [r12]
0x140060f1e  add     rdx, 58h ; 'X'
0x140060f22  mov     [rsp+290h+var_260], rdx
0x140060f27  mov     qword ptr [rsp+290h+dwFlags], rbx
0x140060f2c  mov     [rsp+290h+g], ebx; unsigned int
0x140060f30  xor     r9d, r9d
0x140060f33  mov     r8d, r13d
0x140060f36  lea     rdx, [rbp+190h+name]
0x140060f3a  mov     rcx, [rdi+78h]
0x140060f3e  mov     rax, [rdi+0C0h]
0x140060f45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140060f4a  test    eax, eax
0x140060f4c  jnz     short loc_140060F5F
0x140060f4e  call    cs:__imp_WSAGetLastError
0x140060f54  mov     ebx, eax
0x140060f56  cmp     eax, 3E5h
0x140060f5b  jnz     short loc_140060FBF
0x140060f5d  xor     ebx, ebx
0x140060f5f  mov     [rsp+290h+var_220], bl
0x140060f63  lea     rcx, [rbp+190h+var_190]
0x140060f67  call    ?Stop@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0BAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140060f6c  nop
0x140060f6d  lea     rcx, [rsp+290h+var_240]
0x140060f72  call    wil__details__ScopeExitFnGuard__lambda_55063b63aab1b5e21bc99534019a7834_____operator__
0x140060f77  nop
0x140060f78  lea     rax, ??_7SocketTransport_Connect@TraceProvider@Diagnostics@ComputeService@@6B@; const ComputeService::Diagnostics::TraceProvider::SocketTransport_Connect::`vftable'
0x140060f7f  mov     [rbp+190h+var_190], rax
0x140060f83  lea     rcx, [rbp+190h+var_190]
0x140060f87  call    ?Destroy@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0BAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x140060f8c  lea     rcx, [rbp+190h+var_190]
0x140060f90  call    ??1?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0BAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x140060f95  mov     rcx, [rbp+190h+var_40]
0x140060f9c  xor     rcx, rsp; StackCookie
0x140060f9f  call    __security_check_cookie
0x140060fa4  mov     rbx, [rsp+290h+arg_10]
0x140060fac  add     rsp, 260h
0x140060fb3  pop     r15
0x140060fb5  pop     r14
0x140060fb7  pop     r13
0x140060fb9  pop     r12
0x140060fbb  pop     rdi
0x140060fbc  pop     rsi
0x140060fbd  pop     rbp
0x140060fbe  retn
0x140060fbf  mov     rcx, rsi
0x140060fc2  call    ??$?CVComputeSystem@Management@ComputeService@@$0A@@?$shared_ptr@VComputeSystem@Management@ComputeService@@@std@@QEBAPEAVComputeSystem@Management@ComputeService@@XZ; std::shared_ptr<ComputeService::Management::ComputeSystem>::operator-><ComputeService::Management::ComputeSystem,0>(void)
0x140060fc7  mov     rcx, rax; pio
0x140060fca  call    cs:__imp_CancelThreadpoolIo
0x140060fd0  mov     rcx, [rbp+198h]; this
0x140060fd7  mov     r9d, ebx; char *
0x140060fda  lea     r8, aOnecoreVmCompu_18; "onecore\\vm\\compute\\common\\transport"...
0x140060fe1  mov     edx, 332h; void *
0x140060fe6  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x140060fec  mov     rcx, [rbp+198h]; this
0x140060ff3  mov     r9d, 139Fh; char *
0x140060ff9  lea     r8, aOnecoreVmCompu_18; "onecore\\vm\\compute\\common\\transport"...
0x140061000  mov     edx, 296h; void *
0x140061005  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x14006100b  call    cs:__imp_WSAGetLastError
0x140061011  mov     r9d, eax; char *
0x140061014  mov     rcx, [rbp+198h]; this
0x14006101b  lea     r8, aOnecoreVmCompu_18; "onecore\\vm\\compute\\common\\transport"...
0x140061022  mov     edx, 2EEh; void *
0x140061027  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x14006102d  call    cs:__imp_WSAGetLastError
0x140061033  mov     r9d, eax; char *
0x140061036  mov     rcx, [rbp+198h]; this
0x14006103d  lea     r8, aOnecoreVmCompu_18; "onecore\\vm\\compute\\common\\transport"...
0x140061044  mov     edx, 2C7h; void *
0x140061049  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x14006104f  mov     rcx, [rbp+198h]; this
0x140061056  lea     r8, aOnecoreVmCompu_18; "onecore\\vm\\compute\\common\\transport"...
0x14006105d  mov     edx, 2FEh; void *
0x140061062  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
