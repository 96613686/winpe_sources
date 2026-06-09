# __scrt_dllmain_crt_thread_detach

- ea: `0x180004e68`
- end: `0x180004e7d`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180004910`

## callees

- `0x1800055e8`

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
0x180004e68  sub     rsp, 28h
0x180004e6c  call    __scrt_stub_for_acrt_uninitialize_critical
0x180004e71  call    __scrt_stub_for_acrt_uninitialize_critical
0x180004e76  mov     al, 1
0x180004e78  add     rsp, 28h
0x180004e7c  retn
```
