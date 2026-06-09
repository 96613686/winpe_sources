# HTTP2TransportChannel::AsyncCompleteHelper(long)

- ea: `0x180005410`
- end: `0x180005420`
- name: `?AsyncCompleteHelper@HTTP2TransportChannel@@MEAAJJ@Z`
- size: `16`
- prototype: `__int64 __fastcall(HTTP2TransportChannel *__hidden this, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180025010`

## pseudocode

```c
__int64 __fastcall HTTP2TransportChannel::AsyncCompleteHelper(HTTP2TransportChannel *this)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 80LL))(*((_QWORD *)this + 3));
}

```

## disassembly

```asm
0x180005410  mov     rcx, [rcx+18h]
0x180005414  mov     rax, [rcx]
0x180005417  mov     rax, [rax+50h]
0x18000541b  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
