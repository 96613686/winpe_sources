# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x18000276c`
- end: `0x18000276f`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180001f78`
- `0x180001fa8`
- `0x18000204c`
- `0x180002068`
- `0x180002208`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x18000276c  mov     al, 1
0x18000276e  retn
```
