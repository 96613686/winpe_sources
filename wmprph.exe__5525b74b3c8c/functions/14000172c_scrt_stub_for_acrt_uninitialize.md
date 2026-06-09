# __scrt_stub_for_acrt_uninitialize

- ea: `0x14000172c`
- end: `0x14000172f`
- name: `__scrt_stub_for_acrt_uninitialize`
- size: `3`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1400010f0`
- `0x140001420`
- `0x1400015c0`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize()
{
  return 1;
}

```

## disassembly

```asm
0x14000172c  mov     al, 1
0x14000172e  retn
```
