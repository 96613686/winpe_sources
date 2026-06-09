# minrpc::RpcListener::StartAccept(utl::unique_lock<utl::mutex> &)

- ea: `0x180098dfc`
- end: `0x180098f85`
- name: `?StartAccept@RpcListener@minrpc@@AEAAXAEAV?$unique_lock@Vmutex@utl@@@utl@@@Z`
- size: `393`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800939e4`
- `0x180098cb0`
- `0x1800d30f8`

## callees

- `0x180098dfc`
- `0x180098f8c`
- `0x18009973c`
- `0x1800d2ad8`
- `0x1800dd010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180098f3d`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180098f3d`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180098ed5`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180098ed5`
- `WS2_32!WSAIoctl` at `0x180098eac`
- `WS2_32!WSAIoctl` at `0x180098eac`
- `WS2_32!__imp_WSAGetLastError` at `0x180098e3e`
- `WS2_32!__imp_WSAGetLastError` at `0x180098eb6`
- `WS2_32!__imp_WSAGetLastError` at `0x180098f2a`
- `WS2_32!__imp_WSAGetLastError` at `0x180098e3e`
- `WS2_32!__imp_WSAGetLastError` at `0x180098eb6`
- `WS2_32!__imp_WSAGetLastError` at `0x180098f2a`

## pseudocode

```c
__int64 __fastcall minrpc::RpcListener::StartAccept(__int64 a1, __int64 a2)
{
  int Error; // eax
  const char *v5; // r9
  __int64 v6; // r8
  __int64 v7; // rdx
  unsigned int (__fastcall *v8)(_QWORD, __int64, __int64, _QWORD, int, int, DWORD *, __int64); // rax
  int v9; // edi
  DWORD cbBytesReturned; // [rsp+70h] [rbp+20h] BYREF
  __int64 v12; // [rsp+80h] [rbp+30h] BYREF
  unsigned int (__fastcall *vOutBuffer)(_QWORD, __int64, __int64, _QWORD, int, int, DWORD *, __int64); // [rsp+88h] [rbp+38h] BYREF

  (*(void (__fastcall **)(_QWORD, __int64 *, __int64))(**(_QWORD **)(a1 + 40) + 16LL))(*(_QWORD *)(a1 + 40), &v12, a2);
  vOutBuffer = 0;
  cbBytesReturned = 0;
  if ( v12 == -1 )
  {
    Error = WSAGetLastError();
    if ( Error > 0 )
      Error = (unsigned __int16)Error | 0x80070000;
    v5 = "StartAccept[OnListenerAccepting]";
LABEL_5:
    v6 = (unsigned int)Error;
    goto LABEL_6;
  }
  if ( WSAIoctl(*(_QWORD *)(a1 + 24), 0xC8000006, &unk_1800FB198, 0x10u, &vOutBuffer, 8u, &cbBytesReturned, 0, 0) )
  {
    Error = WSAGetLastError();
    if ( Error > 0 )
      Error = (unsigned __int16)Error | 0x80070000;
    v5 = "StartAccept[WSAIoctl]";
    goto LABEL_5;
  }
  StartThreadpoolIo(*(PTP_IO *)(a1 + 16));
  v7 = v12;
  cbBytesReturned = 0;
  *(_OWORD *)(a1 + 360) = 0;
  v8 = vOutBuffer;
  *(_OWORD *)(a1 + 376) = 0;
  if ( v8(*(_QWORD *)(a1 + 24), v7, a1 + 72, 0, 144, 144, &cbBytesReturned, a1 + 360)
    || (v9 = WSAGetLastError(), v9 == 997) )
  {
    tlx::unique_any<tlx::handle_traits<unsigned __int64,int (*)(unsigned __int64),&int closesocket(unsigned __int64),-1>>::operator=(
      a1 + 32,
      &v12);
    ++*(_BYTE *)(a1 + 49);
    return tlx::unique_any<tlx::handle_traits<unsigned __int64,int (*)(unsigned __int64),&int closesocket(unsigned __int64),-1>>::~unique_any<tlx::handle_traits<unsigned __int64,int (*)(unsigned __int64),&int closesocket(unsigned __int64),-1>>(&v12);
  }
  CancelThreadpoolIo(*(PTP_IO *)(a1 + 16));
  if ( v9 > 0 )
    v9 = (unsigned __int16)v9 | 0x80070000;
  v5 = "StartAccept[AcceptEx]";
  v6 = (unsigned int)v9;
LABEL_6:
  minrpc::RpcListener::StallLocked(a1, a2, v6, v5);
  return tlx::unique_any<tlx::handle_traits<unsigned __int64,int (*)(unsigned __int64),&int closesocket(unsigned __int64),-1>>::~unique_any<tlx::handle_traits<unsigned __int64,int (*)(unsigned __int64),&int closesocket(unsigned __int64),-1>>(&v12);
}

```

