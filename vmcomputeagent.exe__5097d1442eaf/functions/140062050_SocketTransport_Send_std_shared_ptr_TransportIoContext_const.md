# SocketTransport::Send(std::shared_ptr<TransportIoContext> const &)

- ea: `0x140062050`
- end: `0x1400622fa`
- name: `?Send@SocketTransport@@UEAA_NAEBV?$shared_ptr@VTransportIoContext@@@std@@@Z`
- size: `682`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x140005360`
- `0x140006098`
- `0x14005e070`
- `0x14005e538`
- `0x14005f06c`
- `0x14005f364`
- `0x14005f774`
- `0x140060364`
- `0x140061454`
- `0x140062050`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140062147`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140062167`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140062147`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140062167`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400620f3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400620f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140062292`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140062292`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x1400621f4`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x1400621f4`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x14006224d`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x14006225f`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x14006224d`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x14006225f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400620f9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400620f9`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x140062277`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x140062277`
- `WS2_32!WSASend` at `0x14006221e`
- `WS2_32!WSASend` at `0x14006221e`
- `WS2_32!__imp_WSAGetLastError` at `0x140062229`
- `WS2_32!__imp_WSAGetLastError` at `0x140062229`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall SocketTransport::Send(__int64 a1, struct _WSABUF **a2)
{
  struct _WSABUF *v4; // rbx
  char v5; // r15
  struct _WSABUF *v6; // rax
  int Error; // ecx
  __int64 v9; // [rsp+40h] [rbp-C0h] BYREF
  struct _WSABUF *v10; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v11[5]; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v12; // [rsp+78h] [rbp-88h]
  int v13; // [rsp+7Ah] [rbp-86h]
  __int16 v14; // [rsp+7Eh] [rbp-82h]
  char v15; // [rsp+80h] [rbp-80h] BYREF
  DWORD NumberOfBytesTransferred; // [rsp+84h] [rbp-7Ch] BYREF
  int len; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v18[42]; // [rsp+90h] [rbp-70h] BYREF

  memset_0(v18, 0, sizeof(v18));
  v4 = *a2;
  NumberOfBytesTransferred = 2;
  v10 = v4;
  v9 = a1;
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>(
    v18,
    "SocketTransport_IoStart");
  v18[0] = &ComputeService::Diagnostics::TraceProvider::SocketTransport_IoStart::`vftable';
  ComputeService::Diagnostics::TraceProvider::SocketTransport_IoStart::StartActivity<SocketTransport *,TransportIoContext *,unsigned int,unsigned long &>(
    (unsigned int)v18,
    (unsigned int)&v9,
    (unsigned int)&v10,
    (unsigned int)&NumberOfBytesTransferred,
    (__int64)&v4[2].buf);
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 200));
  *(_DWORD *)(a1 + 208) = GetCurrentThreadId();
  v9 = a1 + 200;
  v5 = 1;
  if ( (unsigned int)(*(_DWORD *)(a1 + 228) - 6) <= 1 )
  {
    SocketTransport::MapAdd(a1, a2);
    *(_DWORD *)(a1 + 208) = 0;
    ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 200));
    len = -1;
    v15 = 1;
    v13 = 0;
    v14 = 0;
    v11[0] = a1;
    v11[1] = &v15;
    v11[2] = a2;
    v11[3] = v18;
    v11[4] = &len;
    v12 = 256;
    (*a2)[3].len = -1;
    v6 = *a2;
    *(_OWORD *)&v6[5].buf = 0;
    *(_OWORD *)&v6[6].buf = 0;
    (*a2)[1].len = 2;
    HIDWORD((*a2)[2].buf) = 0;
    (*a2)[8].len = (ULONG)(*a2)[2].buf;
    (*a2)[8].buf = &(*a2)[1].buf[*(&(*a2)[2].len + 1)];
    StartThreadpoolIo(*(PTP_IO *)(a1 + 136));
    if ( WSASend(*(_QWORD *)(a1 + 120), *a2 + 8, 1u, (LPDWORD)&(*a2)[2].buf + 1, 0, (LPWSAOVERLAPPED)&(*a2)[5].buf, 0) == -1 )
    {
      Error = WSAGetLastError();
      len = Error;
      if ( Error == 997 )
      {
        v15 = 0;
      }
      else
      {
        (*a2)[3].len = Error;
        CancelThreadpoolIo(*(PTP_IO *)(a1 + 136));
      }
    }
    else
    {
      NumberOfBytesTransferred = 0;
      CancelThreadpoolIo(*(PTP_IO *)(a1 + 136));
      if ( GetOverlappedResult(*(HANDLE *)(a1 + 120), (LPOVERLAPPED)&(*a2)[5].buf, &NumberOfBytesTransferred, 0) )
      {
        (*a2)[3].len = 0;
        HIDWORD((*a2)[2].buf) = NumberOfBytesTransferred;
      }
      else
      {
        (*a2)[3].len = GetLastError();
      }
      len = (*a2)[3].len;
    }
    v5 = v15;
    wil::details::ScopeExitFnGuard__lambda_2fccbc412e22120968854e70a899f1ef___::operator()(v11);
  }
  else
  {
    (*a2)[3].len = 5023;
    NumberOfBytesTransferred = 0;
    ComputeService::Diagnostics::TraceProvider::SocketTransport_IoStart::Stop<unsigned long &,int>(
      v18,
      &(*a2)[3],
      &NumberOfBytesTransferred);
    *(_DWORD *)(a1 + 208) = 0;
    ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 200));
  }
  v18[0] = &ComputeService::Diagnostics::TraceProvider::SocketTransport_IoStart::`vftable';
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v18);
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeService::Diagnostics::TraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>(v18);
  return v5;
}

```

