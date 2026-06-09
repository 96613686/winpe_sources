# HTTP2ProxyPlugChannel::AsyncCompleteHelper(long)

- ea: `0x1800053a0`
- end: `0x1800053a9`
- name: `?AsyncCompleteHelper@HTTP2ProxyPlugChannel@@MEAAJJ@Z`
- size: `9`
- prototype: `__int64 __fastcall(HTTP2ProxyPlugChannel *__hidden this, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180011108`

## pseudocode

```c
__int64 __fastcall HTTP2ProxyPlugChannel::AsyncCompleteHelper(struct HTTP2Channel **this, unsigned int a2)
{
  return ProxyAsyncCompleteHelper(this[3], a2);
}

```

## disassembly

```asm
0x1800053a0  mov     rcx, [rcx+18h]; this
0x1800053a4  jmp     ?ProxyAsyncCompleteHelper@@YAJPEAVHTTP2Channel@@J@Z; ProxyAsyncCompleteHelper(HTTP2Channel *,long)
```
