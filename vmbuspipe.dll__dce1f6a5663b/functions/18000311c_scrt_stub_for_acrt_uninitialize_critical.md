# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x18000311c`
- end: `0x18000311f`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x1800025c0`
- `0x1800025f0`
- `0x180002694`
- `0x1800026b0`
- `0x180002850`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x18000311c  mov     al, 1
0x18000311e  retn
```
