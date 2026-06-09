# HTTP2TransportChannel::Send(HTTP2SendContext *)

- ea: `0x180017d90`
- end: `0x180017da0`
- name: `?Send@HTTP2TransportChannel@@UEAAJPEAVHTTP2SendContext@@@Z`
- size: `16`
- prototype: `__int64 __fastcall(HTTP2TransportChannel *__hidden this, struct HTTP2SendContext *)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x1800173b4`
- `0x180017630`
- `0x1800177d0`
- `0x1800179f0`
- `0x180018f08`
- `0x180019020`
- `0x18001ac8c`

## callees

- `0x180025010`

## pseudocode

```c
__int64 __fastcall HTTP2TransportChannel::Send(HTTP2TransportChannel *this, struct HTTP2SendContext *a2)
{
  return (*(__int64 (__fastcall **)(_QWORD, struct HTTP2SendContext *))(**((_QWORD **)this + 1) + 8LL))(
           *((_QWORD *)this + 1),
           a2);
}

```

## disassembly

```asm
0x180017d90  mov     rcx, [rcx+8]
0x180017d94  mov     rax, [rcx]
0x180017d97  mov     rax, [rax+8]
0x180017d9b  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
