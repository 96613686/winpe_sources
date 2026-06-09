# EcOpenSubscriptionEnum$dtor$2

- ea: `0x18000c2db`
- end: `0x18000c2e7`
- name: `EcOpenSubscriptionEnum$dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x1800026c0`

## pseudocode

```c
void __fastcall EcOpenSubscriptionEnum_dtor_2(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 296));
}

```

## disassembly

```asm
0x18000c2db  mov     rcx, [rdx+128h]; void *
0x18000c2e2  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
