# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x1800075bc`
- end: `0x1800075bf`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x1800067d8`
- `0x180006808`
- `0x1800068ac`
- `0x1800068c8`
- `0x180006a68`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x1800075bc  mov     al, 1
0x1800075be  retn
```
