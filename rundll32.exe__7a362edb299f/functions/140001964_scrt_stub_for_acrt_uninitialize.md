# __scrt_stub_for_acrt_uninitialize

- ea: `0x140001964`
- end: `0x140001967`
- name: `__scrt_stub_for_acrt_uninitialize`
- size: `3`
- prototype: `char()`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x140001300`
- `0x140001628`
- `0x1400017c8`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize()
{
  return 1;
}

```

## disassembly

```asm
0x140001964  mov     al, 1
0x140001966  retn
```
