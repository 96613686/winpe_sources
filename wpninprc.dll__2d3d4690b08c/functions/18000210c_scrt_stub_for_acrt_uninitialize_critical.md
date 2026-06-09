# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x18000210c`
- end: `0x18000210f`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x1800015f8`
- `0x180001628`
- `0x1800016cc`
- `0x1800016e8`
- `0x180001888`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x18000210c  mov     al, 1
0x18000210e  retn
```
