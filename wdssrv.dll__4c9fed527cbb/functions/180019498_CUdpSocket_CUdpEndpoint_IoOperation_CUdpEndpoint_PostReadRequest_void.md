# CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>::PostReadRequest(void)

- ea: `0x180019498`
- end: `0x18001965f`
- name: `?PostReadRequest@?$CUdpSocket@VCUdpEndpoint@@U?$IoOperation@VCUdpEndpoint@@@@@@AEAAKXZ`
- size: `455`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800186f0`
- `0x180019434`

## callees

- `0x180003160`
- `0x180003944`
- `0x180018a14`
- `0x180019498`

## import_xrefs

- `KERNEL32!SetEvent` at `0x180019624`
- `KERNEL32!SetEvent` at `0x180019624`
- `WS2_32!WSARecvFrom` at `0x180019590`
- `WS2_32!WSARecvFrom` at `0x180019590`
- `WS2_32!__imp_WSAGetLastError` at `0x1800195a9`
- `WS2_32!__imp_WSAGetLastError` at `0x1800195c0`
- `WS2_32!__imp_WSAGetLastError` at `0x1800195a9`
- `WS2_32!__imp_WSAGetLastError` at `0x1800195c0`
- `WdsServerCommonLib!?Allocate@CMemoryBuffer@@SAPEAV1@K@Z` at `0x1800194fe`
- `WdsServerCommonLib!?Allocate@CMemoryBuffer@@SAPEAV1@K@Z` at `0x1800194fe`
- `WdsServerCommonLib!?ReaderLock@CMRSWLock@@QEAAXXZ` at `0x180019601`
- `WdsServerCommonLib!?ReaderLock@CMRSWLock@@QEAAXXZ` at `0x180019601`
- `WdsServerCommonLib!?ReaderRelease@CMRSWLock@@QEAAXXZ` at `0x180019633`
- `WdsServerCommonLib!?ReaderRelease@CMRSWLock@@QEAAXXZ` at `0x180019633`

## pseudocode

```c
__int64 __fastcall CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>::PostReadRequest(__int64 a1)
{
  unsigned int v1; // ebx
  int v3; // ebp
  __int64 lpOverlapped; // rsi
  struct CMemoryBuffer *v5; // rax
  __int64 v6; // rdx
  int v7; // eax
  unsigned int Error; // eax
  __int64 v9; // rdx
  _WSABUF Buffers; // [rsp+50h] [rbp-18h] BYREF

  v1 = 0;
  Buffers = 0;
  v3 = 0;
  if ( (unsigned int)_InterlockedIncrement((volatile signed __int32 *)(a1 + 428)) > *(_DWORD *)(a1 + 72) )
    goto LABEL_16;
  lpOverlapped = CPool<IoOperation<CUdpEndpoint>>::GetObjectW(a1 + 432);
  if ( !lpOverlapped )
  {
    v1 = 8;
LABEL_16:
    _InterlockedDecrement((volatile signed __int32 *)(a1 + 428));
    return v1;
  }
  *(_QWORD *)(lpOverlapped + 32) = *(_QWORD *)(a1 + 48);
  *(_DWORD *)(lpOverlapped + 40) = 1;
  v5 = CMemoryBuffer::Allocate(*(_DWORD *)(a1 + 76));
  *(_QWORD *)(lpOverlapped + 48) = v5;
  if ( !v5 )
  {
    v1 = 8;
    goto LABEL_12;
  }
  Buffers.buf = (CHAR *)*((_QWORD *)v5 + 5);
  Buffers.len = *(_DWORD *)(*(_QWORD *)(lpOverlapped + 48) + 16LL);
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 480));
  if ( (unsigned int)ElValidateWin32(0, v6, "base\\Eco\\WDS\\wdslib\\net\\UdpSocket.h", 1758) )
    goto LABEL_16;
  *(_DWORD *)(lpOverlapped + 192) = 128;
  v7 = WSARecvFrom(
         *(_QWORD *)(a1 + 56),
         &Buffers,
         1u,
         0,
         (LPDWORD)(lpOverlapped + 56),
         (struct sockaddr *)(lpOverlapped + 64),
         (LPINT)(lpOverlapped + 192),
         (LPWSAOVERLAPPED)lpOverlapped,
         0);
  if ( v7 && (v7 != -1 || WSAGetLastError() != 997) )
  {
    Error = WSAGetLastError();
    v1 = ElValidateWin32(Error, v9, "base\\Eco\\WDS\\wdslib\\net\\UdpSocket.h", 1780);
    if ( !v1 )
      goto LABEL_16;
    v3 = 1;
LABEL_12:
    IoOperation<CUdpEndpoint>::Release(lpOverlapped);
    if ( v3 )
    {
      CMRSWLock::ReaderLock((CMRSWLock *)(a1 + 496));
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 480), 0xFFFFFFFF) == 1 )
        SetEvent(*(HANDLE *)(a1 + 488));
      CMRSWLock::ReaderRelease((CMRSWLock *)(a1 + 496));
    }
    goto LABEL_16;
  }
  return v1;
}

