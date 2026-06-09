# TransportProtocol::DoesAddressSocketHaveAddress(int)

- ea: `0x1800cb8ac`
- end: `0x1800cb996`
- name: `?DoesAddressSocketHaveAddress@TransportProtocol@@AEAAHH@Z`
- size: `234`
- prototype: `__int64 __fastcall(TransportProtocol *__hidden this, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800cc00c`

## callees

- `0x1800cb8ac`
- `0x1800ceda0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x1800cb8e2`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x1800cb8e2`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x1800cb956`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x1800cb956`
- `WS2_32!WSAIoctl` at `0x1800cb92b`
- `WS2_32!WSAIoctl` at `0x1800cb92b`
- `WS2_32!__imp_WSAGetLastError` at `0x1800cb93c`
- `WS2_32!__imp_WSAGetLastError` at `0x1800cb93c`

## pseudocode

```c
bool __fastcall TransportProtocol::DoesAddressSocketHaveAddress(TransportProtocol *this, int a2)
{
  bool result; // al
  DWORD cbBytesReturned; // [rsp+50h] [rbp-48h] BYREF
  _DWORD vOutBuffer[10]; // [rsp+58h] [rbp-40h] BYREF

  cbBytesReturned = 0;
  if ( a2 == 15 )
    return 1;
  StartThreadpoolIo(**((PTP_IO **)this + 8));
  if ( WSAIoctl(*((_QWORD *)this + 3), 0x48000016u, 0, 0, vOutBuffer, 0x28u, &cbBytesReturned, 0, 0) != -1
    || WSAGetLastError() == 997 )
  {
    result = 0;
    if ( cbBytesReturned )
      return vOutBuffer[0] != 0;
  }
  else
  {
    CancelThreadpoolIo(**((PTP_IO **)this + 8));
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800cb8ac  push    rbx
0x1800cb8ae  sub     rsp, 90h
0x1800cb8b5  mov     rax, cs:__security_cookie
0x1800cb8bc  xor     rax, rsp
0x1800cb8bf  mov     [rsp+98h+var_18], rax
0x1800cb8c7  mov     [rsp+98h+cbBytesReturned], 0
0x1800cb8cf  mov     rbx, rcx
0x1800cb8d2  cmp     edx, 0Fh
0x1800cb8d5  jz      loc_1800CB977
0x1800cb8db  mov     rcx, [rcx+40h]
0x1800cb8df  mov     rcx, [rcx]; pio
0x1800cb8e2  call    cs:__imp_StartThreadpoolIo
0x1800cb8e9  nop     dword ptr [rax+rax+00h]
0x1800cb8ee  mov     rcx, [rbx+18h]; s
0x1800cb8f2  lea     rax, [rsp+98h+cbBytesReturned]
0x1800cb8f7  mov     [rsp+98h+lpCompletionRoutine], 0; lpCompletionRoutine
0x1800cb900  xor     r9d, r9d; cbInBuffer
0x1800cb903  mov     [rsp+98h+lpOverlapped], 0; lpOverlapped
0x1800cb90c  xor     r8d, r8d; lpvInBuffer
0x1800cb90f  mov     [rsp+98h+lpcbBytesReturned], rax; lpcbBytesReturned
0x1800cb914  mov     edx, 48000016h; dwIoControlCode
0x1800cb919  lea     rax, [rsp+98h+vOutBuffer]
0x1800cb91e  mov     [rsp+98h+cbOutBuffer], 28h ; '('; cbOutBuffer
0x1800cb926  mov     [rsp+98h+lpvOutBuffer], rax; lpvOutBuffer
0x1800cb92b  call    cs:__imp_WSAIoctl
0x1800cb932  nop     dword ptr [rax+rax+00h]
0x1800cb937  cmp     eax, 0FFFFFFFFh
0x1800cb93a  jnz     short loc_1800CB966
0x1800cb93c  call    cs:__imp_WSAGetLastError
0x1800cb943  nop     dword ptr [rax+rax+00h]
0x1800cb948  cmp     eax, 3E5h
0x1800cb94d  jz      short loc_1800CB966
0x1800cb94f  mov     rcx, [rbx+40h]
0x1800cb953  mov     rcx, [rcx]; pio
0x1800cb956  call    cs:__imp_CancelThreadpoolIo
0x1800cb95d  nop     dword ptr [rax+rax+00h]
0x1800cb962  xor     eax, eax
0x1800cb964  jmp     short loc_1800CB97C
0x1800cb966  xor     eax, eax
0x1800cb968  cmp     [rsp+98h+cbBytesReturned], eax
0x1800cb96c  jz      short loc_1800CB97C
0x1800cb96e  cmp     [rsp+98h+vOutBuffer], eax
0x1800cb972  setnz   al
0x1800cb975  jmp     short loc_1800CB97C
0x1800cb977  mov     eax, 1
0x1800cb97c  mov     rcx, [rsp+98h+var_18]
0x1800cb984  xor     rcx, rsp; StackCookie
0x1800cb987  call    __security_check_cookie
0x1800cb98c  add     rsp, 90h
0x1800cb993  pop     rbx
0x1800cb994  retn
```
