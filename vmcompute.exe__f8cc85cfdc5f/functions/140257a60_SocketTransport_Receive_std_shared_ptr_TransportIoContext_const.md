# SocketTransport::Receive(std::shared_ptr<TransportIoContext> const &)

- ea: `0x140257a60`
- end: `0x140257d3f`
- name: `?Receive@SocketTransport@@UEAA_NAEBV?$shared_ptr@VTransportIoContext@@@std@@@Z`
- size: `735`
- prototype: `__int64 __fastcall(SocketTransport *this)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x140022ca0`
- `0x140024fa8`
- `0x14004c898`
- `0x14006cc98`
- `0x1400de86c`
- `0x140103228`
- `0x1401332f0`
- `0x140134048`
- `0x14025730c`
- `0x140257a60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140257b34`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140257b5c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140257b34`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140257b5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140257ce0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140257ce0`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x140257bf9`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x140257bf9`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x140257c70`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x140257c8c`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x140257c70`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x140257c8c`
- `WS2_32!WSARecv` at `0x140257c31`
- `WS2_32!WSARecv` at `0x140257c31`
- `WS2_32!__imp_WSAGetLastError` at `0x140257c42`
- `WS2_32!__imp_WSAGetLastError` at `0x140257c42`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x140257caa`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x140257caa`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall SocketTransport::Receive(SocketTransport *this, struct _WSABUF **a2)
{
  struct _WSABUF *v4; // rax
  char v5; // r15
  struct _WSABUF *v6; // rax
  int Error; // ecx
  SocketTransport *v9; // [rsp+40h] [rbp-C0h] BYREF
  struct _WSABUF *v10; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v11[6]; // [rsp+50h] [rbp-B0h] BYREF
  char v12; // [rsp+80h] [rbp-80h] BYREF
  DWORD NumberOfBytesTransferred; // [rsp+84h] [rbp-7Ch] BYREF
  int len; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v15[336]; // [rsp+90h] [rbp-70h] BYREF

  memset_0(v15, 0, sizeof(v15));
  v4 = *a2;
  NumberOfBytesTransferred = 3;
  v10 = v4;
  v9 = this;
  ComputeService::Diagnostics::TraceProvider::SocketTransport_IoStart::Start<SocketTransport *,TransportIoContext *,unsigned int,unsigned long &>(
    (unsigned int)v15,
    (unsigned int)&v9,
    (unsigned int)&v10,
    (unsigned int)&NumberOfBytesTransferred,
    (__int64)&v4[2].buf);
  Vml::VmSlimReaderWriterLock::AcquireExclusive((SocketTransport *)((char *)this + 200));
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
  ComputeService::Diagnostics::TraceProvider::SocketTransport_IoStart::~SocketTransport_IoStart((ComputeService::Diagnostics::TraceProvider::SocketTransport_IoStart *)v15);
  return v5;
}

