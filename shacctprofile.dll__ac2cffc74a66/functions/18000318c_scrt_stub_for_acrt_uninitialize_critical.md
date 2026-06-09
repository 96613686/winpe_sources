# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x18000318c`
- end: `0x18000318f`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: `char()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x1800022e0`
- `0x180002310`
- `0x1800023b4`
- `0x1800023d0`
- `0x180002570`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x18000318c  mov     al, 1
0x18000318e  retn
```
