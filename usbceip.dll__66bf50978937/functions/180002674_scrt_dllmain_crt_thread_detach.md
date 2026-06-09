# __scrt_dllmain_crt_thread_detach

- ea: `0x180002674`
- end: `0x180002689`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: `char()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180002090`

## callees

- `0x180002fd4`

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
0x180002674  sub     rsp, 28h
0x180002678  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000267d  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002682  mov     al, 1
0x180002684  add     rsp, 28h
0x180002688  retn
```
