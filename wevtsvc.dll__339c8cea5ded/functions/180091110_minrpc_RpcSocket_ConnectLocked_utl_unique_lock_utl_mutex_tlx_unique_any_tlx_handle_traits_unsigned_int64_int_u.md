# minrpc::RpcSocket::ConnectLocked(utl::unique_lock<utl::mutex> &,tlx::unique_any<tlx::handle_traits<unsigned __int64,int (*)(unsigned __int64),&closesocket(unsigned __int64),-1>> &&,void const *,uint)

- ea: `0x180091110`
- end: `0x180091293`
- name: `?ConnectLocked@RpcSocket@minrpc@@QEAA_NAEAV?$unique_lock@Vmutex@utl@@@utl@@$$QEAV?$unique_any@U?$handle_traits@_KP6AH_K@Z$1?closesocket@@YAH0@Z$0?0@tlx@@@tlx@@PEBXI@Z`
- size: `387`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180099354`

## callees

- `0x180090f4c`
- `0x180091110`
- `0x18009129c`
- `0x1800dd010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18009124f`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18009124f`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180091200`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180091200`
- `WS2_32!WSAIoctl` at `0x1800911b5`
- `WS2_32!WSAIoctl` at `0x1800911b5`
- `WS2_32!__imp_WSAGetLastError` at `0x1800911bf`
- `WS2_32!__imp_WSAGetLastError` at `0x18009123c`
- `WS2_32!__imp_WSAGetLastError` at `0x1800911bf`
- `WS2_32!__imp_WSAGetLastError` at `0x18009123c`

## pseudocode

```c
char __fastcall minrpc::RpcSocket::ConnectLocked(__int64 a1, __int64 a2, __int64 a3, __int64 a4, unsigned int a5)
{
  char v5; // bp
  bool v9; // zf
  SOCKET v10; // rcx
  int Error; // eax
  const char *v12; // r9
  __int64 v13; // r8
  int v14; // ebx
  unsigned int (__fastcall *vOutBuffer[2])(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, __int64); // [rsp+50h] [rbp-28h] BYREF
  DWORD cbBytesReturned; // [rsp+80h] [rbp+8h] BYREF

  v5 = *(_BYTE *)(a1 + 138);
  cbBytesReturned = 0;
  vOutBuffer[0] = 0;
  v9 = v5 == 0;
  if ( !v5 )
  {
    *(_BYTE *)(a1 + 138) = 1;
    if ( minrpc::RpcSocket::PreAttach((char *)a1, a2, a3) )
    {
      v10 = *(_QWORD *)(a1 + 24);
      cbBytesReturned = 0;
      if ( WSAIoctl(v10, 0xC8000006, qword_1800FB188, 0x10u, vOutBuffer, 8u, &cbBytesReturned, 0, 0) )
      {
        Error = WSAGetLastError();
        if ( Error > 0 )
          Error = (unsigned __int16)Error | 0x80070000;
        v12 = "Connect[WSAIoctl]";
        v13 = (unsigned int)Error;
      }
      else
      {
        *(_OWORD *)(a1 + 168) = 0;
        *(_OWORD *)(a1 + 184) = 0;
        StartThreadpoolIo(*(PTP_IO *)(a1 + 32));
        if ( vOutBuffer[0](*(_QWORD *)(a1 + 24), a4, a5, 0, 0, 0, a1 + 168) || (v14 = WSAGetLastError(), v14 == 997) )
        {
          *(_BYTE *)(a1 + 136) |= 4u;
          return 1;
        }
        CancelThreadpoolIo(*(PTP_IO *)(a1 + 32));
        if ( v14 > 0 )
          v14 = (unsigned __int16)v14 | 0x80070000;
        v12 = "Connect[ConnectEx]";
        v13 = (unsigned int)v14;
      }
      minrpc::RpcSocket::DisconnectLocked(a1, a2, v13, v12);
    }
    return 1;
  }
  return v9;
}

```

## disassembly

