# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x180002004`
- end: `0x180002007`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x1800017e8`
- `0x180001818`
- `0x1800018bc`
- `0x1800018d8`
- `0x180001a78`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x180002004  mov     al, 1
0x180002006  retn
```
