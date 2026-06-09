# _CollectorService::CollectorService_::_1_::dtor$8

- ea: `0x180020572`
- end: `0x18002057e`
- name: `_CollectorService::CollectorService_::_1_::dtor$8`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, service_task`

## callees

- `0x1800034f0`

## pseudocode

```c
void __fastcall CollectorService::CollectorService_::_1_::dtor_8(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 168));
}

```

## disassembly

```asm
0x180020572  mov     rcx, [rdx+0A8h]; void *
0x180020579  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
