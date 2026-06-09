# __scrt_dllmain_crt_thread_detach

- ea: `0x18000b630`
- end: `0x18000b645`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000b1e0`

## callees

- `0x18000c8d8`

## pseudocode

```c
char _scrt_dllmain_crt_thread_detach()
{
  _scrt_stub_for_acrt_uninitialize_critical();
  _scrt_stub_for_acrt_uninitialize_critical();
  return 1;
}

```

## disassembly

```asm
0x18000b630  sub     rsp, 28h
0x18000b634  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000b639  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000b63e  mov     al, 1
0x18000b640  add     rsp, 28h
0x18000b644  retn
```
