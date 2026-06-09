# __scrt_dllmain_crt_thread_detach

- ea: `0x180001670`
- end: `0x180001685`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001220`

## callees

- `0x1800031f8`
- `0x180006bec`

## pseudocode

```c
char _scrt_dllmain_crt_thread_detach()
{
  _scrt_stub_for_acrt_uninitialize_critical();
  _vcrt_thread_detach();
  return 1;
}

```

## disassembly

```asm
0x180001670  sub     rsp, 28h
0x180001674  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001679  call    __vcrt_thread_detach
0x18000167e  mov     al, 1
0x180001680  add     rsp, 28h
0x180001684  retn
```
