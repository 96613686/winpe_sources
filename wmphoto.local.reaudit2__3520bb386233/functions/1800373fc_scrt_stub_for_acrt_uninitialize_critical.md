# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x1800373fc`
- end: `0x1800373ff`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180036514`
- `0x180036544`
- `0x1800365e8`
- `0x180036604`
- `0x1800367a4`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x1800373fc  mov     al, 1
0x1800373fe  retn
```
