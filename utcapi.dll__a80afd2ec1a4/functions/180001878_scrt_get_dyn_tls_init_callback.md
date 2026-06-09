# __scrt_get_dyn_tls_init_callback

- ea: `0x180001878`
- end: `0x180001880`
- name: `__scrt_get_dyn_tls_init_callback`
- size: `8`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1800010e8`

## pseudocode

```c
__int64 *_scrt_get_dyn_tls_init_callback()
{
  return &_dyn_tls_init_callback;
}

```

## disassembly

```asm
0x180001878  lea     rax, __dyn_tls_init_callback
0x18000187f  retn
```
