# ___scrt_stub_for_acrt_initialize

- ea: `0x1000470d`
- end: `0x10004710`
- name: `___scrt_stub_for_acrt_initialize`
- size: `3`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x10003e38`
- `0x10003e5d`
- `0x10003ed5`
- `0x10003ee8`
- `0x1000407a`

## pseudocode

```c
char __scrt_stub_for_acrt_initialize()
{
  return 1;
}

```

## disassembly

```asm
0x1000470d  mov     al, 1
0x1000470f  retn
```
