# __scrt_initialize_winrt

- ea: `0x140004e30`
- end: `0x140004e33`
- name: `__scrt_initialize_winrt`
- size: `3`
- prototype: `__int64()`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x140001300`
- `0x1400013d0`
- `0x140001a00`

## pseudocode

```c
__int64 _scrt_initialize_winrt()
{
  return 0;
}

```

## disassembly

```asm
0x140004e30  xor     eax, eax
0x140004e32  retn
```
