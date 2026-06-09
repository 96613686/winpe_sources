# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x1800045e0`
- end: `0x1800045e3`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180003d94`
- `0x180003dc4`
- `0x180003e68`
- `0x180003e84`
- `0x180004024`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x1800045e0  mov     al, 1
0x1800045e2  retn
```
