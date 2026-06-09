# __scrt_dllmain_crt_thread_detach

- ea: `0x180001628`
- end: `0x18000163d`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800011a0`

## callees

- `0x18000210c`

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
0x180001628  sub     rsp, 28h
0x18000162c  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001631  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001636  mov     al, 1
0x180001638  add     rsp, 28h
0x18000163c  retn
```
