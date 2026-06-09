# __scrt_dllmain_crt_thread_detach

- ea: `0x1800016e4`
- end: `0x1800016f9`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: `char()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001170`

## callees

- `0x180002978`

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
0x1800016e4  sub     rsp, 28h
0x1800016e8  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800016ed  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800016f2  mov     al, 1
0x1800016f4  add     rsp, 28h
0x1800016f8  retn
```
