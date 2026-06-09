# __scrt_stub_for_acrt_uninitialize

- ea: `0x140005318`
- end: `0x14000531b`
- name: `__scrt_stub_for_acrt_uninitialize`
- size: `3`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x140004ce0`
- `0x140004ff4`
- `0x140005194`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize()
{
  return 1;
}

```

## disassembly

```asm
0x140005318  mov     al, 1
0x14000531a  retn
```
