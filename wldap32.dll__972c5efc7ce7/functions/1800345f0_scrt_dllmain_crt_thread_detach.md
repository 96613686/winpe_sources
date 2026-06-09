# __scrt_dllmain_crt_thread_detach

- ea: `0x1800345f0`
- end: `0x180034605`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800341a0`

## callees

- `0x180035664`

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
0x1800345f0  sub     rsp, 28h
0x1800345f4  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800345f9  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800345fe  mov     al, 1
0x180034600  add     rsp, 28h
0x180034604  retn
```
