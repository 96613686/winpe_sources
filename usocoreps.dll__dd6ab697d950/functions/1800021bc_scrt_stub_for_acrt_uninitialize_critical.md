# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x1800021bc`
- end: `0x1800021bf`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: `char()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x1800015ec`
- `0x18000161c`
- `0x1800016c0`
- `0x1800016dc`
- `0x18000187c`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x1800021bc  mov     al, 1
0x1800021be  retn
```
