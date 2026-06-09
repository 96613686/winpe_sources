# minrpc::RpcSocket::StartRecv(utl::unique_lock<utl::mutex> &)

- ea: `0x18007917c`
- end: `0x1800792a6`
- name: `?StartRecv@RpcSocket@minrpc@@AEAAXAEAV?$unique_lock@Vmutex@utl@@@utl@@@Z`
- size: `298`
- prototype: `int __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180065d00`
- `0x1800d2b3c`

## callees

- `0x18007917c`
- `0x18009129c`
- `0x1800d2e78`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180079274`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180079274`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180079226`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180079226`
- `WS2_32!WSARecv` at `0x180079257`
- `WS2_32!WSARecv` at `0x180079257`
- `WS2_32!__imp_WSAGetLastError` at `0x180079261`
- `WS2_32!__imp_WSAGetLastError` at `0x180079261`

## pseudocode

```c
int __fastcall minrpc::RpcSocket::StartRecv(__int64 a1, __int64 a2)
{
  minrpc::RpcSocket::IoState *v2; // rbx
  __int64 v3; // rsi
  unsigned int v5; // ecx
  const char *v6; // r9
  __int64 v7; // r8
  int result; // eax
  unsigned int v9; // ebp
  unsigned int v10; // eax
  __int64 v11; // rcx
  ULONG v12; // eax
  CHAR *v13; // rcx
  struct _TP_IO *v14; // rcx
  signed int v15; // ebx
  _WSABUF Buffers; // [rsp+40h] [rbp-38h] BYREF
  DWORD Flags; // [rsp+80h] [rbp+8h] BYREF

  v2 = (minrpc::RpcSocket::IoState *)(a1 + 40);
  v3 = a2;
  if ( *(_DWORD *)(a1 + 64) >= 4u )
  {
    v5 = **(_DWORD **)v2;
    if ( v5 > 0x10000000 )
    {
      v6 = "StartRecv[PacketTooBig]";
      v7 = 2147942413LL;
      return minrpc::RpcSocket::DisconnectLocked(a1, a2, v7, v6);
    }
    v9 = v5 + (-v5 & 7) + 8;
    if ( *(_DWORD *)(a1 + 68) < v9 )
    {
      v10 = minrpc::RpcSocket::IoState::TryReserve(v2, v9);
      *(_DWORD *)(a1 + 68) = v10;
      if ( v10 < v9 )
      {
        v6 = "StartRecv[Allocate]";
        v7 = 2147942414LL;
LABEL_8:
        a2 = v3;
        return minrpc::RpcSocket::DisconnectLocked(a1, a2, v7, v6);
      }
    }
  }
  v11 = *(unsigned int *)(a1 + 64);
  v12 = *(_DWORD *)(a1 + 68) - v11;
  v13 = (CHAR *)(*(_QWORD *)v2 + v11);
  Buffers.len = v12;
  *(_OWORD *)(a1 + 192) = 0;
  Buffers.buf = v13;
  *(_OWORD *)(a1 + 208) = 0;
  v14 = *(struct _TP_IO **)(a1 + 32);
  *(&Buffers.len + 1) = 0;
  Flags = 0;
  StartThreadpoolIo(v14);
  result = WSARecv(*(_QWORD *)(a1 + 24), &Buffers, 1u, 0, &Flags, (LPWSAOVERLAPPED)(a1 + 192), 0);
  if ( result )
  {
    result = WSAGetLastError();
    v15 = result;
    if ( result != 997 )
    {
      CancelThreadpoolIo(*(PTP_IO *)(a1 + 32));
      if ( v15 > 0 )
        v15 = (unsigned __int16)v15 | 0x80070000;
      v6 = "StartRecv[WSARecv]";
      v7 = (unsigned int)v15;
      goto LABEL_8;
    }
  }
  *(_BYTE *)(a1 + 136) |= 2u;
  return result;
}

```

## disassembly

