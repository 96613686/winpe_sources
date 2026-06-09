# CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>::PostReadRequest(void)

- ea: `0x180008174`
- end: `0x18000833b`
- name: `?PostReadRequest@?$CUdpSocket@VCClientLibrary@@U?$IoOperation@VCClientLibrary@@@@@@AEAAKXZ`
- size: `455`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000474c`
- `0x180008110`

## callees

- `0x1800067a4`
- `0x180008174`
- `0x1800095ac`
- `0x18000bd5c`

## import_xrefs

- `KERNEL32!SetEvent` at `0x180008300`
- `KERNEL32!SetEvent` at `0x180008300`
- `WS2_32!WSARecvFrom` at `0x18000826c`
- `WS2_32!WSARecvFrom` at `0x18000826c`
- `WS2_32!__imp_WSAGetLastError` at `0x180008285`
- `WS2_32!__imp_WSAGetLastError` at `0x18000829c`
- `WS2_32!__imp_WSAGetLastError` at `0x180008285`
- `WS2_32!__imp_WSAGetLastError` at `0x18000829c`
- `WdsCommonLib!?ReaderLock@CMRSWLock@@QEAAXXZ` at `0x1800082dd`
- `WdsCommonLib!?ReaderLock@CMRSWLock@@QEAAXXZ` at `0x1800082dd`
- `WdsCommonLib!?Allocate@CMemoryBuffer@@SAPEAV1@K@Z` at `0x1800081da`
- `WdsCommonLib!?Allocate@CMemoryBuffer@@SAPEAV1@K@Z` at `0x1800081da`
- `WdsCommonLib!?ReaderRelease@CMRSWLock@@QEAAXXZ` at `0x18000830f`
- `WdsCommonLib!?ReaderRelease@CMRSWLock@@QEAAXXZ` at `0x18000830f`

## pseudocode

```c
__int64 __fastcall CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>::PostReadRequest(__int64 a1)
{
  unsigned int v1; // ebx
  int v3; // ebp
  __int64 lpOverlapped; // rsi
  struct CMemoryBuffer *v5; // rax
  __int64 v6; // rdx
  int v7; // eax
  unsigned int Error; // eax
  __int64 v9; // rdx
  struct _WSABUF Buffers; // [rsp+50h] [rbp-18h] BYREF

  v1 = 0;
  Buffers = 0;
  v3 = 0;
  if ( (unsigned int)_InterlockedIncrement((volatile signed __int32 *)(a1 + 428)) > *(_DWORD *)(a1 + 72) )
    goto LABEL_16;
  lpOverlapped = CPool<IoOperation<CClientLibrary>>::GetObjectW(a1 + 432);
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
    IoOperation<CClientLibrary>::Release(lpOverlapped);
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
0x180008174  mov     rax, rsp
0x180008177  mov     [rax+10h], rbx
0x18000817b  mov     [rax+18h], rbp
0x18000817f  mov     [rax+20h], rsi
0x180008183  push    rdi
0x180008184  sub     rsp, 60h
0x180008188  xor     ebx, ebx
0x18000818a  xorps   xmm0, xmm0
0x18000818d  movups  xmmword ptr [rax-18h], xmm0
0x180008191  mov     rdi, rcx
0x180008194  xor     ebp, ebp
0x180008196  lea     eax, [rbx+1]
0x180008199  lock xadd [rcx+1ACh], eax
0x1800081a1  inc     eax
0x1800081a3  cmp     eax, [rcx+48h]
0x1800081a6  ja      loc_18000831B
0x1800081ac  add     rcx, 1B0h
0x1800081b3  call    ?GetObjectW@?$CPool@U?$IoOperation@VCClientLibrary@@@@@@QEAAPEAU?$IoOperation@VCClientLibrary@@@@H@Z; CPool<IoOperation<CClientLibrary>>::GetObjectW(int)
0x1800081b8  mov     rsi, rax
0x1800081bb  test    rax, rax
0x1800081be  jnz     short loc_1800081C8
0x1800081c0  lea     ebx, [rbp+8]
0x1800081c3  jmp     loc_18000831B
0x1800081c8  mov     rax, [rdi+30h]
0x1800081cc  mov     [rsi+20h], rax
0x1800081d0  mov     dword ptr [rsi+28h], 1
0x1800081d7  mov     ecx, [rdi+4Ch]
0x1800081da  call    cs:__imp_?Allocate@CMemoryBuffer@@SAPEAV1@K@Z; CMemoryBuffer::Allocate(ulong)
0x1800081e1  nop     dword ptr [rax+rax+00h]
0x1800081e6  mov     [rsi+30h], rax
0x1800081ea  test    rax, rax
0x1800081ed  jnz     short loc_1800081F7
0x1800081ef  lea     ebx, [rax+8]
0x1800081f2  jmp     loc_1800082C7
0x1800081f7  mov     rax, [rax+28h]
0x1800081fb  mov     [rsp+68h+Buffers.buf], rax
0x180008200  mov     rax, [rsi+30h]
0x180008204  mov     ecx, [rax+10h]
0x180008207  mov     [rsp+68h+Buffers.len], ecx
0x18000820b  lock inc dword ptr [rdi+1E0h]
0x180008212  mov     r9d, 6DEh
0x180008218  lea     r8, aBaseEcoWdsWdsl; "base\\Eco\\WDS\\wdslib\\net\\UdpSocket."...
0x18000821f  xor     ecx, ecx
0x180008221  call    ElValidateWin32
0x180008226  test    eax, eax
0x180008228  jnz     loc_18000831B
0x18000822e  and     [rsp+68h+var_28], rbx
0x180008233  lea     rdx, [rsi+0C0h]
0x18000823a  mov     [rsp+68h+lpOverlapped], rsi; lpOverlapped
0x18000823f  lea     rax, [rsi+40h]
0x180008243  mov     [rsp+68h+lpFromlen], rdx; lpFromlen
0x180008248  lea     rcx, [rsi+38h]
0x18000824c  mov     dword ptr [rdx], 80h
0x180008252  xor     r9d, r9d; lpNumberOfBytesRecvd
0x180008255  mov     [rsp+68h+lpFrom], rax; lpFrom
0x18000825a  lea     rdx, [rsp+68h+Buffers]; lpBuffers
0x18000825f  mov     [rsp+68h+lpFlags], rcx; lpFlags
0x180008264  mov     rcx, [rdi+38h]; s
0x180008268  lea     r8d, [r9+1]; dwBufferCount
0x18000826c  call    cs:__imp_WSARecvFrom
0x180008273  nop     dword ptr [rax+rax+00h]
0x180008278  test    eax, eax
0x18000827a  jz      loc_180008322
0x180008280  cmp     eax, 0FFFFFFFFh
0x180008283  jnz     short loc_18000829C
0x180008285  call    cs:__imp_WSAGetLastError
0x18000828c  nop     dword ptr [rax+rax+00h]
0x180008291  cmp     eax, 3E5h
0x180008296  jz      loc_180008322
0x18000829c  call    cs:__imp_WSAGetLastError
0x1800082a3  nop     dword ptr [rax+rax+00h]
0x1800082a8  mov     r9d, 6F4h
0x1800082ae  lea     r8, aBaseEcoWdsWdsl; "base\\Eco\\WDS\\wdslib\\net\\UdpSocket."...
0x1800082b5  mov     ecx, eax
0x1800082b7  call    ElValidateWin32
0x1800082bc  mov     ebx, eax
0x1800082be  test    eax, eax
0x1800082c0  jz      short loc_18000831B
0x1800082c2  mov     ebp, 1
0x1800082c7  mov     rcx, rsi
0x1800082ca  call    ?Release@?$IoOperation@VCClientLibrary@@@@QEAAKXZ; IoOperation<CClientLibrary>::Release(void)
0x1800082cf  test    ebp, ebp
0x1800082d1  jz      short loc_18000831B
0x1800082d3  lea     rsi, [rdi+1F0h]
0x1800082da  mov     rcx, rsi
0x1800082dd  call    cs:__imp_?ReaderLock@CMRSWLock@@QEAAXXZ; CMRSWLock::ReaderLock(void)
0x1800082e4  nop     dword ptr [rax+rax+00h]
0x1800082e9  or      eax, 0FFFFFFFFh
0x1800082ec  lock xadd [rdi+1E0h], eax
0x1800082f4  cmp     eax, 1
0x1800082f7  jnz     short loc_18000830C
0x1800082f9  mov     rcx, [rdi+1E8h]; hEvent
0x180008300  call    cs:__imp_SetEvent
0x180008307  nop     dword ptr [rax+rax+00h]
0x18000830c  mov     rcx, rsi
0x18000830f  call    cs:__imp_?ReaderRelease@CMRSWLock@@QEAAXXZ; CMRSWLock::ReaderRelease(void)
0x180008316  nop     dword ptr [rax+rax+00h]
0x18000831b  lock dec dword ptr [rdi+1ACh]
0x180008322  lea     r11, [rsp+68h+var_8]
0x180008327  mov     eax, ebx
0x180008329  mov     rbx, [r11+18h]
0x18000832d  mov     rbp, [r11+20h]
0x180008331  mov     rsi, [r11+28h]
0x180008335  mov     rsp, r11
0x180008338  pop     rdi
0x180008339  retn
```
