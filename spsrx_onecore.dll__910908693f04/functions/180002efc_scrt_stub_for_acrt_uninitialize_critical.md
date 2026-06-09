# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x180002efc`
- end: `0x180002eff`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x18000267c`
- `0x1800026ac`
- `0x180002750`
- `0x18000276c`
- `0x18000290c`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x180002efc  mov     al, 1
0x180002efe  retn
```
