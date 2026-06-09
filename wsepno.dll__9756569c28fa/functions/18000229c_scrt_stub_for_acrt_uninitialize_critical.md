# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x18000229c`
- end: `0x18000229f`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180001858`
- `0x180001888`
- `0x18000192c`
- `0x180001948`
- `0x180001ae8`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x18000229c  mov     al, 1
0x18000229e  retn
```
