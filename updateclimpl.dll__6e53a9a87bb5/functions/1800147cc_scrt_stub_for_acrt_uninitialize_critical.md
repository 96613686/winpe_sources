# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x1800147cc`
- end: `0x1800147cf`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: `char()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x1800103d8`
- `0x180010408`
- `0x1800104c4`
- `0x1800104e0`
- `0x180010680`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x1800147cc  mov     al, 1
0x1800147ce  retn
```
