# __scrt_stub_for_acrt_uninitialize

- ea: `0x1400025c4`
- end: `0x1400025c7`
- name: `__scrt_stub_for_acrt_uninitialize`
- size: `3`
- prototype: `char()`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x140001e80`
- `0x140002194`
- `0x140002334`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize()
{
  return 1;
}

```

## disassembly

```asm
0x1400025c4  mov     al, 1
0x1400025c6  retn
```
