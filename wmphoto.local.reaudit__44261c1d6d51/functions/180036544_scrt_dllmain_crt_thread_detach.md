# __scrt_dllmain_crt_thread_detach

- ea: `0x180036544`
- end: `0x180036559`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800360b0`

## callees

- `0x1800373fc`

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
0x180036544  sub     rsp, 28h
0x180036548  call    __scrt_stub_for_acrt_uninitialize_critical
0x18003654d  call    __scrt_stub_for_acrt_uninitialize_critical
0x180036552  mov     al, 1
0x180036554  add     rsp, 28h
0x180036558  retn
```
