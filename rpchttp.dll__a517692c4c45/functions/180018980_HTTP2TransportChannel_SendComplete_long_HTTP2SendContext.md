# HTTP2TransportChannel::SendComplete(long,HTTP2SendContext *)

- ea: `0x180018980`
- end: `0x180018990`
- name: `?SendComplete@HTTP2TransportChannel@@UEAAJJPEAVHTTP2SendContext@@@Z`
- size: `16`
- prototype: `__int64 __fastcall(HTTP2TransportChannel *__hidden this, int, struct HTTP2SendContext *)`
- caller_count: `11`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003e20`
- `0x180009030`
- `0x1800091ec`
- `0x180009384`
- `0x1800094a0`
- `0x180018250`
- `0x1800184f0`
- `0x180018580`
- `0x180018640`
- `0x1800189a0`
- `0x1800190d0`

## callees

- `0x180025010`

## pseudocode

```c
__int64 __fastcall HTTP2TransportChannel::SendComplete(
        HTTP2TransportChannel *this,
        __int64 a2,
        struct HTTP2SendContext *a3)
{
  return (*(__int64 (__fastcall **)(_QWORD, __int64, struct HTTP2SendContext *))(**((_QWORD **)this + 2) + 24LL))(
           *((_QWORD *)this + 2),
           a2,
           a3);
}

```

## disassembly

```asm
0x180018980  mov     rcx, [rcx+10h]
0x180018984  mov     rax, [rcx]
0x180018987  mov     rax, [rax+18h]
0x18001898b  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
