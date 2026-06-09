# HTTP2ProxySocketTransportChannel::AsyncCompleteHelper(long)

- ea: `0x1800053b0`
- end: `0x180005400`
- name: `?AsyncCompleteHelper@HTTP2ProxySocketTransportChannel@@UEAAJJ@Z`
- size: `80`
- prototype: `int(HTTP2ProxySocketTransportChannel *__hidden this, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180011108`

## import_xrefs

- `RPCRT4!I_RpcLogEvent` at `0x1800053df`
- `RPCRT4!I_RpcLogEvent` at `0x1800053df`

## pseudocode

```c
__int64 __fastcall HTTP2ProxySocketTransportChannel::AsyncCompleteHelper(
        HTTP2ProxySocketTransportChannel *this,
        __int64 a2)
{
  unsigned int v2; // ebx
  HTTP2ProxySocketTransportChannel *v3; // rdi
  HTTP2ProxySocketTransportChannel *v4; // r8
  int v6; // [rsp+20h] [rbp-28h]

  v2 = a2;
  v3 = this;
  v6 = a2;
  v4 = this;
  LOBYTE(a2) = 111;
  LOBYTE(this) = 50;
  I_RpcLogEvent(this, a2, v4, 16973826, v6, 0, 0);
  ProxyAsyncCompleteHelper(*((struct HTTP2Channel **)v3 + 3), v2);
  return 3221360681LL;
}

```

## disassembly

```asm
0x1800053b0  mov     rax, rsp
0x1800053b3  mov     [rax+8], rbx
0x1800053b7  push    rdi
0x1800053b8  sub     rsp, 40h
0x1800053bc  mov     dword ptr [rax-18h], 0
0x1800053c3  mov     ebx, edx
0x1800053c5  mov     dword ptr [rax-20h], 0
0x1800053cc  mov     rdi, rcx
0x1800053cf  mov     [rax-28h], edx
0x1800053d2  mov     r8, rcx
0x1800053d5  mov     dl, 6Fh ; 'o'
0x1800053d7  mov     r9d, 1030002h
0x1800053dd  mov     cl, 32h ; '2'
0x1800053df  call    cs:__imp_I_RpcLogEvent
0x1800053e5  mov     rcx, [rdi+18h]; this
0x1800053e9  mov     edx, ebx; int
0x1800053eb  call    ?ProxyAsyncCompleteHelper@@YAJPEAVHTTP2Channel@@J@Z; ProxyAsyncCompleteHelper(HTTP2Channel *,long)
0x1800053f0  mov     rbx, [rsp+48h+arg_0]
0x1800053f5  mov     eax, 0C0021029h
0x1800053fa  add     rsp, 40h
0x1800053fe  pop     rdi
0x1800053ff  retn
```
