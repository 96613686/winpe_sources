# DllUnload

- ea: `0x140010bb0`
- end: `0x140010bb3`
- name: `DllUnload`
- size: `3`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## pseudocode

```c
__int64 DllUnload()
{
  return 0;
}

```

## disassembly

```asm
0x140010bb0  xor     eax, eax
0x140010bb2  retn
```
