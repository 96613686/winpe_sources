# __scrt_stub_for_acrt_uninitialize

- ea: `0x14000182c`
- end: `0x14000182f`
- name: `__scrt_stub_for_acrt_uninitialize`
- size: `3`
- prototype: `char()`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1400011f0`
- `0x140001520`
- `0x1400016c0`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize()
{
  return 1;
}

```

## disassembly

```asm
0x14000182c  mov     al, 1
0x14000182e  retn
```