```

## disassembly

```asm
0x140257a60  mov     [rsp-8+arg_10], rbx
0x140257a65  mov     [rsp-8+arg_18], rsi
0x140257a6a  push    rbp
0x140257a6b  push    r14
0x140257a6d  push    r15
0x140257a6f  lea     rbp, [rsp-0F0h]
0x140257a77  sub     rsp, 1F0h
0x140257a7e  mov     rax, cs:__security_cookie
0x140257a85  xor     rax, rsp
0x140257a88  mov     [rbp+100h+var_20], rax
0x140257a8f  mov     rbx, rdx
0x140257a92  mov     rsi, rcx
0x140257a95  xor     edx, edx; Val
0x140257a97  mov     r8d, 150h; Size
0x140257a9d  lea     rcx, [rbp+100h+var_170]; void *
0x140257aa1  call    memset_0
0x140257aa6  mov     rax, [rbx]
0x140257aa9  mov     [rbp+100h+NumberOfBytesTransferred], 3
0x140257ab0  mov     [rsp+200h+var_1B8], rax
0x140257ab5  mov     [rsp+200h+var_1C0], rsi
0x140257aba  add     rax, 28h ; '('
0x140257abe  mov     [rsp+200h+lpFlags], rax
0x140257ac3  lea     r9, [rbp+100h+NumberOfBytesTransferred]
0x140257ac7  lea     r8, [rsp+200h+var_1B8]
0x140257acc  lea     rdx, [rsp+200h+var_1C0]
0x140257ad1  lea     rcx, [rbp+100h+var_170]
0x140257ad5  call    ??$Start@PEAVSocketTransport@@PEAVTransportIoContext@@IAEAK@SocketTransport_IoStart@TraceProvider@Diagnostics@ComputeService@@SA?AV0123@$$QEAPEAVSocketTransport@@$$QEAPEAVTransportIoContext@@$$QEAIAEAK@Z; ComputeService::Diagnostics::TraceProvider::SocketTransport_IoStart::Start<SocketTransport *,TransportIoContext *,uint,ulong &>(SocketTransport * &&,TransportIoContext * &&,uint &&,ulong &)
0x140257ada  nop
0x140257adb  lea     r14, [rsi+0C8h]
0x140257ae2  mov     rcx, r14; this
0x140257ae5  call    ?AcquireExclusive@VmSlimReaderWriterLock@Vml@@QEAAXXZ; Vml::VmSlimReaderWriterLock::AcquireExclusive(void)
0x140257aea  mov     [rsp+200h+var_1C0], r14
0x140257aef  mov     eax, [rsi+0E4h]
0x140257af5  sub     eax, 6
0x140257af8  mov     r15d, 1
0x140257afe  cmp     eax, r15d
0x140257b01  jbe     short loc_140257B45
0x140257b03  mov     rax, [rbx]
0x140257b06  mov     dword ptr [rax+30h], 139Fh
0x140257b0d  mov     [rbp+100h+NumberOfBytesTransferred], 0
0x140257b14  mov     rdx, [rbx]
0x140257b17  add     rdx, 30h ; '0'
0x140257b1b  lea     r8, [rbp+100h+NumberOfBytesTransferred]
0x140257b1f  lea     rcx, [rbp+100h+var_170]
0x140257b23  call    ??$Stop@AEAKH@SocketTransport_IoStart@TraceProvider@Diagnostics@ComputeService@@QEAAXAEAK$$QEAH@Z; ComputeService::Diagnostics::TraceProvider::SocketTransport_IoStart::Stop<ulong &,int>(ulong &,int &&)
0x140257b28  nop
0x140257b29  mov     dword ptr [r14+8], 0
0x140257b31  mov     rcx, r14; SRWLock
0x140257b34  call    cs:__imp_ReleaseSRWLockExclusive
0x140257b3b  nop     dword ptr [rax+rax+00h]
0x140257b40  jmp     loc_140257D0A
0x140257b45  mov     rdx, rbx
0x140257b48  mov     rcx, rsi
0x140257b4b  call    ?MapAdd@SocketTransport@@AEAAXAEBV?$shared_ptr@VTransportIoContext@@@std@@@Z; SocketTransport::MapAdd(std::shared_ptr<TransportIoContext> const &)
0x140257b50  nop
0x140257b51  mov     dword ptr [r14+8], 0
0x140257b59  mov     rcx, r14; SRWLock
0x140257b5c  call    cs:__imp_ReleaseSRWLockExclusive
0x140257b63  nop     dword ptr [rax+rax+00h]
0x140257b68  or      ecx, 0FFFFFFFFh
0x140257b6b  mov     [rbp+100h+var_178], ecx
0x140257b6e  mov     [rbp+100h+var_180], r15b
0x140257b72  xorps   xmm0, xmm0
0x140257b75  movups  [rsp+200h+var_1B0], xmm0
0x140257b7a  movups  [rsp+200h+var_1A0], xmm0
0x140257b7f  movups  [rsp+200h+var_190], xmm0
0x140257b84  mov     qword ptr [rsp+200h+var_1B0], rsi
0x140257b89  lea     rax, [rbp+100h+var_180]
0x140257b8d  mov     qword ptr [rsp+200h+var_1B0+8], rax
0x140257b92  mov     qword ptr [rsp+200h+var_1A0], rbx
0x140257b97  lea     rax, [rbp+100h+var_170]
0x140257b9b  mov     qword ptr [rsp+200h+var_1A0+8], rax
0x140257ba0  lea     rax, [rbp+100h+var_178]
0x140257ba4  mov     qword ptr [rsp+200h+var_190], rax
0x140257ba9  mov     word ptr [rsp+200h+var_190+8], 100h
0x140257bb0  mov     rax, [rbx]
0x140257bb3  mov     [rax+30h], ecx
0x140257bb6  mov     rax, [rbx]
0x140257bb9  movups  xmmword ptr [rax+58h], xmm0
0x140257bbd  movups  xmmword ptr [rax+68h], xmm0
0x140257bc1  mov     rax, [rbx]
0x140257bc4  mov     dword ptr [rax+10h], 3
0x140257bcb  mov     rax, [rbx]
0x140257bce  mov     dword ptr [rax+2Ch], 0
0x140257bd5  mov     rcx, [rbx]
0x140257bd8  mov     eax, [rcx+28h]
0x140257bdb  mov     [rcx+80h], eax
0x140257be1  mov     rcx, [rbx]
0x140257be4  mov     eax, [rcx+24h]
0x140257be7  add     rax, [rcx+18h]
0x140257beb  mov     [rcx+88h], rax
0x140257bf2  mov     rcx, [rsi+88h]; pio
0x140257bf9  call    cs:__imp_StartThreadpoolIo
0x140257c00  nop     dword ptr [rax+rax+00h]
0x140257c05  mov     rdx, [rbx]
0x140257c08  lea     rax, [rdx+58h]
0x140257c0c  lea     rcx, [rdx+78h]
0x140257c10  sub     rdx, 0FFFFFFFFFFFFFF80h; lpBuffers
0x140257c14  mov     [rsp+200h+lpCompletionRoutine], 0; lpCompletionRoutine
0x140257c1d  mov     [rsp+200h+lpOverlapped], rax; lpOverlapped
0x140257c22  mov     [rsp+200h+lpFlags], rcx; lpFlags
0x140257c27  xor     r9d, r9d; lpNumberOfBytesRecvd
0x140257c2a  mov     r8d, r15d; dwBufferCount
0x140257c2d  mov     rcx, [rsi+78h]; s
0x140257c31  call    cs:__imp_WSARecv
0x140257c38  nop     dword ptr [rax+rax+00h]
0x140257c3d  cmp     eax, 0FFFFFFFFh
0x140257c40  jnz     short loc_140257C7E
0x140257c42  call    cs:__imp_WSAGetLastError
0x140257c49  nop     dword ptr [rax+rax+00h]
0x140257c4e  mov     ecx, eax
0x140257c50  mov     [rbp+100h+var_178], eax
0x140257c53  cmp     eax, 3E5h
0x140257c58  jnz     short loc_140257C63
0x140257c5a  mov     [rbp+100h+var_180], 0
0x140257c5e  jmp     loc_140257CFB
0x140257c63  mov     rax, [rbx]
0x140257c66  mov     [rax+30h], ecx
0x140257c69  mov     rcx, [rsi+88h]; pio
0x140257c70  call    cs:__imp_CancelThreadpoolIo
0x140257c77  nop     dword ptr [rax+rax+00h]
0x140257c7c  jmp     short loc_140257CFB
0x140257c7e  mov     [rbp+100h+NumberOfBytesTransferred], 0
0x140257c85  mov     rcx, [rsi+88h]; pio
0x140257c8c  call    cs:__imp_CancelThreadpoolIo
0x140257c93  nop     dword ptr [rax+rax+00h]
0x140257c98  mov     rdx, [rbx]
0x140257c9b  add     rdx, 58h ; 'X'; lpOverlapped
0x140257c9f  xor     r9d, r9d; bWait
0x140257ca2  lea     r8, [rbp+100h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x140257ca6  mov     rcx, [rsi+78h]; hFile
0x140257caa  call    cs:__imp_GetOverlappedResult
0x140257cb1  nop     dword ptr [rax+rax+00h]
0x140257cb6  test    eax, eax
0x140257cb8  jz      short loc_140257CE0
0x140257cba  mov     rax, [rbx]
0x140257cbd  mov     dword ptr [rax+30h], 0
0x140257cc4  mov     rdx, [rbx]
0x140257cc7  mov     eax, [rbp+100h+NumberOfBytesTransferred]
0x140257cca  mov     [rdx+2Ch], eax
0x140257ccd  mov     rax, [rbx]
0x140257cd0  cmp     dword ptr [rax+2Ch], 0
0x140257cd4  jnz     short loc_140257CF2
0x140257cd6  mov     rcx, rsi; this
0x140257cd9  call    ?GracefulDisconnect@SocketTransport@@AEAAXXZ; SocketTransport::GracefulDisconnect(void)
0x140257cde  jmp     short loc_140257CF2
0x140257ce0  call    cs:__imp_GetLastError
0x140257ce7  nop     dword ptr [rax+rax+00h]
0x140257cec  mov     rcx, [rbx]
0x140257cef  mov     [rcx+30h], eax
0x140257cf2  mov     rax, [rbx]
0x140257cf5  mov     ecx, [rax+30h]
0x140257cf8  mov     [rbp+100h+var_178], ecx
0x140257cfb  mov     r15b, [rbp+100h+var_180]
0x140257cff  lea     rcx, [rsp+200h+var_1B0]
0x140257d04  call    wil__details__ScopeExitFnGuard__lambda_c58ba954e3836d9e17bcb8170eca299b_____operator__
0x140257d09  nop
0x140257d0a  lea     rcx, [rbp+100h+var_170]; this
0x140257d0e  call    ??1SocketTransport_IoStart@TraceProvider@Diagnostics@ComputeService@@QEAA@XZ; ComputeService::Diagnostics::TraceProvider::SocketTransport_IoStart::~SocketTransport_IoStart(void)
0x140257d13  mov     al, r15b
0x140257d16  mov     rcx, [rbp+100h+var_20]
0x140257d1d  xor     rcx, rsp; StackCookie
0x140257d20  call    __security_check_cookie
0x140257d25  lea     r11, [rsp+200h+var_10]
0x140257d2d  mov     rbx, [r11+30h]
0x140257d31  mov     rsi, [r11+38h]
0x140257d35  mov     rsp, r11
0x140257d38  pop     r15
0x140257d3a  pop     r14
0x140257d3c  pop     rbp
0x140257d3d  retn
```
