# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x180001e7c`
- end: `0x180001e7f`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: `char()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180001634`
- `0x180001664`
- `0x180001708`
- `0x180001724`
- `0x1800018c4`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x180001e7c  mov     al, 1
0x180001e7e  retn
```
