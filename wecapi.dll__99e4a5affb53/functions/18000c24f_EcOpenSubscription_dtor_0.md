# EcOpenSubscription$dtor$0

- ea: `0x18000c24f`
- end: `0x18000c25b`
- name: `EcOpenSubscription$dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x1800026c0`

## pseudocode

```c
void __fastcall EcOpenSubscription_dtor_0(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 328));
}

```

## disassembly

```asm
0x18000c24f  mov     rcx, [rdx+148h]; void *
0x18000c256  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
