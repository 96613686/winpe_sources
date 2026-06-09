# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x180002b30`
- end: `0x180002b33`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180001f84`
- `0x180001fb4`
- `0x180002058`
- `0x180002074`
- `0x180002214`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x180002b30  mov     al, 1
0x180002b32  retn
```
