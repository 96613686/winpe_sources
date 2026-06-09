# __scrt_dllmain_crt_thread_detach

- ea: `0x180008bcc`
- end: `0x180008be1`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180008710`

## callees

- `0x180009718`

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
0x180008bcc  sub     rsp, 28h
0x180008bd0  call    __scrt_stub_for_acrt_uninitialize_critical
0x180008bd5  call    __scrt_stub_for_acrt_uninitialize_critical
0x180008bda  mov     al, 1
0x180008bdc  add     rsp, 28h
0x180008be0  retn
```
