# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x180015890`
- end: `0x180015893`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: `char()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x18000fd4c`
- `0x18000fd7c`
- `0x18000fe38`
- `0x18000fe54`
- `0x18000fff4`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x180015890  mov     al, 1
0x180015892  retn
```
