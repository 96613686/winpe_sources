# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x18000b030`
- end: `0x18000b033`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: `char()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180009880`
- `0x1800098b0`
- `0x180009954`
- `0x180009970`
- `0x180009b10`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x18000b030  mov     al, 1
0x18000b032  retn
```
