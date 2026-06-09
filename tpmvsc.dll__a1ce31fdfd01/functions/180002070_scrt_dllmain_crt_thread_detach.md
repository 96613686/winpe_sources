# __scrt_dllmain_crt_thread_detach

- ea: `0x180002070`
- end: `0x180002085`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: `char()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001b40`

## callees

- `0x180002c08`

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
0x180002070  sub     rsp, 28h
0x180002074  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002079  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000207e  mov     al, 1
0x180002080  add     rsp, 28h
0x180002084  retn
```
