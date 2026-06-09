# __scrt_get_dyn_tls_init_callback

- ea: `0x180002df8`
- end: `0x180002e00`
- name: `__scrt_get_dyn_tls_init_callback`
- size: `8`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180002668`

## pseudocode

```c
__int64 *_scrt_get_dyn_tls_init_callback()
{
  return _dyn_tls_init_callback;
}

```

## disassembly

```asm
0x180002df8  lea     rax, __dyn_tls_init_callback
0x180002dff  retn
```
