# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x1800055e8`
- end: `0x1800055eb`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180004e38`
- `0x180004e68`
- `0x180004f0c`
- `0x180004f28`
- `0x1800050c8`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x1800055e8  mov     al, 1
0x1800055ea  retn
```
