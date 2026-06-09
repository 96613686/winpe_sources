# __scrt_dllmain_crt_thread_detach

- ea: `0x180001888`
- end: `0x18000189d`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800013f0`

## callees

- `0x18000229c`

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
0x180001888  sub     rsp, 28h
0x18000188c  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001891  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001896  mov     al, 1
0x180001898  add     rsp, 28h
0x18000189c  retn
```
