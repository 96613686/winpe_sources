# __scrt_dllmain_crt_thread_detach

- ea: `0x180035f74`
- end: `0x180035f89`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180035ae0`

## callees

- `0x180036e2c`

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
0x180035f74  sub     rsp, 28h
0x180035f78  call    __scrt_stub_for_acrt_uninitialize_critical
0x180035f7d  call    __scrt_stub_for_acrt_uninitialize_critical
0x180035f82  mov     al, 1
0x180035f84  add     rsp, 28h
0x180035f88  retn
```
