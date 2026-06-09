# DllGetClassObject$dtor$4

- ea: `0x180015ad8`
- end: `0x180015ae4`
- name: `DllGetClassObject$dtor$4`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callees

- `0x180008fa0`

## pseudocode

```c
void __fastcall DllGetClassObject_dtor_4(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 64));
}

```

## disassembly

```asm
0x180015ad8  mov     rcx, [rdx+40h]; void *
0x180015adf  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
