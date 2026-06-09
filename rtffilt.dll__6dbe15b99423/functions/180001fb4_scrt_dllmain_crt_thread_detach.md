# __scrt_dllmain_crt_thread_detach

- ea: `0x180001fb4`
- end: `0x180001fc9`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001ac0`

## callees

- `0x180002b30`

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
0x180001fb4  sub     rsp, 28h
0x180001fb8  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001fbd  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001fc2  mov     al, 1
0x180001fc4  add     rsp, 28h
0x180001fc8  retn
```
