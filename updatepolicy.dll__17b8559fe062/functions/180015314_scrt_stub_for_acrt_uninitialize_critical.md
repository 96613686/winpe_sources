# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x180015314`
- end: `0x180015317`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: `char()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x18000ee78`
- `0x18000eea8`
- `0x18000ef64`
- `0x18000ef80`
- `0x18000f120`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x180015314  mov     al, 1
0x180015316  retn
```
