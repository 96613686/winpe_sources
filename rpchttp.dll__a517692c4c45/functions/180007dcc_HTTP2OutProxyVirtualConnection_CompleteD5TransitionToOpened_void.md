# HTTP2OutProxyVirtualConnection::CompleteD5TransitionToOpened(void)

- ea: `0x180007dcc`
- end: `0x180007e6c`
- name: `?CompleteD5TransitionToOpened@HTTP2OutProxyVirtualConnection@@AEAAJXZ`
- size: `160`
- prototype: `__int64 __fastcall(HTTP2OutProxyVirtualConnection *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180014850`

## callees

- `0x180007dcc`
- `0x18000ad30`
- `0x18000f334`
- `0x180018eb0`
- `0x180019330`
- `0x18001ac1c`
- `0x18001ac8c`

## pseudocode

```c
__int64 __fastcall HTTP2OutProxyVirtualConnection::CompleteD5TransitionToOpened(HTTP2OutProxyVirtualConnection *this)
{
  struct HTTP2Channel *v2; // rsi
  __int64 v4; // rdx
  unsigned int v5; // edi
  unsigned int ConnectionTimeout; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  HTTP2ChannelPointer *v9; // [rsp+30h] [rbp+8h] BYREF

  v9 = 0;
  v2 = HTTP2VirtualConnection::LockDefaultChannel(
         this,
         (volatile int *)this + 68,
         (HTTP2OutProxyVirtualConnection *)((char *)this + 200),
         &v9);
  if ( !v2 )
    return 3221360658LL;
  v5 = HTTP2OutProxyVirtualConnection::SendHeaderToClient(this);
  if ( v5 || (v5 = HTTP2PlugChannel::Unplug((struct HTTP2Channel *)((char *)v2 + 96))) != 0 )
  {
    HTTP2ChannelPointer::UnlockChannelPointer(v9, v4);
    return v5;
  }
  else
  {
    ConnectionTimeout = HTTP2ProxyVirtualConnection::GetConnectionTimeout(this);
    v7 = HTTP2PingOriginator::SetConnectionTimeout((struct HTTP2Channel *)((char *)v2 + 328), ConnectionTimeout);
    HTTP2ChannelPointer::UnlockChannelPointer(v9, v8);
    return v7;
  }
}

```

## disassembly

```asm
0x180007dcc  mov     rax, rsp
0x180007dcf  mov     [rax+10h], rbx
0x180007dd3  mov     [rax+18h], rsi
0x180007dd7  push    rdi
0x180007dd8  sub     rsp, 20h
0x180007ddc  lea     r8, [rcx+0C8h]; struct HTTP2ChannelPointer *
0x180007de3  mov     qword ptr [rax+8], 0
0x180007deb  lea     rdx, [rcx+110h]; volatile int *
0x180007df2  mov     rbx, rcx
0x180007df5  lea     r9, [rax+8]; struct HTTP2ChannelPointer **
0x180007df9  call    ?LockDefaultChannel@HTTP2VirtualConnection@@AEAAPEAVHTTP2Channel@@PECHQEAVHTTP2ChannelPointer@@PEAPEAV3@@Z; HTTP2VirtualConnection::LockDefaultChannel(int volatile *,HTTP2ChannelPointer * const,HTTP2ChannelPointer * *)
0x180007dfe  mov     rsi, rax
0x180007e01  test    rax, rax
0x180007e04  jnz     short loc_180007E0D
0x180007e06  mov     eax, 0C0021012h
0x180007e0b  jmp     short loc_180007E5C
0x180007e0d  mov     rcx, rbx; this
0x180007e10  call    ?SendHeaderToClient@HTTP2OutProxyVirtualConnection@@AEAAJXZ; HTTP2OutProxyVirtualConnection::SendHeaderToClient(void)
0x180007e15  mov     edi, eax
0x180007e17  test    eax, eax
0x180007e19  jz      short loc_180007E29
0x180007e1b  mov     rcx, [rsp+28h+arg_0]; this
0x180007e20  call    ?UnlockChannelPointer@HTTP2ChannelPointer@@QEAAXXZ; HTTP2ChannelPointer::UnlockChannelPointer(void)
0x180007e25  mov     eax, edi
0x180007e27  jmp     short loc_180007E5C
0x180007e29  lea     rcx, [rsi+60h]; this
0x180007e2d  call    ?Unplug@HTTP2PlugChannel@@QEAAJXZ; HTTP2PlugChannel::Unplug(void)
0x180007e32  mov     edi, eax
0x180007e34  test    eax, eax
0x180007e36  jnz     short loc_180007E1B
0x180007e38  mov     rcx, rbx; this
0x180007e3b  call    ?GetConnectionTimeout@HTTP2ProxyVirtualConnection@@IEAAKXZ; HTTP2ProxyVirtualConnection::GetConnectionTimeout(void)
0x180007e40  mov     edx, eax; unsigned int
0x180007e42  lea     rcx, [rsi+148h]; this
0x180007e49  call    ?SetConnectionTimeout@HTTP2PingOriginator@@QEAAJK@Z; HTTP2PingOriginator::SetConnectionTimeout(ulong)
0x180007e4e  mov     rcx, [rsp+28h+arg_0]; this
0x180007e53  mov     ebx, eax
0x180007e55  call    ?UnlockChannelPointer@HTTP2ChannelPointer@@QEAAXXZ; HTTP2ChannelPointer::UnlockChannelPointer(void)
0x180007e5a  mov     eax, ebx
0x180007e5c  mov     rbx, [rsp+28h+arg_8]
0x180007e61  mov     rsi, [rsp+28h+arg_10]
0x180007e66  add     rsp, 20h
0x180007e6a  pop     rdi
0x180007e6b  retn
```
