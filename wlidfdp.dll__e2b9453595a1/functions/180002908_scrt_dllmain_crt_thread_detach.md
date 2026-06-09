# __scrt_dllmain_crt_thread_detach

- ea: `0x180002908`
- end: `0x18000291d`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: `char()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180002470`

## callees

- `0x1800036a0`

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
0x180002908  sub     rsp, 28h
0x18000290c  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002911  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002916  mov     al, 1
0x180002918  add     rsp, 28h
0x18000291c  retn
```
