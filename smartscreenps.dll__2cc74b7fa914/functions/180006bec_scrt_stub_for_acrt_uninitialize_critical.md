# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x180006bec`
- end: `0x180006bef`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180001640`
- `0x180001670`
- `0x180001714`
- `0x180001730`
- `0x1800018d0`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x180006bec  mov     al, 1
0x180006bee  retn
```
