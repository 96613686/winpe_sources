# __scrt_dllmain_crt_thread_detach

- ea: `0x180005400`
- end: `0x180005415`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180004fb0`

## callees

- `0x180006494`

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
0x180005400  sub     rsp, 28h
0x180005404  call    __scrt_stub_for_acrt_uninitialize_critical
0x180005409  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000540e  mov     al, 1
0x180005410  add     rsp, 28h
0x180005414  retn
```
