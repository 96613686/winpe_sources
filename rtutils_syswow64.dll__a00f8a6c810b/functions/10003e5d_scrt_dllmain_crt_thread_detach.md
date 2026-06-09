# ___scrt_dllmain_crt_thread_detach

- ea: `0x10003e5d`
- end: `0x10003e6a`
- name: `___scrt_dllmain_crt_thread_detach`
- size: `13`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x10003880`

## callees

- `0x1000470d`

## pseudocode

```c
char __scrt_dllmain_crt_thread_detach()
{
  __scrt_stub_for_acrt_initialize();
  __scrt_stub_for_acrt_initialize();
  return 1;
}

```

## disassembly

```asm
0x10003e5d  call    ___scrt_stub_for_acrt_initialize
0x10003e62  call    ___scrt_stub_for_acrt_initialize
0x10003e67  mov     al, 1
0x10003e69  retn
```
