# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x18000325c`
- end: `0x18000325f`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180002b38`
- `0x180002b68`
- `0x180002c0c`
- `0x180002c28`
- `0x180002dc8`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x18000325c  mov     al, 1
0x18000325e  retn
```
