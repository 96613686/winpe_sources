# __scrt_stub_for_acrt_uninitialize

- ea: `0x140001cdc`
- end: `0x140001cdf`
- name: `__scrt_stub_for_acrt_uninitialize`
- size: `3`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x140001530`
- `0x1400019b4`
- `0x140001b54`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize()
{
  return 1;
}

```

## disassembly

```asm
0x140001cdc  mov     al, 1
0x140001cde  retn
```
