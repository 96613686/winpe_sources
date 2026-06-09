# __scrt_dllmain_crt_thread_detach

- ea: `0x180006808`
- end: `0x18000681d`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800062b0`

## callees

- `0x1800075bc`

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
0x180006808  sub     rsp, 28h
0x18000680c  call    __scrt_stub_for_acrt_uninitialize_critical
0x180006811  call    __scrt_stub_for_acrt_uninitialize_critical
0x180006816  mov     al, 1
0x180006818  add     rsp, 28h
0x18000681c  retn
```
