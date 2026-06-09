# __scrt_stub_for_acrt_uninitialize

- ea: `0x1400025b4`
- end: `0x1400025b7`
- name: `__scrt_stub_for_acrt_uninitialize`
- size: `3`
- prototype: `char()`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x140001e80`
- `0x140002184`
- `0x140002324`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize()
{
  return 1;
}

```

## disassembly

```asm
0x1400025b4  mov     al, 1
0x1400025b6  retn
```
