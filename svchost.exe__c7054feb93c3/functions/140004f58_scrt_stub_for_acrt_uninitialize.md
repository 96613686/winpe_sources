# __scrt_stub_for_acrt_uninitialize

- ea: `0x140004f58`
- end: `0x140004f5b`
- name: `__scrt_stub_for_acrt_uninitialize`
- size: `3`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x140004920`
- `0x140004c34`
- `0x140004dd4`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize()
{
  return 1;
}

```

## disassembly

```asm
0x140004f58  mov     al, 1
0x140004f5a  retn
```