```asm
0x180091110  mov     rax, rsp
0x180091113  mov     [rax+10h], rbx
0x180091117  mov     [rax+18h], rbp
0x18009111b  push    rsi
0x18009111c  push    rdi
0x18009111d  push    r14
0x18009111f  sub     rsp, 60h
0x180091123  mov     bpl, [rcx+8Ah]
0x18009112a  mov     r14, r9
0x18009112d  mov     dword ptr [rax+8], 0
0x180091134  mov     rsi, rdx
0x180091137  mov     qword ptr [rax-28h], 0
0x18009113f  mov     rdi, rcx
0x180091142  test    bpl, bpl
0x180091145  jnz     loc_18009127B
0x18009114b  mov     eax, 1
0x180091150  xchg    al, [rcx+8Ah]
0x180091156  call    ?PreAttach@RpcSocket@minrpc@@AEAA_NAEAV?$unique_lock@Vmutex@utl@@@utl@@$$QEAV?$unique_any@U?$handle_traits@_KP6AH_K@Z$1?closesocket@@YAH0@Z$0?0@tlx@@@tlx@@@Z; minrpc::RpcSocket::PreAttach(utl::unique_lock<utl::mutex> &,tlx::unique_any<tlx::handle_traits<unsigned __int64,int (*)(unsigned __int64),&closesocket(unsigned __int64),-1>> &&)
0x18009115b  test    al, al
0x18009115d  jz      loc_180091278
0x180091163  mov     rcx, [rdi+18h]; s
0x180091167  lea     rax, [rsp+78h+cbBytesReturned]
0x18009116f  mov     [rsp+78h+lpCompletionRoutine], 0; lpCompletionRoutine
0x180091178  lea     r8, qword_1800FB188; lpvInBuffer
0x18009117f  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x180091188  mov     r9d, 10h; cbInBuffer
0x18009118e  mov     [rsp+78h+lpcbBytesReturned], rax; lpcbBytesReturned
0x180091193  mov     edx, 0C8000006h; dwIoControlCode
0x180091198  lea     rax, [rsp+78h+vOutBuffer]
0x18009119d  mov     [rsp+78h+cbOutBuffer], 8; cbOutBuffer
0x1800911a5  mov     [rsp+78h+lpvOutBuffer], rax; lpvOutBuffer
0x1800911aa  mov     [rsp+78h+cbBytesReturned], 0
0x1800911b5  call    cs:__imp_WSAIoctl
0x1800911bb  test    eax, eax
0x1800911bd  jz      short loc_1800911EB
0x1800911bf  call    cs:__imp_WSAGetLastError
0x1800911c5  test    eax, eax
0x1800911c7  jle     short loc_1800911D1
0x1800911c9  movzx   eax, ax
0x1800911cc  or      eax, 80070000h
0x1800911d1  lea     r9, aConnectWsaioct; "Connect[WSAIoctl]"
0x1800911d8  mov     r8d, eax
0x1800911db  mov     rdx, rsi
0x1800911de  mov     rcx, rdi
0x1800911e1  call    ?DisconnectLocked@RpcSocket@minrpc@@QEAAXAEAV?$unique_lock@Vmutex@utl@@@utl@@JPEBD@Z; minrpc::RpcSocket::DisconnectLocked(utl::unique_lock<utl::mutex> &,long,char const *)
0x1800911e6  jmp     loc_180091278
0x1800911eb  xorps   xmm0, xmm0
0x1800911ee  lea     rbx, [rdi+0A8h]
0x1800911f5  movups  xmmword ptr [rbx], xmm0
0x1800911f8  movups  xmmword ptr [rbx+10h], xmm0
0x1800911fc  mov     rcx, [rdi+20h]; pio
0x180091200  call    cs:__imp_StartThreadpoolIo
0x180091206  mov     r8d, [rsp+78h+arg_20]
0x18009120e  xor     r9d, r9d
0x180091211  mov     rcx, [rdi+18h]
0x180091215  mov     rdx, r14
0x180091218  mov     rax, [rsp+78h+vOutBuffer]
0x18009121d  mov     [rsp+78h+lpcbBytesReturned], rbx
0x180091222  mov     qword ptr [rsp+78h+cbOutBuffer], 0
0x18009122b  mov     dword ptr [rsp+78h+lpvOutBuffer], 0
0x180091233  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091238  test    eax, eax
0x18009123a  jnz     short loc_180091271
0x18009123c  call    cs:__imp_WSAGetLastError
0x180091242  mov     ebx, eax
0x180091244  cmp     eax, 3E5h
0x180091249  jz      short loc_180091271
0x18009124b  mov     rcx, [rdi+20h]; pio
0x18009124f  call    cs:__imp_CancelThreadpoolIo
0x180091255  test    ebx, ebx
0x180091257  jle     short loc_180091262
0x180091259  movzx   ebx, bx
0x18009125c  or      ebx, 80070000h
0x180091262  lea     r9, aConnectConnect; "Connect[ConnectEx]"
0x180091269  mov     r8d, ebx
0x18009126c  jmp     loc_1800911DB
0x180091271  or      byte ptr [rdi+88h], 4
0x180091278  test    bpl, bpl
0x18009127b  lea     r11, [rsp+78h+var_18]
0x180091280  setz    al
0x180091283  mov     rbx, [r11+28h]
0x180091287  mov     rbp, [r11+30h]
0x18009128b  mov     rsp, r11
0x18009128e  pop     r14
0x180091290  pop     rdi
0x180091291  pop     rsi
0x180091292  retn
```
