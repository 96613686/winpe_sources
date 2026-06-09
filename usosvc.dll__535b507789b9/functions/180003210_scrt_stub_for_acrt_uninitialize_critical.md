# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x180003210`
- end: `0x180003213`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: `char()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180002780`
- `0x1800027b0`
- `0x180002854`
- `0x180002870`
- `0x180002a10`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x180003210  mov     al, 1
0x180003212  retn
```
