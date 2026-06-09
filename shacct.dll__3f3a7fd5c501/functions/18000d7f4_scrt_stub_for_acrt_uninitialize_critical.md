# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x18000d7f4`
- end: `0x18000d7f7`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x18000c404`
- `0x18000c434`
- `0x18000c4d8`
- `0x18000c4f4`
- `0x18000c694`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x18000d7f4  mov     al, 1
0x18000d7f6  retn
```
