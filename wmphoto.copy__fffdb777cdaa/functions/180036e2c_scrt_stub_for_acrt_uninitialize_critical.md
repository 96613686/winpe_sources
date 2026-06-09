# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x180036e2c`
- end: `0x180036e2f`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180035f44`
- `0x180035f74`
- `0x180036018`
- `0x180036034`
- `0x1800361d4`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x180036e2c  mov     al, 1
0x180036e2e  retn
```
