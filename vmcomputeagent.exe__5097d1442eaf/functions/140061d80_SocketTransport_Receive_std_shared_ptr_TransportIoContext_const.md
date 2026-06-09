# SocketTransport::Receive(std::shared_ptr<TransportIoContext> const &)

- ea: `0x140061d80`
- end: `0x140062044`
- name: `?Receive@SocketTransport@@UEAA_NAEBV?$shared_ptr@VTransportIoContext@@@std@@@Z`
- size: `708`
- prototype: `__int64 __fastcall(SocketTransport *this)`
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callees

- `0x140005360`
- `0x140006098`
- `0x14005e070`
- `0x14005e538`
- `0x14005f06c`
- `0x14005f364`
- `0x14005f8f0`
- `0x140060364`
- `0x140060654`
- `0x140061454`
- `0x140061d80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140061e77`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140061e97`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140061e77`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140061e97`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140061e23`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140061e23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140061fdc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140061fdc`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x140061f2a`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x140061f2a`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x140061f87`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x140061f99`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x140061f87`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x140061f99`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140061e29`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140061e29`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x140061fb1`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x140061fb1`
- `WS2_32!WSARecv` at `0x140061f58`
- `WS2_32!WSARecv` at `0x140061f58`
- `WS2_32!__imp_WSAGetLastError` at `0x140061f63`
- `WS2_32!__imp_WSAGetLastError` at `0x140061f63`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
char __fastcall SocketTransport::Receive(SocketTransport *this, struct _WSABUF **a2)
{
  struct _WSABUF *v4; // rbx
  char v5; // r15
  struct _WSABUF *v6; // rax
  int Error; // ecx
  SocketTransport *v9; // [rsp+40h] [rbp-C0h] BYREF
  struct _WSABUF *v10; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v11[6]; // [rsp+50h] [rbp-B0h] BYREF
  char v12; // [rsp+80h] [rbp-80h] BYREF
  DWORD NumberOfBytesTransferred; // [rsp+84h] [rbp-7Ch] BYREF
  int len; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v15[42]; // [rsp+90h] [rbp-70h] BYREF

  memset_0(v15, 0, sizeof(v15));
  v4 = *a2;
  NumberOfBytesTransferred = 3;
  v10 = v4;
  v9 = this;
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>(
    v15,
    "SocketTransport_IoStart");
  v15[0] = &ComputeService::Diagnostics::TraceProvider::SocketTransport_IoStart::`vftable';
  ComputeService::Diagnostics::TraceProvider::SocketTransport_IoStart::StartActivity<SocketTransport *,TransportIoContext *,unsigned int,unsigned long &>(
    (unsigned int)v15,
    (unsigned int)&v9,
    (unsigned int)&v10,
    (unsigned int)&NumberOfBytesTransferred,
    (__int64)&v4[2].buf);
  AcquireSRWLockExclusive((PSRWLOCK)this + 25);
  *((_DWORD *)this + 52) = GetCurrentThreadId();
  v9 = (SocketTransport *)((char *)this + 200);
  v5 = 1;
  if ( (unsigned int)(*((_DWORD *)this + 57) - 6) <= 1 )
  {
    SocketTransport::MapAdd(this, a2);
    *((_DWORD *)this + 52) = 0;
    ReleaseSRWLockExclusive((PSRWLOCK)this + 25);
    len = -1;
    v12 = 1;
    v11[5] = 256;
    v11[0] = this;
    v11[1] = &v12;
    v11[2] = a2;
    v11[3] = v15;
    v11[4] = &len;
    (*a2)[3].len = -1;
    v6 = *a2;
    *(_OWORD *)&v6[5].buf = 0;
    *(_OWORD *)&v6[6].buf = 0;
    (*a2)[1].len = 3;
    HIDWORD((*a2)[2].buf) = 0;
    (*a2)[8].len = (ULONG)(*a2)[2].buf;
    (*a2)[8].buf = &(*a2)[1].buf[*(&(*a2)[2].len + 1)];
    StartThreadpoolIo(*((PTP_IO *)this + 17));
    if ( WSARecv(*((_QWORD *)this + 15), *a2 + 8, 1u, 0, (LPDWORD)&(*a2)[7].buf, (LPWSAOVERLAPPED)&(*a2)[5].buf, 0) == -1 )
    {
      Error = WSAGetLastError();
      len = Error;
      if ( Error == 997 )
      {
        v12 = 0;
      }
      else
      {
        (*a2)[3].len = Error;
        CancelThreadpoolIo(*((PTP_IO *)this + 17));
      }
    }
    else
    {
      NumberOfBytesTransferred = 0;
      CancelThreadpoolIo(*((PTP_IO *)this + 17));
      if ( GetOverlappedResult(*((HANDLE *)this + 15), (LPOVERLAPPED)&(*a2)[5].buf, &NumberOfBytesTransferred, 0) )
      {
        (*a2)[3].len = 0;
        HIDWORD((*a2)[2].buf) = NumberOfBytesTransferred;
        if ( !HIDWORD((*a2)[2].buf) )
          SocketTransport::GracefulDisconnect(this);
      }
      else
      {
        (*a2)[3].len = GetLastError();
      }
      len = (*a2)[3].len;
    }
    v5 = v12;
    wil::details::ScopeExitFnGuard__lambda_c58ba954e3836d9e17bcb8170eca299b___::operator()(v11);
  }
  else
  {
    (*a2)[3].len = 5023;
    NumberOfBytesTransferred = 0;
    ComputeService::Diagnostics::TraceProvider::SocketTransport_IoStart::Stop<unsigned long &,int>(
      v15,
      &(*a2)[3],
      &NumberOfBytesTransferred);
    *((_DWORD *)this + 52) = 0;
    ReleaseSRWLockExclusive((PSRWLOCK)this + 25);
  }
  v15[0] = &ComputeService::Diagnostics::TraceProvider::SocketTransport_IoStart::`vftable';
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v15);
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeService::Diagnostics::TraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>(v15);
  return v5;
}

```