## disassembly

```asm
0x180098dfc  mov     [rsp-18h+arg_8], rbx
0x180098e01  push    rbp
0x180098e02  push    rsi
0x180098e03  push    rdi
0x180098e04  mov     rbp, rsp
0x180098e07  sub     rsp, 50h
0x180098e0b  mov     rbx, rcx
0x180098e0e  mov     rsi, rdx
0x180098e11  mov     rcx, [rcx+28h]
0x180098e15  mov     r8, rdx
0x180098e18  lea     rdx, [rbp+arg_10]
0x180098e1c  mov     rax, [rcx]
0x180098e1f  mov     rax, [rax+10h]
0x180098e23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098e28  cmp     [rbp+arg_10], 0FFFFFFFFFFFFFFFFh
0x180098e2d  mov     [rbp+vOutBuffer], 0
0x180098e35  mov     [rbp+cbBytesReturned], 0
0x180098e3c  jnz     short loc_180098E6A
0x180098e3e  call    cs:__imp_WSAGetLastError
0x180098e44  test    eax, eax
0x180098e46  jle     short loc_180098E50
0x180098e48  movzx   eax, ax
0x180098e4b  or      eax, 80070000h
0x180098e50  lea     r9, aStartacceptOnl; "StartAccept[OnListenerAccepting]"
0x180098e57  mov     r8d, eax
0x180098e5a  mov     rdx, rsi
0x180098e5d  mov     rcx, rbx
0x180098e60  call    ?StallLocked@RpcListener@minrpc@@QEAAXAEAV?$unique_lock@Vmutex@utl@@@utl@@JPEBD@Z; minrpc::RpcListener::StallLocked(utl::unique_lock<utl::mutex> &,long,char const *)
0x180098e65  jmp     loc_180098F6F
0x180098e6a  mov     rcx, [rbx+18h]; s
0x180098e6e  lea     rax, [rbp+cbBytesReturned]
0x180098e72  mov     [rsp+50h+lpCompletionRoutine], 0; lpCompletionRoutine
0x180098e7b  lea     r8, unk_1800FB198; lpvInBuffer
0x180098e82  mov     [rsp+50h+lpOverlapped], 0; lpOverlapped
0x180098e8b  mov     r9d, 10h; cbInBuffer
0x180098e91  mov     [rsp+50h+lpcbBytesReturned], rax; lpcbBytesReturned
0x180098e96  mov     edx, 0C8000006h; dwIoControlCode
0x180098e9b  lea     rax, [rbp+vOutBuffer]
0x180098e9f  mov     [rsp+50h+cbOutBuffer], 8; cbOutBuffer
0x180098ea7  mov     [rsp+50h+lpvOutBuffer], rax; lpvOutBuffer
0x180098eac  call    cs:__imp_WSAIoctl
0x180098eb2  test    eax, eax
0x180098eb4  jz      short loc_180098ED1
0x180098eb6  call    cs:__imp_WSAGetLastError
0x180098ebc  test    eax, eax
0x180098ebe  jle     short loc_180098EC8
0x180098ec0  movzx   eax, ax
0x180098ec3  or      eax, 80070000h
0x180098ec8  lea     r9, aStartacceptWsa; "StartAccept[WSAIoctl]"
0x180098ecf  jmp     short loc_180098E57
0x180098ed1  mov     rcx, [rbx+10h]; pio
0x180098ed5  call    cs:__imp_StartThreadpoolIo
0x180098edb  mov     rdx, [rbp+arg_10]
0x180098edf  lea     rcx, [rbx+168h]
0x180098ee6  mov     [rsp+50h+lpOverlapped], rcx
0x180098eeb  lea     rax, [rbp+cbBytesReturned]
0x180098eef  mov     [rsp+50h+lpcbBytesReturned], rax
0x180098ef4  lea     r8, [rbx+48h]
0x180098ef8  mov     eax, 90h
0x180098efd  mov     [rbp+cbBytesReturned], 0
0x180098f04  xorps   xmm0, xmm0
0x180098f07  mov     [rsp+50h+cbOutBuffer], eax
0x180098f0b  movups  xmmword ptr [rcx], xmm0
0x180098f0e  mov     dword ptr [rsp+50h+lpvOutBuffer], eax
0x180098f12  xor     r9d, r9d
0x180098f15  mov     rax, [rbp+vOutBuffer]
0x180098f19  movups  xmmword ptr [rcx+10h], xmm0
0x180098f1d  mov     rcx, [rbx+18h]
0x180098f21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098f26  test    eax, eax
0x180098f28  jnz     short loc_180098F5F
0x180098f2a  call    cs:__imp_WSAGetLastError
0x180098f30  mov     edi, eax
0x180098f32  cmp     eax, 3E5h
0x180098f37  jz      short loc_180098F5F
0x180098f39  mov     rcx, [rbx+10h]; pio
0x180098f3d  call    cs:__imp_CancelThreadpoolIo
0x180098f43  test    edi, edi
0x180098f45  jle     short loc_180098F50
0x180098f47  movzx   edi, di
0x180098f4a  or      edi, 80070000h
0x180098f50  lea     r9, aStartacceptAcc; "StartAccept[AcceptEx]"
0x180098f57  mov     r8d, edi
0x180098f5a  jmp     loc_180098E5A
0x180098f5f  lea     rcx, [rbx+20h]
0x180098f63  lea     rdx, [rbp+arg_10]
0x180098f67  call    ??4?$unique_any@U?$handle_traits@_KP6AH_K@Z$1?closesocket@@YAH0@Z$0?0@tlx@@@tlx@@QEAAAEAV01@$$QEAV01@@Z; tlx::unique_any<tlx::handle_traits<unsigned __int64,int (*)(unsigned __int64),&closesocket(unsigned __int64),-1>>::operator=(tlx::unique_any<tlx::handle_traits<unsigned __int64,int (*)(unsigned __int64),&closesocket(unsigned __int64),-1>> &&)
0x180098f6c  inc     byte ptr [rbx+31h]
0x180098f6f  lea     rcx, [rbp+arg_10]
0x180098f73  call    ??1?$unique_any@U?$handle_traits@_KP6AH_K@Z$1?closesocket@@YAH0@Z$0?0@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<unsigned __int64,int (*)(unsigned __int64),&closesocket(unsigned __int64),-1>>::~unique_any<tlx::handle_traits<unsigned __int64,int (*)(unsigned __int64),&closesocket(unsigned __int64),-1>>(void)
0x180098f78  mov     rbx, [rsp+50h+arg_8]
0x180098f7d  add     rsp, 50h
0x180098f81  pop     rdi
0x180098f82  pop     rsi
0x180098f83  pop     rbp
0x180098f84  retn
```
