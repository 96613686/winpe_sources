# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x18000c8d8`
- end: `0x18000c8db`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x18000b600`
- `0x18000b630`
- `0x18000b6d4`
- `0x18000b6f0`
- `0x18000b890`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x18000c8d8  mov     al, 1
0x18000c8da  retn
```
