# DllInitialize

- ea: `0x14000ceb0`
- end: `0x14000ceb3`
- name: `DllInitialize`
- size: `3`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## pseudocode

```c
__int64 DllInitialize()
{
  return 0;
}

```

## disassembly

```asm
0x14000ceb0  xor     eax, eax; DllInitialize
0x14000ceb2  retn
```