```asm
0x18007917c  push    rbx
0x18007917e  push    rbp
0x18007917f  push    rsi
0x180079180  push    rdi
0x180079181  sub     rsp, 58h
0x180079185  lea     rbx, [rcx+28h]
0x180079189  mov     rsi, rdx
0x18007918c  cmp     dword ptr [rbx+18h], 4
0x180079190  mov     rdi, rcx
0x180079193  jb      short loc_1800791F0
0x180079195  mov     rax, [rbx]
0x180079198  mov     ecx, [rax]
0x18007919a  cmp     ecx, 10000000h
0x1800791a0  jbe     short loc_1800791BC
0x1800791a2  lea     r9, aStartrecvPacke; "StartRecv[PacketTooBig]"
0x1800791a9  mov     r8d, 8007000Dh
0x1800791af  mov     rcx, rdi
0x1800791b2  call    ?DisconnectLocked@RpcSocket@minrpc@@QEAAXAEAV?$unique_lock@Vmutex@utl@@@utl@@JPEBD@Z; minrpc::RpcSocket::DisconnectLocked(utl::unique_lock<utl::mutex> &,long,char const *)
0x1800791b7  jmp     loc_18007929D
0x1800791bc  mov     ebp, ecx
0x1800791be  neg     ebp
0x1800791c0  and     ebp, 7
0x1800791c3  add     ebp, 8
0x1800791c6  add     ebp, ecx
0x1800791c8  cmp     [rdi+44h], ebp
0x1800791cb  jnb     short loc_1800791F0
0x1800791cd  mov     edx, ebp; unsigned int
0x1800791cf  mov     rcx, rbx; this
0x1800791d2  call    ?TryReserve@IoState@RpcSocket@minrpc@@QEAAII@Z; minrpc::RpcSocket::IoState::TryReserve(uint)
0x1800791d7  mov     [rdi+44h], eax
0x1800791da  cmp     eax, ebp
0x1800791dc  jnb     short loc_1800791F0
0x1800791de  lea     r9, aStartrecvAlloc; "StartRecv[Allocate]"
0x1800791e5  mov     r8d, 8007000Eh
0x1800791eb  mov     rdx, rsi
0x1800791ee  jmp     short loc_1800791AF
0x1800791f0  mov     ecx, [rdi+40h]
0x1800791f3  xorps   xmm0, xmm0
0x1800791f6  mov     eax, [rdi+44h]
0x1800791f9  sub     eax, ecx
0x1800791fb  add     rcx, [rbx]
0x1800791fe  lea     rbx, [rdi+0C0h]
0x180079205  mov     [rsp+78h+Buffers.len], eax
0x180079209  movups  xmmword ptr [rbx], xmm0
0x18007920c  xor     eax, eax
0x18007920e  mov     [rsp+78h+Buffers.buf], rcx
0x180079213  movups  xmmword ptr [rbx+10h], xmm0
0x180079217  mov     rcx, [rdi+20h]; pio
0x18007921b  mov     dword ptr [rsp+78h+Buffers+4], eax
0x18007921f  mov     [rsp+78h+Flags], eax
0x180079226  call    cs:__imp_StartThreadpoolIo
0x18007922c  mov     rcx, [rdi+18h]; s
0x180079230  lea     rax, [rsp+78h+Flags]
0x180079238  xor     r9d, r9d; lpNumberOfBytesRecvd
0x18007923b  mov     [rsp+78h+lpCompletionRoutine], 0; lpCompletionRoutine
0x180079244  mov     [rsp+78h+lpOverlapped], rbx; lpOverlapped
0x180079249  lea     rdx, [rsp+78h+Buffers]; lpBuffers
0x18007924e  mov     [rsp+78h+lpFlags], rax; lpFlags
0x180079253  lea     r8d, [r9+1]; dwBufferCount
0x180079257  call    cs:__imp_WSARecv
0x18007925d  test    eax, eax
0x18007925f  jz      short loc_180079296
0x180079261  call    cs:__imp_WSAGetLastError
0x180079267  mov     ebx, eax
0x180079269  cmp     eax, 3E5h
0x18007926e  jz      short loc_180079296
0x180079270  mov     rcx, [rdi+20h]; pio
0x180079274  call    cs:__imp_CancelThreadpoolIo
0x18007927a  test    ebx, ebx
0x18007927c  jle     short loc_180079287
0x18007927e  movzx   ebx, bx
0x180079281  or      ebx, 80070000h
0x180079287  lea     r9, aStartrecvWsare; "StartRecv[WSARecv]"
0x18007928e  mov     r8d, ebx
0x180079291  jmp     loc_1800791EB
0x180079296  or      byte ptr [rdi+88h], 2
0x18007929d  add     rsp, 58h
0x1800792a1  pop     rdi
0x1800792a2  pop     rsi
0x1800792a3  pop     rbp
0x1800792a4  pop     rbx
0x1800792a5  retn
```
