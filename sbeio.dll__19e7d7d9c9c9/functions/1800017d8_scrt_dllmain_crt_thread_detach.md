# __scrt_dllmain_crt_thread_detach

- ea: `0x1800017d8`
- end: `0x1800017ed`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001280`

## callees

- `0x180001f88`

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
0x1800017d8  sub     rsp, 28h
0x1800017dc  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800017e1  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800017e6  mov     al, 1
0x1800017e8  add     rsp, 28h
0x1800017ec  retn
```
