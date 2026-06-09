# SocketTransport::Send(std::shared_ptr<TransportIoContext> const &)

- ea: `0x140257d50`
- end: `0x140257ff4`
- name: `?Send@SocketTransport@@UEAA_NAEBV?$shared_ptr@VTransportIoContext@@@std@@@Z`
- size: `676`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x140022ca0`
- `0x1400249bc`
- `0x14004c898`
- `0x14006cc98`
- `0x1400de86c`
- `0x140103228`
- `0x1401332f0`
- `0x140134048`
- `0x140257d50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140257e1b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140257e41`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140257e1b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140257e41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140257f97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140257f97`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x140257ed4`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x140257ed4`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x140257f40`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x140257f58`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x140257f40`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x140257f58`
- `WS2_32!WSASend` at `0x140257f04`
- `WS2_32!WSASend` at `0x140257f04`
- `WS2_32!__imp_WSAGetLastError` at `0x140257f15`
- `WS2_32!__imp_WSAGetLastError` at `0x140257f15`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x140257f76`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x140257f76`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall SocketTransport::Send(__int64 a1, struct _WSABUF **a2)
{
  struct _WSABUF *v4; // rax
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
  _BYTE v18[336]; // [rsp+90h] [rbp-70h] BYREF

  memset_0(v18, 0, sizeof(v18));
  v4 = *a2;
  NumberOfBytesTransferred = 2;
  v10 = v4;
  v9 = a1;
  ComputeService::Diagnostics::TraceProvider::SocketTransport_IoStart::Start<SocketTransport *,TransportIoContext *,unsigned int,unsigned long &>(
    (unsigned int)v18,
    (unsigned int)&v9,
    (unsigned int)&v10,
    (unsigned int)&NumberOfBytesTransferred,
    (__int64)&v4[2].buf);
  Vml::VmSlimReaderWriterLock::AcquireExclusive((Vml::VmSlimReaderWriterLock *)(a1 + 200));
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
  ComputeService::Diagnostics::TraceProvider::SocketTransport_IoStart::~SocketTransport_IoStart((ComputeService::Diagnostics::TraceProvider::SocketTransport_IoStart *)v18);
  return v5;
}

