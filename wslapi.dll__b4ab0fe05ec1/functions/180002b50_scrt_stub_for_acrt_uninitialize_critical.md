# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x180002b50`
- end: `0x180002b53`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: `char()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180001e70`
- `0x180001ea0`
- `0x180001f44`
- `0x180001f60`
- `0x180002100`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x180002b50  mov     al, 1
0x180002b52  retn
```
