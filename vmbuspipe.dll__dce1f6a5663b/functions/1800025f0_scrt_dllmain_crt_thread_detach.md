# __scrt_dllmain_crt_thread_detach

- ea: `0x1800025f0`
- end: `0x180002605`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180002170`

## callees

- `0x18000311c`

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
0x1800025f0  sub     rsp, 28h
0x1800025f4  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800025f9  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800025fe  mov     al, 1
0x180002600  add     rsp, 28h
0x180002604  retn
```
