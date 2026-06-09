# __scrt_dllmain_crt_thread_detach

- ea: `0x180002b68`
- end: `0x180002b7d`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180002610`

## callees

- `0x18000325c`

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
0x180002b68  sub     rsp, 28h
0x180002b6c  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002b71  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002b76  mov     al, 1
0x180002b78  add     rsp, 28h
0x180002b7c  retn
```
