# __scrt_dllmain_crt_thread_detach

- ea: `0x180001a20`
- end: `0x180001a35`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001220`

## callees

- `0x180002700`

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
0x180001a20  sub     rsp, 28h
0x180001a24  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001a29  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001a2e  mov     al, 1
0x180001a30  add     rsp, 28h
0x180001a34  retn
```
