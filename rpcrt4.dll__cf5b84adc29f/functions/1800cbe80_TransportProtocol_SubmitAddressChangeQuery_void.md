# TransportProtocol::SubmitAddressChangeQuery(void)

- ea: `0x1800cbe80`
- end: `0x1800cbf59`
- name: `?SubmitAddressChangeQuery@TransportProtocol@@AEAAHXZ`
- size: `217`
- prototype: `__int64 __fastcall(TransportProtocol *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800cbb64`
- `0x1800cbd08`
- `0x1800cc00c`

## callees

- `0x180022e80`
- `0x1800cbe80`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x1800cbec7`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x1800cbec7`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x1800cbf38`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x1800cbf38`
- `WS2_32!WSAIoctl` at `0x1800cbf0d`
- `WS2_32!WSAIoctl` at `0x1800cbf0d`
- `WS2_32!__imp_WSAGetLastError` at `0x1800cbf1e`
- `WS2_32!__imp_WSAGetLastError` at `0x1800cbf1e`

## pseudocode

```c
__int64 __fastcall TransportProtocol::SubmitAddressChangeQuery(TransportProtocol *this)
{
  PTP_IO *v2; // rcx
  DWORD cbOutBuffer; // [rsp+28h] [rbp-30h]
  int lpcbBytesReturned; // [rsp+30h] [rbp-28h]

  LogEvent(0x57u, 0x45u, this, 0, 0, cbOutBuffer, lpcbBytesReturned);
  v2 = (PTP_IO *)*((_QWORD *)this + 8);
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 4) = 0;
  StartThreadpoolIo(*v2);
  if ( WSAIoctl(*((_QWORD *)this + 3), 0x28000017u, 0, 0, 0, 0, &cbBytesReturned, (LPWSAOVERLAPPED)this + 1, 0) != -1
    || WSAGetLastError() == 997 )
  {
    return 1;
  }
  CancelThreadpoolIo(**((PTP_IO **)this + 8));
  return 0;
}

```

## disassembly

```asm
0x1800cbe80  mov     [rsp+arg_0], rbx
0x1800cbe85  push    rdi
0x1800cbe86  sub     rsp, 50h
0x1800cbe8a  mov     rdi, rcx
0x1800cbe8d  mov     [rsp+58h+lpvOutBuffer], 0; unsigned __int64
0x1800cbe96  mov     r8, rcx; void *
0x1800cbe99  xor     r9d, r9d; void *
0x1800cbe9c  mov     cl, 57h ; 'W'; unsigned __int8
0x1800cbe9e  mov     dl, 45h ; 'E'; unsigned __int8
0x1800cbea0  call    ?LogEvent@@YAXEEPEAX0_KHH@Z; LogEvent(uchar,uchar,void *,void *,unsigned __int64,int,int)
0x1800cbea5  mov     rcx, [rdi+40h]
0x1800cbea9  lea     rbx, [rdi+20h]
0x1800cbead  mov     qword ptr [rbx+18h], 0
0x1800cbeb5  mov     qword ptr [rdi+30h], 0
0x1800cbebd  mov     qword ptr [rbx], 0
0x1800cbec4  mov     rcx, [rcx]; pio
0x1800cbec7  call    cs:__imp_StartThreadpoolIo
0x1800cbece  nop     dword ptr [rax+rax+00h]
0x1800cbed3  mov     rcx, [rdi+18h]; s
0x1800cbed7  lea     rax, cbBytesReturned
0x1800cbede  mov     [rsp+58h+lpCompletionRoutine], 0; lpCompletionRoutine
0x1800cbee7  xor     r9d, r9d; cbInBuffer
0x1800cbeea  mov     [rsp+58h+lpOverlapped], rbx; lpOverlapped
0x1800cbeef  xor     r8d, r8d; lpvInBuffer
0x1800cbef2  mov     [rsp+58h+lpcbBytesReturned], rax; lpcbBytesReturned
0x1800cbef7  mov     edx, 28000017h; dwIoControlCode
0x1800cbefc  mov     [rsp+58h+cbOutBuffer], 0; cbOutBuffer
0x1800cbf04  mov     [rsp+58h+lpvOutBuffer], 0; lpvOutBuffer
0x1800cbf0d  call    cs:__imp_WSAIoctl
0x1800cbf14  nop     dword ptr [rax+rax+00h]
0x1800cbf19  cmp     eax, 0FFFFFFFFh
0x1800cbf1c  jnz     short loc_1800CBF48
0x1800cbf1e  call    cs:__imp_WSAGetLastError
0x1800cbf25  nop     dword ptr [rax+rax+00h]
0x1800cbf2a  cmp     eax, 3E5h
0x1800cbf2f  jz      short loc_1800CBF48
0x1800cbf31  mov     rcx, [rdi+40h]
0x1800cbf35  mov     rcx, [rcx]; pio
0x1800cbf38  call    cs:__imp_CancelThreadpoolIo
0x1800cbf3f  nop     dword ptr [rax+rax+00h]
0x1800cbf44  xor     eax, eax
0x1800cbf46  jmp     short loc_1800CBF4D
0x1800cbf48  mov     eax, 1
0x1800cbf4d  mov     rbx, [rsp+58h+arg_0]
0x1800cbf52  add     rsp, 50h
0x1800cbf56  pop     rdi
0x1800cbf57  retn
```
