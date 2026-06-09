# __scrt_dllmain_crt_thread_detach

- ea: `0x180001fa8`
- end: `0x180001fbd`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001a50`

## callees

- `0x18000276c`

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
0x180001fa8  sub     rsp, 28h
0x180001fac  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001fb1  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001fb6  mov     al, 1
0x180001fb8  add     rsp, 28h
0x180001fbc  retn
```