## disassembly

```asm
0x140061d80  mov     [rsp-8+arg_10], rbx
0x140061d85  mov     [rsp-8+arg_18], rsi
0x140061d8a  push    rbp
0x140061d8b  push    rdi
0x140061d8c  push    r12
0x140061d8e  push    r14
0x140061d90  push    r15
0x140061d92  lea     rbp, [rsp-0F0h]
0x140061d9a  sub     rsp, 1F0h
0x140061da1  mov     rax, cs:__security_cookie
0x140061da8  xor     rax, rsp
0x140061dab  mov     [rbp+110h+var_30], rax
0x140061db2  mov     rdi, rdx
0x140061db5  mov     rsi, rcx
0x140061db8  xor     edx, edx; Val
0x140061dba  mov     r8d, 150h; Size
0x140061dc0  lea     rcx, [rbp+110h+var_180]; void *
0x140061dc4  call    memset_0
0x140061dc9  mov     rbx, [rdi]
0x140061dcc  mov     [rbp+110h+NumberOfBytesTransferred], 3
0x140061dd3  mov     [rsp+210h+var_1C8], rbx
0x140061dd8  mov     [rsp+210h+var_1D0], rsi
0x140061ddd  lea     rdx, aSockettranspor_4; "SocketTransport_IoStart"
0x140061de4  lea     rcx, [rbp+110h+var_180]
0x140061de8  call    ??0?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0CAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140061ded  lea     r12, ??_7SocketTransport_IoStart@TraceProvider@Diagnostics@ComputeService@@6B@; const ComputeService::Diagnostics::TraceProvider::SocketTransport_IoStart::`vftable'
0x140061df4  mov     [rbp+110h+var_180], r12
0x140061df8  lea     rax, [rbx+28h]
0x140061dfc  mov     [rsp+210h+lpFlags], rax
0x140061e01  lea     r9, [rbp+110h+NumberOfBytesTransferred]
0x140061e05  lea     r8, [rsp+210h+var_1C8]
0x140061e0a  lea     rdx, [rsp+210h+var_1D0]
0x140061e0f  lea     rcx, [rbp+110h+var_180]
0x140061e13  call    ??$StartActivity@PEAVSocketTransport@@PEAVTransportIoContext@@IAEAK@SocketTransport_IoStart@TraceProvider@Diagnostics@ComputeService@@QEAAX$$QEAPEAVSocketTransport@@$$QEAPEAVTransportIoContext@@$$QEAIAEAK@Z; ComputeService::Diagnostics::TraceProvider::SocketTransport_IoStart::StartActivity<SocketTransport *,TransportIoContext *,uint,ulong &>(SocketTransport * &&,TransportIoContext * &&,uint &&,ulong &)
0x140061e18  nop
0x140061e19  lea     r14, [rsi+0C8h]
0x140061e20  mov     rcx, r14; SRWLock
0x140061e23  call    cs:__imp_AcquireSRWLockExclusive
0x140061e29  call    cs:__imp_GetCurrentThreadId
0x140061e2f  mov     [r14+8], eax
0x140061e33  mov     [rsp+210h+var_1D0], r14
0x140061e38  mov     eax, [rsi+0E4h]
0x140061e3e  sub     eax, 6
0x140061e41  mov     r15d, 1
0x140061e47  cmp     eax, r15d
0x140061e4a  jbe     short loc_140061E82
0x140061e4c  mov     rax, [rdi]
0x140061e4f  mov     dword ptr [rax+30h], 139Fh
0x140061e56  xor     ebx, ebx
0x140061e58  mov     [rbp+110h+NumberOfBytesTransferred], ebx
0x140061e5b  mov     rdx, [rdi]
0x140061e5e  add     rdx, 30h ; '0'
0x140061e62  lea     r8, [rbp+110h+NumberOfBytesTransferred]
0x140061e66  lea     rcx, [rbp+110h+var_180]
0x140061e6a  call    ??$Stop@AEAKH@SocketTransport_IoStart@TraceProvider@Diagnostics@ComputeService@@QEAAXAEAK$$QEAH@Z; ComputeService::Diagnostics::TraceProvider::SocketTransport_IoStart::Stop<ulong &,int>(ulong &,int &&)
0x140061e6f  nop
0x140061e70  mov     [r14+8], ebx
0x140061e74  mov     rcx, r14; SRWLock
0x140061e77  call    cs:__imp_ReleaseSRWLockExclusive
0x140061e7d  jmp     loc_140062000
0x140061e82  mov     rdx, rdi
0x140061e85  mov     rcx, rsi
0x140061e88  call    ?MapAdd@SocketTransport@@AEAAXAEBV?$shared_ptr@VTransportIoContext@@@std@@@Z; SocketTransport::MapAdd(std::shared_ptr<TransportIoContext> const &)
0x140061e8d  nop
0x140061e8e  xor     ebx, ebx
0x140061e90  mov     [r14+8], ebx
0x140061e94  mov     rcx, r14; SRWLock
0x140061e97  call    cs:__imp_ReleaseSRWLockExclusive
0x140061e9d  or      ecx, 0FFFFFFFFh
0x140061ea0  mov     [rbp+110h+var_188], ecx
0x140061ea3  mov     [rbp+110h+var_190], r15b
0x140061ea7  xorps   xmm0, xmm0
0x140061eaa  movups  [rsp+210h+var_1C0], xmm0
0x140061eaf  movups  [rsp+210h+var_1B0], xmm0
0x140061eb4  movups  [rsp+210h+var_1A0], xmm0
0x140061eb9  mov     qword ptr [rsp+210h+var_1C0], rsi
0x140061ebe  lea     rax, [rbp+110h+var_190]
0x140061ec2  mov     qword ptr [rsp+210h+var_1C0+8], rax
0x140061ec7  mov     qword ptr [rsp+210h+var_1B0], rdi
0x140061ecc  lea     rax, [rbp+110h+var_180]
0x140061ed0  mov     qword ptr [rsp+210h+var_1B0+8], rax
0x140061ed5  lea     rax, [rbp+110h+var_188]
0x140061ed9  mov     qword ptr [rsp+210h+var_1A0], rax
0x140061ede  mov     word ptr [rsp+210h+var_1A0+8], 100h
0x140061ee5  mov     rax, [rdi]
0x140061ee8  mov     [rax+30h], ecx
0x140061eeb  mov     rax, [rdi]
0x140061eee  movups  xmmword ptr [rax+58h], xmm0
0x140061ef2  movups  xmmword ptr [rax+68h], xmm0
0x140061ef6  mov     rax, [rdi]
0x140061ef9  mov     dword ptr [rax+10h], 3
0x140061f00  mov     rax, [rdi]
0x140061f03  mov     [rax+2Ch], ebx
0x140061f06  mov     rcx, [rdi]
0x140061f09  mov     eax, [rcx+28h]
0x140061f0c  mov     [rcx+80h], eax
0x140061f12  mov     rcx, [rdi]
0x140061f15  mov     eax, [rcx+24h]
0x140061f18  add     rax, [rcx+18h]
0x140061f1c  mov     [rcx+88h], rax
0x140061f23  mov     rcx, [rsi+88h]; pio
0x140061f2a  call    cs:__imp_StartThreadpoolIo
0x140061f30  mov     rdx, [rdi]
0x140061f33  lea     rax, [rdx+58h]
0x140061f37  lea     rcx, [rdx+78h]
0x140061f3b  sub     rdx, 0FFFFFFFFFFFFFF80h; lpBuffers
0x140061f3f  mov     [rsp+210h+lpCompletionRoutine], rbx; lpCompletionRoutine
0x140061f44  mov     [rsp+210h+lpOverlapped], rax; lpOverlapped
0x140061f49  mov     [rsp+210h+lpFlags], rcx; lpFlags
0x140061f4e  xor     r9d, r9d; lpNumberOfBytesRecvd
0x140061f51  mov     r8d, r15d; dwBufferCount
0x140061f54  mov     rcx, [rsi+78h]; s
0x140061f58  call    cs:__imp_WSARecv
0x140061f5e  cmp     eax, 0FFFFFFFFh
0x140061f61  jnz     short loc_140061F8F
0x140061f63  call    cs:__imp_WSAGetLastError
0x140061f69  mov     ecx, eax
0x140061f6b  mov     [rbp+110h+var_188], eax
0x140061f6e  cmp     eax, 3E5h
0x140061f73  jnz     short loc_140061F7A
0x140061f75  mov     [rbp+110h+var_190], bl
0x140061f78  jmp     short loc_140061FF1
0x140061f7a  mov     rax, [rdi]
0x140061f7d  mov     [rax+30h], ecx
0x140061f80  mov     rcx, [rsi+88h]; pio
0x140061f87  call    cs:__imp_CancelThreadpoolIo
0x140061f8d  jmp     short loc_140061FF1
0x140061f8f  mov     [rbp+110h+NumberOfBytesTransferred], ebx
0x140061f92  mov     rcx, [rsi+88h]; pio
0x140061f99  call    cs:__imp_CancelThreadpoolIo
0x140061f9f  mov     rdx, [rdi]
0x140061fa2  add     rdx, 58h ; 'X'; lpOverlapped
0x140061fa6  xor     r9d, r9d; bWait
0x140061fa9  lea     r8, [rbp+110h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x140061fad  mov     rcx, [rsi+78h]; hFile
0x140061fb1  call    cs:__imp_GetOverlappedResult
0x140061fb7  test    eax, eax
0x140061fb9  jz      short loc_140061FDC
0x140061fbb  mov     rax, [rdi]
0x140061fbe  mov     [rax+30h], ebx
0x140061fc1  mov     rdx, [rdi]
0x140061fc4  mov     eax, [rbp+110h+NumberOfBytesTransferred]
0x140061fc7  mov     [rdx+2Ch], eax
0x140061fca  mov     rax, [rdi]
0x140061fcd  cmp     [rax+2Ch], ebx
0x140061fd0  jnz     short loc_140061FE8
0x140061fd2  mov     rcx, rsi; this
0x140061fd5  call    ?GracefulDisconnect@SocketTransport@@AEAAXXZ; SocketTransport::GracefulDisconnect(void)
0x140061fda  jmp     short loc_140061FE8
0x140061fdc  call    cs:__imp_GetLastError
0x140061fe2  mov     rcx, [rdi]
0x140061fe5  mov     [rcx+30h], eax
0x140061fe8  mov     rax, [rdi]
0x140061feb  mov     ecx, [rax+30h]
0x140061fee  mov     [rbp+110h+var_188], ecx
0x140061ff1  mov     r15b, [rbp+110h+var_190]
0x140061ff5  lea     rcx, [rsp+210h+var_1C0]
0x140061ffa  call    wil__details__ScopeExitFnGuard__lambda_c58ba954e3836d9e17bcb8170eca299b_____operator__
0x140061fff  nop
0x140062000  mov     [rbp+110h+var_180], r12
0x140062004  lea     rcx, [rbp+110h+var_180]
0x140062008  call    ?Destroy@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0CAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x14006200d  lea     rcx, [rbp+110h+var_180]
0x140062011  call    ??1?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0CAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeService::Diagnostics::TraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x140062016  mov     al, r15b
0x140062019  mov     rcx, [rbp+110h+var_30]
0x140062020  xor     rcx, rsp; StackCookie
0x140062023  call    __security_check_cookie
0x140062028  lea     r11, [rsp+210h+var_20]
0x140062030  mov     rbx, [r11+40h]
0x140062034  mov     rsi, [r11+48h]
0x140062038  mov     rsp, r11
0x14006203b  pop     r15
0x14006203d  pop     r14
0x14006203f  pop     r12
0x140062041  pop     rdi
0x140062042  pop     rbp
0x140062043  retn
```