## disassembly

```asm
0x140062050  mov     [rsp-8+arg_10], rbx
0x140062055  mov     [rsp-8+arg_18], rsi
0x14006205a  push    rbp
0x14006205b  push    rdi
0x14006205c  push    r12
0x14006205e  push    r14
0x140062060  push    r15
0x140062062  lea     rbp, [rsp-0F0h]
0x14006206a  sub     rsp, 1F0h
0x140062071  mov     rax, cs:__security_cookie
0x140062078  xor     rax, rsp
0x14006207b  mov     [rbp+110h+var_30], rax
0x140062082  mov     rdi, rdx
0x140062085  mov     rsi, rcx
0x140062088  xor     edx, edx; Val
0x14006208a  mov     r8d, 150h; Size
0x140062090  lea     rcx, [rbp+110h+var_180]; void *
0x140062094  call    memset_0
0x140062099  mov     rbx, [rdi]
0x14006209c  mov     [rbp+110h+NumberOfBytesTransferred], 2
0x1400620a3  mov     [rsp+210h+var_1C8], rbx
0x1400620a8  mov     [rsp+210h+var_1D0], rsi
0x1400620ad  lea     rdx, aSockettranspor_4; "SocketTransport_IoStart"
0x1400620b4  lea     rcx, [rbp+110h+var_180]
0x1400620b8  call    ??0?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0CAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1400620bd  lea     r12, ??_7SocketTransport_IoStart@TraceProvider@Diagnostics@ComputeService@@6B@; const ComputeService::Diagnostics::TraceProvider::SocketTransport_IoStart::`vftable'
0x1400620c4  mov     [rbp+110h+var_180], r12
0x1400620c8  lea     rax, [rbx+28h]
0x1400620cc  mov     qword ptr [rsp+210h+dwFlags], rax
0x1400620d1  lea     r9, [rbp+110h+NumberOfBytesTransferred]
0x1400620d5  lea     r8, [rsp+210h+var_1C8]
0x1400620da  lea     rdx, [rsp+210h+var_1D0]
0x1400620df  lea     rcx, [rbp+110h+var_180]
0x1400620e3  call    ??$StartActivity@PEAVSocketTransport@@PEAVTransportIoContext@@IAEAK@SocketTransport_IoStart@TraceProvider@Diagnostics@ComputeService@@QEAAX$$QEAPEAVSocketTransport@@$$QEAPEAVTransportIoContext@@$$QEAIAEAK@Z; ComputeService::Diagnostics::TraceProvider::SocketTransport_IoStart::StartActivity<SocketTransport *,TransportIoContext *,uint,ulong &>(SocketTransport * &&,TransportIoContext * &&,uint &&,ulong &)
0x1400620e8  nop
0x1400620e9  lea     r14, [rsi+0C8h]
0x1400620f0  mov     rcx, r14; SRWLock
0x1400620f3  call    cs:__imp_AcquireSRWLockExclusive
0x1400620f9  call    cs:__imp_GetCurrentThreadId
0x1400620ff  mov     [r14+8], eax
0x140062103  mov     [rsp+210h+var_1D0], r14
0x140062108  mov     eax, [rsi+0E4h]
0x14006210e  sub     eax, 6
0x140062111  mov     r15d, 1
0x140062117  cmp     eax, r15d
0x14006211a  jbe     short loc_140062152
0x14006211c  mov     rax, [rdi]
0x14006211f  mov     dword ptr [rax+30h], 139Fh
0x140062126  xor     ebx, ebx
0x140062128  mov     [rbp+110h+NumberOfBytesTransferred], ebx
0x14006212b  mov     rdx, [rdi]
0x14006212e  add     rdx, 30h ; '0'
0x140062132  lea     r8, [rbp+110h+NumberOfBytesTransferred]
0x140062136  lea     rcx, [rbp+110h+var_180]
0x14006213a  call    ??$Stop@AEAKH@SocketTransport_IoStart@TraceProvider@Diagnostics@ComputeService@@QEAAXAEAK$$QEAH@Z; ComputeService::Diagnostics::TraceProvider::SocketTransport_IoStart::Stop<ulong &,int>(ulong &,int &&)
0x14006213f  nop
0x140062140  mov     [r14+8], ebx
0x140062144  mov     rcx, r14; SRWLock
0x140062147  call    cs:__imp_ReleaseSRWLockExclusive
0x14006214d  jmp     loc_1400622B6
0x140062152  mov     rdx, rdi
0x140062155  mov     rcx, rsi
0x140062158  call    ?MapAdd@SocketTransport@@AEAAXAEBV?$shared_ptr@VTransportIoContext@@@std@@@Z; SocketTransport::MapAdd(std::shared_ptr<TransportIoContext> const &)
0x14006215d  nop
0x14006215e  xor     ebx, ebx
0x140062160  mov     [r14+8], ebx
0x140062164  mov     rcx, r14; SRWLock
0x140062167  call    cs:__imp_ReleaseSRWLockExclusive
0x14006216d  or      ecx, 0FFFFFFFFh
0x140062170  mov     [rbp+110h+var_188], ecx
0x140062173  mov     [rbp+110h+var_190], r15b
0x140062177  mov     [rsp+210h+var_196], ebx
0x14006217b  mov     [rsp+210h+var_192], bx
0x140062180  mov     [rsp+210h+var_1C0], rsi
0x140062185  lea     rax, [rbp+110h+var_190]
0x140062189  mov     [rsp+210h+var_1B8], rax
0x14006218e  mov     [rsp+210h+var_1B0], rdi
0x140062193  lea     rax, [rbp+110h+var_180]
0x140062197  mov     [rsp+210h+var_1A8], rax
0x14006219c  lea     rax, [rbp+110h+var_188]
0x1400621a0  mov     [rsp+210h+var_1A0], rax
0x1400621a5  mov     [rsp+210h+var_198], 100h
0x1400621ac  mov     rax, [rdi]
0x1400621af  mov     [rax+30h], ecx
0x1400621b2  mov     rax, [rdi]
0x1400621b5  xorps   xmm0, xmm0
0x1400621b8  movups  xmmword ptr [rax+58h], xmm0
0x1400621bc  movups  xmmword ptr [rax+68h], xmm0
0x1400621c0  mov     rax, [rdi]
0x1400621c3  mov     dword ptr [rax+10h], 2
0x1400621ca  mov     rax, [rdi]
0x1400621cd  mov     [rax+2Ch], ebx
0x1400621d0  mov     rcx, [rdi]
0x1400621d3  mov     eax, [rcx+28h]
0x1400621d6  mov     [rcx+80h], eax
0x1400621dc  mov     rcx, [rdi]
0x1400621df  mov     eax, [rcx+24h]
0x1400621e2  add     rax, [rcx+18h]
0x1400621e6  mov     [rcx+88h], rax
0x1400621ed  mov     rcx, [rsi+88h]; pio
0x1400621f4  call    cs:__imp_StartThreadpoolIo
0x1400621fa  mov     rdx, [rdi]
0x1400621fd  lea     rax, [rdx+58h]
0x140062201  lea     r9, [rdx+2Ch]; lpNumberOfBytesSent
0x140062205  sub     rdx, 0FFFFFFFFFFFFFF80h; lpBuffers
0x140062209  mov     [rsp+210h+lpCompletionRoutine], rbx; lpCompletionRoutine
0x14006220e  mov     [rsp+210h+lpOverlapped], rax; lpOverlapped
0x140062213  mov     [rsp+210h+dwFlags], ebx; dwFlags
0x140062217  mov     r8d, r15d; dwBufferCount
0x14006221a  mov     rcx, [rsi+78h]; s
0x14006221e  call    cs:__imp_WSASend
0x140062224  cmp     eax, 0FFFFFFFFh
0x140062227  jnz     short loc_140062255
0x140062229  call    cs:__imp_WSAGetLastError
0x14006222f  mov     ecx, eax
0x140062231  mov     [rbp+110h+var_188], eax
0x140062234  cmp     eax, 3E5h
0x140062239  jnz     short loc_140062240
0x14006223b  mov     [rbp+110h+var_190], bl
0x14006223e  jmp     short loc_1400622A7
0x140062240  mov     rax, [rdi]
0x140062243  mov     [rax+30h], ecx
0x140062246  mov     rcx, [rsi+88h]; pio
0x14006224d  call    cs:__imp_CancelThreadpoolIo
0x140062253  jmp     short loc_1400622A7
0x140062255  mov     [rbp+110h+NumberOfBytesTransferred], ebx
0x140062258  mov     rcx, [rsi+88h]; pio
0x14006225f  call    cs:__imp_CancelThreadpoolIo
0x140062265  mov     rdx, [rdi]
0x140062268  add     rdx, 58h ; 'X'; lpOverlapped
0x14006226c  xor     r9d, r9d; bWait
0x14006226f  lea     r8, [rbp+110h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x140062273  mov     rcx, [rsi+78h]; hFile
0x140062277  call    cs:__imp_GetOverlappedResult
0x14006227d  test    eax, eax
0x14006227f  jz      short loc_140062292
0x140062281  mov     rax, [rdi]
0x140062284  mov     [rax+30h], ebx
0x140062287  mov     rcx, [rdi]
0x14006228a  mov     eax, [rbp+110h+NumberOfBytesTransferred]
0x14006228d  mov     [rcx+2Ch], eax
0x140062290  jmp     short loc_14006229E
0x140062292  call    cs:__imp_GetLastError
0x140062298  mov     rcx, [rdi]
0x14006229b  mov     [rcx+30h], eax
0x14006229e  mov     rax, [rdi]
0x1400622a1  mov     ecx, [rax+30h]
0x1400622a4  mov     [rbp+110h+var_188], ecx
0x1400622a7  mov     r15b, [rbp+110h+var_190]
0x1400622ab  lea     rcx, [rsp+210h+var_1C0]
0x1400622b0  call    wil__details__ScopeExitFnGuard__lambda_2fccbc412e22120968854e70a899f1ef_____operator__
0x1400622b5  nop
0x1400622b6  mov     [rbp+110h+var_180], r12
0x1400622ba  lea     rcx, [rbp+110h+var_180]
0x1400622be  call    ?Destroy@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0CAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1400622c3  lea     rcx, [rbp+110h+var_180]
0x1400622c7  call    ??1?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0CAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeService::Diagnostics::TraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x1400622cc  mov     al, r15b
0x1400622cf  mov     rcx, [rbp+110h+var_30]
0x1400622d6  xor     rcx, rsp; StackCookie
0x1400622d9  call    __security_check_cookie
0x1400622de  lea     r11, [rsp+210h+var_20]
0x1400622e6  mov     rbx, [r11+40h]
0x1400622ea  mov     rsi, [r11+48h]
0x1400622ee  mov     rsp, r11
0x1400622f1  pop     r15
0x1400622f3  pop     r14
0x1400622f5  pop     r12
0x1400622f7  pop     rdi
0x1400622f8  pop     rbp
0x1400622f9  retn
```
