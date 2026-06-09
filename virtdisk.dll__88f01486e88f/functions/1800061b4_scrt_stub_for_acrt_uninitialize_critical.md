# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x1800061b4`
- end: `0x1800061b7`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: `char()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180005914`
- `0x180005944`
- `0x1800059e8`
- `0x180005a04`
- `0x180005ba4`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x1800061b4  mov     al, 1
0x1800061b6  retn
```
