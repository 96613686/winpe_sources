# TransportProtocol::DoesAddressSocketHaveAddress(int)

- ea: `0x1800c6dd8`
- end: `0x1800c6ea9`
- name: `?DoesAddressSocketHaveAddress@TransportProtocol@@AEAAHH@Z`
- size: `209`
- prototype: `__int64 __fastcall(TransportProtocol *__hidden this, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800c74d8`

## callees

- `0x1800c6dd8`
- `0x1800ca140`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x1800c6e0e`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x1800c6e0e`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x1800c6e70`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x1800c6e70`
- `WS2_32!WSAIoctl` at `0x1800c6e51`
- `WS2_32!WSAIoctl` at `0x1800c6e51`
- `WS2_32!__imp_WSAGetLastError` at `0x1800c6e5c`
- `WS2_32!__imp_WSAGetLastError` at `0x1800c6e5c`

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
0x1800c6dd8  push    rbx
0x1800c6dda  sub     rsp, 90h
0x1800c6de1  mov     rax, cs:__security_cookie
0x1800c6de8  xor     rax, rsp
0x1800c6deb  mov     [rsp+98h+var_18], rax
0x1800c6df3  mov     [rsp+98h+cbBytesReturned], 0
0x1800c6dfb  mov     rbx, rcx
0x1800c6dfe  cmp     edx, 0Fh
0x1800c6e01  jz      loc_1800C6E8B
0x1800c6e07  mov     rcx, [rcx+40h]
0x1800c6e0b  mov     rcx, [rcx]; pio
0x1800c6e0e  call    cs:__imp_StartThreadpoolIo
0x1800c6e14  mov     rcx, [rbx+18h]; s
0x1800c6e18  lea     rax, [rsp+98h+cbBytesReturned]
0x1800c6e1d  mov     [rsp+98h+lpCompletionRoutine], 0; lpCompletionRoutine
0x1800c6e26  xor     r9d, r9d; cbInBuffer
0x1800c6e29  mov     [rsp+98h+lpOverlapped], 0; lpOverlapped
0x1800c6e32  xor     r8d, r8d; lpvInBuffer
0x1800c6e35  mov     [rsp+98h+lpcbBytesReturned], rax; lpcbBytesReturned
0x1800c6e3a  mov     edx, 48000016h; dwIoControlCode
0x1800c6e3f  lea     rax, [rsp+98h+vOutBuffer]
0x1800c6e44  mov     [rsp+98h+cbOutBuffer], 28h ; '('; cbOutBuffer
0x1800c6e4c  mov     [rsp+98h+lpvOutBuffer], rax; lpvOutBuffer
0x1800c6e51  call    cs:__imp_WSAIoctl
0x1800c6e57  cmp     eax, 0FFFFFFFFh
0x1800c6e5a  jnz     short loc_1800C6E7A
0x1800c6e5c  call    cs:__imp_WSAGetLastError
0x1800c6e62  cmp     eax, 3E5h
0x1800c6e67  jz      short loc_1800C6E7A
0x1800c6e69  mov     rcx, [rbx+40h]
0x1800c6e6d  mov     rcx, [rcx]; pio
0x1800c6e70  call    cs:__imp_CancelThreadpoolIo
0x1800c6e76  xor     eax, eax
0x1800c6e78  jmp     short loc_1800C6E90
0x1800c6e7a  xor     eax, eax
0x1800c6e7c  cmp     [rsp+98h+cbBytesReturned], eax
0x1800c6e80  jz      short loc_1800C6E90
0x1800c6e82  cmp     [rsp+98h+vOutBuffer], eax
0x1800c6e86  setnz   al
0x1800c6e89  jmp     short loc_1800C6E90
0x1800c6e8b  mov     eax, 1
0x1800c6e90  mov     rcx, [rsp+98h+var_18]
0x1800c6e98  xor     rcx, rsp; StackCookie
0x1800c6e9b  call    __security_check_cookie
0x1800c6ea0  add     rsp, 90h
0x1800c6ea7  pop     rbx
0x1800c6ea8  retn
```