```

## disassembly

```asm
0x180019498  mov     rax, rsp
0x18001949b  mov     [rax+10h], rbx
0x18001949f  mov     [rax+18h], rbp
0x1800194a3  mov     [rax+20h], rsi
0x1800194a7  push    rdi
0x1800194a8  sub     rsp, 60h
0x1800194ac  xor     ebx, ebx
0x1800194ae  xorps   xmm0, xmm0
0x1800194b1  movups  xmmword ptr [rax-18h], xmm0
0x1800194b5  mov     rdi, rcx
0x1800194b8  xor     ebp, ebp
0x1800194ba  lea     eax, [rbx+1]
0x1800194bd  lock xadd [rcx+1ACh], eax
0x1800194c5  inc     eax
0x1800194c7  cmp     eax, [rcx+48h]
0x1800194ca  ja      loc_18001963F
0x1800194d0  add     rcx, 1B0h
0x1800194d7  call    ?GetObjectW@?$CPool@U?$IoOperation@VCUdpEndpoint@@@@@@QEAAPEAU?$IoOperation@VCUdpEndpoint@@@@H@Z; CPool<IoOperation<CUdpEndpoint>>::GetObjectW(int)
0x1800194dc  mov     rsi, rax
0x1800194df  test    rax, rax
0x1800194e2  jnz     short loc_1800194EC
0x1800194e4  lea     ebx, [rbp+8]
0x1800194e7  jmp     loc_18001963F
0x1800194ec  mov     rax, [rdi+30h]
0x1800194f0  mov     [rsi+20h], rax
0x1800194f4  mov     dword ptr [rsi+28h], 1
0x1800194fb  mov     ecx, [rdi+4Ch]
0x1800194fe  call    cs:__imp_?Allocate@CMemoryBuffer@@SAPEAV1@K@Z; CMemoryBuffer::Allocate(ulong)
0x180019505  nop     dword ptr [rax+rax+00h]
0x18001950a  mov     [rsi+30h], rax
0x18001950e  test    rax, rax
0x180019511  jnz     short loc_18001951B
0x180019513  lea     ebx, [rax+8]
0x180019516  jmp     loc_1800195EB
0x18001951b  mov     rax, [rax+28h]
0x18001951f  mov     [rsp+68h+Buffers.buf], rax
0x180019524  mov     rax, [rsi+30h]
0x180019528  mov     ecx, [rax+10h]
0x18001952b  mov     [rsp+68h+Buffers.len], ecx
0x18001952f  lock inc dword ptr [rdi+1E0h]
0x180019536  mov     r9d, 6DEh
0x18001953c  lea     r8, aBaseEcoWdsWdsl; "base\\Eco\\WDS\\wdslib\\net\\UdpSocket."...
0x180019543  xor     ecx, ecx
0x180019545  call    ElValidateWin32
0x18001954a  test    eax, eax
0x18001954c  jnz     loc_18001963F
0x180019552  and     [rsp+68h+var_28], rbx
0x180019557  lea     rdx, [rsi+0C0h]
0x18001955e  mov     [rsp+68h+lpOverlapped], rsi; lpOverlapped
0x180019563  lea     rax, [rsi+40h]
0x180019567  mov     [rsp+68h+lpFromlen], rdx; lpFromlen
0x18001956c  lea     rcx, [rsi+38h]
0x180019570  mov     dword ptr [rdx], 80h
0x180019576  xor     r9d, r9d; lpNumberOfBytesRecvd
0x180019579  mov     [rsp+68h+lpFrom], rax; lpFrom
0x18001957e  lea     rdx, [rsp+68h+Buffers]; lpBuffers
0x180019583  mov     [rsp+68h+lpFlags], rcx; lpFlags
0x180019588  mov     rcx, [rdi+38h]; s
0x18001958c  lea     r8d, [r9+1]; dwBufferCount
0x180019590  call    cs:__imp_WSARecvFrom
0x180019597  nop     dword ptr [rax+rax+00h]
0x18001959c  test    eax, eax
0x18001959e  jz      loc_180019646
0x1800195a4  cmp     eax, 0FFFFFFFFh
0x1800195a7  jnz     short loc_1800195C0
0x1800195a9  call    cs:__imp_WSAGetLastError
0x1800195b0  nop     dword ptr [rax+rax+00h]
0x1800195b5  cmp     eax, 3E5h
0x1800195ba  jz      loc_180019646
0x1800195c0  call    cs:__imp_WSAGetLastError
0x1800195c7  nop     dword ptr [rax+rax+00h]
0x1800195cc  mov     r9d, 6F4h
0x1800195d2  lea     r8, aBaseEcoWdsWdsl; "base\\Eco\\WDS\\wdslib\\net\\UdpSocket."...
0x1800195d9  mov     ecx, eax
0x1800195db  call    ElValidateWin32
0x1800195e0  mov     ebx, eax
0x1800195e2  test    eax, eax
0x1800195e4  jz      short loc_18001963F
0x1800195e6  mov     ebp, 1
0x1800195eb  mov     rcx, rsi
0x1800195ee  call    ?Release@?$IoOperation@VCUdpEndpoint@@@@QEAAKXZ; IoOperation<CUdpEndpoint>::Release(void)
0x1800195f3  test    ebp, ebp
0x1800195f5  jz      short loc_18001963F
0x1800195f7  lea     rsi, [rdi+1F0h]
0x1800195fe  mov     rcx, rsi
0x180019601  call    cs:__imp_?ReaderLock@CMRSWLock@@QEAAXXZ; CMRSWLock::ReaderLock(void)
0x180019608  nop     dword ptr [rax+rax+00h]
0x18001960d  or      eax, 0FFFFFFFFh
0x180019610  lock xadd [rdi+1E0h], eax
0x180019618  cmp     eax, 1
0x18001961b  jnz     short loc_180019630
0x18001961d  mov     rcx, [rdi+1E8h]; hEvent
0x180019624  call    cs:__imp_SetEvent
0x18001962b  nop     dword ptr [rax+rax+00h]
0x180019630  mov     rcx, rsi
0x180019633  call    cs:__imp_?ReaderRelease@CMRSWLock@@QEAAXXZ; CMRSWLock::ReaderRelease(void)
0x18001963a  nop     dword ptr [rax+rax+00h]
0x18001963f  lock dec dword ptr [rdi+1ACh]
0x180019646  lea     r11, [rsp+68h+var_8]
0x18001964b  mov     eax, ebx
0x18001964d  mov     rbx, [r11+18h]
0x180019651  mov     rbp, [r11+20h]
0x180019655  mov     rsi, [r11+28h]
0x180019659  mov     rsp, r11
0x18001965c  pop     rdi
0x18001965d  retn
```
