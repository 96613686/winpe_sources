# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x1800158e0`
- end: `0x1800158e3`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x18000fd9c`
- `0x18000fdcc`
- `0x18000fe88`
- `0x18000fea4`
- `0x180010044`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x1800158e0  mov     al, 1
0x1800158e2  retn
```
