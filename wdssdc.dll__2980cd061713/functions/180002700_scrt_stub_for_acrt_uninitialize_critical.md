# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x180002700`
- end: `0x180002703`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x1800019f0`
- `0x180001a20`
- `0x180001adc`
- `0x180001af8`
- `0x180001c98`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x180002700  mov     al, 1
0x180002702  retn
```
