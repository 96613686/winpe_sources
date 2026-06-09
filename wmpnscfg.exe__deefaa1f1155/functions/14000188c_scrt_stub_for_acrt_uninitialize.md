# __scrt_stub_for_acrt_uninitialize

- ea: `0x14000188c`
- end: `0x14000188f`
- name: `__scrt_stub_for_acrt_uninitialize`
- size: `3`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x140001250`
- `0x140001554`
- `0x1400016f4`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize()
{
  return 1;
}

```

## disassembly

```asm
0x14000188c  mov     al, 1
0x14000188e  retn
```
