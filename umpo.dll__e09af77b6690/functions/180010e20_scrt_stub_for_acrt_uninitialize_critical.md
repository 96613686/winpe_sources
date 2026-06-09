# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x180010e20`
- end: `0x180010e23`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: `char()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180010280`
- `0x1800102b0`
- `0x180010354`
- `0x180010370`
- `0x180010510`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x180010e20  mov     al, 1
0x180010e22  retn
```
