# minrpc::RpcSocket::StartSend(utl::unique_lock<utl::mutex> &,uchar)

- ea: `0x180091004`
- end: `0x180091108`
- name: `?StartSend@RpcSocket@minrpc@@AEAA_NAEAV?$unique_lock@Vmutex@utl@@@utl@@E@Z`
- size: `260`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180065d00`
- `0x1800d2cec`

## callees

- `0x180091004`
- `0x18009129c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x1800910bf`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x1800910bf`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180091073`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180091073`
- `WS2_32!WSASend` at `0x1800910a2`
- `WS2_32!WSASend` at `0x1800910a2`
- `WS2_32!__imp_WSAGetLastError` at `0x1800910ac`
- `WS2_32!__imp_WSAGetLastError` at `0x1800910ac`

## pseudocode

```c
char __fastcall minrpc::RpcSocket::StartSend(__int64 a1, __int64 a2, unsigned __int8 a3)
{
  __int64 v6; // rcx
  __int64 v7; // r9
  unsigned int v8; // r8d
  char v9; // bl
  unsigned int v10; // r8d
  ULONG v11; // eax
  CHAR *v12; // rax
  int Error; // esi
  struct _WSABUF Buffers; // [rsp+40h] [rbp-38h] BYREF

  v6 = 32LL * a3;
  v7 = *(unsigned int *)(v6 + a1 + 96);
  v8 = *(_DWORD *)(v6 + a1 + 100);
  if ( (unsigned int)v7 >= v8 )
    return 1;
  v10 = v8 - v7;
  v11 = 0x100000;
  if ( v10 < 0x100000 )
    v11 = v10;
  Buffers.len = v11;
  *(&Buffers.len + 1) = 0;
  v12 = (CHAR *)(*(_QWORD *)(v6 + a1 + 72) + v7);
  *(_OWORD *)(a1 + 160) = 0;
  Buffers.buf = v12;
  *(_OWORD *)(a1 + 176) = 0;
  StartThreadpoolIo(*(PTP_IO *)(a1 + 32));
  v9 = 1;
  if ( !WSASend(*(_QWORD *)(a1 + 24), &Buffers, 1u, 0, 0, (LPWSAOVERLAPPED)(a1 + 160), 0)
    || (Error = WSAGetLastError(), Error == 997) )
  {
    *(_BYTE *)(a1 + 136) |= 1u;
    *(_BYTE *)(a1 + 137) = a3 ^ 1;
  }
  else
  {
    CancelThreadpoolIo(*(PTP_IO *)(a1 + 32));
    if ( Error > 0 )
      Error = (unsigned __int16)Error | 0x80070000;
    minrpc::RpcSocket::DisconnectLocked(a1, a2, (unsigned int)Error, "StartSend[WSASend]");
    return 0;
  }
  return v9;
}

```

## disassembly

```asm
0x180091004  push    rbx
0x180091006  push    rbp
0x180091007  push    rsi
0x180091008  push    rdi
0x180091009  push    r14
0x18009100b  sub     rsp, 50h
0x18009100f  mov     rdi, rcx
0x180091012  movzx   ebp, r8b
0x180091016  mov     ecx, ebp
0x180091018  mov     r14, rdx
0x18009101b  shl     rcx, 5
0x18009101f  mov     r9d, [rcx+rdi+60h]
0x180091024  mov     r8d, [rcx+rdi+64h]
0x180091029  cmp     r9d, r8d
0x18009102c  jb      short loc_180091038
0x18009102e  mov     ebx, 1
0x180091033  jmp     loc_1800910FB
0x180091038  sub     r8d, r9d
0x18009103b  lea     rbx, [rdi+0A0h]
0x180091042  mov     eax, 100000h
0x180091047  xorps   xmm0, xmm0
0x18009104a  cmp     r8d, eax
0x18009104d  cmovb   eax, r8d
0x180091051  mov     [rsp+78h+Buffers.len], eax
0x180091055  xor     eax, eax
0x180091057  mov     dword ptr [rsp+78h+Buffers+4], eax
0x18009105b  mov     rax, r9
0x18009105e  add     rax, [rcx+rdi+48h]
0x180091063  movups  xmmword ptr [rbx], xmm0
0x180091066  mov     [rsp+78h+Buffers.buf], rax
0x18009106b  movups  xmmword ptr [rbx+10h], xmm0
0x18009106f  mov     rcx, [rdi+20h]; pio
0x180091073  call    cs:__imp_StartThreadpoolIo
0x180091079  mov     rcx, [rdi+18h]; s
0x18009107d  lea     rdx, [rsp+78h+Buffers]; lpBuffers
0x180091082  xor     r9d, r9d; lpNumberOfBytesSent
0x180091085  mov     [rsp+78h+lpCompletionRoutine], 0; lpCompletionRoutine
0x18009108e  mov     [rsp+78h+lpOverlapped], rbx; lpOverlapped
0x180091093  mov     [rsp+78h+dwFlags], 0; dwFlags
0x18009109b  lea     ebx, [r9+1]
0x18009109f  mov     r8d, ebx; dwBufferCount
0x1800910a2  call    cs:__imp_WSASend
0x1800910a8  test    eax, eax
0x1800910aa  jz      short loc_1800910EB
0x1800910ac  call    cs:__imp_WSAGetLastError
0x1800910b2  mov     esi, eax
0x1800910b4  cmp     eax, 3E5h
0x1800910b9  jz      short loc_1800910EB
0x1800910bb  mov     rcx, [rdi+20h]; pio
0x1800910bf  call    cs:__imp_CancelThreadpoolIo
0x1800910c5  test    esi, esi
0x1800910c7  jle     short loc_1800910D2
0x1800910c9  movzx   esi, si
0x1800910cc  or      esi, 80070000h
0x1800910d2  lea     r9, aStartsendWsase; "StartSend[WSASend]"
0x1800910d9  mov     r8d, esi
0x1800910dc  mov     rdx, r14
0x1800910df  mov     rcx, rdi
0x1800910e2  call    ?DisconnectLocked@RpcSocket@minrpc@@QEAAXAEAV?$unique_lock@Vmutex@utl@@@utl@@JPEBD@Z; minrpc::RpcSocket::DisconnectLocked(utl::unique_lock<utl::mutex> &,long,char const *)
0x1800910e7  xor     bl, bl
0x1800910e9  jmp     short loc_1800910FB
0x1800910eb  or      [rdi+88h], bl
0x1800910f1  xor     bpl, bl
0x1800910f4  mov     [rdi+89h], bpl
0x1800910fb  mov     al, bl
0x1800910fd  add     rsp, 50h
0x180091101  pop     r14
0x180091103  pop     rdi
0x180091104  pop     rsi
0x180091105  pop     rbp
0x180091106  pop     rbx
0x180091107  retn
```