```

## disassembly

```asm
0x140257d50  mov     [rsp-8+arg_10], rbx
0x140257d55  push    rbp
0x140257d56  push    rsi
0x140257d57  push    rdi
0x140257d58  push    r14
0x140257d5a  push    r15
0x140257d5c  lea     rbp, [rsp-0F0h]
0x140257d64  sub     rsp, 1F0h
0x140257d6b  mov     rax, cs:__security_cookie
0x140257d72  xor     rax, rsp
0x140257d75  mov     [rbp+110h+var_30], rax
0x140257d7c  mov     rbx, rdx
0x140257d7f  mov     rsi, rcx
0x140257d82  xor     edx, edx; Val
0x140257d84  mov     r8d, 150h; Size
0x140257d8a  lea     rcx, [rbp+110h+var_180]; void *
0x140257d8e  call    memset_0
0x140257d93  mov     rax, [rbx]
0x140257d96  mov     [rbp+110h+NumberOfBytesTransferred], 2
0x140257d9d  mov     [rsp+210h+var_1C8], rax
0x140257da2  mov     [rsp+210h+var_1D0], rsi
0x140257da7  add     rax, 28h ; '('
0x140257dab  mov     qword ptr [rsp+210h+dwFlags], rax
0x140257db0  lea     r9, [rbp+110h+NumberOfBytesTransferred]
0x140257db4  lea     r8, [rsp+210h+var_1C8]
0x140257db9  lea     rdx, [rsp+210h+var_1D0]
0x140257dbe  lea     rcx, [rbp+110h+var_180]
0x140257dc2  call    ??$Start@PEAVSocketTransport@@PEAVTransportIoContext@@IAEAK@SocketTransport_IoStart@TraceProvider@Diagnostics@ComputeService@@SA?AV0123@$$QEAPEAVSocketTransport@@$$QEAPEAVTransportIoContext@@$$QEAIAEAK@Z; ComputeService::Diagnostics::TraceProvider::SocketTransport_IoStart::Start<SocketTransport *,TransportIoContext *,uint,ulong &>(SocketTransport * &&,TransportIoContext * &&,uint &&,ulong &)
0x140257dc7  nop
0x140257dc8  lea     r14, [rsi+0C8h]
0x140257dcf  mov     rcx, r14; this
0x140257dd2  call    ?AcquireExclusive@VmSlimReaderWriterLock@Vml@@QEAAXXZ; Vml::VmSlimReaderWriterLock::AcquireExclusive(void)
0x140257dd7  mov     [rsp+210h+var_1D0], r14
0x140257ddc  mov     eax, [rsi+0E4h]
0x140257de2  sub     eax, 6
0x140257de5  mov     r15d, 1
0x140257deb  cmp     eax, r15d
0x140257dee  jbe     short loc_140257E2C
0x140257df0  mov     rax, [rbx]
0x140257df3  mov     dword ptr [rax+30h], 139Fh
0x140257dfa  xor     edi, edi
0x140257dfc  mov     [rbp+110h+NumberOfBytesTransferred], edi
0x140257dff  mov     rdx, [rbx]
0x140257e02  add     rdx, 30h ; '0'
0x140257e06  lea     r8, [rbp+110h+NumberOfBytesTransferred]
0x140257e0a  lea     rcx, [rbp+110h+var_180]
0x140257e0e  call    ??$Stop@AEAKH@SocketTransport_IoStart@TraceProvider@Diagnostics@ComputeService@@QEAAXAEAK$$QEAH@Z; ComputeService::Diagnostics::TraceProvider::SocketTransport_IoStart::Stop<ulong &,int>(ulong &,int &&)
0x140257e13  nop
0x140257e14  mov     [r14+8], edi
0x140257e18  mov     rcx, r14; SRWLock
0x140257e1b  call    cs:__imp_ReleaseSRWLockExclusive
0x140257e22  nop     dword ptr [rax+rax+00h]
0x140257e27  jmp     loc_140257FC1
0x140257e2c  mov     rdx, rbx
0x140257e2f  mov     rcx, rsi
0x140257e32  call    ?MapAdd@SocketTransport@@AEAAXAEBV?$shared_ptr@VTransportIoContext@@@std@@@Z; SocketTransport::MapAdd(std::shared_ptr<TransportIoContext> const &)
0x140257e37  nop
0x140257e38  xor     edi, edi
0x140257e3a  mov     [r14+8], edi
0x140257e3e  mov     rcx, r14; SRWLock
0x140257e41  call    cs:__imp_ReleaseSRWLockExclusive
0x140257e48  nop     dword ptr [rax+rax+00h]
0x140257e4d  or      ecx, 0FFFFFFFFh
0x140257e50  mov     [rbp+110h+var_188], ecx
0x140257e53  mov     [rbp+110h+var_190], r15b
0x140257e57  mov     [rsp+210h+var_196], edi
0x140257e5b  mov     [rsp+210h+var_192], di
0x140257e60  mov     [rsp+210h+var_1C0], rsi
0x140257e65  lea     rax, [rbp+110h+var_190]
0x140257e69  mov     [rsp+210h+var_1B8], rax
0x140257e6e  mov     [rsp+210h+var_1B0], rbx
0x140257e73  lea     rax, [rbp+110h+var_180]
0x140257e77  mov     [rsp+210h+var_1A8], rax
0x140257e7c  lea     rax, [rbp+110h+var_188]
0x140257e80  mov     [rsp+210h+var_1A0], rax
0x140257e85  mov     [rsp+210h+var_198], 100h
0x140257e8c  mov     rax, [rbx]
0x140257e8f  mov     [rax+30h], ecx
0x140257e92  mov     rax, [rbx]
0x140257e95  xorps   xmm0, xmm0
0x140257e98  movups  xmmword ptr [rax+58h], xmm0
0x140257e9c  movups  xmmword ptr [rax+68h], xmm0
0x140257ea0  mov     rax, [rbx]
0x140257ea3  mov     dword ptr [rax+10h], 2
0x140257eaa  mov     rax, [rbx]
0x140257ead  mov     [rax+2Ch], edi
0x140257eb0  mov     rcx, [rbx]
0x140257eb3  mov     eax, [rcx+28h]
0x140257eb6  mov     [rcx+80h], eax
0x140257ebc  mov     rcx, [rbx]
0x140257ebf  mov     eax, [rcx+24h]
0x140257ec2  add     rax, [rcx+18h]
0x140257ec6  mov     [rcx+88h], rax
0x140257ecd  mov     rcx, [rsi+88h]; pio
0x140257ed4  call    cs:__imp_StartThreadpoolIo
0x140257edb  nop     dword ptr [rax+rax+00h]
0x140257ee0  mov     rdx, [rbx]
0x140257ee3  lea     rax, [rdx+58h]
0x140257ee7  lea     r9, [rdx+2Ch]; lpNumberOfBytesSent
0x140257eeb  sub     rdx, 0FFFFFFFFFFFFFF80h; lpBuffers
0x140257eef  mov     [rsp+210h+lpCompletionRoutine], rdi; lpCompletionRoutine
0x140257ef4  mov     [rsp+210h+lpOverlapped], rax; lpOverlapped
0x140257ef9  mov     [rsp+210h+dwFlags], edi; dwFlags
0x140257efd  mov     r8d, r15d; dwBufferCount
0x140257f00  mov     rcx, [rsi+78h]; s
0x140257f04  call    cs:__imp_WSASend
0x140257f0b  nop     dword ptr [rax+rax+00h]
0x140257f10  cmp     eax, 0FFFFFFFFh
0x140257f13  jnz     short loc_140257F4E
0x140257f15  call    cs:__imp_WSAGetLastError
0x140257f1c  nop     dword ptr [rax+rax+00h]
0x140257f21  mov     ecx, eax
0x140257f23  mov     [rbp+110h+var_188], eax
0x140257f26  cmp     eax, 3E5h
0x140257f2b  jnz     short loc_140257F33
0x140257f2d  mov     [rbp+110h+var_190], dil
0x140257f31  jmp     short loc_140257FB2
0x140257f33  mov     rax, [rbx]
0x140257f36  mov     [rax+30h], ecx
0x140257f39  mov     rcx, [rsi+88h]; pio
0x140257f40  call    cs:__imp_CancelThreadpoolIo
0x140257f47  nop     dword ptr [rax+rax+00h]
0x140257f4c  jmp     short loc_140257FB2
0x140257f4e  mov     [rbp+110h+NumberOfBytesTransferred], edi
0x140257f51  mov     rcx, [rsi+88h]; pio
0x140257f58  call    cs:__imp_CancelThreadpoolIo
0x140257f5f  nop     dword ptr [rax+rax+00h]
0x140257f64  mov     rdx, [rbx]
0x140257f67  add     rdx, 58h ; 'X'; lpOverlapped
0x140257f6b  xor     r9d, r9d; bWait
0x140257f6e  lea     r8, [rbp+110h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x140257f72  mov     rcx, [rsi+78h]; hFile
0x140257f76  call    cs:__imp_GetOverlappedResult
0x140257f7d  nop     dword ptr [rax+rax+00h]
0x140257f82  test    eax, eax
0x140257f84  jz      short loc_140257F97
0x140257f86  mov     rax, [rbx]
0x140257f89  mov     [rax+30h], edi
0x140257f8c  mov     rcx, [rbx]
0x140257f8f  mov     eax, [rbp+110h+NumberOfBytesTransferred]
0x140257f92  mov     [rcx+2Ch], eax
0x140257f95  jmp     short loc_140257FA9
0x140257f97  call    cs:__imp_GetLastError
0x140257f9e  nop     dword ptr [rax+rax+00h]
0x140257fa3  mov     rcx, [rbx]
0x140257fa6  mov     [rcx+30h], eax
0x140257fa9  mov     rax, [rbx]
0x140257fac  mov     ecx, [rax+30h]
0x140257faf  mov     [rbp+110h+var_188], ecx
0x140257fb2  mov     r15b, [rbp+110h+var_190]
0x140257fb6  lea     rcx, [rsp+210h+var_1C0]
0x140257fbb  call    wil__details__ScopeExitFnGuard__lambda_2fccbc412e22120968854e70a899f1ef_____operator__
0x140257fc0  nop
0x140257fc1  lea     rcx, [rbp+110h+var_180]; this
0x140257fc5  call    ??1SocketTransport_IoStart@TraceProvider@Diagnostics@ComputeService@@QEAA@XZ; ComputeService::Diagnostics::TraceProvider::SocketTransport_IoStart::~SocketTransport_IoStart(void)
0x140257fca  mov     al, r15b
0x140257fcd  mov     rcx, [rbp+110h+var_30]
0x140257fd4  xor     rcx, rsp; StackCookie
0x140257fd7  call    __security_check_cookie
0x140257fdc  mov     rbx, [rsp+210h+arg_10]
0x140257fe4  add     rsp, 1F0h
0x140257feb  pop     r15
0x140257fed  pop     r14
0x140257fef  pop     rdi
0x140257ff0  pop     rsi
0x140257ff1  pop     rbp
0x140257ff2  retn
```
